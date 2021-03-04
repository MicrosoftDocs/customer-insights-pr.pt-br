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
ms.openlocfilehash: 68aa1b56fb634da80a0c64db72f778d57507104d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269684"
---
# <a name="data-sources-overview"></a><span data-ttu-id="1ef67-103">Visão geral de fontes de dados</span><span class="sxs-lookup"><span data-stu-id="1ef67-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="1ef67-104">O recurso de insights de público-alvo no Dynamics 365 Customer Insights conecta-se aos dados de um amplo conjunto de fontes.</span><span class="sxs-lookup"><span data-stu-id="1ef67-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="1ef67-105">A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*.</span><span class="sxs-lookup"><span data-stu-id="1ef67-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="1ef67-106">Depois de ingerir os dados, você pode [unificar](data-unification.md) e agir sobre eles.</span><span class="sxs-lookup"><span data-stu-id="1ef67-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="1ef67-107">Adicionar fonte de dados</span><span class="sxs-lookup"><span data-stu-id="1ef67-107">Add a data source</span></span>

<span data-ttu-id="1ef67-108">Consulte os artigos detalhados sobre como adicionar uma fonte de dados, dependendo da opção escolhida.</span><span class="sxs-lookup"><span data-stu-id="1ef67-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="1ef67-109">Você pode adicionar uma fonte de dados de três maneiras principais:</span><span class="sxs-lookup"><span data-stu-id="1ef67-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="1ef67-110">Por meio de dezenas de conectores do Power Query</span><span class="sxs-lookup"><span data-stu-id="1ef67-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="1ef67-111">De uma pasta do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="1ef67-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="1ef67-112">Do seu próprio lake do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="1ef67-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

> [!NOTE]
> <span data-ttu-id="1ef67-113">Ainda não é possível adicionar dados de fontes de dados locais.</span><span class="sxs-lookup"><span data-stu-id="1ef67-113">You can't add data from on-premises data sources yet.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="1ef67-114">Analisar dados ingeridos</span><span class="sxs-lookup"><span data-stu-id="1ef67-114">Review ingested data</span></span>

<span data-ttu-id="1ef67-115">Você verá o nome de cada fonte de dados ingeridos, seu status e a última vez em que os dados foram atualizados para essa fonte.</span><span class="sxs-lookup"><span data-stu-id="1ef67-115">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="1ef67-116">Você pode classificar a lista de fontes de dados por cada coluna.</span><span class="sxs-lookup"><span data-stu-id="1ef67-116">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1ef67-117">![Fonte de dados adicionada](media/configure-data-datasource-added.png "Fonte de dados adicionada")</span><span class="sxs-lookup"><span data-stu-id="1ef67-117">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="1ef67-118">Status</span><span class="sxs-lookup"><span data-stu-id="1ef67-118">Status</span></span>  |<span data-ttu-id="1ef67-119">Descrição</span><span class="sxs-lookup"><span data-stu-id="1ef67-119">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="1ef67-120">Êxito</span><span class="sxs-lookup"><span data-stu-id="1ef67-120">Successful</span></span>   |<span data-ttu-id="1ef67-121">A fonte de dados foi inserida com sucesso se um horário for mencionado na coluna **Atualizado**.</span><span class="sxs-lookup"><span data-stu-id="1ef67-121">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="1ef67-122">Não iniciada</span><span class="sxs-lookup"><span data-stu-id="1ef67-122">Not started</span></span>   |<span data-ttu-id="1ef67-123">A fonte de dados ainda não recebeu dados ou ainda está no modo de rascunho.</span><span class="sxs-lookup"><span data-stu-id="1ef67-123">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="1ef67-124">Atualizando</span><span class="sxs-lookup"><span data-stu-id="1ef67-124">Refreshing</span></span>    |<span data-ttu-id="1ef67-125">A ingestão de dados está em andamento.</span><span class="sxs-lookup"><span data-stu-id="1ef67-125">Data ingestion is in progress.</span></span> <span data-ttu-id="1ef67-126">Você pode cancelar esta operação selecionando **Interromper atualização** na coluna **Ações**.</span><span class="sxs-lookup"><span data-stu-id="1ef67-126">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="1ef67-127">A interrupção da atualização de uma fonte de dados a reverterá para o último estado de atualização.</span><span class="sxs-lookup"><span data-stu-id="1ef67-127">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="1ef67-128">Falhou</span><span class="sxs-lookup"><span data-stu-id="1ef67-128">Failed</span></span>     |<span data-ttu-id="1ef67-129">A ingestão de dados encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="1ef67-129">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="1ef67-130">Selecione o valor na coluna **Status** de qualquer fonte de dados para revisar mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="1ef67-130">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="1ef67-131">No painel **Detalhes de progresso**, expanda **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="1ef67-131">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="1ef67-132">Selecione **Ver detalhes** para obter mais informações sobre o status de atualização, incluindo detalhes do erro e atualizações do processo downstream.</span><span class="sxs-lookup"><span data-stu-id="1ef67-132">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="1ef67-133">O carregamento de dados pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="1ef67-133">Loading data can take some time.</span></span> <span data-ttu-id="1ef67-134">Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="1ef67-134">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="1ef67-135">Para obter mais informações, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="1ef67-135">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="1ef67-136">Atualizar uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="1ef67-136">Refresh a data source</span></span>

<span data-ttu-id="1ef67-137">As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda.</span><span class="sxs-lookup"><span data-stu-id="1ef67-137">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="1ef67-138">Acesse **Administrador** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações agendadas de todas as fontes de dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="1ef67-138">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="1ef67-139">Para atualizar uma fonte de dados sob demanda, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="1ef67-139">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="1ef67-140">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="1ef67-140">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="1ef67-141">Selecione as reticências verticais ao lado da fonte de dados que deseja atualizar e selecione **Atualizar** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="1ef67-141">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="1ef67-142">A fonte de dados agora é acionada para uma atualização manual.</span><span class="sxs-lookup"><span data-stu-id="1ef67-142">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="1ef67-143">Atualizar uma fonte de dados atualizará tanto o esquema da entidade quanto os dados de todas as entidades especificadas na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="1ef67-143">Refreshing a data source will update both the entity schema as well as data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="1ef67-144">Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e que a fonte de dados seja revertida para seu último status de atualização.</span><span class="sxs-lookup"><span data-stu-id="1ef67-144">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="1ef67-145">Excluir uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="1ef67-145">Delete a data source</span></span>

1. <span data-ttu-id="1ef67-146">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="1ef67-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="1ef67-147">Selecione as reticências verticais ao lado da fonte de dados que você deseja remover e selecione **Excluir** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="1ef67-147">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="1ef67-148">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="1ef67-148">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]