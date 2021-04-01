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
ms.openlocfilehash: edd2cf488b52cef87b09b90336e48fdc7f470a68
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597405"
---
# <a name="use-azure-machine-learning-based-models"></a><span data-ttu-id="5b27e-103">Usar modelos baseados em Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="5b27e-103">Use Azure Machine Learning-based models</span></span>

<span data-ttu-id="5b27e-104">Os dados unificados no Dynamics 365 Customer Insights são uma fonte para a criação de modelos de machine learning que podem gerar insights de negócios adicionais.</span><span class="sxs-lookup"><span data-stu-id="5b27e-104">The unified data in Dynamics 365 Customer Insights is a source for building machine learning models that can generate additional business insights.</span></span> <span data-ttu-id="5b27e-105">O Customer Insights integra-se ao Machine Learning Studio (clássico) e Azure Machine Learning para usar seus próprios modelos personalizados.</span><span class="sxs-lookup"><span data-stu-id="5b27e-105">Customer Insights integrates with Machine Learning Studio (classic) and Azure Machine Learning to use your own custom models.</span></span> <span data-ttu-id="5b27e-106">Consulte os [experimentos do Machine Learning Studio (clássico)](machine-learning-studio-experiments.md) para obter exemplos de experimentos baseados no Machine Learning Studio (clássico).</span><span class="sxs-lookup"><span data-stu-id="5b27e-106">Refer to [Machine Learning Studio (classic) experiments](machine-learning-studio-experiments.md) for examples of experiments built on Machine Learning Studio (classic).</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="5b27e-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="5b27e-107">Prerequisites</span></span>

- <span data-ttu-id="5b27e-108">Acesso ao Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5b27e-108">Access to Customer Insights</span></span>
- <span data-ttu-id="5b27e-109">Ativar assinatura do Azure Enterprise</span><span class="sxs-lookup"><span data-stu-id="5b27e-109">Active Azure Enterprise subscription</span></span>
- [<span data-ttu-id="5b27e-110">Perfis de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="5b27e-110">Unified customer profiles</span></span>](data-unification.md)
- <span data-ttu-id="5b27e-111">[Exportação de entidade para armazenamento de Blobs do Azure](export-azure-blob-storage.md) configurada</span><span class="sxs-lookup"><span data-stu-id="5b27e-111">[Entity export to Azure Blob storage](export-azure-blob-storage.md) configured</span></span>

## <a name="set-up-azure-machine-learning-workspace"></a><span data-ttu-id="5b27e-112">Configurar o espaço de trabalho do Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="5b27e-112">Set up Azure Machine Learning workspace</span></span>

1. <span data-ttu-id="5b27e-113">Consulte [Criar um espaço de trabalho do Azure Machine Learning](/azure/machine-learning/concept-workspace#-create-a-workspace) e conheça opções diferentes para criar o espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="5b27e-113">See [create a Azure Machine Learning workspace](/azure/machine-learning/concept-workspace#-create-a-workspace) for different options to create the workspace.</span></span> <span data-ttu-id="5b27e-114">Para obter o melhor desempenho, crie o espaço de trabalho em uma região do Azure que seja geograficamente mais próxima de seu ambiente do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b27e-114">For best performance, create the workspace in an Azure region that is geographically closest to your Customer Insights environment.</span></span>

1. <span data-ttu-id="5b27e-115">Acesse seu espaço de trabalho por meio do [Azure Machine Learning Studio](https://ml.azure.com/).</span><span class="sxs-lookup"><span data-stu-id="5b27e-115">Access your workspace through the [Azure Machine Learning Studio](https://ml.azure.com/).</span></span> <span data-ttu-id="5b27e-116">Existem várias [maneiras de interagir](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) com seu espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="5b27e-116">There are several [ways to interact](/azure/machine-learning/concept-workspace#tools-for-workspace-interaction) with your workspace.</span></span>

## <a name="work-with-azure-machine-learning-designer"></a><span data-ttu-id="5b27e-117">Trabalhar com o designer do Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="5b27e-117">Work with Azure Machine Learning designer</span></span>

<span data-ttu-id="5b27e-118">O designer do Azure Machine Learning fornece uma tela visual em que você pode arrastar e soltar conjuntos de dados e módulos, de forma semelhante ao Machine Learning Studio (clássico).</span><span class="sxs-lookup"><span data-stu-id="5b27e-118">Azure Machine Learning designer provides a visual canvas where you can drag and drop datasets and modules, similar to Machine Learning Studio (classic).</span></span> <span data-ttu-id="5b27e-119">Um pipeline em lote criado a partir do designer pode ser integrado ao Customer Insights se eles forem configurados apropriadamente.</span><span class="sxs-lookup"><span data-stu-id="5b27e-119">A batch pipeline created from the designer can be integrated into Customer Insights if they are configured accordingly.</span></span> 
   
## <a name="working-with-azure-machine-learning-sdk"></a><span data-ttu-id="5b27e-120">Trabalhar com o SDK do Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="5b27e-120">Working with Azure Machine Learning SDK</span></span>

<span data-ttu-id="5b27e-121">Cientistas de dados e desenvolvedores de IA usam o [SDK do Azure Machine Learning](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) para criar fluxos de trabalho de aprendizado de máquina.</span><span class="sxs-lookup"><span data-stu-id="5b27e-121">Data scientists and AI developers use the [Azure Machine Learning SDK](/python/api/overview/azure/ml/?preserve-view=true&view=azure-ml-py) to build machine learning workflows.</span></span> <span data-ttu-id="5b27e-122">Atualmente, os modelos treinados com o SDK não podem ser integrados diretamente ao Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b27e-122">Currently, models trained using the SDK can't be integrated directly with Customer Insights.</span></span> <span data-ttu-id="5b27e-123">Um pipeline de inferência em lote que usa esse modelo é necessário para a integração com o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="5b27e-123">A batch inference pipeline that consumes that model is required for integration with Customer Insights.</span></span>

## <a name="batch-pipeline-requirements-to-integrate-with-customer-insights"></a><span data-ttu-id="5b27e-124">Requisitos de pipeline em lote para a integração com o Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5b27e-124">Batch pipeline requirements to integrate with Customer Insights</span></span>

### <a name="dataset-configuration"></a><span data-ttu-id="5b27e-125">Configuração do conjunto de dados</span><span class="sxs-lookup"><span data-stu-id="5b27e-125">Dataset Configuration</span></span>

<span data-ttu-id="5b27e-126">Você precisa criar conjuntos de dados para usar dados de entidade do Customer Insights para seu pipeline de inferência em lote.</span><span class="sxs-lookup"><span data-stu-id="5b27e-126">You need to create datasets to use entity data from Customer Insights to your batch inference pipeline.</span></span> <span data-ttu-id="5b27e-127">Esses conjuntos de dados precisam ser registrados no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="5b27e-127">These datasets need to be registered in the workspace.</span></span> <span data-ttu-id="5b27e-128">Atualmente, nós apenas oferecemos suporte a [conjuntos de dados de tabela](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) no formato .csv.</span><span class="sxs-lookup"><span data-stu-id="5b27e-128">Currently, we only support [tabular datasets](/azure/machine-learning/how-to-create-register-datasets#tabulardataset) in .csv format.</span></span> <span data-ttu-id="5b27e-129">Os conjuntos de dados que correspondem aos dados da entidade precisam ser parametrizados como um parâmetro de pipeline.</span><span class="sxs-lookup"><span data-stu-id="5b27e-129">The datasets that correspond to entity data need to be parameterized as a pipeline parameter.</span></span>
   
* <span data-ttu-id="5b27e-130">Parâmetros do conjunto de dados no designer</span><span class="sxs-lookup"><span data-stu-id="5b27e-130">Dataset parameters in Designer</span></span>
   
     <span data-ttu-id="5b27e-131">No designer, abra **Selecionar colunas no conjunto de dados** e selecione **Definir como parâmetro de pipeline** em que você fornece um nome para o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="5b27e-131">In the designer, open **Select Columns in Dataset** and select **Set as pipeline parameter** where you provide a name for the parameter.</span></span>

     > [!div class="mx-imgBorder"]
     > <span data-ttu-id="5b27e-132">![Parametrização do conjunto de dados no designer](media/intelligence-designer-dataset-parameters.png "Parametrização do conjunto de dados no designer")</span><span class="sxs-lookup"><span data-stu-id="5b27e-132">![Dataset parameterization in designer](media/intelligence-designer-dataset-parameters.png "Dataset parameterization in designer")</span></span>
   
* <span data-ttu-id="5b27e-133">Parâmetro do conjunto de dados no SDK (Python)</span><span class="sxs-lookup"><span data-stu-id="5b27e-133">Dataset parameter in SDK (Python)</span></span>
   
   ```python
   HotelStayActivity_dataset = Dataset.get_by_name(ws, name='Hotel Stay Activity Data')
   HotelStayActivity_pipeline_param = PipelineParameter(name="HotelStayActivity_pipeline_param", default_value=HotelStayActivity_dataset)
   HotelStayActivity_ds_consumption = DatasetConsumptionConfig("HotelStayActivity_dataset", HotelStayActivity_pipeline_param)
   ```

### <a name="batch-inference-pipeline"></a><span data-ttu-id="5b27e-134">Pipeline de inferência em lote</span><span class="sxs-lookup"><span data-stu-id="5b27e-134">Batch inference pipeline</span></span>
  
* <span data-ttu-id="5b27e-135">No designer, um pipeline de treinamento pode ser usado para criar ou atualizar um pipeline de inferência.</span><span class="sxs-lookup"><span data-stu-id="5b27e-135">In the designer, a training pipeline can be used to create or update an inference pipeline.</span></span> <span data-ttu-id="5b27e-136">Atualmente, apenas pipelines de inferência em lote são compatíveis.</span><span class="sxs-lookup"><span data-stu-id="5b27e-136">Currently, only batch inference pipelines are supported.</span></span>

* <span data-ttu-id="5b27e-137">Usando o SDK, você pode publicar o pipeline em um ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="5b27e-137">Using the SDK, you can publish the pipeline to an endpoint.</span></span> <span data-ttu-id="5b27e-138">Atualmente, o Customer Insights se integra ao pipeline padrão em um ponto de extremidade de pipeline em lote no espaço de trabalho do Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="5b27e-138">Currently, Customer Insights integrates with the default pipeline in a batch pipeline endpoint in the Machine Learning workspace.</span></span>
   
   ```python
   published_pipeline = pipeline.publish(name="ChurnInferencePipeline", description="Published Churn Inference pipeline")
   pipeline_endpoint = PipelineEndpoint.get(workspace=ws, name="ChurnPipelineEndpoint") 
   pipeline_endpoint.add_default(pipeline=published_pipeline)
   ```

### <a name="import-pipeline-data-into-customer-insights"></a><span data-ttu-id="5b27e-139">Importar dados de pipeline para o Customer Insights</span><span class="sxs-lookup"><span data-stu-id="5b27e-139">Import pipeline data into Customer Insights</span></span>

* <span data-ttu-id="5b27e-140">O designer fornece o [Módulo de exportação de dados](/azure/machine-learning/algorithm-module-reference/export-data) que permite à saída de um pipeline ser exportada para o armazenamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="5b27e-140">The designer provides the [Export Data module](/azure/machine-learning/algorithm-module-reference/export-data) that allows the output of a pipeline to be exported to Azure storage.</span></span> <span data-ttu-id="5b27e-141">Atualmente, o módulo deve usar o tipo de armazenamento de dados **Armazenamento de Blobs do Azure** e parametrizar o **Armazenamento de dados** e o **Caminho** relativo.</span><span class="sxs-lookup"><span data-stu-id="5b27e-141">Currently, the module must use the datastore type **Azure Blob Storage** and parameterize the **Datastore** and relative **Path**.</span></span> <span data-ttu-id="5b27e-142">O Customer Insights substitui esses dois parâmetros durante a execução do pipeline com um armazenamento de dados e caminho que é acessível ao produto.</span><span class="sxs-lookup"><span data-stu-id="5b27e-142">Customer Insights overrides both these parameters during pipeline execution with a datastore and path that is accessible to the product.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5b27e-143">![Configuração do módulo de exportação de dados](media/intelligence-designer-importdata.png "Configuração do módulo de exportação de dados")</span><span class="sxs-lookup"><span data-stu-id="5b27e-143">![Export Data Module Configuration](media/intelligence-designer-importdata.png "Export Data Module Configuration")</span></span>
   
* <span data-ttu-id="5b27e-144">Ao gravar a saída de inferência usando código, você pode carregar a saída para um caminho dentro de um *armazenamento de dados registrado* no espaço de trabalho.</span><span class="sxs-lookup"><span data-stu-id="5b27e-144">When writing the inference output using code, you can upload the output to the a path within a *registered datastore* in the workspace.</span></span> <span data-ttu-id="5b27e-145">Se o caminho e o armazenamento de dados forem parametrizados no pipeline, o Customer Insights poderá ler e importar a saída da inferência.</span><span class="sxs-lookup"><span data-stu-id="5b27e-145">If the path and datastore are parameterized in the pipeline, Customer insights will be able to read and import the inference output.</span></span> <span data-ttu-id="5b27e-146">Atualmente, uma única saída de tabela no formato csv é compatível.</span><span class="sxs-lookup"><span data-stu-id="5b27e-146">Currently, a single tabular output in csv format is supported.</span></span> <span data-ttu-id="5b27e-147">O caminho deve incluir o diretório e o nome do arquivo.</span><span class="sxs-lookup"><span data-stu-id="5b27e-147">The path must include the directory and filename.</span></span>

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