---
title: Conectar-se a uma conta Gen2 do Azure Data Lake Storage com uma entidade de serviço
description: Use uma entidade de serviço do Azure para insights de público-alvo para se conectar ao seu próprio data lake ao anexá-lo aos insights de público-alvo.
ms.date: 02/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c670b0065a2833a6dc311d9e86d2b351140382ce
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596485"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a><span data-ttu-id="af195-103">Conectar-se a uma conta Gen2 do Azure Data Lake Storage com uma entidade de serviço do Azure para obter insights de público-alvo</span><span class="sxs-lookup"><span data-stu-id="af195-103">Connect to an Azure Data Lake Storage Gen2 account with an Azure service principal for audience insights</span></span>

<span data-ttu-id="af195-104">As ferramentas automatizadas que usam os serviços do Azure devem sempre ter permissões restritas.</span><span class="sxs-lookup"><span data-stu-id="af195-104">Automated tools that use Azure services should always have restricted permissions.</span></span> <span data-ttu-id="af195-105">Em vez de fazer com que os aplicativos entrem como um usuário totalmente privilegiado, o Azure oferece entidades de serviço.</span><span class="sxs-lookup"><span data-stu-id="af195-105">Instead of having applications sign in as a fully privileged user, Azure offers service principals.</span></span> <span data-ttu-id="af195-106">Continue lendo para saber como conectar insights de público-alvo com uma conta Gen2 do Azure Data Lake Storage usando uma entidade de serviço do Azure em vez de chaves de conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="af195-106">Read on to learn how to connect audience insights with an Azure Data Lake Storage Gen2 account using an Azure service principal instead of storage account keys.</span></span> 

<span data-ttu-id="af195-107">Você pode usar a entidade de serviço para, com segurança, [adicionar ou editar uma pasta do Common Data Model como uma fonte de dados](connect-common-data-model.md) ou [criar um ambiente ou atualizar um existente](manage-environments.md#create-an-environment-in-an-existing-organization).</span><span class="sxs-lookup"><span data-stu-id="af195-107">You can use the service principal to securely [add or edit a Common Data Model folder as a data source](connect-common-data-model.md) or [create a new or update an existing environment](manage-environments.md#create-an-environment-in-an-existing-organization).</span></span>

> [!IMPORTANT]
> - <span data-ttu-id="af195-108">A conta de armazenamento do Azure Data Lake Gen2 que pretende usar a entidade de serviço deve ter o [Espaço Hierárquico de Nomes (HNS) habilitado](/azure/storage/blobs/data-lake-storage-namespace).</span><span class="sxs-lookup"><span data-stu-id="af195-108">The Azure Data Lake Gen2 storage account that intends to use the service principal must have [Hierarchical Name Space (HNS) enabled](/azure/storage/blobs/data-lake-storage-namespace).</span></span>
> - <span data-ttu-id="af195-109">Você precisa de permissões de administrador para sua assinatura do Azure para criar a entidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="af195-109">You need admin permissions for your Azure subscription to create the service principal.</span></span>

## <a name="create-azure-service-principal-for-audience-insights"></a><span data-ttu-id="af195-110">Criar entidade de serviço do Azure para insights de público-alvo</span><span class="sxs-lookup"><span data-stu-id="af195-110">Create Azure service principal for audience insights</span></span>

<span data-ttu-id="af195-111">Antes de criar uma entidade de serviço para insights de público-alvo, verifique se ela já existe em sua organização.</span><span class="sxs-lookup"><span data-stu-id="af195-111">Before creating a new service principal for audience insights, check if it already exists in your organization.</span></span>

### <a name="look-for-an-existing-service-principal"></a><span data-ttu-id="af195-112">Procurar uma entidade de serviço existente</span><span class="sxs-lookup"><span data-stu-id="af195-112">Look for an existing service principal</span></span>

1. <span data-ttu-id="af195-113">Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.</span><span class="sxs-lookup"><span data-stu-id="af195-113">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

2. <span data-ttu-id="af195-114">Selecione **Azure Active Directory** nos serviços do Azure.</span><span class="sxs-lookup"><span data-stu-id="af195-114">Select **Azure Active Directory** from the Azure services.</span></span>

3. <span data-ttu-id="af195-115">Em **Gerenciar**, selecione **Aplicativos Empresariais**.</span><span class="sxs-lookup"><span data-stu-id="af195-115">Under **Manage**, select **Enterprise Applications**.</span></span>

4. <span data-ttu-id="af195-116">Pesquise a ID do aplicativo interno de insights de público-alvo `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou o nome `Dynamics 365 AI for Customer Insights`.</span><span class="sxs-lookup"><span data-stu-id="af195-116">Search for the audience insights first party application ID `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` or the name `Dynamics 365 AI for Customer Insights`.</span></span>

5. <span data-ttu-id="af195-117">Se você encontrar um registro correspondente, isso significa que a entidade de serviço para insights de público-alvo existe.</span><span class="sxs-lookup"><span data-stu-id="af195-117">If you find a matching record, it means that the service principal for audience insights exists.</span></span> <span data-ttu-id="af195-118">Você não precisa criá-la novamente.</span><span class="sxs-lookup"><span data-stu-id="af195-118">You don't need to create it again.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de tela mostrando a entidade de serviço existente.":::
   
6. <span data-ttu-id="af195-120">Se nenhum resultado for retornado, crie uma entidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="af195-120">If no results are returned, create a new service principal.</span></span>

### <a name="create-a-new-service-principal"></a><span data-ttu-id="af195-121">Criar uma entidade de serviço</span><span class="sxs-lookup"><span data-stu-id="af195-121">Create a new service principal</span></span>

1. <span data-ttu-id="af195-122">Instale a versão mais recente do **Azure Active Directory PowerShell para Graph**.</span><span class="sxs-lookup"><span data-stu-id="af195-122">Install the latest version of the **Azure Active Directory PowerShell for Graph**.</span></span> <span data-ttu-id="af195-123">Para obter mais informações, consulte [Instalar Azure Active Directory PowerShell para Graph](/powershell/azure/active-directory/install-adv2).</span><span class="sxs-lookup"><span data-stu-id="af195-123">For more information, see [Install Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).</span></span>
   - <span data-ttu-id="af195-124">No seu computador, selecione a tecla Windows e pesquise **Windows PowerShell** e **Executar como Administrador**.</span><span class="sxs-lookup"><span data-stu-id="af195-124">On your PC, select the Windows key on your keyboard and search for **Windows PowerShell** and **Run as Administrator**.</span></span>
   
   - <span data-ttu-id="af195-125">Na janela do PowerShell que é aberta, digite `Install-Module AzureAD`.</span><span class="sxs-lookup"><span data-stu-id="af195-125">In the PowerShell window that opens, enter `Install-Module AzureAD`.</span></span>

2. <span data-ttu-id="af195-126">Crie a entidade de serviço para insights de público-alvo com o Azure AD PowerShell Module.</span><span class="sxs-lookup"><span data-stu-id="af195-126">Create the  service principal for audience insights with the Azure AD PowerShell Module.</span></span>
   - <span data-ttu-id="af195-127">Na janela do PowerShell, digite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span><span class="sxs-lookup"><span data-stu-id="af195-127">In the PowerShell window, enter `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`.</span></span> <span data-ttu-id="af195-128">Substitua “sua ID de locatário” pela ID real de seu locatário em que deseja criar a entidade de serviço.</span><span class="sxs-lookup"><span data-stu-id="af195-128">Replace “your tenant ID” with the actual ID of your tenant where you want to create the service principal.</span></span> <span data-ttu-id="af195-129">O parâmetro de nome de ambiente `AzureEnvironmentName` é opcional.</span><span class="sxs-lookup"><span data-stu-id="af195-129">The environment name parameter `AzureEnvironmentName` is optional.</span></span>
  
   - <span data-ttu-id="af195-130">Insira `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span><span class="sxs-lookup"><span data-stu-id="af195-130">Enter `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`.</span></span> <span data-ttu-id="af195-131">Este comando cria a entidade de serviço para insights de público-alvo no locatário selecionado.</span><span class="sxs-lookup"><span data-stu-id="af195-131">This command creates the service principal for audience insights on the selected tenant.</span></span>  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a><span data-ttu-id="af195-132">Conceder permissões à entidade de serviço para acessar a conta de armazenamento</span><span class="sxs-lookup"><span data-stu-id="af195-132">Grant permissions to the service principal to access the storage account</span></span>

<span data-ttu-id="af195-133">Acesso o portal do Azure para conceder permissões à entidade de serviço para a conta de armazenamento que você deseja usar nas insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="af195-133">Go to the Azure portal to grant permissions to the service principal for the storage account you want to use in audience insights.</span></span>

1. <span data-ttu-id="af195-134">Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.</span><span class="sxs-lookup"><span data-stu-id="af195-134">Go to the [Azure admin portal](https://portal.azure.com) and sign in to your organization.</span></span>

1. <span data-ttu-id="af195-135">Abra a conta de armazenamento à qual deseja que a entidade de serviço para insights de público-alvo tenha acesso.</span><span class="sxs-lookup"><span data-stu-id="af195-135">Open the storage account you want the service principal for audience insights to have access to.</span></span>

1. <span data-ttu-id="af195-136">Selecione **Controle de acesso (IAM)** no painel de navegação e escolha **Adicionar** > **Adicionar Atribuição de Função**.</span><span class="sxs-lookup"><span data-stu-id="af195-136">Select **Access control (IAM)** from the navigation pane and select **Add** > **Add role assignment**.</span></span>
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de tela mostrando o portal do Azure ao adicionar uma atribuição de função.":::
   
1. <span data-ttu-id="af195-138">No painel **Adicionar Atribuição de Função**, defina as propriedades a seguir:</span><span class="sxs-lookup"><span data-stu-id="af195-138">In the **Add role assignment** pane, set the following properties:</span></span>
   - <span data-ttu-id="af195-139">Função: *Colaborador de Dados do Storage Blob*</span><span class="sxs-lookup"><span data-stu-id="af195-139">Role: *Storage Blob Data Contributor*</span></span>
   - <span data-ttu-id="af195-140">Atribua acesso a: *Usuário, grupo ou entidade de serviço*</span><span class="sxs-lookup"><span data-stu-id="af195-140">Assign access to: *User, group, or service principal*</span></span>
   - <span data-ttu-id="af195-141">Selecione: *Dynamics 365 AI para o Customer Insights* (a [entidade de serviço que você criou](#create-a-new-service-principal))</span><span class="sxs-lookup"><span data-stu-id="af195-141">Select: *Dynamics 365 AI for Customer Insights* (the [service principal you created](#create-a-new-service-principal))</span></span>

1.  <span data-ttu-id="af195-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="af195-142">Select **Save**.</span></span>

<span data-ttu-id="af195-143">A propagação das alterações pode levar até 15 minutos.</span><span class="sxs-lookup"><span data-stu-id="af195-143">It can take up to 15 minutes to propagate the changes.</span></span>

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a><span data-ttu-id="af195-144">Insira a ID do recurso do Azure ou os detalhes da assinatura do Azure no anexo da conta de armazenamento para insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="af195-144">Enter the Azure Resource ID or the Azure Subscription details in the storage account attachment to Audience Insights.</span></span>

<span data-ttu-id="af195-145">Anexe uma conta do Azure Data Lake Storage em insights de público-lavo para [armazenar dados de saída](manage-environments.md) ou [usá-los como fonte de dados](connect-common-data-service-lake.md).</span><span class="sxs-lookup"><span data-stu-id="af195-145">Attach an Azure Data Lake storage account in audience insights to [store output data](manage-environments.md) or [use it as a data source](connect-common-data-service-lake.md).</span></span> <span data-ttu-id="af195-146">Escolher a opção Azure Data Lake permite que você escolha entre uma abordagem baseada em recursos ou baseada em assinatura.</span><span class="sxs-lookup"><span data-stu-id="af195-146">Choosing the Azure Data Lake option lets you choose between a resource-based or a subscription-based based approach.</span></span>

<span data-ttu-id="af195-147">Siga as etapas abaixo para fornecer as informações necessárias sobre a abordagem selecionada.</span><span class="sxs-lookup"><span data-stu-id="af195-147">Follow the below steps to provide the required information on the selected approach.</span></span>

### <a name="resource-based-storage-account-connection"></a><span data-ttu-id="af195-148">Conexão de conta de armazenamento baseada em recursos</span><span class="sxs-lookup"><span data-stu-id="af195-148">Resource-based storage account connection</span></span>

1. <span data-ttu-id="af195-149">Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="af195-149">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="af195-150">Acesse **Configurações** > **Propriedades** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="af195-150">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="af195-151">Copie o valor da ID do recurso da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="af195-151">Copy the storage account resource ID value.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie a ID do recurso da conta de armazenamento.":::

1. <span data-ttu-id="af195-153">Em insights de público-alvo, insira a ID do recurso no campo do recurso exibido na tela de conexão da conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="af195-153">In audience insights, insert the resource ID in the resource field displayed in the storage account connection screen.</span></span>

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira as informações de ID do recurso da conta de armazenamento.":::   
   
1. <span data-ttu-id="af195-155">Continue com as etapas restantes nos insights de público-alvo para anexar a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="af195-155">Continue with the remaining steps in audience insights to attach the storage account.</span></span>

### <a name="subscription-based-storage-account-connection"></a><span data-ttu-id="af195-156">Conexão de conta de armazenamento baseada em assinatura</span><span class="sxs-lookup"><span data-stu-id="af195-156">Subscription-based storage account connection</span></span>

1. <span data-ttu-id="af195-157">Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="af195-157">Go to the [Azure admin portal](https://portal.azure.com), sign in to your subscription and open the storage account.</span></span>

1. <span data-ttu-id="af195-158">Acesse **Configurações** > **Propriedades** no painel de navegação.</span><span class="sxs-lookup"><span data-stu-id="af195-158">Go to **Settings** > **Properties** on navigation pane.</span></span>

1. <span data-ttu-id="af195-159">Revise a **Assinatura**, o **Grupo de recursos** e o **Nome** da conta de armazenamento para ter certeza de selecionar os valores corretos nos insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="af195-159">Review the **Subscription**, **Resource group**, and the **Name** of the storage account to make sure you select the right values in audience insights.</span></span>

1. <span data-ttu-id="af195-160">Em insights de público-alvo, escolha os valores ou os campos correspondentes ao anexar a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="af195-160">In audience insights, choose the values or for the corresponding fields when attaching the storage account.</span></span>
   
1. <span data-ttu-id="af195-161">Continue com as etapas restantes nos insights de público-alvo para anexar a conta de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="af195-161">Continue with the remaining steps in audience insights to attach the storage account.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]