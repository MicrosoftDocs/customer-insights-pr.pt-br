---
title: Configurações de segurança do Customer Insights
description: Saiba mais sobre configurações de segurança no Dynamics 365 Customer Insights.
ms.date: 06/08/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 163deb9bed4f82d742c46cace27dd128f0aca18b
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947401"
---
# <a name="security-settings-in-customer-insights"></a>Configurações de segurança do Customer Insights

A página **Segurança** lista opções para configurar permissões de usuário e recursos que ajudam a tornar o Dynamics 365 Customer Insights mais seguro. Somente administradores podem acessar esta página.

Vá para **Administrador** > **Segurança** para definir as configurações.

A página **Segurança** inclui as seguintes guias:

- [Usuários](#users-tab)
- [APIs](#apis-tab)
- [Links Privados](#private-links-tab)
- [Cofre de chaves](#key-vault-tab)
- [Acessar com segurança os dados do cliente com o Sistema de Proteção de Dados do Cliente (versão preliminar)](#securely-access-customer-data-with-customer-lockbox-preview)

## <a name="users-tab"></a>Guia Usuários

O acesso ao Customer Insights é restrito a usuários em sua organização que foram adicionados ao aplicativo por um administrador. A guia **Usuários** permite gerenciar o acesso do usuário e suas permissões. Para obter mais informações, consulte [Permissões de usuário](permissions.md).

## <a name="apis-tab"></a>Guia APIs

Exiba e gerencie as chaves para usar as [APIs do Customer Insights](apis.md) com os dados do seu ambiente.

Você pode criar novas chaves primárias e secundárias selecionando **Regenerar primário** ou **Regenerar secundário**. 

Para bloquear o acesso da API ao ambiente, selecione **Desabilitar**. Se as APIs estiverem desabilitadas, você poderá selecionar **Habilitar** para conceder acesso novamente.

## <a name="private-links-tab"></a>Guia Links Privados

O [Link Privado do Azure](/azure/private-link/private-link-overview) permite que o Customer Insights conecte-se à sua conta do Azure Data Lake Storage em um ponto de extremidade privado em sua rede virtual. Para dados em uma conta de armazenamento, que não está exposta à Internet pública, o Link Privado permite a conexão com essa rede restrita.

> [!IMPORTANT]
> Requisito mínimo de função para configurar uma conexão de Link Privado:
>
> - Customer Insights: Administrador
> - Função interna do Azure: [Colaborador da Conta de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permissões para a função personalizada do Azure: [Microsoft.Storage/storageAccounts/read e Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)
>

A configuração do Link Privado no Customer Insights é um processo de duas etapas. Primeiro, você inicia a criação de um Link Privado de **Administrador** > **Segurança** > **Links Privados** no Customer Insights. O painel **Adicionar Link Privado** lista as contas de armazenamento do seu locatário que você tem permissões para ver. Selecione a conta de armazenamento e dê consentimento para criar o Link Privado.

Em seguida, você precisa aprovar o Link Privado no lado da conta do Data Lake Storage. Abra o link apresentado na tela para aprovar o novo Link Privado.

## <a name="key-vault-tab"></a>Guia Key Vault

A guia **Key Vault** permite vincular e gerenciar seu próprio [Azure Key Vault](/azure/key-vault/general/basic-concepts) no ambiente.
O cofre de chaves dedicado pode ser usado para preparar e usar segredos nos limites de conformidade de uma organização. O Customer Insights pode usar os segredos do Azure Key Vault para [configurar conexões](connections.md) para sistemas de terceiros.

Para obter mais informações, consulte [Trazer seu próprio Azure Key Vault](use-azure-key-vault.md).

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Acessar com segurança os dados do cliente com o Sistema de Proteção de Dados do Cliente (versão preliminar)

O Customer Insights está usando a capacidade Sistema de Proteção de Dados do Cliente do Power Platform. O Sistema de Proteção de Dados do Cliente fornece uma interface para revisar e aprovar (ou rejeitar) solicitações de acesso a dados. Essas solicitações ocorrem quando o acesso aos dados do cliente é necessário para resolver um caso de suporte. Para usar esse recurso, o Customer Insights deverá ter uma conexão existente com um ambiente do Microsoft Dataverse em seu locatário.

Para obter mais informações sobre o Sistema de Proteção de Dados do Cliente, consulte o[resumo](/power-platform/admin/about-lockbox#summary) do Sistema de Proteção de Dados do Cliente do Power Platform. O artigo também descreve o [fluxo de trabalho](/power-platform/admin/about-lockbox#workflow) e a [configuração](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) necessária para habilitar o Sistema de Proteção de Dados do Cliente.

> [!IMPORTANT]
> Os administradores globais para Power Platform ou administradores do Power Platform podem aprovar as solicitações do Sistema de Proteção de Dados do Cliente emitidas para o Customer Insights.

[!INCLUDE [footer-include](includes/footer-banner.md)]
