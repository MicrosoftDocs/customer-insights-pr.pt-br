---
title: Usar fontes de dados para ingerir dados
description: Saiba como importar dados de várias fontes.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643939"
---
# <a name="overview-about-data-sources"></a><span data-ttu-id="b3dcb-103">Visão geral sobre fontes de dados</span><span class="sxs-lookup"><span data-stu-id="b3dcb-103">Overview about data sources</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b3dcb-104">O recurso de insights de público-alvo no Dynamics 365 Customer Insights conecta-se aos dados de um amplo conjunto de fontes.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="b3dcb-105">A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="b3dcb-106">Depois de ingerir os dados, você pode [unificar](data-unification.md) e agir sobre eles.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="b3dcb-107">Adicionar fonte de dados</span><span class="sxs-lookup"><span data-stu-id="b3dcb-107">Add a data source</span></span>

<span data-ttu-id="b3dcb-108">Consulte os artigos detalhados sobre como adicionar uma fonte de dados, dependendo da opção escolhida.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="b3dcb-109">Você pode adicionar uma fonte de dados de três maneiras principais:</span><span class="sxs-lookup"><span data-stu-id="b3dcb-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="b3dcb-110">Por meio de dezenas de conectores do Power Query</span><span class="sxs-lookup"><span data-stu-id="b3dcb-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="b3dcb-111">De uma pasta do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="b3dcb-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="b3dcb-112">Do seu próprio lake do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="b3dcb-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="b3dcb-113">Ainda não é possível adicionar dados de fontes de dados locais.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="b3dcb-114">Analisar dados ingeridos</span><span class="sxs-lookup"><span data-stu-id="b3dcb-114">Review ingested data</span></span>

<span data-ttu-id="b3dcb-115">Você verá o nome de cada fonte de dados ingeridos, seu status e a última vez em que os dados foram atualizados para essa fonte.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="b3dcb-116">Você pode classificar a lista de fontes de dados por cada coluna.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b3dcb-117">![Fonte de dados adicionada](media/configure-data-datasource-added.png "Fonte de dados adicionada")</span><span class="sxs-lookup"><span data-stu-id="b3dcb-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="b3dcb-118">Status</span><span class="sxs-lookup"><span data-stu-id="b3dcb-118">Status</span></span>  |<span data-ttu-id="b3dcb-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="b3dcb-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="b3dcb-120">Êxito</span><span class="sxs-lookup"><span data-stu-id="b3dcb-120">Successful</span></span>   |<span data-ttu-id="b3dcb-121">A fonte de dados foi inserida com sucesso se um horário for mencionado na coluna **Atualizado**.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="b3dcb-122">Não iniciada</span><span class="sxs-lookup"><span data-stu-id="b3dcb-122">Not started</span></span>   |<span data-ttu-id="b3dcb-123">A fonte de dados ainda não recebeu dados ou ainda está no modo de rascunho.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="b3dcb-124">Atualizando</span><span class="sxs-lookup"><span data-stu-id="b3dcb-124">Refreshing</span></span>    |<span data-ttu-id="b3dcb-125">A ingestão de dados está em andamento.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-125">Data ingestion is in progress.</span></span> <span data-ttu-id="b3dcb-126">Você pode cancelar esta operação selecionando **Interromper atualização** na coluna **Ações**.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="b3dcb-127">A interrupção da atualização de uma fonte de dados a reverterá para o último estado de atualização.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="b3dcb-128">Falhou</span><span class="sxs-lookup"><span data-stu-id="b3dcb-128">Failed</span></span>     |<span data-ttu-id="b3dcb-129">A ingestão de dados encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="b3dcb-130">Selecione **Status da Atualização** para revisar mais detalhes sobre o status de atualização, incluindo detalhes do erro e atualizações do processo downstream.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-130">Select **Refresh status** to review more details on the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="b3dcb-131">O carregamento de dados pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-131">Loading data can take some time.</span></span> <span data-ttu-id="b3dcb-132">Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-132">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="b3dcb-133">Para obter mais informações, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="b3dcb-133">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="b3dcb-134">Atualizar uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="b3dcb-134">Refresh a data source</span></span>

<span data-ttu-id="b3dcb-135">As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-135">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="b3dcb-136">Acesse **Administrador** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações agendadas de todas as fontes de dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-136">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="b3dcb-137">Para atualizar uma fonte de dados sob demanda, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="b3dcb-137">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="b3dcb-138">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-138">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="b3dcb-139">Selecione as reticências verticais ao lado da fonte de dados que deseja atualizar e selecione **Atualizar** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-139">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="b3dcb-140">A fonte de dados agora é acionada para uma atualização manual.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-140">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="b3dcb-141">Atualizar uma fonte de dados atualizará tanto o esquema da entidade quanto os dados de todas as entidades especificadas na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-141">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="b3dcb-142">Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e que a fonte de dados seja revertida para seu último status de atualização.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-142">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="b3dcb-143">Excluir uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="b3dcb-143">Delete a data source</span></span>

1. <span data-ttu-id="b3dcb-144">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-144">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="b3dcb-145">Selecione as reticências verticais ao lado da fonte de dados que você deseja remover e selecione **Excluir** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-145">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="b3dcb-146">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="b3dcb-146">Confirm your deletion.</span></span>
