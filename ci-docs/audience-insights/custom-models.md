---
title: Modelos de aprendizado de máquina personalizados | Microsoft Docs
description: Trabalhar com modelos personalizados do Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34489faaecc5da1ce3dd68d799b3e0e0d9672ab7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267220"
---
# <a name="custom-machine-learning-models"></a>Modelos de aprendizado de máquina personalizados

**Inteligência** > **Modelos personalizados** permite que você gerencie fluxos de trabalho com base nos modelos do Azure Machine Learning. Os fluxos de trabalho ajudam você a escolher os dados dos quais deseja gerar insights e mapear os resultados para os dados unificados do cliente. Para obter mais informações sobre a criação de modelos do ML personalizados, consulte [Usar modelos baseados em Aprendizado de Máquina do Azure](azure-machine-learning-experiments.md).

## <a name="responsible-ai"></a>IA responsável

As previsões oferecem recursos para criar melhores experiências para o cliente, melhorar os recursos de negócios e fluxos de receita. Recomendamos fortemente que você equilibre o valor de sua previsão com o impacto que ela tem e os desvios que podem ser introduzidos de maneira ética. Saiba mais sobre como a Microsoft está [tratando a IA responsável](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6). Você também pode conhecer [técnicas e processos de aprendizado de máquina responsável](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) específico para o Azure Machine Learning.

## <a name="prerequisites"></a>Pré-requisitos

- Atualmente, esse recurso oferece suporte a serviços da Web publicados por meio de [Machine Learning Studio (clássico)](https://studio.azureml.net) e [Pipelines em lote do Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).

- Você precisa de uma conta de armazenamento Gen2 do Azure Data Lake associada à sua instância do Azure Studio para usar esse recurso. Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)

## <a name="add-a-new-workflow"></a>Adicionar um novo fluxo de trabalho

1. Vamos para **Inteligência** > **Modelos personalizados** e selecione **Novo Fluxo de Trabalho**.

1. Dê ao seu modelo personalizado um nome reconhecível no campo **Nome**.

   > [!div class="mx-imgBorder"]
   > ![Captura de tela do painel Novo fluxo de trabalho](media/new-workflowv2.png "Captura de tela do painel Novo fluxo de trabalho")

1. Selecione a organização que contém o serviço Web em **Locatário que contém seu serviço Web**.

1. Se sua assinatura do Aprendizado de Máquina do Azure estiver em um locatário diferente do Customer Insights, selecione **Entrar** com suas credenciais para a organização selecionada.

1. Selecione **Espaços de Trabalho** associado ao seu serviço da Web. Há duas seções listadas, uma para o Azure Machine Learning v1 (Machine Learning Studio [clássico]) e o Azure Machine Learning v2 (Azure Machine Learning). Se você não tiver certeza de qual espaço de trabalho é o correto para seu serviço da Web do Machine Learning Studio (clássico), selecione **Qualquer um**.

1. Escolha o serviço Web do Machine Learning Studio (clássico) ou o pipeline do Azure Machine Learning na lista suspensa **Serviço Web que contém seu modelo**. Em seguida, selecione **Próximo**.
   - Saiba mais sobre como [publicar um serviço Web no Machine Learning Studio (clássico)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)
   - Saiba mais sobre como [publicar um pipeline no Azure Machine Learning usando o designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk). Seu pipeline deve ser publicado em um [ponto de extremidade do pipeline](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).

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
   Você precisa escolher um atributo da saída de inferência com valores semelhantes à coluna ID do cliente da entidade Cliente. Se não tiver essa coluna em seu conjunto de dados, escolha um atributo que identifique a linha de maneira exclusiva.

## <a name="run-a-workflow"></a>Executar um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** ao lado de um fluxo de trabalho que você criou anteriormente.

1. Selecione **Executar**.

Seu fluxo de trabalho também é executado automaticamente com cada atualização agendada. Saiba mais sobre como [configurar atualizações agendadas](system.md#schedule-tab).

## <a name="delete-a-workflow"></a>Excluir um fluxo de trabalho

1. Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** ao lado de um fluxo de trabalho que você criou anteriormente.

1. Selecione **Excluir** e confirme sua exclusão.

Seu fluxo de trabalho será excluído. A [entidade](entities.md) criada quando você criou o fluxo de trabalho persiste e pode ser visualizada na página **Entidades**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]