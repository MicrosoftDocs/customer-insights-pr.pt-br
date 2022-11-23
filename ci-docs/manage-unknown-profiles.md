---
title: Gerenciar perfis desconhecidos com o Customer Insights
description: Trabalhe com perfis de clientes desconhecidos que são criados e gerenciados no Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: andtapia
ms.author: andreatapia
manager: shellyha
ms.openlocfilehash: 0e12f64a22b93d117009fb8aee76d02a7583e699
ms.sourcegitcommit: 24627d53dcdf607baaab1cc3c299a3584c386173
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/15/2022
ms.locfileid: "9776807"
---
# <a name="manage-unknown-profiles-with-customer-insights"></a>Gerenciar perfis desconhecidos com o Customer Insights

Os usuários da Internet geralmente não são identificados ou permanecem anônimos online. Mesmo os clientes mais leais podem parecer "desconhecidos" se não estiverem conectados em diferentes dispositivos. Para muitas marcas, os usuários conhecidos ou autenticados são a minoria, apesar da crescente expectativa dos clientes em relação à personalização. Com o futuro dos cookies de terceiros provavelmente em xeque, gerenciar as preferências do usuário com base em dados primários é crucial para conseguir experiências personalizadas.

A personalização depende do quanto você sabe sobre seu cliente, e o Customer Insights ajuda você a fazer isso rastreando todos eles.  Você não precisa limitar ou interromper o uso dos dados coletados no início da jornada do cliente. O Customer Insights permite que você crie um perfil de cliente para os usuários desconhecidos com base em dados próprios. Você pode usar esse perfil para outras ações, apesar da falta de informações de contato. Importe dados próprios de fontes como a Web, dispositivos móveis ou sistemas CRM para o Customer Insights e enriqueça os perfis dos clientes de maneira contínua. À medida que você unifica mais interações, [transforma o cliente *desconhecido* em *conhecido*](unknown-to-known.md).

## <a name="sample-scenario"></a>Cenário de Exemplo

Suponha que um usuário utilize o dispositivo móvel para navegar no seu site de comércio eletrônico. O site atribui o visitante "mobile_guest123" como um identificador exclusivo, e você começa a coletar atividades comportamentais com base na atividade online dele. Por exemplo, quais páginas a pessoa visitou, quanto tempo passou nessas páginas ou em quais links clicou. Você não sabe o nome ou endereço de e-mail dele, mas esses dados ajudam a fornecer insights significativos sobre esse usuário específico às marcas. Assim, você pode usar esses insights como base na próxima vez que o usuário visitar o site. Consulte o Customer Insights para "mobile_guest123" para recuperar a lista de segmentos do usuário, como "orgânico", "clientes de pré-venda móvel", "clientes de alto valor" etc., ou recupere o perfil para criar experiências personalizadas na Web. Você também pode exportar os dados para qualquer sistema de ativação para fazer o mesmo.

## <a name="prerequisites"></a>Pré-requisitos

- Ingerir dados primários no Customer Insights
- Cada entidade tem um ID exclusivo que é definido como chave primária
- Cada entidade com uma chave primária para personalização é unificada
- O sistema de gerenciamento de conteúdo do seu site pode usar APIs (para personalização da Web com base na comunicação direta com o Customer Insights)

A tabela a seguir mostra um exemplo simplificado de como eventos de alto valor podem ser capturados.

|EventID|EventTimeStamp|UserID|PrimaryKey|EventName|
|--|--|--|--|--|
|0|09-15-2022 9:00:00|abc123|CookieID1|Visualização de produto|
|2|09-18-2022 10:05:00|abc123|CookieID1|Visualização de produto|
|3|09-18-2022 10:10:00|abc123|CookieID1|Adicionar ao carrinho|
|4|09-21-2022 09:05:00|abc123|CookieID1|Visualização de produto|

## <a name="data-ingestion"></a>Ingestão de dados

Para obter mais informações sobre as opções disponíveis para a ingestão de dados, consulte [Visão geral de fontes de dados](data-sources.md).

## <a name="data-unification"></a>Unificação de dados

Para obter mais informações sobre a unificação dos perfis de cliente, consulte [Visão geral da unificação de dados](data-unification.md).

## <a name="get-insights"></a>Obtenha insights

[Enriqueça](enrichment-hub.md) seus dados, crie [medidas](measures.md) e crie [segmentos](segments.md) para ativação adicional.

Por exemplo, você pode criar segmentos de usuários desconhecidos que navegaram nas mesmas páginas de produtos, mas nunca fizeram o check-out.

## <a name="activation"></a>Ativação

Com seus dados no Customer Insights e seus insights prontos, você pode usar o Customer Insights para personalização:

1. Use a [API OData](apis.md) para recuperar uma associação de segmento ou perfil de cliente. Consulte mais exemplos em [Exemplos de consulta OData para APIs do Customer Insights](odata-examples.md).

1. [Exporte](export-destinations.md) seus dados para seus sistemas de ativação.

Exemplo: um usuário desconhecido visita um site várias vezes e acessa páginas de produtos de vários modelos de sapatos de couro. Com esses dados disponíveis no Customer Insights, você pode incluir o usuário desconhecido no segmento de pessoas interessadas em sapatos de couro. Use esse segmento para informar a personalização da criação do seu site para visitantes recorrentes. Na próxima visita, o site vai reconhecer o usuário desconhecido e poderá oferecer um cupom de 10% em sapatos de couro.

[!INCLUDE [footer-include](includes/footer-banner.md)]
