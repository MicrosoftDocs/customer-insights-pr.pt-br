---
title: Limite de serviço no Dynamics 365 Customer Insights
description: Compreenda limites e restrições.
ms.date: 09/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: eb25e050b8aa768e6e1d8d4c5adce6095cccc346
ms.sourcegitcommit: 31a9b531dacd3a6465b3030c704ff5c085b7e122
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/10/2021
ms.locfileid: "7791969"
---
# <a name="service-limits-in-customer-insights-capabilities"></a>Limites de serviço em funcionalidades do Customer Insights

Este artigo descreve os limites internos para o serviço do Customer Insights que são projetados para garantir a confiabilidade e estabilidade do serviço. Todas as solicitações de alterações podem ser feitas através do [Fórum de ideias](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="audience-insights"></a>Insights do público-alvo

### <a name="service-limits-in-dynamics-365-customer-insights-audience-insights-capability"></a>Limites de serviço na funcionalidade de insights do público-alvo do Dynamics 365 Customer Insights

| Area  | Limites  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas e previsões | 300  | O número total de [segmentos](audience-insights/segments.md), [medidas](audience-insights/measures.md) e [previsões](audience-insights/predictions.md) combinados não pode exceder 300.  |
| Relações | 20 níveis de profundidade nos relacionamentos de caminhos de entidades. | Ao criar [segmentos](audience-insights/segments.md) ou [medidas](audience-insights/measures.md) usando a interface do construtor, os caminhos das entidades podem ter até 20 saltos de relacionamento entre a entidade inicial e a entidade de destino.  |


## <a name="engagement-insights"></a>Insights de participação

### <a name="workspace-and-event-quotas"></a>Cotas de espaço de trabalho e eventos

Os insights de interação são um aplicativo altamente escalonável que pode oferecer suporte a milhões de eventos por segundo. Durante a versão preliminar pública, os eventos têm um limite de volume. Também há um limite para o número de espaços de trabalho em uma organização.

### <a name="engagement-insights-limits"></a>Limites dos insights de interação

- Volume máximo de eventos por espaço de trabalho = 100 eventos por segundo

- Número máximo de espaços de trabalho por organização = 100

Quando os eventos excedem o limite, isso pode levar à perda de dados em relatórios baseados nesses eventos. Você pode [entrar em contato com o suporte](https://go.microsoft.com/fwlink/?linkid=2145734) para solicitar o aumento do volume antes de exceder limites. Trabalharemos com você para determinar sua necessidade de aumento de volume e oferecer suporte à sua solicitação.


[!INCLUDE[footer-include](includes/footer-banner.md)]
