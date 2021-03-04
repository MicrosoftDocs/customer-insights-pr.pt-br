---
title: Unificação de dados
description: Saiba como unificar os dados ingeridos.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 44f97696ec91dc488dd6a7528e186abb99c8288b
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269638"
---
# <a name="data-unification-overview"></a>Visão geral da unificação de dados

Após a [configuração das fontes de dados](data-sources.md), você pode unificar os dados. A unificação de dados inclui três etapas: **Mapear**, **Corresponder** e **Mesclar**.

O processo de unificação de dados permite unificar fontes de dados antes díspares em um único conjunto de dados mestre que fornece uma visão unificada de seus clientes. Os estágios de unificação são obrigatórios e executados na seguinte ordem:

1. [Mapa](map-entities.md)
2. [Corresponder](match-entities.md)
3. [Mesclar](merge-entities.md)

Depois de concluir a unificação de dados, como opção você pode

- [configurar relacionamentos entre entidades](relationships.md) para criar segmentos sofisticados
- [enriquecer seus dados](enrichment-hub.md) para obter um intervalo maior de informações sobre seus clientes
- [definir atividades](activities.md) a partir de alguns dos atributos ingeridos


[!INCLUDE[footer-include](../includes/footer-banner.md)]