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
ms.openlocfilehash: 3c0b4690e18285aa37eef481b3cfac951884ead6
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085516"
---
# <a name="data-sources-overview"></a><span data-ttu-id="d5e55-103">Visão geral de fontes de dados</span><span class="sxs-lookup"><span data-stu-id="d5e55-103">Data sources overview</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="d5e55-104">O recurso de insights de público-alvo no Dynamics 365 Customer Insights conecta-se aos dados de um amplo conjunto de fontes.</span><span class="sxs-lookup"><span data-stu-id="d5e55-104">The audience insights capability in Dynamics 365 Customer Insights connects to data from a broad set of sources.</span></span> <span data-ttu-id="d5e55-105">A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*.</span><span class="sxs-lookup"><span data-stu-id="d5e55-105">Connecting to a data source is often referred to as the process of *data ingestion*.</span></span> <span data-ttu-id="d5e55-106">Depois de ingerir os dados, você pode [unificar](data-unification.md) e agir sobre eles.</span><span class="sxs-lookup"><span data-stu-id="d5e55-106">After ingesting the data, you can [unify](data-unification.md) and take action on it.</span></span>

## <a name="add-a-data-source"></a><span data-ttu-id="d5e55-107">Adicionar fonte de dados</span><span class="sxs-lookup"><span data-stu-id="d5e55-107">Add a data source</span></span>

<span data-ttu-id="d5e55-108">Consulte os artigos detalhados sobre como adicionar uma fonte de dados, dependendo da opção escolhida.</span><span class="sxs-lookup"><span data-stu-id="d5e55-108">Refer to the detailed articles on how to add a data source, depending on which option you choose.</span></span>

<span data-ttu-id="d5e55-109">Você pode adicionar uma fonte de dados de três maneiras principais:</span><span class="sxs-lookup"><span data-stu-id="d5e55-109">You can add a data source in three main ways:</span></span>

- [<span data-ttu-id="d5e55-110">Por meio de dezenas de conectores do Power Query</span><span class="sxs-lookup"><span data-stu-id="d5e55-110">Through dozens of Power Query connectors</span></span>](connect-power-query.md)
- [<span data-ttu-id="d5e55-111">De uma pasta do Common Data Model</span><span class="sxs-lookup"><span data-stu-id="d5e55-111">From a Common Data Model folder</span></span>](connect-common-data-model.md)
- [<span data-ttu-id="d5e55-112">Do seu próprio lake do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="d5e55-112">From your own Common Data Service lake</span></span>](connect-common-data-service-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a><span data-ttu-id="d5e55-113">Adicionar dados de fontes de dados locais</span><span class="sxs-lookup"><span data-stu-id="d5e55-113">Add data from on-premises data sources</span></span>

<span data-ttu-id="d5e55-114">A ingestão de dados de fontes de dados locais no Audience Insights tem suporte com base nos fluxos de dados do Power Platform.</span><span class="sxs-lookup"><span data-stu-id="d5e55-114">Ingesting data from on-premises data sources in Audience Insights is supported based on Power Platform dataflows.</span></span> <span data-ttu-id="d5e55-115">Os fluxos de dados podem ser habilitados no Customer Insights [fornecendo a URL do ambiente do Microsoft Dataverse](manage-environments.md#create-an-environment-in-an-existing-organization) durante a configuração do ambiente.</span><span class="sxs-lookup"><span data-stu-id="d5e55-115">Dataflows can be enabled in Customer Insights by [providing the Microsoft Dataverse environment URL](manage-environments.md#create-an-environment-in-an-existing-organization) when setting up the environment.</span></span>

<span data-ttu-id="d5e55-116">As fontes de dados criadas após a associação de um ambiente do Dataverse com o Customer Insights usará[fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por padrão.</span><span class="sxs-lookup"><span data-stu-id="d5e55-116">Data sources that are created after associating a Dataverse environment with Customer Insights will use [Power Platform dataflows](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) by default.</span></span> <span data-ttu-id="d5e55-117">Os fluxos de dados oferecem suporte à conectividade local usando gateway de dados.</span><span class="sxs-lookup"><span data-stu-id="d5e55-117">Dataflows support on-premises connectivity using the data gateway.</span></span> <span data-ttu-id="d5e55-118">Remova e recrie fontes de dados que existiam antes que um ambiente do Dataverse fosse associado para [usar os gateways de dados locais](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span><span class="sxs-lookup"><span data-stu-id="d5e55-118">Remove and recreate data sources that existed before a Dataverse environment was associated to [use the on-premises data gateways](/powerapps/maker/data-platform/using-dataflows-with-on-premises-data.md).</span></span>

<span data-ttu-id="d5e55-119">Os gateways de dados de um ambiente existente do Power BI ou do Power Apps ficará visível e você poderá reutilizá-lo no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d5e55-119">Data gateways from an existing Power BI or Power Apps environment will be visible and you can reuse in Customer Insights.</span></span> <span data-ttu-id="d5e55-120">A página de fontes de dados mostra links para acessar o ambiente do Power Platform, onde você pode exibir e configurar gateways de dados locais.</span><span class="sxs-lookup"><span data-stu-id="d5e55-120">The data sources page shows links to go the Power Platform environment where you can view and configure on-premises data gateways.</span></span>

## <a name="review-ingested-data"></a><span data-ttu-id="d5e55-121">Analisar dados ingeridos</span><span class="sxs-lookup"><span data-stu-id="d5e55-121">Review ingested data</span></span>

<span data-ttu-id="d5e55-122">Você verá o nome de cada fonte de dados ingeridos, seu status e a última vez em que os dados foram atualizados para essa fonte.</span><span class="sxs-lookup"><span data-stu-id="d5e55-122">You'll see the name of each ingested data source, its status, and the last time the data was refreshed for that source.</span></span> <span data-ttu-id="d5e55-123">Você pode classificar a lista de fontes de dados por cada coluna.</span><span class="sxs-lookup"><span data-stu-id="d5e55-123">You can sort the list of data sources by every column.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="d5e55-124">![Fonte de dados adicionada](media/configure-data-datasource-added.png "Fonte de dados adicionada")</span><span class="sxs-lookup"><span data-stu-id="d5e55-124">![Data source added](media/configure-data-datasource-added.png "Data source added")</span></span>

|<span data-ttu-id="d5e55-125">Status</span><span class="sxs-lookup"><span data-stu-id="d5e55-125">Status</span></span>  |<span data-ttu-id="d5e55-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="d5e55-126">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="d5e55-127">Êxito</span><span class="sxs-lookup"><span data-stu-id="d5e55-127">Successful</span></span>   |<span data-ttu-id="d5e55-128">A fonte de dados foi inserida com sucesso se um horário for mencionado na coluna **Atualizado**.</span><span class="sxs-lookup"><span data-stu-id="d5e55-128">Data source was successfully ingested if a time is mentioned in the **Refreshed** column.</span></span>
|<span data-ttu-id="d5e55-129">Não iniciada</span><span class="sxs-lookup"><span data-stu-id="d5e55-129">Not started</span></span>   |<span data-ttu-id="d5e55-130">A fonte de dados ainda não recebeu dados ou ainda está no modo de rascunho.</span><span class="sxs-lookup"><span data-stu-id="d5e55-130">The data source has no data ingested yet or still in draft mode.</span></span>         |
|<span data-ttu-id="d5e55-131">Atualizando</span><span class="sxs-lookup"><span data-stu-id="d5e55-131">Refreshing</span></span>    |<span data-ttu-id="d5e55-132">A ingestão de dados está em andamento.</span><span class="sxs-lookup"><span data-stu-id="d5e55-132">Data ingestion is in progress.</span></span> <span data-ttu-id="d5e55-133">Você pode cancelar esta operação selecionando **Interromper atualização** na coluna **Ações**.</span><span class="sxs-lookup"><span data-stu-id="d5e55-133">You can cancel this operation by selecting **Stop refreshing** in the **Actions** column.</span></span> <span data-ttu-id="d5e55-134">A interrupção da atualização de uma fonte de dados a reverterá para o último estado de atualização.</span><span class="sxs-lookup"><span data-stu-id="d5e55-134">Stopping the refresh of a data source will revert it to its last refresh state.</span></span>       |
|<span data-ttu-id="d5e55-135">Falhou</span><span class="sxs-lookup"><span data-stu-id="d5e55-135">Failed</span></span>     |<span data-ttu-id="d5e55-136">A ingestão de dados encontrou erros.</span><span class="sxs-lookup"><span data-stu-id="d5e55-136">Data ingestion ran into errors.</span></span>         |

<span data-ttu-id="d5e55-137">Selecione o valor na coluna **Status** de qualquer fonte de dados para revisar mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d5e55-137">Select the value in the **Status** column of any data source to review more details.</span></span> <span data-ttu-id="d5e55-138">No painel **Detalhes de progresso**, expanda **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="d5e55-138">In the **Progress details** pane, expand **Data sources**.</span></span> <span data-ttu-id="d5e55-139">Selecione **Ver detalhes** para obter mais informações sobre o status de atualização, incluindo detalhes do erro e atualizações do processo downstream.</span><span class="sxs-lookup"><span data-stu-id="d5e55-139">Select **See details** for more information about the refresh status, including error details and downstream process updates.</span></span>

<span data-ttu-id="d5e55-140">O carregamento de dados pode demorar algum tempo.</span><span class="sxs-lookup"><span data-stu-id="d5e55-140">Loading data can take some time.</span></span> <span data-ttu-id="d5e55-141">Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="d5e55-141">After a successful refresh, the ingested data can be reviewed from the **Entities** page.</span></span> <span data-ttu-id="d5e55-142">Para obter mais informações, consulte [Entidades](entities.md).</span><span class="sxs-lookup"><span data-stu-id="d5e55-142">For more information, see [Entities](entities.md).</span></span>

## <a name="refresh-a-data-source"></a><span data-ttu-id="d5e55-143">Atualizar uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="d5e55-143">Refresh a data source</span></span>

<span data-ttu-id="d5e55-144">As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda.</span><span class="sxs-lookup"><span data-stu-id="d5e55-144">Data sources can be refreshed on an automatic schedule or refreshed manually on demand.</span></span> 

<span data-ttu-id="d5e55-145">Acesse **Administrador** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações agendadas de todas as fontes de dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="d5e55-145">Go to **Admin** > **System** > [**Schedule**](system.md#schedule-tab) to configure scheduled refreshes of all your ingested data sources.</span></span>

<span data-ttu-id="d5e55-146">Para atualizar uma fonte de dados sob demanda, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d5e55-146">To refresh a data source on demand, follow these steps:</span></span>

1. <span data-ttu-id="d5e55-147">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="d5e55-147">In audience insights, go to **Data** > **Data sources**</span></span>

2. <span data-ttu-id="d5e55-148">Selecione as reticências verticais ao lado da fonte de dados que deseja atualizar e selecione **Atualizar** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="d5e55-148">Select the vertical ellipsis next to the data source you want to refresh and select **Refresh** from the drop-down list.</span></span>

3. <span data-ttu-id="d5e55-149">A fonte de dados agora é acionada para uma atualização manual.</span><span class="sxs-lookup"><span data-stu-id="d5e55-149">The data source is now triggered for a manual refresh.</span></span> <span data-ttu-id="d5e55-150">Atualizar um fonte de dados atualizará o esquema da entidade e os dados de todas as entidades especificadas na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d5e55-150">Refreshing a data source will update both the entity schema and data for all the entities specified in the data source.</span></span>

4. <span data-ttu-id="d5e55-151">Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e que a fonte de dados seja revertida para seu último status de atualização.</span><span class="sxs-lookup"><span data-stu-id="d5e55-151">Select **Stop refreshing** if you want to cancel an existing refresh and the data source will revert to its last refresh status.</span></span>

## <a name="delete-a-data-source"></a><span data-ttu-id="d5e55-152">Excluir uma fonte de dados</span><span class="sxs-lookup"><span data-stu-id="d5e55-152">Delete a data source</span></span>

1. <span data-ttu-id="d5e55-153">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="d5e55-153">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="d5e55-154">Selecione as reticências verticais ao lado da fonte de dados que você deseja remover e selecione **Excluir** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="d5e55-154">Select the vertical ellipsis next to the data source you want to remove and select **Delete** from the drop-down menu.</span></span>

3. <span data-ttu-id="d5e55-155">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="d5e55-155">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
