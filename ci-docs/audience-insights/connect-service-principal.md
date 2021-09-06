---
title: Conecte-se a uma conta do Azure Data Lake Storage usando uma entidade de serviço
description: Use uma entidade de serviço do Azure para se conectar ao seu próprio data lake.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 845d1f55eb99f2adf9b437124addec4f6d016fec
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461134"
---
# <a name="connect-to-an-azure-data-lake-storage-account-by-using-an-azure-service-principal"></a>Conecte-se a uma conta do Azure Data Lake Storage usando uma entidade de serviço do Azure
<!--note from editor: The Cloud Style Guide would have us just use "Azure Data Lake Storage" to mean the current version, unless the old version (Gen1) is mentioned. I've followed this guidance, even though it seems that our docs and Azure docs are all over the map on this.-->
As ferramentas automatizadas que usam os serviços do Azure devem sempre ter permissões restritas. Em vez de fazer com que os aplicativos entrem como um usuário totalmente privilegiado, o Azure oferece entidades de serviço. Continue lendo para saber como se conectar ao Dynamics 365 Customer Insights com uma conta do Azure Data Lake Storage usando uma entidade de serviço do Azure em vez das chaves de conta de armazenamento. 

Você pode usar a entidade de serviço para [adicionar ou editar uma pasta de Common Data Model como uma fonte de dados](connect-common-data-model.md) ou [criar ou atualizar um ambiente](get-started-paid.md).<!--note from editor: Suggested. Or it could be ", or create a new environment or update an existing one". I think "new" is implied with "create". The comma is necessary.-->

> [!IMPORTANT]
> - A conta do Data Lake Storage que usará<!--note from editor: Suggested. Or perhaps it could be "The Data Lake Storage account to which you want to give access to the service principal..."--> a entidade de serviço deve ter [namespace hierárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace).
> - Você precisa de permissões de administrador para sua assinatura do Azure para criar a entidade de serviço.

## <a name="create-an-azure-service-principal-for-customer-insights"></a>Crie uma entidade de serviço do Azure para o Customer Insights

Antes de criar uma entidade de serviço para insights sobre o público-alvo ou de participação, verifique se já existe uma em sua organização.

### <a name="look-for-an-existing-service-principal"></a>Procurar uma entidade de serviço existente

1. Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.

2. Em **Serviços do Azure**, selecione **Azure Active Directory**.

3. Em **Gerenciar**, selecione **Aplicativos Empresariais**.

4. Pesquise a Microsoft<!--note from editor: Via Microsoft Writing Style Guide.--> ID do aplicativo:
   - Insights sobre o público-alvo: `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` com o nome `Dynamics 365 AI for Customer Insights`
   - Insights de participação: `ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd` com o nome `Dynamics 365 AI for Customer Insights engagement insights`

5. Se encontrar um registro correspondente, significará que a entidade de serviço já existe. 
   
   :::image type="content" source="media/ADLS-SP-AlreadyProvisioned.png" alt-text="Captura de tela mostrando uma entidade de serviço existente.":::
   
6. Se nenhum resultado for retornado, crie uma entidade de serviço.

>[!NOTE]
>Para aproveitar todos os recursos do Dynamics 365 Customer Insights, sugerimos que você adicione os dois aplicativos à entidade de serviço.<!--note from editor: Using the note format is suggested, just so this doesn't get lost by being tucked up in the step.-->

### <a name="create-a-new-service-principal"></a>Criar uma entidade de serviço
<!--note from editor: Some general formatting notes: The MWSG wants bold for text the user enters (in addition to UI strings and the settings users select), but there's plenty of precedent for using code format for entering text in PowerShell so I didn't change that. Note that italic should be used for placeholders, but not much else.-->
1. Instale a versão mais recente do PowerShell para o Graph do Azure Active Directory. Para obter mais informações, acesse [Instalar o PowerShell para o Graph do Azure Active Directory](/powershell/azure/active-directory/install-adv2).

   1. No seu PC, pressione a tecla Windows no teclado e pesquise **Windows PowerShell** e selecione a opção **Executar como administrador**.<!--note from editor: Or should this be something like "search for **Windows PowerShell** and, if asked, select **Run as administrator**."?-->
   
   1. Na janela do PowerShell que é aberta, digite `Install-Module AzureAD`.

2. Crie a entidade de serviço para o Customer Insights com o módulo PowerShell do Azure AD.

   1. Na janela do PowerShell, digite `Connect-AzureAD -TenantId "[your tenant ID]" -AzureEnvironmentName Azure`. Substitua *"[sua ID de locatário]"*<!--note from editor: Edit okay? Or should the quotation marks stay in the command line, in which case it would be "Replace *[your tenant ID]* --> pela o ID real de seu locatário onde deseja criar a entidade de serviço. O parâmetro de nome de ambiente, `AzureEnvironmentName`, é opcional.
  
   1. Insira `New-AzureADServicePrincipal -AppId "0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff" -DisplayName "Dynamics 365 AI for Customer Insights"`. Este comando cria a entidade de serviço para insights de público-alvo no locatário selecionado. 

   1. Insira `New-AzureADServicePrincipal -AppId "ffa7d2fe-fc04-4599-9f6d-7ca06dd0c4fd" -DisplayName "Dynamics 365 AI for Customer Insights engagement insights"`. Este comando cria a entidade de serviço para insights de participação<!--note from editor: Edit okay?--> em locatários selecionados.

## <a name="grant-permissions-to-the-service-principal-to-access-the-storage-account"></a>Conceder permissões à entidade de serviço para acessar a conta de armazenamento

Acesso o portal do Azure para conceder permissões à entidade de serviço para a conta de armazenamento que você deseja usar nas insights do público-alvo.

1. Acesse o [portal administrativo do Azure](https://portal.azure.com) e faça logon em sua organização.

1. Abra a conta de armazenamento à qual deseja que a entidade de serviço para insights de público-alvo tenha acesso.

1. No painel esquerdo, selecione a opção **Controle de acesso (IAM)** e selecione **Adicionar** > **Adicionar atribuição de função**.

   :::image type="content" source="media/ADLS-SP-AddRoleAssignment.png" alt-text="Captura de tela mostrando o portal do Azure enquanto adiciona uma atribuição de função.":::

1. No painel **Adicionar atribuição de função**, defina as seguintes propriedades:
   - Função: **Colaborador de Dados do Storage Blob**
   - Atribua acesso a: **Usuário, grupo ou entidade de serviço**
   - Selecione: **IA para o Customer Insights do Dynamics 365** e **Insights de participação da IA para o Customer Insights do Dynamics 365** (as duas [entidades de serviço](#create-a-new-service-principal) criadas anteriormente neste procedimento)

1.  Selecione **Salvar**.

A propagação das alterações pode levar até 15 minutos.

## <a name="enter-the-azure-resource-id-or-the-azure-subscription-details-in-the-storage-account-attachment-to-audience-insights"></a>Insira a ID do recurso do Azure ou os detalhes da assinatura do Azure no anexo da conta de armazenamento para insights de público-alvo

Você pode<!--note from editor: Edit suggested only if this section is optional.--> anexar uma conta do Data Lake Storage em insights de público-alvo para [armazenar dados de saída](manage-environments.md) ou [usá-la como uma fonte de dados](connect-common-data-service-lake.md). Esta opção permite que você escolha entre uma abordagem baseada em recursos ou baseada em assinatura. Dependendo da abordagem escolhida, siga o procedimento descrito em uma destas seções.<!--note from editor: Suggested.-->

### <a name="resource-based-storage-account-connection"></a>Conexão de conta de armazenamento baseada em recursos

1. Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.

1. No painel esquerdo, acesse **Configurações** > **Propriedades**.

1. Copie o valor da ID do recurso da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceId.png" alt-text="Copie a ID do recurso da conta de armazenamento.":::

1. Em insights de público-alvo, insira o ID do recurso no campo do recurso exibido na tela de conexão da conta de armazenamento.

   :::image type="content" source="media/ADLS-SP-ResourceIdConnection.png" alt-text="Insira as informações de ID do recurso da conta de armazenamento.":::   

1. Continue com as etapas restantes nos insights de público-alvo para anexar a conta de armazenamento.

### <a name="subscription-based-storage-account-connection"></a>Conexão de conta de armazenamento baseada em assinatura

1. Acesse o [portal administrativo do Azure](https://portal.azure.com), entre na sua assinatura e abra a conta de armazenamento.

1. No painel esquerdo, acesse **Configurações** > **Propriedades**.

1. Revise a **Assinatura**, o **Grupo de recursos** e o **Nome** da conta de armazenamento para ter certeza de selecionar os valores corretos nos insights de público-alvo.

1. Em insights do público-alvo, selecione os valores dos campos correspondentes ao anexar a conta de armazenamento.

1. Continue com as etapas restantes nos insights de público-alvo para anexar a conta de armazenamento.


[!INCLUDE[footer-include](../includes/footer-banner.md)]