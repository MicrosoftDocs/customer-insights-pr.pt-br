---
title: Limite de serviço no Customer Insights
description: Entenda os limites e as restrições no serviço SaaS do Customer Insights.
ms.date: 08/30/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: c3863b1a72fd92ddc87755699feda11371ec9214
ms.sourcegitcommit: dfba60e17ae6dc1e2e3830e6365e2c1f87230afd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9463205"
---
# <a name="service-limits-in-customer-insights"></a>Limite de serviço no Customer Insights

 O Customer Insights tem limites internos projetados para garantir a confiabilidade e a estabilidade do serviço. Todas as solicitações de alterações podem ser feitas através do [Fórum de ideias](https://go.microsoft.com/fwlink/?linkid=2074172).

## <a name="customer-insights"></a>Customer Insights

| Area  | Limites  | Notes |
|-------------|---------------------------------------------------------------------|---------------------------------------------------------------------|
| Segmentos, medidas e previsões | 300  | O número total de [segmentos](segments.md), [medidas](measures.md) e [previsões](predictions-overview.md) combinados não pode exceder 300.  |
| Relações | 20 níveis de profundidade nos relacionamentos de caminhos de entidades. | Ao criar [segmentos](segments.md) ou [medidas](measures.md) usando a interface do construtor, os caminhos das entidades podem ter até 20 saltos de relacionamento entre a entidade inicial e a entidade de destino.  |
|Ingestão de dados| As avaliações simultâneas para fontes de dados do Power Query são limitadas. | O Customer Insights tem os mesmos [limites de atualização como fluxos de dados no PowerBI.com](/power-query/power-query-online-limits#refresh-limits). |

## <a name="fair-scheduling-of-jobs"></a>Agendamento justo de trabalhos

O Customer Insights é um serviço SaaS que usa recursos compartilhados do Azure. Os clientes tendem a ter workloads de intensidade variável e em agendas diferentes. Para garantir o acesso justo aos recursos subjacentes, garantimos que os processos do sistema sejam executados em ordem justa. Exemplos de processos do sistema são os trabalhos relacionados à unificação de dados, às atualizações de segmentos ou ao cálculo de medidas. O agendamento justo protege você de enfileirar recursos se houver um pico de trabalhos solicitados. Ao mesmo tempo, o Customer Insights não garante que todos os trabalhos que você enfileirar serão processados em paralelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
