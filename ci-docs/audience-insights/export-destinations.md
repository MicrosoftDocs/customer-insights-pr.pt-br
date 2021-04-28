---
title: Exportar dados do Customer Insights
description: Gerencie exportações para compartilhar dados.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 354ce9ef30fe918975d06290430996c84f8bd3f7
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896129"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="adfdd-103">Visão geral de exportações (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="adfdd-103">Exports (preview) overview</span></span>

<span data-ttu-id="adfdd-104">A página **Exportações** mostra todas as exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="adfdd-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="adfdd-105">As exportações compartilham dados específicos com vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="adfdd-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="adfdd-106">Elas podem incluir perfis ou entidades de clientes, esquemas e detalhes de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="adfdd-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="adfdd-107">Cada exportação requer uma [conexão, configurada por um administrador, para gerenciar a autenticação e o acesso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="adfdd-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

> [!NOTE]
> <span data-ttu-id="adfdd-108">Até março de 2021, as exportações criavam uma conexão com o serviço correspondente automaticamente.</span><span class="sxs-lookup"><span data-stu-id="adfdd-108">Until March 2021, exports created a connection to the corresponding service automatically.</span></span> <span data-ttu-id="adfdd-109">As exportações agora exigem uma [conexão, criada e compartilhada por um administrador](connections.md) para que você possa criá-las.</span><span class="sxs-lookup"><span data-stu-id="adfdd-109">Exports now require a [connection, created and shared by an administrator](connections.md) before you can create them.</span></span>

<span data-ttu-id="adfdd-110">Vamos para **Dados** > **Exportações** para exibir a página de exportações.</span><span class="sxs-lookup"><span data-stu-id="adfdd-110">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="adfdd-111">Todas as funções de usuário têm acesso para exibir exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="adfdd-111">All user roles have access to view configured exports.</span></span> <span data-ttu-id="adfdd-112">Use o campo de pesquisa na barra de comandos para localizar exportações por nome, nome de conexão ou tipo de conexão.</span><span class="sxs-lookup"><span data-stu-id="adfdd-112">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="adfdd-113">Configurar uma nova exportação</span><span class="sxs-lookup"><span data-stu-id="adfdd-113">Set up a new export</span></span>

<span data-ttu-id="adfdd-114">Para configurar ou editar uma exportação, você precisa ter conexões disponíveis.</span><span class="sxs-lookup"><span data-stu-id="adfdd-114">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="adfdd-115">As conexões dependem da sua [função de usuário](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="adfdd-115">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="adfdd-116">Os administradores têm acesso a todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="adfdd-116">Administrators have access to all connections.</span></span> <span data-ttu-id="adfdd-117">Eles também podem criar novas conexões ao configurar uma exportação.</span><span class="sxs-lookup"><span data-stu-id="adfdd-117">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="adfdd-118">Os colaboradores podem ter acesso a conexões específicas.</span><span class="sxs-lookup"><span data-stu-id="adfdd-118">Contributors can have access to specific connections.</span></span> <span data-ttu-id="adfdd-119">Eles dependem de administradores para configurar e compartilhar conexões.</span><span class="sxs-lookup"><span data-stu-id="adfdd-119">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="adfdd-120">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="adfdd-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="adfdd-121">Os visualizadores podem apenas exibir exportações existentes, mas não podem criá-las.</span><span class="sxs-lookup"><span data-stu-id="adfdd-121">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="adfdd-122">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="adfdd-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="adfdd-123">Selecione **Adicionar exportação** para criar um novo destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="adfdd-123">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="adfdd-124">No painel **Configurar exportação**, selecione qual conexão usar.</span><span class="sxs-lookup"><span data-stu-id="adfdd-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="adfdd-125">[Conexões](connections.md) são gerenciadas por administradores.</span><span class="sxs-lookup"><span data-stu-id="adfdd-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="adfdd-126">Forneça os detalhes necessários e selecione **Salvar** para criar a exportação.</span><span class="sxs-lookup"><span data-stu-id="adfdd-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="adfdd-127">Editar uma exportação</span><span class="sxs-lookup"><span data-stu-id="adfdd-127">Edit an export</span></span>

1. <span data-ttu-id="adfdd-128">Selecione as reticências verticais do destino de exportação que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="adfdd-128">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="adfdd-129">Selecione **Editar** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="adfdd-129">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="adfdd-130">Altere os valores que deseja atualizar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="adfdd-130">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="adfdd-131">Exibir Exportações e detalhes de exportações</span><span class="sxs-lookup"><span data-stu-id="adfdd-131">View Exports and export details</span></span>

<span data-ttu-id="adfdd-132">Depois de criar destinos de exportação, eles são listados em **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="adfdd-132">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="adfdd-133">Todos os usuários podem ver quais dados são compartilhados e seu status mais recente.</span><span class="sxs-lookup"><span data-stu-id="adfdd-133">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="adfdd-134">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="adfdd-134">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="adfdd-135">Usuários sem permissões de edição selecionam **Exibir** em vez de **Editar** para ver os detalhes da exportação.</span><span class="sxs-lookup"><span data-stu-id="adfdd-135">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="adfdd-136">Este painel lateral mostra a configuração desta exportação.</span><span class="sxs-lookup"><span data-stu-id="adfdd-136">This side pane shows the set up of this export.</span></span> <span data-ttu-id="adfdd-137">Sem permissões de edição, você não pode alterar os valores.</span><span class="sxs-lookup"><span data-stu-id="adfdd-137">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="adfdd-138">Selecione **Fechar** para retornar à página de exportações.</span><span class="sxs-lookup"><span data-stu-id="adfdd-138">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="adfdd-139">Executar exportações sob demanda</span><span class="sxs-lookup"><span data-stu-id="adfdd-139">Run exports on demand</span></span>

<span data-ttu-id="adfdd-140">Depois de configurar uma exportação, ela será executada com cada [atualização agendada](system.md#schedule-tab) desde que tenha uma conexão funcionando.</span><span class="sxs-lookup"><span data-stu-id="adfdd-140">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="adfdd-141">Para exportar dados sem esperar por uma atualização agendada, vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="adfdd-141">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="adfdd-142">Você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="adfdd-142">You have two options:</span></span>

- <span data-ttu-id="adfdd-143">Para executar todas as exportações, selecione **Executar todas** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="adfdd-143">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="adfdd-144">Para executar uma única exportação, selecione as reticências (...) em um item da lista e escolha **Executar**.</span><span class="sxs-lookup"><span data-stu-id="adfdd-144">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="adfdd-145">Remover uma Exportação</span><span class="sxs-lookup"><span data-stu-id="adfdd-145">Remove an Export</span></span>

1. <span data-ttu-id="adfdd-146">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="adfdd-146">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="adfdd-147">Selecione as reticências verticais da Exportação que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="adfdd-147">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="adfdd-148">Selecione **Remover** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="adfdd-148">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="adfdd-149">Confirme a remoção selecionando **Remover** na tela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="adfdd-149">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
