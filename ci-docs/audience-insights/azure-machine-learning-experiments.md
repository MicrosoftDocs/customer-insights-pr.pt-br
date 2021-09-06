---
title: Experimentos do Azure Machine Learning
description: Use modelos baseados em Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 11/30/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: naravill
ms.author: naravill
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4c04a1d08aba152ce91d452ae2300c1ce0fc79e5d6980ac506dc40d9914c9fca
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033158"
---
# <a name="use-azure-machine-learning-based-models"></a>Usar modelos baseados em Azure Machine Learning

Os dados unificados no Dynamics 365 Customer Insights são uma fonte para a criação de modelos de machine learning que podem gerar insights de negócios adicionais. O Customer Insights integra-se ao Machine Learning Studio (clássico) e Azure Machine Learning para usar seus próprios modelos personalizados. Consulte os [experimentos do Machine Learning Studio (clássico)](machine-learning-studio-experiments.md) para obter exemplos de experimentos baseados no Machine Learning Studio (clássico). 

## <a name="prerequisites"></a>Pré-requisitos

- Acesso ao Customer Insights
- Ativar assinatura do Azure Enterprise
- [Perfis de cliente unificados](data-unification.md)
- [Exportação de entidade para armazenamento de Blobs do Azure](export-azure-blob-storage.md) configurada

## <a name="set-up-azure-machine-learning-workspace"></a>Configurar o espaço de trabalho do Azure Machine Learning

1. Consulte [Criar um espaço de trabalho do Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) e conheça opções diferentes para criar o espaço de trabalho. Para obter o melhor desempenho, crie o espaço de trabalho em uma região do Azure que seja geograficamente mais próxima de seu ambiente do Customer Insights.

1. Acesse seu espaço de trabalho por meio do [Azure Machine Learning Studio](https://ml.azure.com/). Existem várias [maneiras de interagir](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) com seu espaço de trabalho.

## <a name="work-with-azure-machine-learning-designer"></a>Trabalhar com o designer do Azure Machine Learning

O designer do Azure Machine Learning fornece uma tela visual em que você pode arrastar e soltar conjuntos de dados e módulos, de forma semelhante ao Machine Learning Studio (clássico). Um pipeline em lote criado a partir do designer pode ser integrado ao Customer Insights se eles forem configurados apropriadamente. 
   
## <a name="working-with-azure-machine-learning-sdk"></a>Trabalhar com o SDK do Azure Machine Learning

Cientistas de dados e desenvolvedores de IA usam o [SDK do Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) para criar fluxos de trabalho de aprendizado de máquina. Atualmente, os modelos treinados com o SDK não podem ser integrados diretamente ao Customer Insights. Um pipeline de inferência em lote que usa esse modelo é necessário para a integração com o Customer Insights.

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a>Requisitos de pipeline em lote para a integração com o Customer Insights

### <a name="dataset-configuration"></a>Configuração do conjunto de dados

Você precisa criar conjuntos de dados para usar dados de entidade do Customer Insights para seu pipeline de inferência em lote. Esses conjuntos de dados precisam ser registrados no espaço de trabalho. Atualmente, nós apenas oferecemos suporte a [conjuntos de dados de tabela](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) no formato .csv. Os conjuntos de dados que correspondem aos dados da entidade precisam ser parametrizados como um parâmetro de pipeline.
   
* Parâmetros do conjunto de dados no designer
   
     No designer, abra **Selecionar colunas no conjunto de dados** e selecione **Definir como parâmetro de pipeline** em que você fornece um nome para o parâmetro.

     > [!div class="mx-imgBorder"]
     > ![Parametrização do conjunto de dados no designer.](media/intelligence-designer-dataset-parameters.png "Parametrização do conjunto de dados no designer")
   
* Parâmetro do conjunto de dados no SDK (Python)
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a>Pipeline de inferência em lote
  
* No designer, um pipeline de treinamento pode ser usado para criar ou atualizar um pipeline de inferência. Atualmente, apenas pipelines de inferência em lote são compatíveis.

* Usando o SDK, você pode publicar o pipeline em um ponto de extremidade. Atualmente, o Customer Insights se integra ao pipeline padrão em um ponto de extremidade de pipeline em lote no espaço de trabalho do Machine Learning.
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a>Importar dados de pipeline para o Customer Insights

* O designer fornece o [Módulo de exportação de dados](/azure/machine-learning/algorithm-module-reference/export-data) que permite à saída de um pipeline ser exportada para o armazenamento do Azure. Atualmente, o módulo deve usar o tipo de armazenamento de dados **Armazenamento de Blobs do Azure** e parametrizar o **Armazenamento de dados** e o **Caminho** relativo. O Customer Insights substitui esses dois parâmetros durante a execução do pipeline com um armazenamento de dados e caminho que é acessível ao produto.
   > [!div class="mx-imgBorder"]
   > ![Configuração do módulo de exportação de dados.](media/intelligence-designer-importdata.png "Configuração do módulo de exportação de dados")
   
* Ao gravar a saída de inferência usando código, você pode carregar a saída para um caminho dentro de um *armazenamento de dados registrado* no espaço de trabalho. Se o caminho e o armazenamento de dados forem parametrizados no pipeline, o Customer Insights poderá ler e importar a saída da inferência. Atualmente, uma única saída de tabela no formato csv é compatível. O caminho deve incluir o diretório e o nome do arquivo.

   ```python
   # In Pipeline setup script
      OutputPathParameter = PipelineParameter(name="output_path", default_value="HotelChurnOutput/HotelChurnOutput.csv")
      OutputDatastoreParameter = PipelineParameter(name="output_datastore", default_value="workspaceblobstore")
   ...
   # In pipeline execution script
      run = Run.get_context()
      ws = run.experiment.workspace
      datastore = Datastore.get(ws, output_datastore) # output_datastore is parameterized
      directory_name =  os.path.dirname(output_path)  # output_path is parameterized.
      
      # Datastore.upload() or Dataset.File.upload_directory() are supported methods to uplaod the data
      # datastore.upload(src_dir=<<working directory>>, target_path=directory_name, overwrite=False, show_progress=True)
      output_dataset = Dataset.File.upload_directory(src_dir=<<working directory>>, target = (datastore, directory_name)) # Remove trailing "/" from directory_name
   ```


[!INCLUDE[footer-include](../includes/footer-banner.md)]