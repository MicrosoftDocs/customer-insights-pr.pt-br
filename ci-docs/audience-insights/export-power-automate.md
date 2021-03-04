---
title: Conector do Power Automate | Microsoft Docs
description: Crie fluxos no Microsoft Power Automate desde o Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: fb1df4e9ab1f78300b8ec1f8dfdfbfbac0e71447
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268810"
---
# <a name="power-automate-connector-preview"></a>Conector do Power Automate (versão prévia)

Dispare eventos específicos para ocorrerem automaticamente quando os dados forem alterados e gerencie fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Gatilhos do Power Automate

Use gatilhos para criar fluxos da nuvem e automatizar tarefas repetitivas, como notificações ou ações mais avançadas. 

- Gatilho quando uma atualização fonte de dados falhar. 
- Gatilho quando uma atualização fonte de dados for bem-sucedida.
- Gatilho quando um limite for ultrapassado em um segmento. O gatilho é limitado ao cruzamento acima do limite.
- Gatilho quando um limite for ultrapassado em uma medida de negócios. O gatilho é limitado ao cruzamento acima do limite.
- Dispare quando uma atualização completa (de fontes de dados, segmentos, medidas,...) for concluída.
- Dispare quando uma atualização do processo de unificação (mapear, corresponder, mesclar) for concluída.

[Configure seus gatilhos no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Ações do Power Automate
O conector do Power Automate fornece outras ações além dos gatilhos disponíveis. Para obter mais informações, consulte [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Criar um fluxo do Power Automate

1. Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.

1. No bloco do **Power Automate**, selecione **Configurar**.

1. O Conector do Customer Insights (versão preliminar) no Power Automate é exibido. **Entre** no Power Automate.

1. Escolha um dos gatilhos disponíveis e adicione mais etapas ao novo fluxo. Para obter mais informações, consulte [Criar um fluxo da nuvem no Power Automate](https://docs.microsoft.com/power-automate/get-started-logic-flow).

Exemplos de como usar fluxos: 
- Publique uma mensagem em um canal do Microsoft Teams se houver falha na atualização da fonte de dados. 
- Envie um email para os proprietários dos dados quando um limite em um segmento for excedido.



[!INCLUDE[footer-include](../includes/footer-banner.md)]