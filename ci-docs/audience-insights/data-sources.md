---
title: Usar fontes de dados para ingerir dados
description: Saiba como importar dados de várias fontes.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 54dd7b629d4b4e7f640b932b0f9246e0602f46bd
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304682"
---
# <a name="data-sources-overview"></a><span data-ttu-id="9c06a-103">Visão geral de fontes de dados</span><span class="sxs-lookup"><span data-stu-id="9c06a-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="9c06a-104">O recurso de insights de público-alvo no Dynamics 365 Customer Insights conecta-se aos dados de um amplo conjunto de fontes.</span><span class="sxs-lookup"><span data-stu-id="9c06a-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="9c06a-105">A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*.</span><span class="sxs-lookup"><span data-stu-id="9c06a-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="9c06a-106">Depois de ingerir os dados, você pode [unificar](data-unification.md) e agir sobre eles.</span><span class="sxs-lookup"><span data-stu-id="9c06a-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="9c06a-107">Adicionar fonte de dados</span><span class="sxs-lookup"><span data-stu-id="9c06a-107">Add a data source</span></span>

<span data-ttu-id="9c06a-108">Consulte os artigos detalhados sobre como adicionar uma fonte de dados, dependendo da opção escolhida.</span><span class="sxs-lookup"><span data-stu-id="9c06a-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="9c06a-109">Você pode adicionar uma fonte de dados de três maneiras principais:</span><span class="sxs-lookup"><span data-stu-id="9c06a-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="9c06a-110">Por meio de dezenas de conectores do Power Query</span><span class="sxs-lookup"><span data-stu-id="9c06a-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="9c06a-111">De uma pasta do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="9c06a-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="9c06a-112">Do seu próprio lake do Microsoft Dataverse</span><span class="sxs-lookup"><span data-stu-id="9c06a-112">From your own Microsoft Dataverse lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="9c06a-113">Adicionar dados de fontes de dados locais</span><span class="sxs-lookup"><span data-stu-id="9c06a-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="9c06a-114">Há suporte à ingestão de dados de fontes de dados locais nos insights de público-alvo com base nos fluxos de dados do Microsoft Power Platform.</span><span class="sxs-lookup"><span data-stu-id="9c06a-114">Ingesting data from on-premises data sources in audience insights is supported based on Microsoft Power Platform dataflows.</span></span> <span data-ttu-id="9c06a-115">Os fluxos de dados podem ser habilitados no Customer Insights [fornecendo a URL do ambiente do Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) durante a configuração do ambiente.</span><span class="sxs-lookup"><span data-stu-id="9c06a-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="9c06a-116">As fontes de dados criadas após a associação de um ambiente do Dataverse com o Customer Insights usará[fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por padrão.</span><span class="sxs-lookup"><span data-stu-id="9c06a-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="9c06a-117">Os fluxos de dados oferecem suporte à conectividade local usando gateway de dados.</span><span class="sxs-lookup"><span data-stu-id="9c06a-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="9c06a-118">Remova e recrie fontes de dados que existiam antes que um ambiente do Dataverse fosse associado para [usar os gateways de dados locais](/data-integration/gateway/service-gateway-app.md).</span><span class="sxs-lookup"><span data-stu-id="9c06a-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/data-integration/gateway/service-gateway-app.md).</span></span>

<span data-ttu-id="9c06a-119">Os gateways de dados de um ambiente existente do Power BI ou do Power Apps ficará visível e você poderá reutilizá-lo no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="9c06a-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="9c06a-120">A página de fontes de dados mostra links para acessar o ambiente do Microsoft Power Platform onde você pode exibir e configurar gateways locais de dados.</span><span class="sxs-lookup"><span data-stu-id="9c06a-120">The data sources page shows links to go to the Microsoft Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="9c06a-121">Analisar dados ingeridos</span><span class="sxs-lookup"><span data-stu-id="9c06a-121">Review ingested data</span></span>

<span data-ttu-id="9c06a-122">Você verá o nome de cada fonte de dados ingeridos, seu status e a última vez em que os dados foram atualizados para essa fonte.</span><span class="sxs-lookup"><span data-stu-id="9c06a-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="9c06a-123">Você pode classificar a lista de fontes de dados por cada coluna.</span><span class="sxs-lookup"><span data-stu-id="9c06a-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="9c06a-124">![Fonte de dados adicionada](media/configure-data-datasource-added.png "Fonte de dados adicionada")</span><span class="sxs-lookup"><span data-stu-id="9c06a-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="9c06a-125">Status</span><span class="sxs-lookup"><span data-stu-id="9c06a-125">Status</span></span>  |<span data-ttu-id="9c06a-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="9c06a-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="9c06a-127">Êxito</span><span class="sxs-lookup"><span data-stu-id="9c06a-127">Successful</span></span>   |<span data-ttu-id="9c06a-128">A fonte de dados foi inserida com sucesso se um horário for mencionado na coluna **Atualizado**.</span><span class="sxs-lookup"><span data-stu-id="9c06a-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="9c06a-129">Não iniciada</span><span class="sxs-lookup"><span data-stu-id="9c06a-129">Not started</span></span>   |<span data-ttu-id="9c06a-130">A fonte de dados ainda não recebeu dados ou ainda está no modo de rascunho.</span><span class="sxs-lookup"><span data-stu-id="9c06a-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="9c06a-131">Atualizando</span><span class="sxs-lookup"><span data-stu-id="9c06a-131">Refreshing</span></span>    |<span data-ttu-id="9c06a-132">A ingestão de dados está em andamento.</span><span class="sxs-lookup"><span data-stu-id="9c06a-132">Data ingestion is in progress.</span></span> <span data-ttu-id="9c06a-133">Você pode cancelar esta operação selecionando **Interromper atualização** na coluna **Ações**.</span><span class="sxs-lookup"><span data-stu-id="9c06a-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="9c06a-134">A interrupção da atualização de uma fonte de dados a reverterá para o último estado de atualização.</span><span class="sxs-lookup"><span data-stu-id="9c06a-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="9c06a-135">Falhou</span><span class="sxs-lookup"><span data-stu-id="9c06a-135">Failed</span></span>     |<span data-ttu-id="9c06a-136">A ingestão de dados encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="9c06a-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="9c06a-137">Selecione o valor na coluna **Status** de qualquer fonte de dados para revisar mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9c06a-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="9c06a-138">No painel **Detalhes de progresso**, expanda **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="9c06a-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="9c06a-139">Selecione **Ver detalhes** para obter mais informações sobre o status de atualização, incluindo detalhes do erro e atualizações do processo downstream.</span><span class="sxs-lookup"><span data-stu-id="9c06a-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="9c06a-140">O carregamento de dados pode levar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="9c06a-140">Loading data can take time.</span></span> <span data-ttu-id="9c06a-141">Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="9c06a-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="9c06a-142">Para obter mais informações, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="9c06a-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="9c06a-143">Atualizar uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="9c06a-143">Refresh a data source</span></span>

<span data-ttu-id="9c06a-144">As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda.</span><span class="sxs-lookup"><span data-stu-id="9c06a-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="9c06a-145">Acesse **Administrador** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações agendadas de todas as fontes de dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="9c06a-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="9c06a-146">Para atualizar uma fonte de dados sob demanda, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9c06a-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="9c06a-147">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="9c06a-147">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9c06a-148">Selecione as reticências verticais ao lado da fonte de dados que você deseja atualizar e selecione **Atualizar** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="9c06a-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the dropdown list.</span></span>

3. <span data-ttu-id="9c06a-149">A fonte de dados agora é acionada para uma atualização manual.</span><span class="sxs-lookup"><span data-stu-id="9c06a-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="9c06a-150">Atualizar um fonte de dados atualizará o esquema da entidade e os dados de todas as entidades especificadas na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9c06a-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="9c06a-151">Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e que a fonte de dados seja revertida para seu último status de atualização.</span><span class="sxs-lookup"><span data-stu-id="9c06a-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="9c06a-152">Excluir uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="9c06a-152">Delete a data source</span></span>

1. <span data-ttu-id="9c06a-153">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="9c06a-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="9c06a-154">Selecione as reticências verticais ao lado da fonte de dados que você deseja remover e selecione **Excluir** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="9c06a-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the dropdown menu.</span></span>

3. <span data-ttu-id="9c06a-155">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="9c06a-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
