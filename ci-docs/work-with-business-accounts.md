---
title: Comece com contas comerciais como público-alvo primário
description: Saiba sobre contas comerciais como público-alvo primário Dynamics 365 Customer Insights.
ms.date: 10/19/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.custom: intro-internal
ms.author: wimohabb
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-connections
- customerInsights
ms.openlocfilehash: f16c8ad50ed290562fa9f223a3e8c86228e5331e
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645659"
---
# <a name="work-with-business-accounts"></a>Trabalhe com contas corporativas

O Dynamics 365 Customer Insights permite configurar seu ambiente para diferentes públicos-alvo primários: clientes individuais (B2C) e contas comerciais (B2B). Em cenários B2C, os dados são centralizados em torno de indivíduos. Para B2B, os públicos-alvo primários são contas - organizações ou empresas - e contatos. Este artigo ajuda você a começar com um ambiente para contas comerciais. Ele lista as diferenças para as áreas de recursos no Customer Insights, dependendo do foco do seu ambiente. Para obter mais informações sobre as diferenças, revise os documentos das áreas de recursos. 

## <a name="create-an-environment-for-business-accounts"></a>Crie um ambiente para contas comerciais

Os administradores podem [criar um ambiente em uma organização existente](create-environment.md). Uma etapa no processo de criação de um novo ambiente solicita aos administradores o público-alvo primário do ambiente. No caso de ser o ajuste inicial após comprar uma licença, uma experiência guiada ajuda na criação do primeiro ambiente.

Daí, você pode [ingerir dados](data-sources.md) para contas comerciais e contatos relacionados como fontes de dados de todas as fontes suportadas.

Depois de unificar os dados, [especifique hierarquias de contas](relationships.md#set-up-account-hierarchies) como parte da configuração do relacionamento. Você também pode [configurar mapeamentos semânticos](semantic-mappings.md) para conectar entidades de contato e conta. 

## <a name="switch-between-primary-target-audience"></a>Alterne entre o público-alvo primário

Se sua organização mantém ambientes para clientes individuais e contas comerciais, você pode usar o alternador no painel esquerdo para escolher o público-alvo primário.

:::image type="content" source="media/switch-primary-target-audience.png" alt-text="Alternador para alterar o público-alvo primário entre clientes individuais e contas comerciais.":::

## <a name="supported-feature-areas"></a>Áreas de recurso suportadas

- [Atividades](activities.md): suporte para contas e contatos relacionados para criar atividades e exibi-las em uma linha do tempo.
- [Relacionamentos](relationships.md): o assistente de atividade ajuda a criar relacionamentos entre as entidades para que a visão da conta possa mostrar todas as atividades dos contatos. Os contatos podem ser detalhados para ver a visualização do contato e as hierarquias podem ser usadas para agregações de atividades da conta.
- [Medidas](measures.md): oferece suporte a medidas criadas a partir do construtor de medidas com um cálculo. Uma configuração opcional permite o roll-up para subcontas ao criar medidas.
- [Segmentos](segments.md): oferece suporte a segmentos criados do zero com o construtor de segmentos. Novos operadores permitem incorporar hierarquia de contas ao construir segmentos.
- [Ingestão de dados](data-sources.md): todos os recursos nesta área são iguais para contas comerciais e clientes individuais.
- [Unificação de dados](data-unification.md): todos os recursos nesta área são iguais para contas comerciais e clientes individuais.
- [Enriquecimento](enrichment-hub.md): alguns tipos de enriquecimento estão disponíveis apenas para cenários de clientes individuais, enquanto outros estão disponíveis exclusivamente para contas comerciais.
- [Previsões e modelos prontos para uso](predictions-overview.md): previsão de rotatividade transacional contém etapas adicionais para contas comerciais. Outras previsões estão disponíveis apenas para clientes individuais.
- [Ativação e exportação](export-destinations.md): as exportações estão disponíveis para contas comerciais e clientes individuais. Algumas exportações requerem configuração extra e informações de contato projetadas nos segmentos subjacentes para serem válidas para contas comerciais.
- [Configurações do sistema](system.md) e [gerenciamento de usuários](permissions.md): todos os recursos nesta área são iguais para contas comerciais e clientes individuais.

