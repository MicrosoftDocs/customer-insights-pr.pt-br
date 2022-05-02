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
ms.openlocfilehash: e2e7fc3033c25646693831d4c4c800d84ae6d6da
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8641748"
---
# <a name="service-limits-in-customer-insights"></a>Limite de serviço no Customer Insights

Este artigo descreve os limites internos para o serviço do Customer Insights que são projetados para garantir a confiabilidade e estabilidade do serviço. Todas as solicitações de alterações podem ser feitas através do [Fórum de ideias](https://go.microsoft.com/fwlink/?linkid=2074172). 

## <a name="customer-insights"></a>Customer Insights

| Area  | Limites  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas e previsões | 300  | O número total de [segmentos](segments.md), [medidas](measures.md) e [previsões](predictions.md) combinados não pode exceder 300.  |
| Relações | 20 níveis de profundidade nos relacionamentos de caminhos de entidades. | Ao criar [segmentos](segments.md) ou [medidas](measures.md) usando a interface do construtor, os caminhos das entidades podem ter até 20 saltos de relacionamento entre a entidade inicial e a entidade de destino.  |


[!INCLUDE [footer-include](includes/footer-banner.md)]
