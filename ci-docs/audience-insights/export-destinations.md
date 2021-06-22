---
title: Exportar dados do Customer Insights
description: Gerencie exportações para compartilhar dados.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6e7793fa99f8431d9d420529b39e0b5b5dbf6748
ms.sourcegitcommit: 0689e7ed4265855d1f76745d68af390f8f4af8a0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6253026"
---
# <a name="exports-preview-overview"></a><span data-ttu-id="c0841-103">Visão geral de exportações (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="c0841-103">Exports (preview) overview</span></span>

<span data-ttu-id="c0841-104">A página **Exportações** mostra todas as exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="c0841-104">The **Exports** page shows you all configured exports.</span></span> <span data-ttu-id="c0841-105">As exportações compartilham dados específicos com vários aplicativos.</span><span class="sxs-lookup"><span data-stu-id="c0841-105">Exports share specific data with various applications.</span></span> <span data-ttu-id="c0841-106">Elas podem incluir perfis ou entidades de clientes, esquemas e detalhes de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c0841-106">They can include customer profiles or entities, schemas, and mapping details.</span></span> <span data-ttu-id="c0841-107">Cada exportação requer uma [conexão, configurada por um administrador, para gerenciar a autenticação e o acesso](connections.md).</span><span class="sxs-lookup"><span data-stu-id="c0841-107">Each export requires a [connection, set up by an administrator, to manage authentication and access](connections.md).</span></span>

<span data-ttu-id="c0841-108">Vamos para **Dados** > **Exportações** para exibir a página de exportações.</span><span class="sxs-lookup"><span data-stu-id="c0841-108">Go to **Data** > **Exports** to view the exports page.</span></span> <span data-ttu-id="c0841-109">Todas as funções de usuário têm acesso para exibir exportações configuradas.</span><span class="sxs-lookup"><span data-stu-id="c0841-109">All user roles have access to view configured exports.</span></span> <span data-ttu-id="c0841-110">Use o campo de pesquisa na barra de comandos para localizar exportações por nome, nome de conexão ou tipo de conexão.</span><span class="sxs-lookup"><span data-stu-id="c0841-110">Use of the search field in the command bar to find exports by their name, connection name, or connection type.</span></span>

## <a name="set-up-a-new-export"></a><span data-ttu-id="c0841-111">Configurar uma nova exportação</span><span class="sxs-lookup"><span data-stu-id="c0841-111">Set up a new export</span></span>

<span data-ttu-id="c0841-112">Para configurar ou editar uma exportação, você precisa ter conexões disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c0841-112">To set up or edit an export, you need to have connections available to you.</span></span> <span data-ttu-id="c0841-113">As conexões dependem da sua [função de usuário](permissions.md):</span><span class="sxs-lookup"><span data-stu-id="c0841-113">Connections depend on your [user role](permissions.md):</span></span>
- <span data-ttu-id="c0841-114">Os administradores têm acesso a todas as conexões.</span><span class="sxs-lookup"><span data-stu-id="c0841-114">Administrators have access to all connections.</span></span> <span data-ttu-id="c0841-115">Eles também podem criar novas conexões ao configurar uma exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-115">They can also create new connections when setting up an export.</span></span>
- <span data-ttu-id="c0841-116">Os colaboradores podem ter acesso a conexões específicas.</span><span class="sxs-lookup"><span data-stu-id="c0841-116">Contributors can have access to specific connections.</span></span> <span data-ttu-id="c0841-117">Eles dependem de administradores para configurar e compartilhar conexões.</span><span class="sxs-lookup"><span data-stu-id="c0841-117">They depend on administrators to configure and share connections.</span></span> <span data-ttu-id="c0841-118">A lista de exportações mostra aos colaboradores se eles podem editar ou somente visualizar uma exportação na coluna **Suas permissões**.</span><span class="sxs-lookup"><span data-stu-id="c0841-118">The exports list shows contributors whether they can edit or only view an export in the **Your permissions** column.</span></span> <span data-ttu-id="c0841-119">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="c0841-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>
- <span data-ttu-id="c0841-120">Os visualizadores podem apenas exibir exportações existentes, mas não podem criá-las.</span><span class="sxs-lookup"><span data-stu-id="c0841-120">Viewers can only view existing exports but not create them.</span></span>

### <a name="define-a-new-export"></a><span data-ttu-id="c0841-121">Definir uma nova exportação</span><span class="sxs-lookup"><span data-stu-id="c0841-121">Define a new export</span></span>

1. <span data-ttu-id="c0841-122">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c0841-122">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c0841-123">Selecione **Adicionar exportação** para criar uma exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-123">Select **Add export** to create a new export.</span></span>

1. <span data-ttu-id="c0841-124">No painel **Configurar exportação**, selecione qual conexão usar.</span><span class="sxs-lookup"><span data-stu-id="c0841-124">In the **Set up export** pane, select which connection to use.</span></span> <span data-ttu-id="c0841-125">[Conexões](connections.md) são gerenciadas por administradores.</span><span class="sxs-lookup"><span data-stu-id="c0841-125">[Connections](connections.md) are managed by administrators.</span></span> 

1. <span data-ttu-id="c0841-126">Forneça os detalhes necessários e selecione **Salvar** para criar a exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-126">Provide the required details and select **Save** to create the export.</span></span>

### <a name="define-a-new-export-based-on-an-existing-export"></a><span data-ttu-id="c0841-127">Definir uma nova exportação com base em uma exportação existente</span><span class="sxs-lookup"><span data-stu-id="c0841-127">Define a new export based on an existing export</span></span>

1. <span data-ttu-id="c0841-128">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c0841-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c0841-129">Na lista de exportações, selecione a exportação que deseja duplicar.</span><span class="sxs-lookup"><span data-stu-id="c0841-129">In the list of exports, select the export you want to duplicate.</span></span>

1. <span data-ttu-id="c0841-130">Selecione **Criar duplicata** na barra de comando para abrir o painel **Configurar exportação** com os detalhes da exportação selecionada.</span><span class="sxs-lookup"><span data-stu-id="c0841-130">Select **Create duplicate** in the command bar to open the **Set up export** pane with the details of the selected export.</span></span>

1. <span data-ttu-id="c0841-131">Examine e adapte a exportação e selecione **Salvar** para criar a exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-131">Review and adapt the export and select **Save** to create a new export.</span></span>

### <a name="edit-an-export"></a><span data-ttu-id="c0841-132">Editar uma exportação</span><span class="sxs-lookup"><span data-stu-id="c0841-132">Edit an export</span></span>

1. <span data-ttu-id="c0841-133">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c0841-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c0841-134">Na lista de exportações, selecione a exportação que deseja editar.</span><span class="sxs-lookup"><span data-stu-id="c0841-134">In the list of exports, select the export you want to edit.</span></span>

1. <span data-ttu-id="c0841-135">Selecione **Editar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="c0841-135">Select **Edit** in the command bar.</span></span>

1. <span data-ttu-id="c0841-136">Altere os valores que deseja atualizar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c0841-136">Change the values you want to update and select **Save**.</span></span>

## <a name="view-exports-and-export-details"></a><span data-ttu-id="c0841-137">Exibir exportações e detalhes de exportações</span><span class="sxs-lookup"><span data-stu-id="c0841-137">View exports and export details</span></span>

<span data-ttu-id="c0841-138">Depois que criar os destinos de exportação, eles serão listados em **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c0841-138">After creating export destinations, they're listed on **Data** > **Exports**.</span></span> <span data-ttu-id="c0841-139">Todos os usuários podem ver quais dados são compartilhados e seu status mais recente.</span><span class="sxs-lookup"><span data-stu-id="c0841-139">All users can see which data is shared and its latest status.</span></span>

1. <span data-ttu-id="c0841-140">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c0841-140">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c0841-141">Usuários sem permissões de edição selecionam **Exibir** em vez de **Editar** para ver os detalhes da exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-141">Users without edit permissions select **View** instead of **Edit** see the export details.</span></span>

1. <span data-ttu-id="c0841-142">O painel lateral mostra a configuração de uma exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-142">The side pane shows the configuration of an export.</span></span> <span data-ttu-id="c0841-143">Sem permissões de edição, você não pode alterar os valores.</span><span class="sxs-lookup"><span data-stu-id="c0841-143">Without edit permissions, you can't change values.</span></span> <span data-ttu-id="c0841-144">Selecione **Fechar** para retornar à página de exportações.</span><span class="sxs-lookup"><span data-stu-id="c0841-144">Select **Close** to return to the exports page.</span></span>

## <a name="schedule-and-run-exports"></a><span data-ttu-id="c0841-145">Agendar e executar exportações</span><span class="sxs-lookup"><span data-stu-id="c0841-145">Schedule and run exports</span></span>

<span data-ttu-id="c0841-146">Cada exportação que você configura tem uma agenda de atualizações.</span><span class="sxs-lookup"><span data-stu-id="c0841-146">Each export you configure has a refresh schedule.</span></span> <span data-ttu-id="c0841-147">Durante uma atualização, o sistema procura dados novos ou atualizados para incluir em uma exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-147">During a refresh, the system looks for new or updated data to include in an export.</span></span> <span data-ttu-id="c0841-148">Por padrão, as exportações são executadas como parte de cada [atualização agendada do sistema](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="c0841-148">By default, exports are run as part of every [scheduled system refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="c0841-149">Você pode personalizar a agenda de atualização ou desativá-la para executar as exportações manualmente.</span><span class="sxs-lookup"><span data-stu-id="c0841-149">You can customize the refresh schedule or turn it off to run exports manually.</span></span>

<span data-ttu-id="c0841-150">As agendas de exportação dependem do estado do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="c0841-150">Export schedules depend on the state of your environment.</span></span> <span data-ttu-id="c0841-151">Se houver atualizações nas [dependências](system.md#refresh-policies) em andamento no momento em que uma exportação agendada deve começar, o sistema primeiro concluirá as dependências e, em seguida, executará a exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-151">If there are updates on [dependencies](system.md#refresh-policies) in progress when a scheduled export should start, the system will first complete the dependencies and then run the export.</span></span> <span data-ttu-id="c0841-152">Você pode ver quando uma exportação foi atualizada pela última vez na coluna **Atualizada**.</span><span class="sxs-lookup"><span data-stu-id="c0841-152">You can see when an export was last refreshed in column **Refreshed**.</span></span>

### <a name="schedule-exports"></a><span data-ttu-id="c0841-153">Agenda exportações</span><span class="sxs-lookup"><span data-stu-id="c0841-153">Schedule exports</span></span>

<span data-ttu-id="c0841-154">Você pode definir agendas de atualização personalizadas para exportações individuais ou várias exportações de uma vez.</span><span class="sxs-lookup"><span data-stu-id="c0841-154">You can define custom refresh schedules for individual exports or several exports at once.</span></span> <span data-ttu-id="c0841-155">A agenda definida atualmente está listada na coluna **Agenda** da lista de exportação.</span><span class="sxs-lookup"><span data-stu-id="c0841-155">The currently defined schedule is listed in the **Schedule** column of the export list.</span></span> <span data-ttu-id="c0841-156">A permissão para alterar a agenda é a mesma que para [editar e definir exportações](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="c0841-156">The permission to change the schedule is the same as for [editing and defining exports](export-destinations.md#set-up-a-new-export).</span></span> 

1. <span data-ttu-id="c0841-157">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c0841-157">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c0841-158">Selecione a exportação que você quer agendar.</span><span class="sxs-lookup"><span data-stu-id="c0841-158">Select the export you want to schedule.</span></span>

1. <span data-ttu-id="c0841-159">Selecione **Agendar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="c0841-159">Select **Schedule** in the command bar.</span></span>

1. <span data-ttu-id="c0841-160">No painel **Agendar exportação**, defina a opção **Execução da agenda** como **Ativado** para executar a exportação automaticamente.</span><span class="sxs-lookup"><span data-stu-id="c0841-160">In the **Schedule export** pane, set the **Schedule run** to **On** to run the export automatically.</span></span> <span data-ttu-id="c0841-161">Defina-o como **Desativado** para fazer a atualização manualmente.</span><span class="sxs-lookup"><span data-stu-id="c0841-161">Set it to **Off** to refresh it manually.</span></span>

1. <span data-ttu-id="c0841-162">Para exportações atualizadas automaticamente, escolha um valor de **Recorrência** e especifique os detalhes para ele.</span><span class="sxs-lookup"><span data-stu-id="c0841-162">For automatically refreshed exports, choose a **Recurrence** value and specify the details for it.</span></span> <span data-ttu-id="c0841-163">O tempo definido se aplicará a todas as instâncias de recorrência.</span><span class="sxs-lookup"><span data-stu-id="c0841-163">The time defined applies to all instances of a recurrence.</span></span> <span data-ttu-id="c0841-164">É o momento em que uma exportação deve começar a ser atualizada.</span><span class="sxs-lookup"><span data-stu-id="c0841-164">It's the time when an export should start refreshing.</span></span>

1. <span data-ttu-id="c0841-165">Aplique e ative suas alterações selecionando **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="c0841-165">Apply and activate your changes by selecting **Save**.</span></span>

<span data-ttu-id="c0841-166">Ao editar a agenda para várias exportações, você deve fazer uma seleção em **Manter ou substituir agendas**:</span><span class="sxs-lookup"><span data-stu-id="c0841-166">When editing the schedule for several exports, you need to make a selection under **Keep or override schedules**:</span></span>
- <span data-ttu-id="c0841-167">**Manter agendas individuais**: persiste a agenda previamente definida para as exportações selecionadas e somente as habilita ou desabilita.</span><span class="sxs-lookup"><span data-stu-id="c0841-167">**Keep individual schedules**: Persist the previously defined schedule for the selected exports and only disable or enable them.</span></span>
- <span data-ttu-id="c0841-168">**Definir uma nova agenda para todas as exportações selecionadas**: substitua as agendas existentes das exportações selecionadas.</span><span class="sxs-lookup"><span data-stu-id="c0841-168">**Define new schedule for all selected exports**: Override the existing schedules of the selected exports.</span></span>

### <a name="run-exports-on-demand"></a><span data-ttu-id="c0841-169">Executar exportações sob demanda</span><span class="sxs-lookup"><span data-stu-id="c0841-169">Run exports on demand</span></span>

<span data-ttu-id="c0841-170">Para exportar dados sem esperar por uma atualização agendada, vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c0841-170">To export data without waiting for a scheduled refresh, go to **Data** > **Exports**.</span></span>

- <span data-ttu-id="c0841-171">Para executar todas as exportações, selecione **Executar todas** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="c0841-171">To run all exports, select **Run all** in the command bar.</span></span> <span data-ttu-id="c0841-172">Esta ação executará somente as exportações que tenham uma agenda ativa.</span><span class="sxs-lookup"><span data-stu-id="c0841-172">This action will only run exports that have an active schedule.</span></span>
- <span data-ttu-id="c0841-173">Para executar uma única exportação, selecione-a na lista e, em seguida, selecione **Executar** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="c0841-173">To run a single export, select it in the list and select **Run** in the command bar.</span></span> <span data-ttu-id="c0841-174">É assim que as exportações sem agenda ativa são executadas.</span><span class="sxs-lookup"><span data-stu-id="c0841-174">That's how you run exports with no active schedule.</span></span> 

## <a name="remove-an-export"></a><span data-ttu-id="c0841-175">Remover uma Exportação</span><span class="sxs-lookup"><span data-stu-id="c0841-175">Remove an Export</span></span>

1. <span data-ttu-id="c0841-176">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="c0841-176">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="c0841-177">Selecione a exportação que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="c0841-177">Select the export you want to remove.</span></span>

1. <span data-ttu-id="c0841-178">Selecione **Remover** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="c0841-178">Select **Remove** in the command bar.</span></span>

1. <span data-ttu-id="c0841-179">Confirme a remoção selecionando **Remover** na tela de confirmação.</span><span class="sxs-lookup"><span data-stu-id="c0841-179">Confirm the removal by selecting **Remove** on the confirmation screen.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
