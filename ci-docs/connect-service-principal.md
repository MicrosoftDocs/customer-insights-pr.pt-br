---
title: Conecte-se a uma conta do Azure Data Lake Storage usando uma entidade de serviço do Azure
description: Use uma entidade de serviço do Azure para se conectar ao seu próprio data lake.
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: eba10068c48db5c147100c25a397bcc13b014784
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304183"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conecte-se a uma conta do Azure Data Lake Storage usando uma entidade de serviço do Azure

O Dynamics 365 Customer Insights fornece uma opção para se conectar a uma conta do Azure Data Lake Storage usando uma entidade de serviço do Azure em vez de chaves de conta de armazenamento.

As ferramentas automatizadas que usam os serviços do Azure devem ter permissões restritas. Em vez de fazer com que os aplicativos entrem como um usuário totalmente privilegiado, o Azure oferece entidades de serviço. Use entidades de serviço para [adicionar ou editar uma pasta do Common Data Model como uma fonte de dados](connect-common-data-model.md) ou [criar ou atualizar um ambiente](create-environment.md) com segurança.

## <a name="prerequisites"></a>Pré-requisitos

- A conta do Data Lake Storage que usará a entidade de segurança do serviço deve ser Gen2. As contas de armazenamento do Azure Data Lake Gen1 não têm suporte.
- A conta do Data Lake Storage tem o recurso [namespace hierárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace).
- Permissões de administrador para seu locatário do Azure, se você precisar criar uma entidade de serviço.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crie uma entidade de serviço do Azure para o Customer Insights

Antes de criar uma nova entidade de serviço para o Customer Insights, verifique se ela já existe na sua organização. Na maioria dos casos, já existe.

### <a name="look-for-an-existing-service-principal"></a>Procurar uma entidade de serviço existente

1. Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.

2. Em **Serviços do Azure**, selecione **Azure Active Directory**.

3. Em **Gerenciar**, selecione **Aplicativo da Microsoft**.

4. Adicione um filtro para **A ID do aplicativo começa com** `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` ou procure o nome `Dynamics 365 AI for Customer Insights`.

5. Se encontrar um registro correspondente, significará que a entidade de serviço já existe. [Conceder permissões](#grant-permissions-to-the-service-principal-to-access-the-storage-account) para a entidade de serviço para acessar a conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de tela mostrando uma entidade de serviço existente.":::

6. Se nenhum resultado for retornado, [crie uma entidade de serviço](#create-a-new-service-principal).

### <a name="create-a-new-service-principal"></a>Criar uma entidade de serviço

1. Instale a versão mais recente do PowerShell para o Graph do Azure Active Directory. Para obter mais informações, acesse [Instalar o PowerShell para o Graph do Azure Active Directory](/powershell/azure/active-directory/install-adv2).

   1. No seu PC, pressione a tecla Windows no teclado, procure por **Windows PowerShell** e selecione **Executar como administrador**.

   1. Na janela do PowerShell que é aberta, digite `Install-Module AzureAD`.

2. Crie a entidade de serviço para o Customer Insights com o módulo PowerShell do Azure AD.

   1. Na janela do PowerShell, digite `Connect-AzureAD -TenantId "[your Directory ID]" -AzureEnvironmentName Azure`. Substitua *[sua ID de Diretório]* pela ID de Diretório real da assinatura do Azure na qual você deseja criar a entidade de serviço. O parâmetro de nome de ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Insira `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando cria a entidade de serviço para o Customer Insights na assinatura do Azure selecionada.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceder permissões à entidade de serviço para acessar a conta de armazenamento

Para conceder permissões à entidade de serviço para a conta de armazenamento que você deseja usar no Customer Insights, uma das seguintes funções deve ser atribuída à conta de armazenamento ou contêiner:

|Credencial|Requisitos|
|----------|------------|
|Usuário conectado no momento|**Função**: Leitor de Dados de Blob de Armazenamento, Colaborador de Blob de Armazenamento ou Proprietário de Blob de Armazenamento.<br>**Nível**: permissões concedidas na conta de armazenamento ou no contêiner.</br>|
|Entidade de Serviço do Customer Insights -<br>Uso do Azure Data Lake Storage como fonte de dados</br>|Opção 1<ul><li>**Função**: Leitor de Dados de Blob de Armazenamento, Colaborador de Dados de Blob de Armazenamento ou Proprietário de Dados de Blob de Armazenamento.</li><li>**Nível**: permissões concedidas na conta de armazenamento.</li></ul>Opção 2 *(sem compartilhamento de acesso de Entidade de Serviço à conta de armazenamento)*<ul><li>**Função 1**: Leitor de Dados de Blob de Armazenamento, Colaborador de Dados de Blob de Armazenamento ou Proprietário de Dados de Blob de Armazenamento.</li><li>**Nível**: permissões concedidas no contêiner.</li><li>**Função 2**: Delegante de Dados do Blob de Armazenamento.</li><li>**Nível**: permissões concedidas na conta de armazenamento.</li></ul>|
|Entidade de Serviço do Customer Insights - <br>Uso do Azure Data Lake Storage como saída ou destino</br>|Opção 1<ul><li>**Função**: Colaborador de Blob de Armazenamento ou Proprietário de Blob de Armazenamento.</li><li>**Nível**: permissões concedidas na conta de armazenamento.</li></ul>Opção 2 *(sem compartilhamento de acesso de Entidade de Serviço à conta de armazenamento)*<ul><li>**Função**: Colaborador de Blob de Armazenamento ou Proprietário de Blob de Armazenamento.</li><li>**Nível**: permissões concedidas no contêiner.</li><li>**Função 2**: Delegante do Blob de Armazenamento.</li><li>**Nível**: permissões concedidas na conta de armazenamento.</li></ul>|

1. Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.

1. Abra a conta de armazenamento à qual você deseja que a entidade de serviço do Customer Insights tenha acesso.

1. No painel esquerdo, selecione a opção **Controle de acesso (IAM)** e selecione **Adicionar** > **Adicionar atribuição de função**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de tela mostrando o portal do Azure enquanto adiciona uma atribuição de função.":::

1. No painel **Adicionar atribuição de função**, defina as seguintes propriedades:
   - **Função**: Leitor de Dados de Blob de Armazenamento, Colaborador de Dados de Blob de Armazenamento ou Proprietário de Blob de Armazenamento com base nas credenciais listadas acima.
   - **Atribua acesso a**: **Usuário, grupo ou entidade de serviço**
   - **Selecione** membros: **Dynamics 365 AI for Customer Insights** (a [entidade de serviço](#create-a-new-service-principal) pesquisada anteriormente neste procedimento)

1. Selecione **Revisar + atribuir**.

A propagação das alterações pode levar até 15 minutos.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-customer-insights"></a>Insira a ID do recurso do Azure ou os detalhes da assinatura do Azure no anexo da conta de armazenamento para o Customer Insights

Anexe uma conta do Data Lake Storage em insights no Customer Insights para [armazenar dados de saída](manage-environments.md) ou [usá-la como uma fonte de dados](connect-dataverse-managed-lake.md). Escolha entre uma abordagem [baseada em recursos](#resource-based-storage-account-connection) ou uma abordagem [baseada em assinaturas](#subscription-based-storage-account-connection) e siga essas etapas.

### <a name="resource-based-storage-account-connection"></a>Conexão de conta de armazenamento baseada em recursos

1. Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.

1. No painel à esquerda, acesse **Configurações** > **Pontos de Extremidade**.

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
