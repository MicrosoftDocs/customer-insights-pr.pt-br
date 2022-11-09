---
title: Exportar dados do Customer Insights para o HubSpot
description: Saiba como configurar a conexão e exportar para o HubSpot.
ms.date: 09/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b34f1d54fa499f6c6b80fa547a8aaf61af3b35a1
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725340"
---
# <a name="export-segments-to-hubspot-preview"></a>Exportar segmentos para o HubSpot (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o HubSpot e use-os no marketing por email.

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

- Uma [conta do HubSpot](https://www.hubspot.com/) e as credenciais de administrador correspondentes.
- [Chave de API](https://knowledge.hubspot.com/Integrations/How-do-I-get-my-HubSpot-API-key) do HubSpot.
- [Segmentos configurados](segments.md) no Customer Insights.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 100.000 perfis de clientes por exportação para o HubSpot, o que pode levar até 15 minutos para ser concluído. O número de perfis de clientes que você pode exportar para o HubSpot depende e está limitado ao seu contrato com o HubSpot.
- Apenas segmentos.

## <a name="set-up-connection-to-hubspot"></a>Configurar conexão com o HubSpot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **HubSpot** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira suas credenciais do HubSpot quando solicitado.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão com o HubSpot.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Para criar uma exportação, selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do HubSpot. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. Repita as mesmas etapas para outros campos opcionais.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
