---
title: Conecte-se a uma conta do Azure Data Lake Storage usando uma entidade de serviço
description: Use uma entidade de serviço do Azure para se conectar ao seu próprio data lake.
ms.date: 04/26/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 776eee79c25edbd40ed119510a314f5126933c3e
ms.sourcegitcommit: a50c5e70d2baf4db41a349162fd1b1f84c3e03b6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8739148"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conecte-se a uma conta do Azure Data Lake Storage usando uma entidade de serviço do Azure

Este artigo descreve como conectar o Dynamics 365 Customer Insights a uma conta do Azure Data Lake Storage usando uma entidade de serviço do Azure em vez de chaves de conta de armazenamento. 

As ferramentas automatizadas que usam os serviços do Azure devem sempre ter permissões restritas. Em vez de fazer com que os aplicativos entrem como um usuário totalmente privilegiado, o Azure oferece entidades de serviço. Você pode usar entidades de serviço para [adicionar ou editar uma pasta do Common Data Model como uma fonte de dados](connect-common-data-model.md) ou [criar ou atualizar um ambiente](create-environment.md) com segurança.

> [!IMPORTANT]
> - A conta do Data Lake Storage que usará a entidade de serviço deve ser Gen2 e ter o [namespace hierárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace). As contas de armazenamento do Azure Data Lake Gen1 não têm suporte.
> - Você precisa de permissões de administrador para sua assinatura do Azure para criar uma entidade de serviço.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crie uma entidade de serviço do Azure para o Customer Insights

Antes de criar uma nova entidade de serviço para o Customer Insights, verifique se ela já existe na sua organização.

### <a name="look-for-an-existing-service-principal"></a>Procurar uma entidade de serviço existente

1. Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.

2. Em **Serviços do Azure**, selecione **Azure Active Directory**.

3. Em **Gerenciar**, selecione **Aplicativos Empresariais**.

4. Adicione um filtro para **A ID do aplicativo começa com** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou procure o nome `Dynamics 365 AI for Customer Insights`.

5. Se encontrar um registro correspondente, significará que a entidade de serviço já existe. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de tela mostrando uma entidade de serviço existente.":::
   
6. Se nenhum resultado for retornado, crie uma entidade de serviço.

### <a name="create-a-new-service-principal"></a>Criar uma entidade de serviço

1. Instale a versão mais recente do PowerShell para o Graph do Azure Active Directory. Para obter mais informações, acesse [Instalar o PowerShell para o Graph do Azure Active Directory](/powershell/azure/active-directory/install-adv2).

   1. No seu PC, pressione a tecla Windows no teclado e pesquise **Windows PowerShell** e selecione a opção **Executar como administrador**.
   
   1. Na janela do PowerShell que é aberta, digite `Install-Module AzureAD`.

2. Crie a entidade de serviço para o Customer Insights com o módulo PowerShell do Azure AD.

   1. Na janela do PowerShell, digite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Substitua *[sua ID de Diretório]* pela ID de Diretório real da assinatura do Azure na qual você deseja criar a entidade de serviço. O parâmetro de nome de ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Insira `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando cria a entidade de serviço para o Customer Insights na assinatura do Azure selecionada. 

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceder permissões à entidade de serviço para acessar a conta de armazenamento

Vá para o portal do Azure para conceder permissões à entidade de serviço da conta de armazenamento que você deseja usar no Customer Insights.

1. Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.

1. Abra a conta de armazenamento à qual você deseja que a entidade de serviço do Customer Insights tenha acesso.

1. No painel esquerdo, selecione a opção **Controle de acesso (IAM)** e selecione **Adicionar** > **Adicionar atribuição de função**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de tela mostrando o portal do Azure enquanto adiciona uma atribuição de função.":::

1. No painel **Adicionar atribuição de função**, defina as seguintes propriedades:
   - Função: **Colaborador de Dados do Storage Blob**
   - Atribua acesso a: **Usuário, grupo ou entidade de serviço**
   - Selecione membros: **Dynamics 365 AI for Customer Insights** (a [entidade de serviço](#create-a-new-service-principal) criada anteriormente neste procedimento)

1.  Selecione **Revisar + atribuir**.

A propagação das alterações pode levar até 15 minutos.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Insira a ID do recurso do Azure ou os detalhes da assinatura do Azure no anexo da conta de armazenamento para o Customer Insights

Você pode anexar uma conta do Data Lake Storage no Customer Insights para [armazenar dados de saída](manage-environments.md) ou [usá-la como um fonte de dados](connect-dataverse-managed-lake.md). Esta opção permite que você escolha entre uma abordagem baseada em recursos ou baseada em assinatura. Dependendo da abordagem escolhida, siga o procedimento descrito em uma destas seções.

### <a name="resource-based-storage-account-connection"></a>Conexão de conta de armazenamento baseada em recursos

1. Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.

1. No painel esquerdo, acesse **Configurações** > **Propriedades**.

1. Copie o valor da ID do recurso da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie a ID do recurso da conta de armazenamento.":::

1. No Customer Insights, insira a ID do recurso no campo de recurso exibido na tela de conexão da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira as informações de ID do recurso da conta de armazenamento.":::   

1. Continue com as etapas restantes no Customer Insights para anexar a conta de armazenamento.

### <a name="subscription-based-storage-account-connection"></a>Conexão de conta de armazenamento baseada em assinatura

1. Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.

1. No painel esquerdo, acesse **Configurações** > **Propriedades**.

1. Reveja a **Assinatura**, o **Grupo de recursos** e o **Nome** da conta de armazenamento para certificar-se de que selecionou os valores certos no Customer Insights.

1. No Customer Insights, escolha os valores dos campos correspondentes ao anexar a conta de armazenamento.

1. Continue com as etapas restantes no Customer Insights para anexar a conta de armazenamento.


[!INCLUDE [footer-include](includes/footer-banner.md)]