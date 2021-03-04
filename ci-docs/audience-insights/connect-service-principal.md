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
ms.openlocfilehash: eebbac1370a847869d98beaf70db49b809d762e7
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267708"
---
# <a name="connect-to-an-azure-data-lake-storage-gen2-account-with-an-azure-service-principal-for-audience-insights"></a>Conectar-se a uma conta Gen2 do Azure Data Lake Storage com uma entidade de serviço do Azure para obter insights de público-alvo

As ferramentas automatizadas que usam os serviços do Azure devem sempre ter permissões restritas. Em vez de fazer com que os aplicativos entrem como um usuário totalmente privilegiado, o Azure oferece entidades de serviço. Continue lendo para saber como conectar insights de público-alvo com uma conta Gen2 do Azure Data Lake Storage usando uma entidade de serviço do Azure em vez de chaves de conta de armazenamento. 

Você pode usar a entidade de serviço para, com segurança, [adicionar ou editar uma pasta do Common Data Model como uma fonte de dados](connect-common-data-model.md) ou [criar um ambiente ou atualizar um existente](manage-environments.md#create-an-environment-in-an-existing-organization).

> [!IMPORTANT]
> - A conta de armazenamento do Azure Data Lake Gen2 que pretende usar a entidade de serviço deve ter o [Espaço Hierárquico de Nomes (HNS) habilitado](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-namespace).
> - Você precisa de permissões de administrador para sua assinatura do Azure para criar a entidade de serviço.

## <a name="create-azure-service-principal-for-audience-insights"></a>Criar entidade de serviço do Azure para insights de público-alvo

Antes de criar uma entidade de serviço para insights de público-alvo, verifique se ela já existe em sua organização.

### <a name="look-for-an-existing-service-principal"></a>Procurar uma entidade de serviço existente

1. Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.

2. Selecione **Azure Active Directory** nos serviços do Azure.

3. Em **Gerenciar**, selecione **Aplicativos Empresariais**.

4. Pesquise a ID do aplicativo interno de insights de público-alvo `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou o nome `Dynamics 365 AI for Customer Insights`.

5. Se você encontrar um registro correspondente, isso significa que a entidade de serviço para insights de público-alvo existe. Você não precisa criá-la novamente.
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de tela mostrando a entidade de serviço existente.":::
   
6. Se nenhum resultado for retornado, crie uma entidade de serviço.

### <a name="create-a-new-service-principal"></a>Criar uma entidade de serviço

1. Instale a versão mais recente do **Azure Active Directory PowerShell para Graph**. Para obter mais informações, consulte [Instalar Azure Active Directory PowerShell para Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2).
   - No seu computador, selecione a tecla Windows e pesquise **Windows PowerShell** e **Executar como Administrador**.
   
   - Na janela do PowerShell que é aberta, digite `Install-Module AzureAD`.

2. Crie a entidade de serviço para insights de público-alvo com o Azure AD PowerShell Module.
   - Na janela do PowerShell, digite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substitua “sua ID de locatário” pela ID real de seu locatário em que deseja criar a entidade de serviço. O parâmetro de nome de ambiente `AzureEnvironmentName` é opcional.
  
   - Insira `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando cria a entidade de serviço para insights de público-alvo no locatário selecionado.  

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceder permissões à entidade de serviço para acessar a conta de armazenamento

Acesso o portal do Azure para conceder permissões à entidade de serviço para a conta de armazenamento que você deseja usar nas insights do público-alvo.

1. Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.

1. Abra a conta de armazenamento à qual deseja que a entidade de serviço para insights de público-alvo tenha acesso.

1. Selecione **Controle de acesso (IAM)** no painel de navegação e escolha **Adicionar** > **Adicionar Atribuição de Função**.
   
   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de tela mostrando o portal do Azure ao adicionar uma atribuição de função.":::
   
1. No painel **Adicionar Atribuição de Função**, defina as propriedades a seguir:
   - Função: *Colaborador de Dados do Storage Blob*
   - Atribua acesso a: *Usuário, grupo ou entidade de serviço*
   - Selecione: *Dynamics 365 AI para o Customer Insights* (a [entidade de serviço que você criou](#create-a-new-service-principal))

1.  Selecione **Salvar**.

A propagação das alterações pode levar até 15 minutos.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Insira a ID do recurso do Azure ou os detalhes da assinatura do Azure no anexo da conta de armazenamento para insights de público-alvo.

Anexe uma conta do Azure Data Lake Storage em insights de público-lavo para [armazenar dados de saída](manage-environments.md) ou [usá-los como fonte de dados](connect-common-data-service-lake.md). Escolher a opção Azure Data Lake permite que você escolha entre uma abordagem baseada em recursos ou baseada em assinatura.

Siga as etapas abaixo para fornecer as informações necessárias sobre a abordagem selecionada.

### <a name="resource-based-storage-account-connection"></a>Conexão de conta de armazenamento baseada em recursos

1. Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.

1. Acesse **Configurações** > **Propriedades** no painel de navegação.

1. Copie o valor da ID do recurso da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie a ID do recurso da conta de armazenamento.":::

1. Em insights de público-alvo, insira a ID do recurso no campo do recurso exibido na tela de conexão da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira as informações de ID do recurso da conta de armazenamento.":::   
   
1. Continue com as etapas restantes nos insights de público-alvo para anexar a conta de armazenamento.

### <a name="subscription-based-storage-account-connection"></a>Conexão de conta de armazenamento baseada em assinatura

1. Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.

1. Acesse **Configurações** > **Propriedades** no painel de navegação.

1. Revise a **Assinatura**, o **Grupo de recursos** e o **Nome** da conta de armazenamento para ter certeza de selecionar os valores corretos nos insights de público-alvo.

1. Em insights de público-alvo, escolha os valores ou os campos correspondentes ao anexar a conta de armazenamento.
   
1. Continue com as etapas restantes nos insights de público-alvo para anexar a conta de armazenamento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]