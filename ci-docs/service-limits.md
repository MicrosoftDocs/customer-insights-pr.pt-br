---
title: Limite de serviço no Dynamics 365 Customer Insights
description: Compreenda limites e restrições.
ms.date: 09/03/2021
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9bf8f03b785fb3035e3fc979a3304d4e98fd8d28
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350393"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limites de serviço em funcionalidades do Customer Insights

Este artigo descreve os limites internos para o serviço do Customer Insights que são projetados para garantir a confiabilidade e estabilidade do serviço. Todas as solicitações de alterações podem ser feitas através do [Fórum de ideias](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Insights do público-alvo

| Area  | Limites  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas e previsões | 300  | O número total de [segmentos](audience-insights/segments.md), [medidas](audience-insights/measures.md) e [previsões](audience-insights/predictions.md) combinados não pode exceder 300.  |
| Relações | 20 níveis de profundidade nos relacionamentos de caminhos de entidades. | Ao criar [segmentos](audience-insights/segments.md) ou [medidas](audience-insights/measures.md) usando a interface do construtor, os caminhos das entidades podem ter até 20 saltos de relacionamento entre a entidade inicial e a entidade de destino.  |

<!--
## Engagement insights

### Workspace and event quotas

Engagement insights is a highly scalable application that can support millions of events per second. During public preview, events have a volume threshold. There's also a limit to the number of workspaces in an organization.

### Engagement insights limits

- Maximum event volume per workspace  = 100 events per second

- Maximum number of workspaces per organization = 100

When events exceed the threshold, it can lead to loss of data in reports based on those events. You can [contact support](https://go.microsoft.com/fwlink/?linkid=2145734) to request a volume increase before you exceed limits. We'll work with you to determine your need for a volume increase and support your request.
-->

[!INCLUDE[footer-include](includes/footer-banner.md)]
