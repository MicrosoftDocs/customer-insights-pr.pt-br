---
title: Usar perfis unificados no Dynamics 365 Marketing
description: Saiba como integrar perfis e segmentos unificados com o Dynamics 365 Marketing.
ms.date: 04/20/2022
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 45c59465771e4ad25ed36d5da1568e67b94cf994
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653695"
---
# <a name="work-with-unified-customer-profiles-in-dynamics-365-marketing"></a>Trabalhar com perfis de clientes unificados no Dynamics 365 Marketing

O [Dynamics 365 Marketing](/dynamics365/marketing/overview) eleva experiências do cliente, permitindo que você orquestre jornadas personalizadas em todos os pontos de contato para fortalecer relacionamentos e ganhar fidelidade. O aplicativo Dynamics 365 Marketing funciona perfeitamente com o Dynamics 365 Sales, Dynamics 365 Customer Insights, Microsoft Teams e outros produtos, além de permitir que você tome decisões melhores e mais rápidas usando a eficiência dos dados e da IA.

Ao conectar dados do Customer Insights ao Marketing, você pode:

- Direcione perfis e segmentos unificados do cliente. Isso permite que você envolva todos os clientes, independentemente do local de dados do cliente.
- Basear o conteúdo dinâmico (como tokens personalizados) em emails, SMS e notificações por push em medidas como status de fidelidade, data de renovação da assinatura, conta primária ou qualquer outra medida capturada no perfil do Customer Insights.
- Carregar dados do Marketing no Customer Insights e combiná-los com dados do cliente de outras fontes.
- Aplicar ferramentas de limpeza, enriquecimento e correspondência difusa a dados do Customer Insights.


## <a name="use-rich-customer-profiles-in-real-time-marketing"></a>Usar perfis de cliente avançados no marketing em tempo real

O marketing em tempo real permite criar [gatilhos personalizados](/dynamics365/marketing/real-time-marketing-custom-triggers) que iniciam jornadas do cliente com base em qualquer ação do cliente. Quanto mais personalizados os dados, mais relevantes e personalizadas serão as jornadas. É isso que torna a combinação do Marketing e do Customer Insights tão poderosa. Você pode [unificar dados](data-unification.md) de qualquer fonte e usá-los para alimentar jornadas hiperpersonalizadas do cliente.

Saiba mais: [Usar perfis e segmentos do Customer Insights no marketing em tempo real](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="use-unified-segments-with-outbound-customer-journeys"></a>Usar segmentos unificados com jornadas de saída do cliente

O Customer Insights permite refinar dados de várias fontes e combiná-los em segmentos de clientes agregados. Ao [conectar o Customer Insights ao marketing de saída](export-dynamics365-marketing.md), esses segmentos aparecerão automaticamente *e* serão atualizados automaticamente no designer da jornada do cliente.

Saiba mais: [Usar segmentos do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="pull-data-from-your-own-azure-data-lake-storage"></a>Extrair dados do seu próprio Azure Data Lake Storage

Você não estará limitado ao armazenamento em nuvem se desejar usar dados do Customer Insights com o Marketing. Se você já tiver o Azure Data Lake Storage configurado, poderá se conectar ao Customer Insights e, depois, compartilhar os dados com o aplicativo Marketing, da mesma forma que faria com uma configuração baseada em nuvem.

Saiba mais: [Habilitar o compartilhamento de dados com o Dataverse do seu próprio Azure Data Lake Storage](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview)