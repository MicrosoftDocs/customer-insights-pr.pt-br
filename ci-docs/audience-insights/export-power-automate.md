---
title: Conector do Power Automate | Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dd90ef4576246b49d4a9c74005196ee9813a6744
ms.sourcegitcommit: d168a738a08adb8b4b2e410bdaa3716d7b63cc9b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2022
ms.locfileid: "8455893"
---
# <a name="power-automate-connector-preview"></a>Conector do Power Automate (versão prévia)

Dispare eventos específicos para ocorrerem automaticamente quando os dados forem alterados e gerencie fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).

## <a name="known-limitations"></a>Limitações conhecidas

- Você pode fazer no máximo 100 chamadas por 60 segundos. Você pode fazer uma chamada para o ponto de extremidade da API várias vezes usando o parâmetro $skip. [Saiba mais sobre o parâmetro $skip](/connectors/customerinsights/#get-items-from-an-entity).

## <a name="power-automate-triggers"></a>Gatilhos do Power Automate

Use gatilhos para criar fluxos da nuvem e automatizar tarefas repetitivas, como notificações ou ações mais avançadas. 

- Gatilho quando uma atualização fonte de dados falhar. 
- Gatilho quando uma atualização fonte de dados for bem-sucedida.
- Gatilho quando um limite for ultrapassado em um segmento. O gatilho é limitado ao cruzamento acima do limite.
- Gatilho quando um limite for ultrapassado em uma medida de negócios. Somente medidas de negócios sem uma dimensão contam com suporte. O gatilho é limitado ao cruzamento acima do limite.
- Acione quando uma atualização completa de (fontes de dados, segmentos, medidas, ...) for concluída.
- Dispare quando uma atualização do processo de unificação (mapear, corresponder, mesclar) for concluída.

[Configurar seus gatilhos no Power Automate.](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/)

## <a name="power-automate-actions"></a>Ações do Power Automate

O conector do Power Automate fornece outras ações além dos gatilhos disponíveis. Para obter mais informações, consulte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).

## <a name="create-a-power-automate-flow"></a>Criar um fluxo do Power Automate

1. Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.

1. No bloco do **Power Automate**, selecione **Configurar**.

1. O Conector do Customer Insights (versão preliminar) no Power Automate é exibido. **Entre** no Power Automate.

1. Escolha um dos gatilhos disponíveis e adicione mais etapas ao novo fluxo. Para obter mais informações, consulte [Criar um fluxo da nuvem no Power Automate](/power-automate/get-started-logic-flow).

Exemplos de como usar os fluxos: 
- Publique uma mensagem em um canal do Microsoft Teams se houver falha na atualização da fonte de dados. 
- Envie um email para os proprietários dos dados quando um limite em um segmento for excedido.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
