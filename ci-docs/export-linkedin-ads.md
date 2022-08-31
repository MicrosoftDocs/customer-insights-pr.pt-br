---
title: Exportar segmentos para o LinkedIn Ads (versão preliminar)
description: Saiba como configurar a conexão e exportar para o LinkedIn Ads.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4c3928e05db0ebda262b4ad3e928ce85f70035b9
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304689"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segmentos para o LinkedIn Ads (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o LinkedIn Ads para criar públicos-alvo correspondentes. Use os públicos-alvo correspondentes para a segmentação de empresas e a segmentação de contatos.

## <a name="prerequisites"></a>Pré-requisitos

- Uma conta do [LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e as credenciais de administrador correspondentes.
- Uma [ID de conta do LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).
- [Segmentos configurados](segments.md) no Customer Insights.
- Os segmentos exportados precisam de pelo menos um campo específico, dependendo se você escolher a [segmentação de contatos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou [segmentação de empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) no LinkedIn. Os campos possíveis são listados na etapa **Correspondência de dados** ao [configurar a exportação](#configure-an-export).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 100.000 perfis de cliente por exportação para o LinkedIn Ads, o que pode levar até 10 minutos.
- Apenas segmentos. Um segmento deve conter pelo menos 300 perfis exclusivos.

## <a name="set-up-connection-to-linkedin-ads"></a>Configurar conexão com o LinkedIn Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **LinkedIn Ads**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça a ID de sua conta do LinkedIn Campaign Manager.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Autenticar com o LinkedIn** e forneça suas credenciais de administrador do LinkedIn Campaign Manager.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do LinkedIn Ads. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Escolha se deseja exportar dados para fazer a [segmentação de contatos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou a [segmentação de empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) no LinkedIn.

1. Nã seção **Correspondência de dados**, para segmentação de contato, selecione pelo menos um campo que representa o endereço de email de um cliente, ID de anúncio da Apple, ID de anúncio do Google, ID de usuário do Google ou nome e sobrenome. Se você escolher a segmentação da empresa, selecione pelo menos um campo que represente o nome da empresa, domínio de e-mail, URL da página do LinkedIn, símbolo de ação ou site.

1. Se preferir, adicione campos para definir melhor a exportação. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar. Os públicos-alvo correspondentes no LinkedIn Campaign Manager serão criados automaticamente com o nome dos segmentos que você selecionou para exportação. Cada segmento resultará em um público-alvo correspondente separado.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
