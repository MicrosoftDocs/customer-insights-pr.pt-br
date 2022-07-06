---
title: Traga seu próprio cofre de chaves do Azure (versão preliminar)
description: Saiba como configurar o Customer Insights para usar seu próprio cofre de chaves do Azure para gerenciar segredos.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-security
- customerInsights
ms.openlocfilehash: 8fdb131de35c7d936d2921265f03faa5682db6f6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080812"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Traga seu próprio cofre de chaves do Azure (versão preliminar)

Vincular um [cofre de chaves do Azure](/azure/key-vault/general/basic-concepts) dedicado para um ambiente do Customer Insights para ajudar organizações a atender aos requisitos de conformidade.
O cofre de chaves dedicado pode ser usado para preparar e usar segredos nos limites de conformidade de uma organização. O Customer Insights pode usar os segredos do Azure Key Vault para [configurar conexões](connections.md) para sistemas de terceiros.

## <a name="link-the-key-vault-to-the-customer-insights-environment"></a>Vincular o cofre de chaves ao ambiente do Customer Insights

### <a name="prerequisites"></a>Pré-requisitos

Para configurar o cofre de chaves no Customer Insights, atenda aos seguintes pré-requisitos:

- Você deve ter uma assinatura ativa do Azure.

- Você deve ter uma permissão de [Administrador](permissions.md#admin) no Customer Insights. Saiba mais sobre [permissões do usuário no Customer Insights](permissions.md#assign-roles-and-permissions).

- Você tem funções de [Contribuinte](/azure/role-based-access-control/built-in-roles#contributor) e [Administrador de acesso de usuário](/azure/role-based-access-control/built-in-roles#user-access-administrator) no cofre de chaves ou no grupo de recursos ao qual o cofre de chaves pertence. Para obter mais informações, acesse [Adicionar ou remover atribuições de função do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal). Se você não tiver a função de Administrador de Acesso de Usuário no cofre principal, você deve configurar separadamente as permissões de controle de acesso baseadas em funções para o diretor de serviços Azure para o Dynamics 365 Customer Insights. Siga os passos para [usar um diretor de serviços do Azure](connect-service-principal.md) para o cofre de chaves que deve ser vinculado.

- O cofre da chave deve ter o firewall do Key Vault **desativado**.

- O cofre de chaves está na mesma [localização do Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que o ambiente do Customer Insights. A região do ambiente no Customer Insights está listada em **Administrador** > **Sistema** > **Sobre** > **Região**.

### <a name="link-a-key-vault-to-the-environment"></a>Vincule um cofre de chaves ao ambiente

1. Vá para **Administrador** > **Segurança** e selecione a guia **Key Vault**.
1. No azulejo **Key Vault**, selecione **Configuração**.
1. Selecione uma **Assinatura**.
1. Escolha um cofre de chaves na lista suspensa **Key Vault**. Se muitos cofres de chaves estiverem aparecendo, selecione um grupo de recursos para limitar os resultados da pesquisa.
1. Aceite o aviso de **privacidade de dados e conformidade**.
1. Selecione **Salvar**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Etapas para configurar um cofre de chaves vinculado no Customer Insights.":::

O azulejo **Key Vault** agora mostra o nome do cofre de chaves vinculado, o grupo de recursos e a assinatura. Ele está pronto para ser usado na configuração da conexão.
Para obter detalhes sobre quais permissões no cofre de chaves são concedidas ao Customer Insights, vá para [Permissões concedidas no cofre de chaves](#permissions-granted-on-the-key-vault), mais adiante neste artigo.

## <a name="use-the-key-vault-in-the-connection-setup"></a>Use o cofre de chaves na configuração da conexão

Ao [configuar conexões](connections.md) com sistemas de terceiros, os segredos do Key Vault vinculado podem ser usados para configurar as conexões.

1. Vá para **Administração** > **Conexões**.
1. Selecione **Adicionar uma conexão**.
1. Para os tipos de conexão suportados, uma alternância de **Usar Key Vault** está disponível, se você vinculou um cofre de chaves.
1. Em vez de inserir o segredo manualmente, você pode escolher o nome do segredo que aponta para o valor do segredo no cofre de chaves.

:::image type="content" source="media/use-key-vault-secret.png" alt-text="Painel de conexão com uma conexão SFTP que usa um segredo do Key Vault.":::

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

As funções Key Vault Reader e Key Vault Secrets User serão adicionadas ao Customer Insights. Para obter detalhes sobre essas funções, vá para [Funções integradas do Azure para operações de plano de dados do Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomendações

- Use um cofre de chaves separado ou dedicado contendo apenas os segredos necessários para o Customer Insights. Leia mais sobre porque os [cofres de chaves separados são recomendados](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Siga as [práticas recomendadas para usar o Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para controle de acesso, backup, auditoria e opções de recuperação.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="can-customer-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Os Customer Insights pode escrever ou sobrescrever segredos no cofre de chaves?

Nº Apenas as permissões de leitura e lista descritas na seção [permissões concedidas](#permissions-granted-on-the-key-vault) anterior neste artigo são concedidas ao Customer Insights. O sistema não pode adicionar, excluir ou sobrescrever segredos no cofre de chaves. Esse também é o motivo pelo qual você não pode inserir credenciais quando uma conexão usa o Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Posso alterar uma conexão de segredos do Key Vault para autenticação padrão?

Nº Você não pode voltar para uma conexão padrão depois de configurá-la usando um segredo de um cofre de chaves vinculado. Crie uma conexão separada e exclua a antiga se não precisar mais dela.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-customer-insights"></a>Como posso revogar o acesso a um cofre de chaves para o Customer Insights?

Dependendo de se a [política de acesso ao Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [controle de acesso baseado em função do Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) está habilitado, você precisa remover as permissões para o diretor de serviço`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` com o nome `Dynamics 365 AI for Customer Insights`. Todas as conexões que usam o cofre de chaves deixarão de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Um segredo usado em uma conexão foi removido do cofre de chaves. O que posso fazer?

Uma notificação aparece no Customer Insights quando um segredo configurado do cofre de chaves não está mais acessível. Habilite [soft-delete](/azure/key-vault/general/soft-delete-overview) no cofre dechaves para restaurar segredos, caso tenham sido removidos acidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>A conexão não funciona, mas meu segredo está no cofre de chaves. Qual pode ser a causa?

Uma notificação aparece no Customer Insights quando não é possível acessar o cofre de chaves. A causa pode ser:

- As permissões para a entidade de serviço do Customer Insights foram removidas. Elas precisam ser restauradas manualmente.

- O firewall do cofre de chaves está ativado. O firewall deve ser desativado para tornar o cofre de chaves acessível para o Customer Insights novamente.
