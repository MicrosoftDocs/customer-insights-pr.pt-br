---
title: Exportar dados do Customer Insights
description: Gerencie exportações para compartilhar dados.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016600"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="efbb2-103">Visão geral de exportações (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="efbb2-103">Exports (preview) overview</span></span>

<span data-ttu-id="efbb2-104">A página **Exportações** mostra todas as exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="efbb2-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="efbb2-105">As exportações compartilham dados específicos com vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="efbb2-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="efbb2-106">Elas podem incluir perfis ou entidades de clientes, esquemas e detalhes de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="efbb2-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="efbb2-107">Cada exportação requer uma [conexão, configurada por um administrador, para gerenciar a autenticação e o acesso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="efbb2-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="efbb2-108">Vamos para **Dados** > **Exportações** para exibir a página de exportações.</span><span class="sxs-lookup"><span data-stu-id="efbb2-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="efbb2-109">Todas as funções de usuário têm acesso para exibir exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="efbb2-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="efbb2-110">Use o campo de pesquisa na barra de comandos para localizar exportações por nome, nome de conexão ou tipo de conexão.</span><span class="sxs-lookup"><span data-stu-id="efbb2-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="efbb2-111">Configurar uma nova exportação</span><span class="sxs-lookup"><span data-stu-id="efbb2-111">Set up a new export</span></span>

<span data-ttu-id="efbb2-112">Para configurar ou editar uma exportação, você precisa ter conexões disponíveis.</span><span class="sxs-lookup"><span data-stu-id="efbb2-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="efbb2-113">As conexões dependem da sua [função de usuário](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="efbb2-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="efbb2-114">Os administradores têm acesso a todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="efbb2-114">Administrators have access to all connections.</span></span> <span data-ttu-id="efbb2-115">Eles também podem criar novas conexões ao configurar uma exportação.</span><span class="sxs-lookup"><span data-stu-id="efbb2-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="efbb2-116">Os colaboradores podem ter acesso a conexões específicas.</span><span class="sxs-lookup"><span data-stu-id="efbb2-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="efbb2-117">Eles dependem de administradores para configurar e compartilhar conexões.</span><span class="sxs-lookup"><span data-stu-id="efbb2-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="efbb2-118">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="efbb2-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="efbb2-119">Os visualizadores podem apenas exibir exportações existentes, mas não podem criá-las.</span><span class="sxs-lookup"><span data-stu-id="efbb2-119">Viewers can only view existing exports but not create them.</span></span>

1. <span data-ttu-id="efbb2-120">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="efbb2-120">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="efbb2-121">Selecione **Adicionar exportação** para criar um novo destino de exportação.</span><span class="sxs-lookup"><span data-stu-id="efbb2-121">Select **Add export** to create a new export destination.</span></span>

1. <span data-ttu-id="efbb2-122">No painel **Configurar exportação**, selecione qual conexão usar.</span><span class="sxs-lookup"><span data-stu-id="efbb2-122">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="efbb2-123">[Conexões](connections.md) são gerenciadas por administradores.</span><span class="sxs-lookup"><span data-stu-id="efbb2-123">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="efbb2-124">Forneça os detalhes necessários e selecione **Salvar** para criar a exportação.</span><span class="sxs-lookup"><span data-stu-id="efbb2-124">Provide the required details and select **Save** to create the export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="efbb2-125">Editar uma exportação</span><span class="sxs-lookup"><span data-stu-id="efbb2-125">Edit an export</span></span>

1. <span data-ttu-id="efbb2-126">Selecione as reticências verticais do destino de exportação que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="efbb2-126">Select the vertical ellipsis for the export destination you want to edit.</span></span>

1. <span data-ttu-id="efbb2-127">Selecione **Editar** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="efbb2-127">Select **Edit** from the drop-down menu.</span></span>

1. <span data-ttu-id="efbb2-128">Altere os valores que deseja atualizar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="efbb2-128">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="efbb2-129">Exibir Exportações e detalhes de exportações</span><span class="sxs-lookup"><span data-stu-id="efbb2-129">View Exports and export details</span></span>

<span data-ttu-id="efbb2-130">Depois de criar destinos de exportação, eles são listados em **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="efbb2-130">After creating export destinations, they are listed on **Data** > **Exports**.</span></span> <span data-ttu-id="efbb2-131">Todos os usuários podem ver quais dados são compartilhados e seu status mais recente.</span><span class="sxs-lookup"><span data-stu-id="efbb2-131">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="efbb2-132">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="efbb2-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="efbb2-133">Usuários sem permissões de edição selecionam **Exibir** em vez de **Editar** para ver os detalhes da exportação.</span><span class="sxs-lookup"><span data-stu-id="efbb2-133">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="efbb2-134">Este painel lateral mostra a configuração desta exportação.</span><span class="sxs-lookup"><span data-stu-id="efbb2-134">This side pane shows the set up of this export.</span></span> <span data-ttu-id="efbb2-135">Sem permissões de edição, você não pode alterar os valores.</span><span class="sxs-lookup"><span data-stu-id="efbb2-135">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="efbb2-136">Selecione **Fechar** para retornar à página de exportações.</span><span class="sxs-lookup"><span data-stu-id="efbb2-136">Select **Close** to return to the exports page.</span></span>

## <a name="run-exports-on-demand"></a><span data-ttu-id="efbb2-137">Executar exportações sob demanda</span><span class="sxs-lookup"><span data-stu-id="efbb2-137">Run exports on demand</span></span>

<span data-ttu-id="efbb2-138">Depois de configurar uma exportação, ela será executada com cada [atualização agendada](system.md#schedule-tab) desde que tenha uma conexão funcionando.</span><span class="sxs-lookup"><span data-stu-id="efbb2-138">After configuring an export, it will run with every [scheduled refresh](system.md#schedule-tab) as long as it has a working connection.</span></span>

<span data-ttu-id="efbb2-139">Para exportar dados sem esperar por uma atualização agendada, vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="efbb2-139">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span> <span data-ttu-id="efbb2-140">Você tem duas opções:</span><span class="sxs-lookup"><span data-stu-id="efbb2-140">You have two options:</span></span>

- <span data-ttu-id="efbb2-141">Para executar todas as exportações, selecione **Executar todas** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="efbb2-141">To run all exports, select **Run all** in the command bar.</span></span> 
- <span data-ttu-id="efbb2-142">Para executar uma única exportação, selecione as reticências (...) em um item da lista e escolha **Executar**.</span><span class="sxs-lookup"><span data-stu-id="efbb2-142">To run a single export, select the ellipsis (...) on a list item and then choose **Run**.</span></span>

## <a name="remove-an-export"></a><span data-ttu-id="efbb2-143">Remover uma Exportação</span><span class="sxs-lookup"><span data-stu-id="efbb2-143">Remove an Export</span></span>

1. <span data-ttu-id="efbb2-144">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="efbb2-144">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="efbb2-145">Selecione as reticências verticais da Exportação que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="efbb2-145">Select the vertical ellipsis for the Export you want to remove.</span></span>

1. <span data-ttu-id="efbb2-146">Selecione **Remover** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="efbb2-146">Select **Remove** from the dropdown menu.</span></span>

1. <span data-ttu-id="efbb2-147">Confirme a remoção selecionando **Remover** na tela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="efbb2-147">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
