---
title: Gerenciar permissões de usuário
description: Saiba mais sobre permissões e funções de usuário.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 8638489dba908d4504278916d2c28454e3ea9e18
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760359"
---
# <a name="user-permissions"></a><span data-ttu-id="5bcab-103">Permissões de usuário</span><span class="sxs-lookup"><span data-stu-id="5bcab-103">User permissions</span></span>

<span data-ttu-id="5bcab-104">Na página **Permissões**, você configurará funções e permissões para usar insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="5bcab-104">The **Permissions** page is where you'll set up roles and permissions for using audience insights.</span></span>

<span data-ttu-id="5bcab-105">Você precisa ter permissões de administrador para ver a página.</span><span class="sxs-lookup"><span data-stu-id="5bcab-105">You need to have administrator permissions to see the page.</span></span> <span data-ttu-id="5bcab-106">Para acessar a página de permissões nos insights de público-alvo, vá para **Administrador** > **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-106">To access the permissions page in audience insights, go to **Admin** > **Permissions**.</span></span>

<span data-ttu-id="5bcab-107">Há três tipos de funções:</span><span class="sxs-lookup"><span data-stu-id="5bcab-107">There are three types of roles:</span></span>

## <a name="viewer"></a><span data-ttu-id="5bcab-108">Espectador</span><span class="sxs-lookup"><span data-stu-id="5bcab-108">Viewer</span></span>

- <span data-ttu-id="5bcab-109">Explore insights e segmentos nas páginas **Página Inicial** e **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-109">Explore insights and segments within the **Home** and **Segments** pages.</span></span>
- <span data-ttu-id="5bcab-110">Pesquise e filtre perfis do cliente usando a página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-110">Search and filter customer profiles using the **Customers** page.</span></span> <span data-ttu-id="5bcab-111">Os campos devem ser pesquisáveis.</span><span class="sxs-lookup"><span data-stu-id="5bcab-111">Fields must be searchable.</span></span>
- <span data-ttu-id="5bcab-112">Exiba e explore a página **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-112">View and explore the **Enrichment** page.</span></span>
- <span data-ttu-id="5bcab-113">Explorar e exportar entidades usando a página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-113">Explore and export entities using the **Entities** page.</span></span>
- <span data-ttu-id="5bcab-114">Exiba o status dos processos do sistema usando a página **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-114">View the status of system processes  using the **System** page.</span></span>
- <span data-ttu-id="5bcab-115">Exiba exportações na página **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-115">View exports in **Exports** page.</span></span>
- <span data-ttu-id="5bcab-116">Instale e use o painel **Power BI Customer Insights**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-116">Install and use the **Power BI Customer Insights** dashboard.</span></span>

## <a name="contributor"></a><span data-ttu-id="5bcab-117">Colaborador</span><span class="sxs-lookup"><span data-stu-id="5bcab-117">Contributor</span></span>

- <span data-ttu-id="5bcab-118">Todas as permissões disponíveis para o Visualizador.</span><span class="sxs-lookup"><span data-stu-id="5bcab-118">All permissions available to the Viewer.</span></span>
- <span data-ttu-id="5bcab-119">Carregue e transforme dados usando a página **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-119">Load and transform data using the **Data sources** page.</span></span>
- <span data-ttu-id="5bcab-120">Preencha as seções de *Unificação de Dados* (**Mapear**, **Corresponder** e **Mesclar**) que resultam na entidade de perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="5bcab-120">Complete the *Data Unification* sections (**Map**, **Match**, and **Merge**) which result in the unified customer profile entity.</span></span>
- <span data-ttu-id="5bcab-121">Defina **Relacionamentos** e **Atividades**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-121">Define **Relationships** and **Activities**.</span></span>
- <span data-ttu-id="5bcab-122">Crie segmentos usando a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-122">Create segments using the **Segments** page.</span></span>
- <span data-ttu-id="5bcab-123">Crie medidas usando a página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-123">Create measures using the **Measures** page.</span></span>
- <span data-ttu-id="5bcab-124">Gerencie a configuração e enriqueça os perfis de cliente na página **Enriquecimento** (somente para os primeiros enriquecimentos da parte).</span><span class="sxs-lookup"><span data-stu-id="5bcab-124">Manage configuration and enrich customer profiles from the **Enrichment** page (for first party enrichments only).</span></span>
- <span data-ttu-id="5bcab-125">Gerencie e crie exportações com base em conexões compartilhadas com colaboradores.</span><span class="sxs-lookup"><span data-stu-id="5bcab-125">Manage and create exports based on connections shared with contributors.</span></span> <span data-ttu-id="5bcab-126">[Saiba mais sobre como os administradores permitem que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="5bcab-126">[Learn more about how administrators allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

## <a name="administrator"></a><span data-ttu-id="5bcab-127">Administrador</span><span class="sxs-lookup"><span data-stu-id="5bcab-127">Administrator</span></span>

- <span data-ttu-id="5bcab-128">Todas as permissões disponíveis para o Colaborador.</span><span class="sxs-lookup"><span data-stu-id="5bcab-128">All permissions available to the Contributor.</span></span>
- <span data-ttu-id="5bcab-129">Altere as configurações na página **Sistema**, incluindo o idioma de trabalho, e atualize os cronogramas de seus processos do sistema.</span><span class="sxs-lookup"><span data-stu-id="5bcab-129">Change settings on the **System** page, including the working language and refresh schedules for your system processes.</span></span>
- <span data-ttu-id="5bcab-130">Exiba e adicione permissões usando a página **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-130">View and add permissions using the **Permissions** page.</span></span>
- <span data-ttu-id="5bcab-131">Configure as definições de filtro e pesquisa para a página Clientes usando a página **Índice de filtro e pesquisa** (accessível pela página **Clientes**).</span><span class="sxs-lookup"><span data-stu-id="5bcab-131">Set search and filter definitions for the Customers page using the **Search & filter index** page (accessible via the **Customers** page).</span></span>
- <span data-ttu-id="5bcab-132">Gerencie conexões e as permita para outras funções de usuário na página **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-132">Manage connections and allow them for other user roles on **Connections** page.</span></span>
- <span data-ttu-id="5bcab-133">Gerencie a configuração e enriqueça os perfis de cliente na página **Enriquecimento** (para todos os enriquecimentos).</span><span class="sxs-lookup"><span data-stu-id="5bcab-133">Manage configuration and enrich customer profiles from the **Enrichment** page (for all enrichments).</span></span>
- <span data-ttu-id="5bcab-134">Gerencie e crie exportações na página **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-134">Manage and create exports on **Exports** page.</span></span>
- <span data-ttu-id="5bcab-135">Instale e use o **Complemento do Cartão do Cliente**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-135">Install and use the **Customer Card Add-in**.</span></span>
- <span data-ttu-id="5bcab-136">Adicione e use o **conector do Power Apps**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-136">Add and use the **Power Apps connector**.</span></span>
- <span data-ttu-id="5bcab-137">Habilite o uso de [APIs do Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="5bcab-137">Enable usage of [Customer Insights APIs](apis.md).</span></span>

## <a name="assign-roles-and-permissions"></a><span data-ttu-id="5bcab-138">Atribuir funções e permissões</span><span class="sxs-lookup"><span data-stu-id="5bcab-138">Assign roles and permissions</span></span>

1. <span data-ttu-id="5bcab-139">Nos insights de público-alvo, vá para **Administrador** > **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-139">In audience insights, go to **Admin** > **Permissions**.</span></span>

1. <span data-ttu-id="5bcab-140">Selecione **Adicionar usuários** para abrir o painel **Adicionar/Editar permissões**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-140">Select **Add users** to open the **Add/Edit permissions** pane.</span></span>

1. <span data-ttu-id="5bcab-141">Use o campo **Pesquisar** para localizar o usuário ou grupo do Azure Active Directory para o qual você deseja ajustar as permissões.</span><span class="sxs-lookup"><span data-stu-id="5bcab-141">Use the **Search** field to find the Azure Active Directory user or group whose permissions you want to adjust.</span></span> <span data-ttu-id="5bcab-142">Selecione uma **Função** para atribuir a esse usuário ou grupo.</span><span class="sxs-lookup"><span data-stu-id="5bcab-142">Select a **Role** to assign to that user or group.</span></span>

1. <span data-ttu-id="5bcab-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-143">Select **Save**.</span></span> <span data-ttu-id="5bcab-144">O ambiente atual será compartilhado automaticamente com o usuário ou os membros do grupo cujas permissões você alterou.</span><span class="sxs-lookup"><span data-stu-id="5bcab-144">The current environment will automatically be shared with the user or members of the group whose permissions you've changed.</span></span> <span data-ttu-id="5bcab-145">Os usuários podem acessar o aplicativo Customer Insights e trabalhar de acordo com sua função especificada.</span><span class="sxs-lookup"><span data-stu-id="5bcab-145">Users can access the Customer Insights app and work according to their specified role.</span></span>

## <a name="view-current-permissions"></a><span data-ttu-id="5bcab-146">Ver as permissões atuais</span><span class="sxs-lookup"><span data-stu-id="5bcab-146">View current permissions</span></span>

<span data-ttu-id="5bcab-147">Nos insights de público-alvo, vá para **Administrador** > **Permissões** para ver quais atribuições de função estão ativas no momento.</span><span class="sxs-lookup"><span data-stu-id="5bcab-147">In audience insights, go to **Admin** > **Permissions** to see what role assignments are currently active.</span></span>

- <span data-ttu-id="5bcab-148">A coluna **Tipo** especifica um usuário único, grupo ou aplicativo.</span><span class="sxs-lookup"><span data-stu-id="5bcab-148">The **Type** column specifies a single user, group, or application.</span></span> <span data-ttu-id="5bcab-149">O sistema suporta usuários e grupos individuais.</span><span class="sxs-lookup"><span data-stu-id="5bcab-149">The system supports individual users and groups.</span></span>
- <span data-ttu-id="5bcab-150">As funções são especificadas na coluna **Função**.</span><span class="sxs-lookup"><span data-stu-id="5bcab-150">Roles are specified under the **Role** column.</span></span>
- <span data-ttu-id="5bcab-151">Selecione qualquer título de coluna para classificar os resultados pelo valor dessa coluna.</span><span class="sxs-lookup"><span data-stu-id="5bcab-151">Select any column title to sort the results by that column's value.</span></span>
- <span data-ttu-id="5bcab-152">Use o campo **Pesquisar** na parte superior da página para localizar usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="5bcab-152">Use the **Search** field at the top of the page to locate specific users.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
