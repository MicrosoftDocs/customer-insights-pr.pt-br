---
title: Modelos de aprendizado de máquina personalizados | Microsoft Docs
description: Trabalhar com modelos personalizados do Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: zacookmsft
ms.author: zacook
manager: shellyha
searchScope:
- ci-custom-models
- customerInsights
ms.openlocfilehash: 89553b511d249fd586e36a1c4944a977513b0643
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609724"
---
# <a name="custom-machine-learning-models"></a>Modelos de aprendizado de máquina personalizados

> [!NOTE]
> O suporte para o Machine Learning Studio (clássico) terminará em 31 de agosto de 2024. Recomendamos que você faça a transição para o [Azure Machine Learning](/azure/machine-learning/overview-what-is-azure-machine-learning) até essa data.
>
> A partir de 1º de dezembro de 2021, você não poderá criar novos recursos do Machine Learning Studio (clássico). Até 31 de agosto de 2024, você pode continuar a usar os recursos existentes do Machine Learning Studio (clássico). Para obter mais informações, consulte [Migrar para o Azure Machine Learning](/azure/machine-learning/migrate-overview).

Os modelos personalizados permitem que você gerencie fluxos de trabalho com base nos modelos do Azure Machine Learning. Os fluxos de trabalho ajudam você a escolher os dados dos quais deseja gerar insights e mapear os resultados para os dados unificados do cliente. Para obter mais informações sobre a criação de modelos do ML personalizados, consulte [Usar modelos baseados em Aprendizado de Máquina do Azure](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Pré-requisitos

- Serviços Web publicados por meio de [pipelines de lote do Azure Machine Learning](/azure/machine-learning/concept-ml-pipelines).
- A pipeline deve ser publicado em um [ponto de extremidade do pipeline](/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).
- Uma [conta de armazenamento Gen2 do Azure Data Lake](/azure/storage/blobs/data-lake-storage-quickstart-create-account) associada à sua instância do Azure Studio para usar esse recurso.
- Para espaços de trabalho do Azure Machine Learning com pipelines, permissões de Proprietário ou Administrador de Acesso de Usuários para o Azure Machine Learning Workspace.

  > [!NOTE]
  > Os dados são transferidos entre as instâncias do Customer Insights e os serviços da Web ou pipelines do Azure selecionados no fluxo de trabalho. Ao transferir dados para um serviço do Azure, verifique se o serviço está configurado para processar dados da forma e do local necessários para obedecer a requisitos legais ou regulamentares para esses dados para sua organização.

## <a name="add-a-new-workflow"></a>Adicionar um novo fluxo de trabalho

1. Vamos para **Inteligência** > **Modelos personalizados** e selecione **Novo Fluxo de Trabalho**.

1. Forneça um **Nome** reconhecível.

   :::image type="content" source="media/new-workflowv2.png" alt-text="Captura de tela do painel Novo fluxo de trabalho.":::

1. Selecione a organização que contém o serviço Web em **Locatário que contém seu serviço Web**.

1. Se sua assinatura do Aprendizado de Máquina do Azure estiver em um locatário diferente do Customer Insights, selecione **Entrar** com suas credenciais para a organização selecionada.

1. Selecione **Espaços de Trabalho** associado ao seu serviço da Web.

1. Escolha o pipeline do Azure Machine Learning na lista suspensa **Serviço Web que contém seu modelo**. Em seguida, selecione **Próximo**.
   Saiba mais sobre como [publicar um pipeline no Azure Machine Learning usando o designer](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou [SDK](/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).

1. Para cada **Entrada de serviço Web**, selecione a **Entidade** correspondente no Customer Insights. Em seguida, selecione **Próximo**.
   > [!NOTE]
   > O fluxo de trabalho do modelo personalizado aplicará heurística para mapear os campos de entrada do serviço Web para atributos de entidade com base no nome e tipo de dados do campo. Você verá um erro se um campo do serviço Web não puder ser mapeado para uma entidade.

   :::image type="content" source="media/intelligence-screen2-updated.png" alt-text="Configure um fluxo de trabalho.":::

1. Para **Parâmetros de saída do modelo**, defina as seguintes propriedades:
   - **Nome da entidade** para os resultados de saída do pipeline
   - **Nome do parâmetro de armazenamento de dados de saída** do seu pipeline de lote
   - **Nome do parâmetro do Caminho de Saída** do seu pipeline de lote

   :::image type="content" source="media/intelligence-screen3-outputparameters.png" alt-text="Painel de Parâmetros de Saída do Modelo.":::

1. Selecione o atributo correspondente em **ID do cliente nos resultados** que identifica os clientes e selecione **Salvar**.

   :::image type="content" source="media/intelligence-screen4-relatetocustomer.png" alt-text="Relacione os resultados ao painel de Dados do cliente.":::

   A tela **Fluxo de Trabalho Salvo** exibe detalhes sobre o fluxo de trabalho. Se você configurou um fluxo de trabalho para um pipeline Azure Machine Learning, o Customer Insights é anexado ao espaço de trabalho que contém o pipeline. O Customer Insights obterá uma função **Colaborador** no espaço de trabalho do Azure.

1. Selecione **Concluído**. A página **Modelos personalizados** é exibida.

1. Selecione as reticências verticais (&vellip;) para o fluxo de trabalho e selecione **Executar**. Seu fluxo de trabalho também é executado automaticamente com cada [atualização agendada](schedule-refresh.md).

## <a name="manage-an-existing-workflow"></a>Gerenciar um fluxo de trabalho existente

Acesse **Inteligência** > **Modelos personalizados** para exibir os fluxos de trabalho que você criou.

Selecione um fluxo de trabalho para exibir as ações disponíveis.

- **Editar** um fluxo de trabalho
- **Executar** um fluxo de trabalho
- [**Excluir**](#delete-a-workflow) um fluxo de trabalho

### <a name="edit-a-workflow"></a>Editar um fluxo de trabalho

1. Acesse **Inteligência** > **Modelos personalizados**.

1. Ao lado do fluxo de trabalho que deseja atualizar, selecione as reticências verticais (&vellip;) e selecione **Editar**.

1. Altere o **Nome de exibição** se necessário e selecione **Próximo**.

1. Para cada **Entrada de serviço Web**, atualize a **Entidade** correspondente no Customer Insights, se necessário. Em seguida, selecione **Próximo**.

1. Para **Parâmetros de saída do modelo**, altere qualquer um dos seguintes:
   - **Nome da entidade** para os resultados de saída do pipeline
   - **Nome do parâmetro de armazenamento de dados de saída** do seu pipeline de lote
   - **Nome do parâmetro do Caminho de Saída** do seu pipeline de lote

1. Altere o atributo correspondente de **ID do cliente nos resultados** para identificar os clientes. Escolha um atributo da saída de inferência com valores semelhantes à coluna ID do Cliente da entidade Cliente. Se não tiver essa coluna em seu conjunto de dados, escolha um atributo que identifique a linha de maneira exclusiva.

1. Selecione **Salvar**

### <a name="delete-a-workflow"></a>Excluir um fluxo de trabalho

1. Acesse **Inteligência** > **Modelos personalizados**.

1. Ao lado do fluxo de trabalho que deseja excluir, selecione as reticências verticais (&vellip;) e selecione **Excluir**.

1. Confirme a exclusão.

Seu fluxo de trabalho será excluído. A [entidade](entities.md) criada quando você criou o fluxo de trabalho persiste e pode ser visualizada na página **Dados** > **Entidades**.

## <a name="view-the-results"></a>Exibir os resultados

Os resultados de um fluxo de trabalho são armazenados no nome da entidade definido para **Parâmetros de saída do modelo**. Acesse esses dados na página [**Dados** > **Entidades**](entities.md) ou com o [acesso à API](apis.md).

### <a name="api-access"></a>Acesso à API

Para que a consulta OData específica obtenha dados de uma entidade de modelo personalizado, use o seguinte formato:

`https://api.ci.ai.dynamics.com/v1/instances/<your instance id>/data/<custom model output entity name>%3Ffilter%3DCustomerId%20eq%20'<guid value>'`

1. Substitua `<your instance id>` pela ID de seu ambiente do Customer Insights, que exibe na barra de endereços do seu navegador ao acessar o Customer Insights.

1. Substitua `<custom model output entity>` pelo nome da entidade que você forneceu para os **Parâmetros de saída do modelo**.

1. Substitua `<guid value>` pela ID de Cliente do cliente do qual você deseja acessar. Esta ID é exibida na [página de perfis de clientes](customer-profiles.md) no campo CustomerID.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

- Por que não consigo ver meu pipeline ao configurar um fluxo de trabalho de modelo personalizado?
  Esse problema é frequentemente causado por um problema de configuração no pipeline. Verifique se o [parâmetro de entrada está configurado](azure-machine-learning-experiments.md#dataset-configuration) e se os [parâmetros de armazenamento de dados de saída e de caminho](azure-machine-learning-experiments.md#import-pipeline-data-into-customer-insights) também estão configurados.

- O que significa o erro "Não foi possível salvar o fluxo de trabalho de inteligência"? 
  Os usuários geralmente veem essa mensagem de erro se não tiverem privilégios de Proprietário ou de Administrador de Acesso de Usuários no espaço de trabalho. O usuário precisa de um nível mais alto de permissões para permitir que o Customer Insights processe o fluxo de trabalho como um serviço, em vez de usar as credenciais do usuário para execuções subsequentes do fluxo de trabalho.

- Há suporte para um ponto de extremidade privado/link privado para meu fluxo de trabalho de modelo personalizado?
  O Customer Insights atualmente não oferece suporte a pontos de extremidade privados para modelos personalizados prontos para uso, mas uma solução alternativa manual está disponível. Entre em contato com o suporte para obter detalhes.

## <a name="responsible-ai"></a>IA responsável

As previsões oferecem recursos para criar melhores experiências para o cliente, melhorar os recursos de negócios e fluxos de receita. Recomendamos fortemente que você equilibre o valor de sua previsão com o impacto que ela tem e os desvios que podem ser introduzidos de maneira ética. Saiba mais sobre como a Microsoft está [tratando a IA responsável](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Você também pode conhecer [técnicas e processos de aprendizado de máquina responsável](/azure/machine-learning/concept-responsible-ml) específico para o Azure Machine Learning.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElk]

[!INCLUDE [footer-include](includes/footer-banner.md)]
