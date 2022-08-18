---
title: Traga seu próprio cofre de chaves do Azure (versão preliminar)
description: Saiba como configurar o Customer Insights para usar seu próprio cofre de chaves do Azure para gerenciar segredos.
ms.date: 08/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 229fb5698a02d1d73c30442f61c7b1b5fce918bf
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246141"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Traga seu próprio cofre de chaves do Azure (versão preliminar)

Vincular um [Azure Key Vault](/azure/key-vault/general/basic-concepts) a um ambiente do Customer Insights ajuda as organizações a atender aos requisitos de conformidade.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Vincular o cofre de chaves ao ambiente do Customer Insights

Configure o cofre de chaves dedicado para preparar e usar segredos nos limites de conformidade de uma organização.

### <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura ativa do Azure.

- Uma permissão de [Administrador](permissions.md#admin) [atribuída](permissions.md#add-users) no Customer Insights.

- Funções de [Colaborador](/azure/role-based-access-control/built-in-roles#contributor) e [Administrador de Acesso de Usuário](/azure/role-based-access-control/built-in-roles#user-access-administrator) no cofre de chaves ou no grupo de recursos ao qual o cofre de chaves pertence. Para obter mais informações, acesse [Adicionar ou remover atribuições de função do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal). Se não tiver a função de Administrador de Acesso de Usuário no cofre de chaves, você deverá configurar separadamente as permissões de controle de acesso baseadas em funções para a entidade de serviço do Azure para o Dynamics 365 Customer Insights. Siga os passos para [usar um diretor de serviços do Azure](connect-service-principal.md) para o cofre de chaves que deve ser vinculado.

- O cofre de chaves deve ter o firewall do Key Vault **desabilitado**.

- O cofre de chaves está na mesma [localização do Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que o ambiente do Customer Insights. No Customer Insights, acesse **Administrador** > **Sistema** e a guia **Sobre** para exibir a região do Azure do ambiente.

### <a name="recommendations"></a>Recomendações

- [Use um cofre de chaves separado ou dedicado](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults) que contenha somente os segredos necessários para o Customer Insights.

- Siga as [práticas recomendadas para usar o Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para controle de acesso, backup, auditoria e opções de recuperação.

### <a name="link-a-key-vault-to-the-environment"></a>Vincule um cofre de chaves ao ambiente

1. Vá para **Administrador** > **Segurança** e selecione a guia **Key Vault**.
1. No azulejo **Key Vault**, selecione **Configuração**.
1. Selecione uma **Assinatura**.
1. Escolha um cofre de chaves na lista suspensa **Key Vault**. Se muitos cofres de chaves estiverem disponíveis, selecione um grupo de recursos para limitar os resultados da pesquisa.
1. Examine a [Conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.
1. Selecione **Salvar**.

O bloco **Key Vault** mostra o nome do cofre de chaves vinculado, a assinatura e o grupo de recursos. Ele está pronto para ser usado na configuração da conexão.
Para obter detalhes sobre quais permissões no cofre de chaves são concedidas ao Customer Insights, acesse [Permissões concedidas no cofre de chaves](#permissions-granted-on-the-key-vault).

## <a name="use-the-key-vault-in-the-connection-setup"></a>Use o cofre de chaves na configuração da conexão

Ao [configurar conexões](connections.md) com [sistemas de terceiros](#supported-connection-types), use os segredos do Key Vault vinculado para configurar as conexões.

1. Vá para **Administração** > **Conexões**.
1. Selecione **Adicionar uma conexão**.
1. Para os tipos de conexão suportados, uma alternância de **Usar Key Vault** está disponível, se você vinculou um cofre de chaves.
1. Em vez de inserir o segredo manualmente, escolha o nome do segredo que aponta para o valor do segredo no cofre de chaves.

   :::image type="content" source="media/use-key-vault-secret.png" alt-text="Painel de conexão com uma conexão SFTP que usa um segredo do Key Vault.":::

1. Selecione **Salvar** para criar a conexão.

## <a name="supported-connection-types"></a>Tipos de conexão suportados

As seguintes conexões de [exportação](export-destinations.md) são suportadas:

* [ActiveCampaign](export-active-campaign.md)
* [Autopilot](export-autopilot.md)
* [DotDigital](export-dotdigital.md)
* [Google Ads](export-google-ads.md)
* [Klaviyo](export-klaviyo.md)
* [LiveRamp](export-liveramp.md)
* [Marketo](export-marketo.md)
* [Omnisend](export-omnisend.md)
* [Salesforce Marketing Cloud](export-salesforce.md)
* [Sendgrid](export-sendgrid.md)
* [Sendinblue](export-sendinblue.md)
* [SFTP](export-sftp.md)

## <a name="permissions-granted-on-the-key-vault"></a>Permissões concedidas no cofre de chaves

As permissões a seguir serão concedidas ao Customer Insights em um cofre de chaves vinculado se a [política de acesso ao Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [controle de acesso baseado em função do Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) estiver ativado.

### <a name="key-vault-access-policy"></a>Políticas de acesso do cofre de chaves

| Digitar        | Permissões          |
| ----------- | -------------------- |
| Tecla         | [Obter chaves](/rest/api/keyvault/keys/get-keys/get-keys), [Obter chave](/rest/api/keyvault/keys/get-key/get-key)                                 |
| Segredo      | [Obter segredos](/rest/api/keyvault/secrets/get-secrets/get-secrets), [Obter segredo](/rest/api/keyvault/secrets/get-secret/get-secret)                     |
| Certificado | [Obter certificados](/rest/api/keyvault/certificates/get-certificates/get-certificates), [Obter certificado](/rest/api/keyvault/certificates/get-certificate/get-certificate) |

Os valores anteriores são os mínimos para listar e ler durante a execução.

### <a name="azure-role-based-access-control"></a>Controle de acesso baseado em função do Azure

As funções [Leitor do Key Vault e Usuário de Segredos do Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli) serão adicionadas ao Customer Insights.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Os Customer Insights pode escrever ou sobrescrever segredos no cofre de chaves?

Não. Somente as permissões de leitura e de lista descritas em [permissões concedidas](#permissions-granted-on-the-key-vault) são concedidas ao Customer Insights. O sistema não pode adicionar, excluir ou sobrescrever segredos no cofre de chaves. Esse também é o motivo pelo qual você não pode inserir credenciais quando uma conexão usa o Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Posso alterar uma conexão de segredos do Key Vault para autenticação padrão?

Nº Você não pode voltar para uma conexão padrão depois de configurá-la usando um segredo de um cofre de chaves vinculado. Crie uma conexão separada e exclua a antiga se não precisar mais dela.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Como posso revogar o acesso a um cofre de chaves para o Customer Insights?

Se a [política de acesso ao Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [controle de acesso baseado em função do Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) estiver habilitado, remova as permissões para a entidade de serviço `0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` com o nome `Dynamics 365 AI for Customer Insights`. Todas as conexões que usam o cofre de chaves deixarão de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Um segredo usado em uma conexão foi removido do cofre de chaves. O que posso fazer?

Uma notificação aparece no Customer Insights quando um segredo configurado do cofre de chaves não está mais acessível. Habilite [soft-delete](/azure/key-vault/general/soft-delete-overview) no cofre dechaves para restaurar segredos, caso tenham sido removidos acidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>A conexão não funciona, mas meu segredo está no cofre de chaves. Qual pode ser a causa?

Uma notificação aparece no Customer Insights quando não é possível acessar o cofre de chaves. A causa pode ser:

- As permissões para a entidade de serviço do Customer Insights foram removidas. Elas precisam ser restauradas manualmente.

- O firewall do cofre de chaves está ativado. O firewall deve ser desativado para tornar o cofre de chaves acessível para o Customer Insights novamente.
