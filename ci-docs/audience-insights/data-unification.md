---
title: Unificação de dados
description: Saiba como unificar os dados ingeridos.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: bf1bbcd31333c8a557b59b001112042a1783546ab0cd2af394d8af2953a493f4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032744"
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