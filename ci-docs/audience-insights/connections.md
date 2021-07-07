---
title: Conexões com outros serviços do Customer Insights.
description: Compartilhe dados com outros serviços.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 17e04b243e9b3d4375c86f5a890a18be35956835
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304958"
---
# <a name="connections-preview-overview"></a><span data-ttu-id="f4a84-103">Visão geral de conexões (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="f4a84-103">Connections (preview) overview</span></span>

<span data-ttu-id="f4a84-104">As conexões são a chave para permitir o compartilhamento de dados do Customer Insights e com o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f4a84-104">Connections are the key to enable data sharing to and from Customer Insights.</span></span> <span data-ttu-id="f4a84-105">Cada conexão estabelece o compartilhamento de dados com um serviço específico.</span><span class="sxs-lookup"><span data-stu-id="f4a84-105">Each connection establishes data sharing with a specific service.</span></span> <span data-ttu-id="f4a84-106">As conexões são a base para [configurar enriquecimentos de terceiros](enrichment-hub.md) e [configurar exportações](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f4a84-106">Connections are the foundation to [configure third-party enrichments](enrichment-hub.md) and [configure exports](export-destinations.md).</span></span> <span data-ttu-id="f4a84-107">A mesma conexão pode ser usada várias vezes.</span><span class="sxs-lookup"><span data-stu-id="f4a84-107">The same connection can be used multiple times.</span></span> <span data-ttu-id="f4a84-108">Por exemplo, uma conexão com o Dynamics 365 Marketing funciona para várias exportações e uma conexão da Leadspace pode ser usada para vários enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="f4a84-108">For example, one connection to Dynamics 365 Marketing works for multiple exports and one Leadspace connection can be used for several enrichments.</span></span>

<span data-ttu-id="f4a84-109">Acesse **Administração** > **Conexões** para criar e visualizar conexões.</span><span class="sxs-lookup"><span data-stu-id="f4a84-109">Go to **Admin** > **Connections** to create and view connections.</span></span>

<span data-ttu-id="f4a84-110">A guia **Conexões** mostra todas as conexões ativas.</span><span class="sxs-lookup"><span data-stu-id="f4a84-110">The **Connections** tab shows you all active connections.</span></span> <span data-ttu-id="f4a84-111">A lista mostra uma linha para cada conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-111">The list shows a row for each connection.</span></span> 

<span data-ttu-id="f4a84-112">Obtenha uma rápida visão geral, uma descrição e descubra o que você pode fazer com cada opção de extensibilidade na guia **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-112">Get a quick overview, description, and find out what you can do with each extensibility option on the **Discover** tab.</span></span>

### <a name="exports"></a><span data-ttu-id="f4a84-113">Exportações</span><span class="sxs-lookup"><span data-stu-id="f4a84-113">Exports</span></span>

<span data-ttu-id="f4a84-114">Somente os administradores podem configurar novas conexões, mas eles podem conceder acesso aos colaboradores para usarem as conexões existentes.</span><span class="sxs-lookup"><span data-stu-id="f4a84-114">Only administrators can configure new connections but they can grant access to contributors to use existing connections.</span></span> <span data-ttu-id="f4a84-115">Os administradores controlam para onde os dados podem ir, os colaboradores definem o conteúdo e a frequência de acordo com suas necessidades.</span><span class="sxs-lookup"><span data-stu-id="f4a84-115">Administrators control where data can go, contributors define the payload and frequency fitting their needs.</span></span> <span data-ttu-id="f4a84-116">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f4a84-116">For more information, see [Allow contributors to use a connection for exports](#allow-contributors-to-use-a-connection-for-exports).</span></span>

### <a name="enrichments"></a><span data-ttu-id="f4a84-117">Enriquecimentos</span><span class="sxs-lookup"><span data-stu-id="f4a84-117">Enrichments</span></span>

<span data-ttu-id="f4a84-118">Somente os administradores podem configurar novas conexões, mas as conexões criadas estão sempre disponíveis para os administradores e os colaboradores.</span><span class="sxs-lookup"><span data-stu-id="f4a84-118">Only administrators can configure new connections but the created connections are always available to both administrators and contributors.</span></span> <span data-ttu-id="f4a84-119">Os administradores gerenciam credenciais e fornecem consentimento para a transferências de dados.</span><span class="sxs-lookup"><span data-stu-id="f4a84-119">Administrators manage credentials and give consent to data transfers.</span></span> <span data-ttu-id="f4a84-120">As conexões podem então ser usadas para enriquecimentos pelos administradores e colaboradores.</span><span class="sxs-lookup"><span data-stu-id="f4a84-120">The connections can then be used for enrichments by both administrators and contributors.</span></span>

## <a name="add-a-new-connection"></a><span data-ttu-id="f4a84-121">Adicionar uma nova conexão</span><span class="sxs-lookup"><span data-stu-id="f4a84-121">Add a new connection</span></span>

<span data-ttu-id="f4a84-122">Para adicionar conexões, você deve ter [permissões de administrador](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="f4a84-122">To add connections, you need to have [administrator permissions](permissions.md).</span></span> <span data-ttu-id="f4a84-123">Se você se conectar a outros serviços da Microsoft, presumimos que os serviços estejam na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="f4a84-123">If you connect to other Microsoft services, we assume both services are in the same organization.</span></span>

1. <span data-ttu-id="f4a84-124">Acesse **Administração** > **Conexões (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-124">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="f4a84-125">Acesse a guia **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-125">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="f4a84-126">Selecione **Adicionar conexão** para criar uma conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-126">Select **Add connection** to create a new connection.</span></span> <span data-ttu-id="f4a84-127">Escolha no menu suspenso o tipo de conexão que deseja criar.</span><span class="sxs-lookup"><span data-stu-id="f4a84-127">Choose from the dropdown menu what type of connection you want to create.</span></span>

1. <span data-ttu-id="f4a84-128">No painel **Configurar conexão**, forneça os detalhes necessários.</span><span class="sxs-lookup"><span data-stu-id="f4a84-128">In the **Set up connection** pane, provide the required details.</span></span> 
   1. <span data-ttu-id="f4a84-129">O **Nome de exibição** e o tipo de conexão descrevem uma conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-129">The **Display name** and the type of the connection describe a connection.</span></span> <span data-ttu-id="f4a84-130">Recomendamos escolher um nome que explique a finalidade e o objetivo dessa conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-130">We recommend choosing a name that explains the purpose and target of this connection.</span></span>
   1. <span data-ttu-id="f4a84-131">Os campos exatos dependem do serviço ao qual você está se conectando.</span><span class="sxs-lookup"><span data-stu-id="f4a84-131">The exact fields depend on what service you are connecting to.</span></span> <span data-ttu-id="f4a84-132">Você pode saber mais sobre os detalhes de um tipo de conexão específico no artigo sobre o serviço de destino.</span><span class="sxs-lookup"><span data-stu-id="f4a84-132">You can learn about details of a specific connection type in the article about the target service.</span></span>

1. <span data-ttu-id="f4a84-133">Para criar a conexão, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-133">To create the connection, select **Save**.</span></span>

<span data-ttu-id="f4a84-134">Você também pode selecionar **Configurar** em um bloco na aba **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-134">You can also select **Set up** on a tile on the **Discover** tab.</span></span>

### <a name="allow-contributors-to-use-a-connection-for-exports"></a><span data-ttu-id="f4a84-135">Permitir que os colaboradores usem uma conexão para exportações</span><span class="sxs-lookup"><span data-stu-id="f4a84-135">Allow contributors to use a connection for exports</span></span>

<span data-ttu-id="f4a84-136">Ao configurar ou editar uma conexão de exportação, você escolhe quais usuários têm permissão para usar esta conexão específica para definir [exportações](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f4a84-136">When setting up or editing an export connection, you choose which users are allowed to use this specific connection to define [exports](export-destinations.md).</span></span> <span data-ttu-id="f4a84-137">Por padrão, uma conexão está disponível para os usuários com função de administrador.</span><span class="sxs-lookup"><span data-stu-id="f4a84-137">By default a connection is available to users with an administrator role.</span></span> <span data-ttu-id="f4a84-138">Você pode alterar essa configuração em **Escolher quem pode usar esta conexão** e permitir que os usuários com função de colaborador usem a conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-138">You can change this setting under **Choose who can use this connection** and allow users with contributor role to use this connection.</span></span>

- <span data-ttu-id="f4a84-139">Os colaboradores não poderão visualizar ou editar a conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-139">Contributors won't be able to view or edit the connection.</span></span> <span data-ttu-id="f4a84-140">Eles verão somente o nome de exibição e seu tipo ao criar uma exportação.</span><span class="sxs-lookup"><span data-stu-id="f4a84-140">They will only see the display name and its type when creating an export.</span></span>
- <span data-ttu-id="f4a84-141">Ao compartilhar uma conexão, você permite que os colaboradores usem uma conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-141">By sharing a connection, you allow contributors to use a connection.</span></span> <span data-ttu-id="f4a84-142">Os colaboradores verão as conexões compartilhadas ao configurar as exportações.</span><span class="sxs-lookup"><span data-stu-id="f4a84-142">Contributors will see shared connections when they set up exports.</span></span> <span data-ttu-id="f4a84-143">Eles podem gerenciar todas as exportações que usam essa conexão específica.</span><span class="sxs-lookup"><span data-stu-id="f4a84-143">They can manage every export that uses this specific connection.</span></span>
- <span data-ttu-id="f4a84-144">Você pode alterar essa configuração enquanto mantém as exportações que já foram definidas pelos colaboradores.</span><span class="sxs-lookup"><span data-stu-id="f4a84-144">You can change this setting while keeping the exports that have already been defined by contributors.</span></span>

## <a name="edit-a-connection"></a><span data-ttu-id="f4a84-145">Editar uma conexão</span><span class="sxs-lookup"><span data-stu-id="f4a84-145">Edit a connection</span></span>

1. <span data-ttu-id="f4a84-146">Acesse **Administração** > **Conexões (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-146">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="f4a84-147">Acesse a guia **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-147">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="f4a84-148">Selecione as reticências verticais para a conexão que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="f4a84-148">Select the vertical ellipsis for the connection you want to edit.</span></span>

1. <span data-ttu-id="f4a84-149">Selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-149">Select **Edit**.</span></span>

1. <span data-ttu-id="f4a84-150">Altere os valores que deseja atualizar e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-150">Change the values you want to update and select **Save**.</span></span>

## <a name="remove-a-connection"></a><span data-ttu-id="f4a84-151">Remover uma conexão</span><span class="sxs-lookup"><span data-stu-id="f4a84-151">Remove a connection</span></span>

<span data-ttu-id="f4a84-152">Se a conexão que você estiver removendo for usada para enriquecimentos ou exportações, primeiro é necessário separá-los ou removê-los.</span><span class="sxs-lookup"><span data-stu-id="f4a84-152">If the connection you are removing is used by enrichments or exports, you first need to detach or remove them.</span></span> <span data-ttu-id="f4a84-153">A caixa de diálogo de remoção guiará você para os enriquecimentos ou exportações relevantes.</span><span class="sxs-lookup"><span data-stu-id="f4a84-153">The remove dialog will guide you to the relevant enrichments or exports.</span></span> 

<span data-ttu-id="f4a84-154">Os enriquecimentos e as exportações separados tornam-se inativos.</span><span class="sxs-lookup"><span data-stu-id="f4a84-154">Detached enrichments and exports become inactive.</span></span> <span data-ttu-id="f4a84-155">Você os reativa adicionando outra conexão a eles na página [Enriquecimentos](enrichment-hub.md) ou [Exportações](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f4a84-155">You reactivate them by adding another connection to them on the [Enrichments](enrichment-hub.md) or [Exports](export-destinations.md) page.</span></span>

1. <span data-ttu-id="f4a84-156">Acesse **Administração** > **Conexões (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-156">Go to **Admin** > **Connections (preview)**.</span></span>

1. <span data-ttu-id="f4a84-157">Acesse a guia **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-157">Go to the **Connections** tab.</span></span>

1. <span data-ttu-id="f4a84-158">Selecione as reticências verticais para a conexão que você deseja remover.</span><span class="sxs-lookup"><span data-stu-id="f4a84-158">Select the vertical ellipsis for the connection you want to remove.</span></span>

1. <span data-ttu-id="f4a84-159">Selecione **Remover** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="f4a84-159">Select **Remove** from the dropdown menu.</span></span> <span data-ttu-id="f4a84-160">Uma caixa de diálogo de confirmação será exibida.</span><span class="sxs-lookup"><span data-stu-id="f4a84-160">A confirmation dialog appears.</span></span>

   1. <span data-ttu-id="f4a84-161">Se houver enriquecimentos ou exportações usando a conexão, selecione o botão para ver o que está usando-a.</span><span class="sxs-lookup"><span data-stu-id="f4a84-161">If there are enrichments or exports using this connection, select the button to see what's using the connection.</span></span>
      - <span data-ttu-id="f4a84-162">**Exportações:** você pode optar por remover ou desconectar as exportações para poder remover a conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-162">**Exports:** You can choose to either remove or disconnect the exports to be able to remove the connection.</span></span> <span data-ttu-id="f4a84-163">Para desconectar uma exportação, os administradores podem usar a ação **Desconectar**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-163">To disconnect an export, administrators can use the **Disconnect** action.</span></span> <span data-ttu-id="f4a84-164">Esta ação está disponível para exportações individuais e múltiplas selecionadas.</span><span class="sxs-lookup"><span data-stu-id="f4a84-164">This action is available for individual and multiple selected exports.</span></span> <span data-ttu-id="f4a84-165">Ao desconectar, você mantém a configuração de exportação, mas ela não será executada até que outra conexão seja adicionada a ela.</span><span class="sxs-lookup"><span data-stu-id="f4a84-165">By disconnecting you keep the export config, but it won't be run until another connection is added to it.</span></span>
      - <span data-ttu-id="f4a84-166">**Enriquecimentos:** você pode optar por remover ou desativar os enriquecimentos para poder remover a conexão.</span><span class="sxs-lookup"><span data-stu-id="f4a84-166">**Enrichments:** You can choose to either remove or deactivate the enrichments to be able to remove the connection.</span></span> 
   1. <span data-ttu-id="f4a84-167">Assim que a conexão não tiver mais dependências, volte para **Administração** > **Conexões** e tente remover a conexão novamente.</span><span class="sxs-lookup"><span data-stu-id="f4a84-167">Once the connection has no more dependencies, go back to **Admin** > **Connections** and try removing the connection again.</span></span>

1. <span data-ttu-id="f4a84-168">Para confirmar a exclusão, selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="f4a84-168">To confirm the deletion, select **Remove**.</span></span>

