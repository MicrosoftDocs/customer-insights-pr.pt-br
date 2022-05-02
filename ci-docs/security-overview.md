---
title: Configurações de segurança no Dynamics 365 Customer Insights
description: Saiba mais sobre configurações de segurança no Dynamics 365 Customer Insights.
ms.date: 04/28/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 5d73bacccadc9193d76d8dfafd0365dabc911e00
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653694"
---
# <a name="security-overview-page"></a>Página Visão geral de segurança

A página **Segurança** lista opções para configurar permissões de usuário e recursos que ajudam a tornar o Dynamics 365 Customer Insights mais seguro. Somente administradores podem acessar esta página. 

Vá para **Administrador** > **Segurança** para definir as configurações.

A página **Segurança** inclui as seguintes guias:
- [Usuários](#users-tab)
- [APIs](#apis-tab)
- [Cofre de chaves](#key-vault-tab)

## <a name="users-tab"></a>Guia Usuários

O acesso ao Customer Insights é restrito a usuários em sua organização que foram adicionados ao aplicativo por um administrador. A guia **Usuários** permite gerenciar o acesso do usuário e suas permissões. Para obter mais informações, consulte [Permissões de usuário](permissions.md).

## <a name="apis-tab"></a>Guia APIs

Exiba e gerencie as chaves para usar as [APIs do Customer Insights](apis.md) com os dados do seu ambiente.

Você pode criar novas chaves primárias e secundárias selecionando **Regenerar primário** ou **Regenerar secundário**. 

Para bloquear o acesso da API ao ambiente, selecione **Desabilitar**. Se as APIs estiverem desabilitadas, você poderá selecionar **Habilitar** para conceder acesso novamente.

## <a name="key-vault-tab"></a>Guia Key Vault

A guia **Key Vault** permite vincular e gerenciar seu próprio [Azure Key Vault](/azure/key-vault/general/basic-concepts) no ambiente.
O cofre de chaves dedicado pode ser usado para preparar e usar segredos nos limites de conformidade de uma organização. O Customer Insights pode usar os segredos do Azure Key Vault para [configurar conexões](connections.md) para sistemas de terceiros.

Para obter mais informações, consulte [Trazer seu próprio Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
