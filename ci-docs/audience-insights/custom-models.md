---
title: Modelos de aprendizado de máquina personalizados | Microsoft Docs
description: Trabalhar com modelos personalizados do Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 82f6f363497f8f1b45fa84acd49bcaed332e60e8
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305606"
---
# <a name="custom-machine-learning-models"></a>Modelos de aprendizado de máquina personalizados

**Inteligência** > **Modelos personalizados** permite que você gerencie fluxos de trabalho com base nos modelos do Azure Machine Learning. Os fluxos de trabalho ajudam você a escolher os dados dos quais deseja gerar insights e mapear os resultados para os dados unificados do cliente. Para obter mais informações sobre a criação de modelos do ML personalizados, consulte [Usar modelos baseados em Aprendizado de Máquina do Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsável

As previsões oferecem recursos para criar melhores experiências para o cliente, melhorar os recursos de negócios e fluxos de receita. Recomendamos fortemente que você equilibre o valor de sua previsão com o impacto que ela tem e os desvios que podem ser introduzidos de maneira ética. Saiba mais sobre como a Microsoft está [tratando a IA responsável](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Você também pode conhecer [técnicas e processos de aprendizado de máquina responsável](/azure/machine-learning/concept-responsible-ml) específico para o Azure Machine Learning.

## <a name="prerequisites"></a>Pré-requisitos

- Atualmente, esse recurso oferece suporte a serviços da Web publicados por meio de [Machine Learning Studio (clássico)](https://studio.azureml.net) e [Pipelines em lote do Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).

- Você precisa de uma conta de armazenamento Gen2 do Azure Data Lake associada à sua instância do Azure Studio para usar esse recurso. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-quickstart-create-account).

- Para espaços de trabalho do Azure Machine Learning com pipelines, você precisa de permissões de Proprietário ou Administrador de Acesso de Usuários para o Azure Machine Learning Workspace.

   > [!NOTE]
   > Os dados são transferidos entre as instâncias do Customer Insights e os serviços da Web ou pipelines do Azure selecionados no fluxo de trabalho. Ao transferir dados para um serviço do Azure, verifique se o serviço está configurado para processar dados da forma e do local necessários para obedecer a requisitos legais ou regulamentares para esses dados para sua organização.

## <a name="add-a-new-workflow"></a>Adicionar um novo fluxo de trabalho

1. Vamos para **Inteligência** > **Modelos personalizados** e selecione **Novo Fluxo de Trabalho**.

1. Dê ao seu modelo personalizado um nome reconhecível no campo **Nome**.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do painel Novo fluxo de trabalho](media/new-workflowv2.png "Captura de tela do painel Novo fluxo de trabalho")

1. Selecione a organização que contém o serviço Web em **Locatário que contém seu serviço Web**.

1. Se sua assinatura do Aprendizado de Máquina do Azure estiver em um locatário diferente do Customer Insights, selecione **Entrar** com suas credenciais para a organização selecionada.

1. Selecione **Espaços de Trabalho** associado ao seu serviço da Web. Há duas seções listadas, uma para o Azure Machine Learning v1 (Machine Learning Studio [clássico]) e o Azure Machine Learning v2 (Azure Machine Learning). Se você não tiver certeza de qual espaço de trabalho é o correto para seu serviço da Web do Machine Learning Studio (clássico), selecione **Qualquer um**.

1. Escolha o serviço Web do Machine Learning Studio (clássico) ou o pipeline do Azure Machine Learning na lista suspensa **Serviço Web que contém seu modelo**. Em seguida, selecione **Próximo**.
   - Saiba mais sobre como [publicar um serviço Web no Machine Learning Studio (clássico)](/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Saiba mais sobre como [publicar um pipeline no Azure Machine Learning usando o designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Seu pipeline deve ser publicado em um [ponto de extremidade do pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

1. Para cada **Entrada do serviço Web**, selecione **Entidade** correspondente nos insights de público-alvo e selecione **Avançar**.
   > [!NOTE]
   > O fluxo de trabalho do modelo personalizado aplicará heurística para mapear os campos de entrada do serviço Web para atributos de entidade com base no nome e tipo de dados do campo. Você verá um erro se um campo do serviço Web não puder ser mapeado para uma entidade.

   > [!div class="mx-imgBorder"]
   > ![Configurar um fluxo de trabalho](media/intelligence-screen2-updated.png "Configurar um fluxo de trabalho")

1. Na etapa **Parâmetros de saída do modelo**, defina as seguintes propriedades:
   - Machine Learning Studio (clássico)
      1. Insira a saída **Nome da entidade** para a qual deseja que os resultados de saída do serviço Web fluam.
   - Aprendizado de Máquina do Azure
      1. Insira a saída **Nome da entidade** para a qual deseja que os resultados de saída do pipeline fluam.
      1. Selecione **Nome do parâmetro de armazenamento de dados de saída** do pipeline em lote no menu suspenso.
      1. Selecione **Nome do parâmetro do Caminho de Saída** do pipeline em lote no menu suspenso.

      > [!div class="mx-imgBorder"]
      > ![Painel de parâmetros de saída do modelo](media/intelligence-screen3-outputparameters.png "Painel de parâmetros de saída do modelo")

1. Selecione o atributo correspondente na lista suspensa **ID do cliente nos resultados** que identifica os clientes e selecione **Salvar**.

   > [!div class="mx-imgBorder"]
   > ![Relacionar os resultados ao painel de dados do cliente](media/intelligence-screen4-relatetocustomer.png "Relacionar os resultados ao painel de dados do cliente")

1. Você verá a tela **Fluxo de Trabalho Salvo** com detalhes sobre o fluxo de trabalho.    
   Se você configurou um fluxo de trabalho para um pipeline do Azure Machine Learning, os insights de público-lavo serão anexados ao espaço de trabalho que contém o pipeline. Os insights de público-alvo receberão uma função **Colaborador** no espaço de trabalho do Azure.

1. Escolha **Concluído**.

1. Agora é possível executar o fluxo de trabalho na página **Modelos personalizados**.

## <a name="edit-a-workflow"></a>Editar um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** ao lado de um fluxo de trabalho que você criou anteriormente e selecione **Editar**.

1. Você pode atualizar o nome reconhecível do seu fluxo de trabalho no campo **Nome de exibição**, mas não pode alterar o serviço Web ou pipeline configurado. Selecione **Avançar**.

1. Para cada **entrada de serviço Web**, você pode atualizar a **Entidade** correspondente usando insights de público-alvo. Em seguida, selecione **Próximo**.

1. Na etapa **Parâmetros de saída do modelo**, defina as seguintes propriedades:
   - Machine Learning Studio (clássico)
      1. Insira a saída **Nome da entidade** para a qual deseja que os resultados de saída do serviço Web fluam.
   - Aprendizado de Máquina do Azure
      1. Insira a saída **Nome da entidade** para a qual deseja que os resultados de saída do pipeline fluam.
      1. Selecione **Nome do parâmetro de armazenamento de dados de saída** para seu pipeline de teste.
      1. Selecione **Nome do parâmetro do Caminho de Saída** para seu pipeline de teste.

1. Selecione o atributo correspondente na lista suspensa **ID do cliente nos resultados** que identifica os clientes e selecione **Salvar**.
   Escolha um atributo da saída de inferência com valores semelhantes à coluna ID do Cliente da entidade Cliente. Se não tiver essa coluna em seu conjunto de dados, escolha um atributo que identifique a linha de maneira exclusiva.

## <a name="run-a-workflow"></a>Executar um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** ao lado de um fluxo de trabalho que você criou anteriormente.

1. Selecione **Executar**.

Seu fluxo de trabalho também é executado automaticamente com cada atualização agendada. Saiba mais sobre como [configurar atualizações agendadas](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Excluir um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** ao lado de um fluxo de trabalho que você criou anteriormente.

1. Selecione **Excluir** e confirme sua exclusão.

Seu fluxo de trabalho será excluído. A [entidade](entities.md) criada quando você criou o fluxo de trabalho persiste e pode ser visualizada na página **Entidades**.

## <a name="results"></a>Resultados

Os resultados de um fluxo de trabalho são armazenados na entidade configurada durante a fase de parâmetros de saída do modelo. Você pode acessar esses dados a partir da [página de entidades](entities.md) ou com o [acesso à API](apis.md).

### <a name="api-access"></a>Acesso à API

Para que a consulta OData específica obtenha dados de uma entidade de modelo personalizado, use o seguinte formato:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Substitua `<your instance id>` pela ID de seu ambiente do Customer Insights, que você encontra na barra de endereços do seu navegador ao acessar o Customer Insights.

1. Substitua `<custom model output entity>` pelo nome da entidade que você forneceu durante a etapa de parâmetros de saída do modelo da configuração do modelo personalizado.

1. Substitua `<guid value>` pela ID de Cliente do cliente do qual você deseja acessar o registro. Normalmente, você pode encontrar essa ID na [página de perfis de clientes](customer-profiles.md) no campo CustomerID.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

- Por que não consigo ver meu pipeline ao configurar um fluxo de trabalho de modelo personalizado?    
  Esse problema é frequentemente causado por um problema de configuração no pipeline. Verifique se o [parâmetro de entrada está configurado](azure-machine-learning-experiments.md#dataset-configuration) e se os [parâmetros de armazenamento de dados de saída e de caminho](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) também estão configurados.

- O que significa o erro "Não foi possível salvar o fluxo de trabalho de inteligência"?    
  Os usuários geralmente veem essa mensagem de erro se não tiverem privilégios de Proprietário ou de Administrador de Acesso de Usuários no espaço de trabalho. O usuário precisa de um nível mais alto de permissões para permitir que o Customer Insights processe o fluxo de trabalho como um serviço, em vez de usar as credenciais do usuário para execuções subsequentes do fluxo de trabalho.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
