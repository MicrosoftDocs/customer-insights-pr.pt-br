---
title: Conector do Power Automate (versão preliminar) | Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f87bd6db7143294a264813f6c5c7d7963f303628
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196104"
---
# <a name="power-automate-connector-preview"></a>Conector do Power Automate (versão prévia)

Dispare eventos específicos para ocorrerem automaticamente quando os dados forem alterados e gerencie fluxos mais complexos diretamente no [Microsoft Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitações conhecidas

- No máximo, 100 chamadas a cada 60 segundos. Use o [parâmetro $skip](/connectors/customerinsights/#get-items-from-an-entity) para chamar o ponto de extremidade de API várias vezes.

## <a name="power-automate-triggers"></a>Gatilhos do Power Automate

Use gatilhos para criar fluxos da nuvem e automatizar tarefas repetitivas, como notificações ou ações mais avançadas. Use gatilhos quando:

- Uma atualização de fonte de dados falhar.
- Uma atualização de fonte de dados for bem-sucedida.
- Um limite for ultrapassado em um segmento. O gatilho é limitado ao cruzamento acima do limite.
- Um limite for ultrapassado em uma medida de negócios. Somente medidas de negócios sem uma dimensão contam com suporte. O gatilho é limitado ao cruzamento acima do limite.
- Uma atualização completa agendada for concluída. Esse gatilho não funciona para atualizações iniciadas manualmente.
- Uma atualização do processo de unificação for concluída.

[Configurar seus gatilhos no Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Ações do Power Automate

O conector do Power Automate fornece outras ações além dos gatilhos disponíveis. Para obter mais informações, consulte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Criar um fluxo do Power Automate

1. Vá para **Administração** > **Conexões**.

1. No bloco do **Power Automate**, selecione **Configurar**.

1. O Conector do Customer Insights (versão preliminar) no Power Automate é exibido. **Entre** no Power Automate.

1. Escolha um dos gatilhos disponíveis e adicione mais etapas ao novo fluxo. Para obter mais informações, consulte [Criar um fluxo da nuvem no Power Automate](/power-automate/get-started-logic-flow).

Exemplos de como usar os fluxos: 
- Publique uma mensagem em um canal do Microsoft Teams se houver falha na atualização da fonte de dados. 
- Envie um email para os proprietários dos dados quando um limite em um segmento for excedido.

[!INCLUDE [footer-include](includes/footer-banner.md)]
