---
title: Traga seu próprio cofre de chaves do Azure para gerenciar segredos
description: Aprenda a configurar o Customer Insights para usar seu próprio cofre de chaves do Azure.
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
ms.openlocfilehash: 418575f724090628da8bd01e2569a4cb9e646337
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376494"
---
# <a name="bring-your-own-azure-key-vault-preview"></a>Traga seu próprio cofre de chaves do Azure (versão preliminar)

Vincular um [Cofre de chaves do Azure](/azure/key-vault/general/basic-concepts) dedicado para um ambiente de insights do público-alvo para ajudar as organizações a atender aos requisitos de conformidade.
O cofre de chaves dedicado pode ser usado para preparar e usar segredos nos limites de conformidade de uma organização. As percepções do público-alvo podem usar os segredos do Azure Key Vault para [configurar conexões](connections.md) para sistemas de terceiros.

## <a name="link-the-key-vault-to-the-audience-insights-environment"></a>Vincule o cofre das chaves ao ambiente de insights do público-alvo

### <a name="prerequisites"></a>Pré-requisitos

Para configurar o cofre de chaves em insights do público, os seguintes pré-requisitos devem ser atendidos:

- Você deve ter uma assinatura ativa do Azure.

- Você tem uma função de [Administrador](permissions.md#admin) nos insights do público-alvo. Saiba mais sobre [permissões do usuário em insights do público-alvo](permissions.md#assign-roles-and-permissions).

- Você tem funções de [Contribuinte](/azure/role-based-access-control/built-in-roles#contributor) e [Administrador de acesso de usuário](/azure/role-based-access-control/built-in-roles#user-access-administrator) no cofre de chaves ou no grupo de recursos ao qual o cofre de chaves pertence. Para obter mais informações, acesse [Adicionar ou remover atribuições de função do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal). Se você não tiver a função de Administrador de Acesso de Usuário no cofre principal, você deve configurar separadamente as permissões de controle de acesso baseadas em funções para o diretor de serviços Azure para o Dynamics 365 Customer Insights. Siga os passos para [usar um diretor de serviços do Azure](connect-service-principal.md) para o cofre de chaves que deve ser vinculado.

- O cofre da chave deve ter o firewall do Key Vault **desativado**.

- O cofre da chave está na mesma [localização do Azure](https://azure.microsoft.com/global-infrastructure/geographies/#overview) que o ambiente de insights do público-alvo. A região do ambiente de insights do público-alvo está listada em **Admin** > **Sistema** > **Sobre** > **Região**.

### <a name="link-a-key-vault-to-the-environment"></a>Vincule um cofre de chaves ao ambiente

1. Vá para **Admin** > **Sistema**, e então selecione a guia **Segurança**.
1. No azulejo **Key Vault**, selecione **Configuração**.
1. Selecione uma **Assinatura**.
1. Escolha um cofre de chaves na lista suspensa **Key Vault**. Se muitos cofres de chaves estiverem aparecendo, selecione um grupo de recursos para limitar os resultados da pesquisa.
1. Aceite o aviso de **privacidade de dados e conformidade**.
1. Selecione **Salvar**.

:::image type="content" source="media/set-up-azure-key-vault.png" alt-text="Etapas para configurar um cofre de chaves vinculado em insights do público-alvo.":::

O azulejo **Key Vault** agora mostra o nome do cofre de chaves vinculado, o grupo de recursos e a assinatura. Ele está pronto para ser usado na configuração da conexão.
Para obter detalhes sobre quais permissões no cofre de chaves são concedidas aos insights do público-alvo, vá para [Permissões concedidas no cofre de chaves para insights do público-alvo](#permissions-granted-on-the-key-vault-to-audience-insights), mais adiante neste artigo.

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

## <a name="permissions-granted-on-the-key-vault-to-audience-insights"></a>Permissões concedidas no cofre de chaves para insights do público-alvo

As seguintes permissões são concedidas aos insights do público-alvo em um cofre de chaves vinculado, se a [Política de acesso ao Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou ao [Controle de acesso baseado em função do Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) estiver ativado.

### <a name="key-vault-access-policy"></a>Políticas de acesso do cofre de chaves

| Digitar        | Permissões          |
| ----------- | -------------------- |
| Tecla         | [Obter chaves](/rest/api/keyvault/get-keys), [Obter chave](/rest/api/keyvault/get-key)                                 |
| Segredo      | [Obter segredos](/rest/api/keyvault/get-secrets), [Obter segredo](/rest/api/keyvault/get-secret)                     |
| Certificado | [Obter certificados](/rest/api/keyvault/get-certificates), [Obter certificado](/rest/api/keyvault/get-certificate) |

Os valores anteriores são os mínimos para listar e ler durante a execução.

### <a name="azure-role-based-access-control"></a>Controle de acesso baseado em função do Azure

As funções Key Vault Reader e Key Vault Secrets User serão adicionadas para insights do público-alvo. Para obter detalhes sobre essas funções, vá para [Funções integradas do Azure para operações de plano de dados do Key Vault](/azure/key-vault/general/rbac-guide?tabs=azure-cli).

## <a name="recommendations"></a>Recomendações

- Use um cofre de chaves separado ou dedicado que contenha apenas os segredos necessários para os insights do público-alvo. Leia mais sobre porque os [cofres de chaves separados são recomendados](/azure/key-vault/general/best-practices#why-we-recommend-separate-key-vaults).

- Siga as [práticas recomendadas para usar o Key Vault](/azure/key-vault/general/best-practices#turn-on-logging) para controle de acesso, backup, auditoria e opções de recuperação.

## <a name="frequently-asked-questions"></a>Perguntas frequentes

### <a name="can-audience-insights-write-secrets-or-overwrite-secrets-into-the-key-vault"></a>Os insights do público-alvo podem escrever segredos ou sobrescrever segredos no cofre de chaves?

Nº Apenas as permissões de leitura e lista descritas na seção [permissões concedidas](#permissions-granted-on-the-key-vault-to-audience-insights) que aparece anteriormente neste artigo são concedidas aos insights do público-alvo. O sistema não pode adicionar, excluir ou sobrescrever segredos no cofre de chaves. Esse também é o motivo pelo qual você não pode inserir credenciais quando uma conexão usa o Key Vault.

### <a name="can-i-change-a-connection-from-using-key-vault-secrets-to-default-authentication"></a>Posso alterar uma conexão de segredos do Key Vault para autenticação padrão?

Nº Você não pode voltar para uma conexão padrão depois de configurá-la usando um segredo de um cofre de chaves vinculado. Crie uma conexão separada e exclua a antiga se não precisar mais dela.

### <a name="how-can-i-revoke-access-to-a-key-vault-for-audience-insights"></a>Como posso revogar o acesso a um cofre de chaves para obter insights do público-alvo?

Dependendo de se a [política de acesso ao Key Vault](/azure/key-vault/general/assign-access-policy?tabs=azure-portal) ou o [controle de acesso baseado em função do Azure](/azure/key-vault/general/rbac-guide?tabs=azure-cli) está habilitado, você precisa remover as permissões para o diretor de serviço`0bfc4568-a4ba-4c58-bd3e-5d3e76bd7fff` com o nome `Dynamics 365 AI for Customer Insights`. Todas as conexões que usam o cofre de chaves deixarão de funcionar.

### <a name="a-secret-thats-used-in-a-connection-got-removed-from-the-key-vault-what-can-i-do"></a>Um segredo usado em uma conexão foi removido do cofre de chaves. O que posso fazer?

Uma notificação aparece nos insights do público-alvo quando um segredo configurado do cofre de chaves não está mais acessível. Habilite [soft-delete](/azure/key-vault/general/soft-delete-overview) no cofre dechaves para restaurar segredos, caso tenham sido removidos acidentalmente.

### <a name="a-connection-doesnt-work-but-my-secret-is-in-the-key-vault-what-might-be-the-cause"></a>A conexão não funciona, mas meu segredo está no cofre de chaves. Qual pode ser a causa?

Uma notificação aparece nos insights do público-alvo quando não é possível acessar o cofre de chaves. A causa pode ser:

- As permissões para o diretor de serviços do insights de público-alvo foram removidas. Elas precisam ser restauradas manualmente.

- O firewall do cofre de chaves está ativado. O firewall deve ser desativado para tornar o cofre de chaves acessível para insights do público-alvo novamente.
