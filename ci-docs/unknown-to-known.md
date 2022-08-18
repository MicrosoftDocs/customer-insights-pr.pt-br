---
title: Personalizar suas experiências com dados sobre usuários conhecidos e desconhecidos
description: Incorpore as informações sobre usuários desconhecidos anteriormente quando souber suas identidades.
ms.date: 07/07/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 8e3477750d82f965dc2d62174fb35554d9447b7b
ms.sourcegitcommit: 52eca81c36e93d553140f5a37cf6013aaa42623a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/03/2022
ms.locfileid: "9224281"
---
# <a name="personalize-your-experiences-with-data-about-known-and-unknown-users"></a>Personalizar suas experiências com dados sobre usuários conhecidos e desconhecidos

Gerenciar dados dos clientes não é um novo desafio, mas está se tornando cada vez mais difícil à medida que os usuários navegam pelos diversos canais digitais que as marcas oferecem. Um usuário que é conhecido (autenticado) em um canal torna-se desconhecido (não autenticado) em outro se não estiver conectado. Geralmente, o problema é que os usuários não autenticados (desconhecidos) não têm uma ID comum. Ela pode ser usada para associar atributos de perfil significativos e gerar perfis unificados de cliente. O Customer Insights ajuda a resolver esse problema ingerindo dados de métodos de rastreamento em seus sistemas de origem. Consolidar perfis desconhecidos e conhecidos fornece às organizações uma visão completa dos perfis atualizados e suas transações históricas, comportamentos e dados demográficos. Ele vai além fornecendo resolução de identidades que permite que você unifique a atividade do cliente em vários canais, incluindo seu site, compras na loja, programas de fidelidade, etc.

## <a name="sample-scenario"></a>Cenário de exemplo

Vamos pensar em uma rede de cafés, que tenha uma ampla base de clientes que compram cafés e alimentos nas lojas e fazem pedidos online. Geralmente, somente os visitantes não são autenticados quando procuram os produtos, o que os torna "usuários desconhecidos". É difícil para a rede de cafés fornecer ofertas e experiências personalizadas se os usuários são desconhecidos. Por outro lado, os clientes podem entrar em suas contas e se tornar "usuários conhecidos" para a empresa ao participar de um sistema de fidelidade, o que, por sua vez, permite experiências mais personalizadas. O Customer Insights pode ajudar a rede de cafés a obter insights sobre usuários conhecidos e anteriormente desconhecidos.

Como Customer Insights, a empresa pode combinar os perfis dos clientes com dados de atividade de sessões de clientes não autenticados (desconhecidos) depois que um usuário se conecta e se torna conhecido. A rede de cafés pode trazer dados de outras fontes usando os conectores internos no Customer Insights para mesclar identidades dos clientes de vários canais.

## <a name="prerequisites"></a>Pré-requisitos

- Os dados da Web são coletados e contêm "IDs do visitante" para todos os visitantes.
- Os dados da Web contêm "IDs do usuário autenticado" para os visitantes conectados. Essas IDs são vinculadas com o sistema de fidelidade.
- Eventos de alto valor, como "Visualização de produtos" e " Finalização da Compra" são definidos e incluídos na fonte de dados, juntamente com o carimbo de data/hora do evento como uma ID de evento.

A tabela a seguir mostra um exemplo simplificado de como eventos de alto valor podem ser capturados.

|EventID|EventTimeStamp|UserID|LoyaltyID|EventName|
|--|--|--|--|--|
|0|23-07-2022 10:00:00|abc123|--|Visualização de produto|
|2|23-07-2022 10:05:00|abc123|707|Entrada no programa de fidelidade|
|3|23-07-2022 10:10:00|abc123|707|Check-out|
|4|23-07-2022 10:20:00|xyz789|--|Visualização de produto|

## <a name="data-ingestion"></a>Ingestão de dados

Os dados sobre os clientes podem ser originários de seu site como dados de um evento e podem ser armazenados localmente ou em serviços de análise de dados de terceiros. Os dados da web contêm usuários conhecidos e desconhecidos se o site tiver um fluxo de autenticação que se integre a um serviço de autenticação. Por exemplo um sistema de comércio eletrônico que exige que os usuários forneçam seus detalhes completos para a conclusão de uma transação de compra. Ou um sistema de fidelidade que exige autenticação para confirma um destinatário válido dos descontos de recompensas.

Os dados do evento em nosso exemplo acima contêm as IDs de perfil distintas dos usuários conhecidos e desconhecidos. Nos eventos 1 e 4, os usuários são desconhecidos, enquanto que, nos eventos 2 e 3, o usuário com a ID abc123 se inscreve em um programa de fidelidade.

:::image type="content" source="media/website-data-source.png" alt-text="Fontes de dados incluindo o site da Contoso.":::

Para obter mais informações sobre as opções disponíveis para a ingestão de dados, consulte [Visão geral de fontes de dados](data-sources.md).

## <a name="data-unification"></a>Unificação de dados

A conversão de identidades desconhecidas com identidades conhecidas ajuda a habilitar a personalização com base nos comportamentos do usuário, independentemente do estado de seu perfil (conhecido e desconhecido). O conteúdo personalizado para todos os usuários ajuda os clientes a obter os produtos ou serviços mais relevantes nos tenham interesse no momento.

Já que alguns dos usuários em seus dados são conhecidos, podemos usar o Customer Insights para combinar esses dados com o perfil do usuário. Para obter mais informações sobre a unificação dos perfis de cliente, consulte [Visão geral da unificação de dados](data-unification.md).

1. Selecione os campos de origem na entidade de dados da Web. Use os dados do perfil que estão armazenados em seus dados da Web e selecione os campos que representam IDs com dados demográficos.

   :::image type="content" source="media/website-source-fields.png" alt-text="Campos de origem para a fonte de dados da Web.":::

1. Adicionar regras para mesclar registros duplicados. Para dados da Web, escolha os dados mais preenchidos.

1. Configurar regras de correspondência e condições. A correspondência dos dados de eventos de perfis da Web nesse exemplo será feita nas IDS com os perfis de outras fontes de dados que contêm informações do cliente. Configure regras de correspondência exatas nas IDs como regras separadas com cada uma das outras entidades de perfil que tenham uma chave primária ou ID correspondente. No exemplo, os dados do perfil de evento da Web são usados como a última entidade correspondente para que outros dados de perfil sejam combinados primeiro.
   1. Não marcar a opção **Incluir todos os registros** cria perfis unificados para usuários conhecidos e inclui suas IDs de usuário desconhecido correspondentes. Isso é útil em cenários quando você tem interesse em exibir atividades comportamentais passadas de usuários conhecidos quando eles ainda eram desconhecidos.
   1. Marcar a opção **Incluir todos os registros** cria registros de perfil separados para usuários desconhecidos. Os usuários desconhecidos recebem uma ID de cliente exclusiva. No futuro, quando um perfil conhecido for associado a dados de perfil de eventos da Web, a jornada do usuário que acabou de se tornar conhecido poderá ser exibida e usada para personalização com base em dados comportamentais do passado também.

:::image type="content" source="media/website-match-rule.png" alt-text="Regra de correspondência para a entidade de fonte de dados do site.":::

## <a name="get-insights"></a>Obtenha insights

Se os perfis de cliente orem criados para usuários conhecidos e desconhecidos, os dados de eventos da Web de alto valor poderão ser usados como [atividades](activities.md). Essas atividades podem ser usadas para criar mais insights. Por exemplo, os clientes que visitaram um site há seis meses (quando ainda eram desconhecidos) ou os clientes que não têm uma ID de fidelidade nunca concluíram uma finalização de compra.

:::image type="content" source="media/website-known-unknown.png" alt-text="Captura de tela da página de um cliente com clientes conhecidos e desconhecidos.":::

[Enriqueça](enrichment-hub.md) seus dados, crie [medidas](measures.md) e crie [segmentos](segments.md) para ativação adicional.

Por exemplo, você pode criar segmentos de usuários conhecidos que viram alguns produtos mas nunca finalizaram a compra.

Para obter mais informações, consulte [Visão geral de segmentos](segments.md).

## <a name="activate-insights"></a>Ativar insights

Há várias maneiras de exportar seus dados e realizar ações com base nos insights subjacentes.

Para obter mais informações, consulte a [Visão geral de exportações](export-destinations.md).
