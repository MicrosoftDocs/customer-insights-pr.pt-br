---
title: Definir configurações de segurança
description: Saiba mais sobre configurações de segurança no Dynamics 365 Customer Insights.
ms.date: 08/02/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: d20d57e9b7724e9921f9341eeaa39141b4555ff1
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387235"
---
# <a name="configure-security-settings"></a>Definir configurações de segurança

Gerencie chaves de API, acesse dados do cliente e configure um Link Privado do Azure.

## <a name="manage-api-keys"></a>Gerenciar chaves de API

Exiba e gerencie as chaves para usar as [APIs do Customer Insights](apis.md) com os dados em seu ambiente.

1. Acesse **Administrador** > **Segurança** e selecione a guia **APIs**.

1. Se o acesso da API ao ambiente não tiver sido configurado, selecione **Habilitar**. Ou, para bloquear o acesso da API ao ambiente, selecione **Desabilitar** e confirme.

1. Gerencie as chaves de API primária e secundária:

   1. Para mostrar a chave de API primária ou secundária, selecione o símbolo **Mostrar**.

   1. Para copiar a chave de API primária ou secundária, selecione o símbolo **Copiar**.

   1. Para criar chaves de API primárias ou secundárias, selecione **Regenerar primária** ou **Regenerar secundária**.

## <a name="securely-access-customer-data-with-customer-lockbox-preview"></a>Acessar com segurança os dados do cliente com o Sistema de Proteção de Dados do Cliente (versão preliminar)

O Customer Insights usa a capacidade Sistema de Proteção de Dados do Cliente do Power Platform. O Sistema de Proteção de Dados do Cliente fornece uma interface para revisar e aprovar (ou rejeitar) solicitações de acesso a dados. Essas solicitações ocorrem quando o acesso aos dados do cliente é necessário para resolver um caso de suporte. Para usar esse recurso, o Customer Insights deverá ter uma conexão existente com um ambiente do Microsoft Dataverse em seu locatário.

Para obter mais informações sobre o Sistema de Proteção de Dados do Cliente, consulte o[resumo](/power-platform/admin/about-lockbox#summary) do Sistema de Proteção de Dados do Cliente do Power Platform. O artigo também descreve o [fluxo de trabalho](/power-platform/admin/about-lockbox#workflow) e a [configuração](/power-platform/admin/about-lockbox#enable-the-lockbox-policy) necessária para habilitar o Sistema de Proteção de Dados do Cliente.

> [!IMPORTANT]
> Os administradores globais para Power Platform ou administradores do Power Platform podem aprovar as solicitações do Sistema de Proteção de Dados do Cliente emitidas para o Customer Insights.

## <a name="set-up-an-azure-private-link"></a>Configurar um Link Privado do Azure

O [Link Privado do Azure](/azure/private-link/private-link-overview) permite que o Customer Insights conecte-se à sua conta do Azure Data Lake Storage em um ponto de extremidade privado em sua rede virtual. Para dados em uma conta de armazenamento, que não está exposta à Internet pública, o Link Privado permite a conexão com essa rede restrita.

> [!IMPORTANT]
> Requisito mínimo de função para configurar uma conexão de Link Privado:
>
> - Customer Insights: Administrador
> - Função interna do Azure: [Colaborador da Conta de Armazenamento](/azure/role-based-access-control/built-in-roles#storage-account-contributor)
> - Permissões para a função personalizada do Azure: [Microsoft.Storage/storageAccounts/read e Microsoft.Storage/storageAccounts/PrivateEndpointConnectionsApproval/action](/azure/role-based-access-control/resource-provider-operations#microsoftstorage)

1. No Customer Insights, acesse **Administrador** > **Segurança** e selecione a guia **Links Privados**.

1. Selecione **Adicionar Link Privado**.

   O painel **Adicionar Link Privado** lista as contas de armazenamento do seu locatário que você tem permissões para ver.

1. Selecione a assinatura, o grupo de recursos e a conta de armazenamento.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Salvar**.

1. Acesse sua conta do Data Lake Storage e abra o link apresentado na tela.

1. Aprove o Link Privado.


[!INCLUDE [footer-include](includes/footer-banner.md)]
