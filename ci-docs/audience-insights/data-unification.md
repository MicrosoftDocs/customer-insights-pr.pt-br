---
title: Crie uma visão unificada de seus clientes
description: Passe pelo processo de unificação de dados com seus dados para criar um único conjunto de dados mestre de perfis de clientes.
ms.date: 10/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-unify
ms.openlocfilehash: c5422c9b60c21923caf4d9dc9baeec575cba093f
ms.sourcegitcommit: bb1ca84bc38e81fb2ff2961c457384b7beb5b5fa
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "7977445"
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