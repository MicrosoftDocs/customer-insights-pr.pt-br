---
title: Exportar dados do Customer Insights para o Azure Synapse Analytics
description: Aprenda a configurar a conexão e exportar para o Azure Synapse Analytics.
ms.date: 04/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 822082d661863e737ea3d3a749a6c878db766967
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5977363"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a><span data-ttu-id="bd2ee-103">Exportar para o Azure Synapse Analytics (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="bd2ee-103">Export data to Azure Synapse Analytics (Preview)</span></span>

<span data-ttu-id="bd2ee-104">O Azure Synapse é um serviço de análise que acelera o tempo de insight de armazéns de dados e sistemas de big data.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-104">Azure Synapse is an analytics service that accelerates time to insight across data warehouses and big data systems.</span></span> <span data-ttu-id="bd2ee-105">Você pode ingerir e usar seus dados de Customer Insights em [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-105">You can ingest and use your Customer Insights data in [Azure Synapse](/azure/synapse-analytics/overview-what-is).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bd2ee-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bd2ee-106">Prerequisites</span></span>

<span data-ttu-id="bd2ee-107">Os seguintes pré-requisitos devem ser cumpridos para configurar a conexão do Customer Insights para o Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-107">The following prerequisites must be met to configure the connection from Customer Insights to Azure Synapse.</span></span>

> [!NOTE]
> <span data-ttu-id="bd2ee-108">Lembre-se de definir todas as **atribuições de função** conforme descrito.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-108">Make sure to set all **role assignments** as described.</span></span>  

## <a name="prerequisites-in-customer-insights"></a><span data-ttu-id="bd2ee-109">Pré-requisitos no Customer Insights</span><span class="sxs-lookup"><span data-stu-id="bd2ee-109">Prerequisites in Customer Insights</span></span>

* <span data-ttu-id="bd2ee-110">Você tem uma função de **Administrador** nos insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-110">You have an **Administrator** role in audience insights.</span></span> <span data-ttu-id="bd2ee-111">Saiba mais sobre [como definir permissões do usuário em insights de público-alvo](permissions.md#assign-roles-and-permissions)</span><span class="sxs-lookup"><span data-stu-id="bd2ee-111">Learn more about [setting user permissions in audience insights](permissions.md#assign-roles-and-permissions)</span></span>

<span data-ttu-id="bd2ee-112">No Azure:</span><span class="sxs-lookup"><span data-stu-id="bd2ee-112">In Azure:</span></span> 

- <span data-ttu-id="bd2ee-113">Uma assinatura ativa do Azure.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-113">An active Azure subscription.</span></span>

- <span data-ttu-id="bd2ee-114">Se estiver usando uma nova conta do Azure Data Lake Storage Gen2, a *entidade de serviço para insights do público-alvo* precisa de permissões do **Colaborador de Dados do Storage Blob**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-114">If using a new Azure Data Lake Storage Gen2 account, the *service principal for audience insights* needs **Storage Blob Data Contributor** permissions.</span></span> <span data-ttu-id="bd2ee-115">Saiba mais sobre [como conectar-se a uma conta do Azure Data Lake Storage Gen2 com a entidade de serviço para insights do público-alvo](connect-service-principal.md).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-115">Learn more on [connecting to an Azure Data Lake Storage Gen2 account with Azure service principal for audience insights](connect-service-principal.md).</span></span> <span data-ttu-id="bd2ee-116">O Data Lake Storage Gen2 **deve ter** [namespace hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-116">The Data Lake Storage Gen2 **must have** [hierarchical namespace](/azure/storage/blobs/data-lake-storage-namespace) enabled.</span></span>

- <span data-ttu-id="bd2ee-117">No grupo de recursos onde o espaço de trabalho do Azure Synapse está localizado, a *entidade de serviço* e o *usuário para insights do público-alvo* precisa receber, pelo menos, permissões de **Leitor**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-117">On the resource group the Azure Synapse workspace is located, the *service principal* and the *user for audience insights* needs to be assigned at least **Reader** permissions.</span></span> <span data-ttu-id="bd2ee-118">Para mais informações, veja [Atribuir funções do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-118">For more information, see [Assign Azure roles using the Azure portal](/azure/role-based-access-control/role-assignments-portal).</span></span>

- <span data-ttu-id="bd2ee-119">O *usuário* precisa de permissões do **Colaborador de Dados do Storage Blob** na conta do Azure Data Lake Storage Gen2 onde os dados estão localizados e vinculados ao espaço de trabalho do Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-119">The *user* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="bd2ee-120">Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-120">Learn more about [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="bd2ee-121">A identidade gerenciada do espaço de trabalho do *[Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões do **Colaborador de Dados do Storage Blob** na conta do Azure Data Lake Storage Gen2 onde os dados estão localizados e vinculados ao espaço de trabalho do Azure Synapse.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-121">The *[Azure Synapse workspace managed identity](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* needs **Storage Blob Data Contributor** permissions on the Azure Data Lake Storage Gen2 account where the data is located and linked to the Azure Synapse workspace.</span></span> <span data-ttu-id="bd2ee-122">Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-122">Learn more on [using the Azure portal to assign an Azure role for access to blob and queue data](/azure/storage/common/storage-auth-aad-rbac-portal) and [Storage Blob Data Contributor permissions](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).</span></span>

- <span data-ttu-id="bd2ee-123">No espaço de trabalho do Azure Synapse, a *entidade de serviço para insights do público-alvo* precisa da função de **Administrador do Synapse** atribuída.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-123">On the Azure Synapse workspace, the *service principal for audience insights* needs **Synapse Administrator** role assigned.</span></span> <span data-ttu-id="bd2ee-124">Para mais informações, veja [Como configurar o controle de acesso para o seu espaço de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-124">For more information, see [How to set up access control for your Synapse workspace](/azure/synapse-analytics/security/how-to-set-up-access-control).</span></span>

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a><span data-ttu-id="bd2ee-125">Configurar a conexão e exportar para o Azure Synapse</span><span class="sxs-lookup"><span data-stu-id="bd2ee-125">Set up the connection and export to Azure Synapse</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="bd2ee-126">Configurar uma conexão</span><span class="sxs-lookup"><span data-stu-id="bd2ee-126">Configure a connection</span></span>

1. <span data-ttu-id="bd2ee-127">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-127">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bd2ee-128">Selecione **Adicionar conexão** e escolha **Azure Synapse Analytics** ou selecione **Configurar** no bloco **Azure Synapse Analytics** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-128">Select **Add connection** and choose **Azure Synapse Analytics** or select the **Set up** on the **Azure Synapse Analytics** tile to configure the connection.</span></span>

1. <span data-ttu-id="bd2ee-129">Dê um nome reconhecível à sua conexão no campo Nome de exibição.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-129">Give your connection a recognizable name in the Display name field.</span></span> <span data-ttu-id="bd2ee-130">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-130">The name and the type of the connection describes this connection.</span></span> <span data-ttu-id="bd2ee-131">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-131">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bd2ee-132">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-132">Choose who can use this connection.</span></span> <span data-ttu-id="bd2ee-133">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-133">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bd2ee-134">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-134">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bd2ee-135">Selecione ou pesquise pela assinatura na qual deseja usar os dados do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-135">Select or search for the subscription you want to use the Customer Insights data in.</span></span> <span data-ttu-id="bd2ee-136">Assim que uma assinatura for selecionada, você também pode selecionar **Espaço de trabalho**, **Conta de armazenamento** e **Recipiente**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-136">As soon as a subscription is selected, you can also select **Workspace**, **Storage account**, and **Container**.</span></span>

1. <span data-ttu-id="bd2ee-137">Selecione **Salvar** para salvar a conexão.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-137">Select **Save** to save the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="bd2ee-138">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="bd2ee-138">Configure an export</span></span>

<span data-ttu-id="bd2ee-139">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-139">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bd2ee-140">Para obter mais informações, veja [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-140">For more information, see [permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bd2ee-141">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-141">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bd2ee-142">Para criar uma exportação, selecione **Adicionar exportação**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-142">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="bd2ee-143">No campo **Conexão para exportação**, escolha uma conexão da seção do **Azure Synapse Analytics**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-143">In the **Connection for export** field, choose a connection from the **Azure Synapse Analytics** section.</span></span> <span data-ttu-id="bd2ee-144">Se não vir este nome de seção, não há [conexões](connections.md) deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-144">If you don't see this section name, there are no [connections](connections.md) of this type available to you.</span></span>

1. <span data-ttu-id="bd2ee-145">Fornece um **Nome de exibição** reconhecívelf para sua exportação e um **Nome do banco de dados**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-145">Provide a recognizable **Display name** for your export and a **Database name**.</span></span>

1. <span data-ttu-id="bd2ee-146">Selecione quais entidades você deseja exportar para o Azure Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-146">Select which entities you want to export to Azure Synapse Analytics.</span></span>

1. <span data-ttu-id="bd2ee-147">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-147">Select **Save**.</span></span>

<span data-ttu-id="bd2ee-148">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-148">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bd2ee-149">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-149">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bd2ee-150">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bd2ee-150">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span>

### <a name="update-an-export"></a><span data-ttu-id="bd2ee-151">Atualizar uma exportação</span><span class="sxs-lookup"><span data-stu-id="bd2ee-151">Update an export</span></span>

1. <span data-ttu-id="bd2ee-152">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-152">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bd2ee-153">Selecione **Editar** na exportação que você deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-153">Select **Edit** on the export you want to update.</span></span>

   - <span data-ttu-id="bd2ee-154">**Adicionar** ou **Remove** entidades da seleção.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-154">**Add** or **Remove** entities from the selection.</span></span> <span data-ttu-id="bd2ee-155">Se forem removidas da seleção, as entidades não serão excluídas do banco de dados do Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-155">If entities are removed from the selection, they aren't deleted from the Synapse Analytics database.</span></span> <span data-ttu-id="bd2ee-156">Porém, futuras atualizações de dados não irão atualizar as entidades removidas desse banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-156">However, future data refreshes won't update the removed entities in that database.</span></span>

   - <span data-ttu-id="bd2ee-157">**Alterar o nome do banco de dados** cria um novo banco de dados do Synapse Analytics.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-157">**Changing the Database Name** creates a new Synapse Analytics database.</span></span> <span data-ttu-id="bd2ee-158">O banco de dados cujo o nome já foi configurado não será atualizado em nenhuma atualização futura.</span><span class="sxs-lookup"><span data-stu-id="bd2ee-158">The database with the name that was configured before won't receive any updates in future refreshes.</span></span>
