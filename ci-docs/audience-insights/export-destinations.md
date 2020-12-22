---
title: Destinos de exportação
description: Exporte dados e gerencie destinos de exportação.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9032d99357db86e66588eda544211a5f8eb2f23b
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643849"
---
# <a name="export-destinations-preview"></a><span data-ttu-id="b9c27-103">Destinos de exportação (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="b9c27-103">Export destinations (preview)</span></span>

<span data-ttu-id="b9c27-104">A página **Exportar destinos** mostra todos os locais para os quais você configurou para exportar dados.</span><span class="sxs-lookup"><span data-stu-id="b9c27-104">The **Export destinations** page shows you all locations you've set up to export data to.</span></span> <span data-ttu-id="b9c27-105">Você também pode adicionar novos destinos para exportação.</span><span class="sxs-lookup"><span data-stu-id="b9c27-105">You can also add new destinations for export.</span></span> <span data-ttu-id="b9c27-106">Além disso, ela mostra as opções de exportação disponíveis no momento.</span><span class="sxs-lookup"><span data-stu-id="b9c27-106">Additionally, it shows export currently available options.</span></span> <span data-ttu-id="b9c27-107">Obtenha uma visão geral rápida, descrição e descubra o que você pode fazer com cada opção de extensibilidade.</span><span class="sxs-lookup"><span data-stu-id="b9c27-107">Get a quick overview, description, and find out what you can do with each extensibility option.</span></span> <span data-ttu-id="b9c27-108">Exporte perfis, medidas e segmentos unificados para aplicativos suportados relevantes para seus negócios.</span><span class="sxs-lookup"><span data-stu-id="b9c27-108">Export unified profiles, measures, and segments to supported apps relevant for your business.</span></span>

<span data-ttu-id="b9c27-109">Vá para **Admin** > **Exportar destinos** para encontrar as seguintes opções de extensibilidade:</span><span class="sxs-lookup"><span data-stu-id="b9c27-109">Go to **Admin** > **Export destinations** to find the following extensibility options:</span></span>

- [<span data-ttu-id="b9c27-110">Complemento do Cartão do Cliente do Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="b9c27-110">Dynamics 365 Customer Card Add-in</span></span>](customer-card-add-in.md)
- [<span data-ttu-id="b9c27-111">Conector do Facebook Ads Manager</span><span class="sxs-lookup"><span data-stu-id="b9c27-111">Facebook Ads Manager connector</span></span>](export-facebook.md)
- [<span data-ttu-id="b9c27-112">Power Automateconector</span><span class="sxs-lookup"><span data-stu-id="b9c27-112">Power Automate connector</span></span>](export-power-automate.md)
- [<span data-ttu-id="b9c27-113">Power Appsconector</span><span class="sxs-lookup"><span data-stu-id="b9c27-113">Power Apps connector</span></span>](export-power-apps.md)
- [<span data-ttu-id="b9c27-114">Power BIconector</span><span class="sxs-lookup"><span data-stu-id="b9c27-114">Power BI connector</span></span>](export-power-bi.md)
- [<span data-ttu-id="b9c27-115">DotDigital</span><span class="sxs-lookup"><span data-stu-id="b9c27-115">DotDigital</span></span>](export-dotdigital.md)
- [<span data-ttu-id="b9c27-116">Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="b9c27-116">Dynamics 365 Sales</span></span>](export-dynamics365-sales.md)
- [<span data-ttu-id="b9c27-117">Dynamics 365 Marketing</span><span class="sxs-lookup"><span data-stu-id="b9c27-117">Dynamics 365 Marketing</span></span>](export-dynamics365-marketing.md)
- [<span data-ttu-id="b9c27-118">Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="b9c27-118">Azure Blob Storage</span></span>](export-azure-blob-storage.md)
- [<span data-ttu-id="b9c27-119">Conector&reg; LiveRamp</span><span class="sxs-lookup"><span data-stu-id="b9c27-119">LiveRamp&reg; connector</span></span>](export-liveramp.md)
- [<span data-ttu-id="b9c27-120">Bot para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9c27-120">Bot for Microsoft Teams</span></span>](export-teams-bot.md)
- [<span data-ttu-id="b9c27-121">Mailchimp</span><span class="sxs-lookup"><span data-stu-id="b9c27-121">Mailchimp</span></span>](export-mailchimp.md)
- [<span data-ttu-id="b9c27-122">API do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="b9c27-122">Customer Insights API</span></span>](apis.md)

## <a name="add-a-new-export-destination"></a><span data-ttu-id="b9c27-123">Adicionar um novo destino de exportação</span><span class="sxs-lookup"><span data-stu-id="b9c27-123">Add a new export destination</span></span>

<span data-ttu-id="b9c27-124">Para adicionar destinos de exportação, você tem [permissões de administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b9c27-124">To add export destinations, you have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="b9c27-125">Se você exportar para os serviços da Microsoft, assumimos que os dois serviços estão na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="b9c27-125">If you export to Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="b9c27-126">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="b9c27-126">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b9c27-127">Mude para a guia **Meus destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="b9c27-127">Switch to the **My export destinations** tab.</span></span>

1. <span data-ttu-id="b9c27-128">Selecione **Adicionar destino** para criar um novo destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="b9c27-128">Select **Add destination** to create a new export destination.</span></span>

1. <span data-ttu-id="b9c27-129">No painel **Adicionar destino**, selecione o **Tipo** de destino de exportação no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="b9c27-129">In the **Add destination** pane, select the **Type** of export destination in the drop-down.</span></span>

1. <span data-ttu-id="b9c27-130">Forneça os detalhes necessários e selecione **Avançar** para criar o destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="b9c27-130">Provide the required details and select **Next** to create the export destination.</span></span>

<span data-ttu-id="b9c27-131">Você também pode selecionar **Configurar** em um bloco na aba **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="b9c27-131">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

## <a name="view-export-destinations"></a><span data-ttu-id="b9c27-132">Exibir Destinos de exportação</span><span class="sxs-lookup"><span data-stu-id="b9c27-132">View Export destinations</span></span>

<span data-ttu-id="b9c27-133">Depois de criar destinos de exportação, você os encontrará em uma tabela na guia **Meus destinos de exportação**. Esta tabela possui três colunas:</span><span class="sxs-lookup"><span data-stu-id="b9c27-133">After creating export destinations, you'll find them in a table on the **My export destinations** tab. This table has three columns:</span></span>

- <span data-ttu-id="b9c27-134">**Nome de exibição**: o nome que você inseriu ao criar o destino.</span><span class="sxs-lookup"><span data-stu-id="b9c27-134">**Display name**: The name you entered when creating the destination.</span></span>
- <span data-ttu-id="b9c27-135">**Tipo**: o tipo de destino de exportação que você definiu ao criar o destino.</span><span class="sxs-lookup"><span data-stu-id="b9c27-135">**Type**: The export destination type you set when creating the destination.</span></span>
- <span data-ttu-id="b9c27-136">**Criado**: a data na qual você criou o destino.</span><span class="sxs-lookup"><span data-stu-id="b9c27-136">**Created**: The date you created the destination.</span></span>

## <a name="edit-an-export-destination"></a><span data-ttu-id="b9c27-137">Editar um destino de exportação</span><span class="sxs-lookup"><span data-stu-id="b9c27-137">Edit an export destination</span></span>

1. <span data-ttu-id="b9c27-138">Selecione as reticências verticais para o Destino de exportação que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="b9c27-138">Select the vertical ellipsis for the Export destination you want to edit.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b9c27-139">![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")</span><span class="sxs-lookup"><span data-stu-id="b9c27-139">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

1. <span data-ttu-id="b9c27-140">Selecione **Editar** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="b9c27-140">Select **Edit** from the dropdown menu.</span></span>

1. <span data-ttu-id="b9c27-141">Altere os valores que exigem atualização e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b9c27-141">Change the values that require update and select **Save**.</span></span>

## <a name="export-data-on-demand"></a><span data-ttu-id="b9c27-142">Exportar dados sob demanda</span><span class="sxs-lookup"><span data-stu-id="b9c27-142">Export data on demand</span></span>

<span data-ttu-id="b9c27-143">Depois de configurar um conector para um destino de exportação, as exportações serão executadas a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b9c27-143">After configuring a connector for an export destination, exports will run with every [scheduled refresh](system.md#schedule-tab).</span></span>

<span data-ttu-id="b9c27-144">Para exportar dados sem aguardar uma atualização agendada, vá para a guia **Meus destinos de exportação** em **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="b9c27-144">To export data without waiting for a scheduled refresh, go the **My export destinations** tab on **Admin** > **Export destinations**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b9c27-145">![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")</span><span class="sxs-lookup"><span data-stu-id="b9c27-145">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

- <span data-ttu-id="b9c27-146">Selecione **Exportação** acima da lista para executar a exportação para todos os destinos de exportação simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="b9c27-146">Select **Export** above the list to run the export to all export destinations simultaneously.</span></span>
- <span data-ttu-id="b9c27-147">Selecione as reticências (...) após um item da lista e escolha a opção **Exportação** para executar a exportação para um único destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="b9c27-147">Select the ellipsis (...) after a list item and then choose the **Export** option to run the export for a single export destination.</span></span>

## <a name="remove-an-export-destination"></a><span data-ttu-id="b9c27-148">Remover um Destino de exportação</span><span class="sxs-lookup"><span data-stu-id="b9c27-148">Remove an Export destination</span></span>

<span data-ttu-id="b9c27-149">Para remover um Destino de exportação, inicie da página principal **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="b9c27-149">To remove an Export destination, start from the main **Export destinations** page.</span></span>

1. <span data-ttu-id="b9c27-150">Selecione as reticências verticais para o Destino de exportação que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="b9c27-150">Select the vertical ellipsis for the Export destination you want to remove.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b9c27-151">![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")</span><span class="sxs-lookup"><span data-stu-id="b9c27-151">![Vertical ellipsis](media/export-destinations-page-ellipsis.png "Vertical ellipsis")</span></span>

2. <span data-ttu-id="b9c27-152">Selecione **Remover** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="b9c27-152">Select **Remove** from the dropdown menu.</span></span>

3. <span data-ttu-id="b9c27-153">Confirme a remoção selecionando **Remover** na tela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="b9c27-153">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>
