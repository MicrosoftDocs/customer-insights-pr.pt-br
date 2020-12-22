---
title: Conector do Power Automate | Microsoft Docs
description: Crie fluxos no Microsoft Power Automate desde o Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405009"
---
# <a name="power-automate-connector-preview"></a>Conector do Power Automate (versão prévia)

Dispare eventos específicos para ocorrerem automaticamente quando os dados forem alterados e gerencie fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).

## <a name="power-automate-triggers"></a>Gatilhos do Power Automate

Você pode usar uma variedade de gatilhos que permitem criar fluxos para automatizar tarefas repetitivas, como notificações ou ações mais avançadas. 

- Gatilho quando uma atualização fonte de dados falhar. 
- Gatilho quando uma atualização fonte de dados for bem-sucedida.
- Gatilho quando um limite for ultrapassado em um segmento. O gatilho é limitado ao cruzamento acima do limite.
- Gatilho quando um limite for ultrapassado em uma medida de negócios. O gatilho é limitado ao cruzamento acima do limite.
- Dispare quando uma atualização completa (de fontes de dados, segmentos, medidas,...) for concluída.
- Dispare quando uma atualização do processo de unificação (mapear, corresponder, mesclar) for concluída.

[Configure seus gatilhos no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).

## <a name="power-automate-actions"></a>Ações do Power Automate
O conector do Power Automate fornece outras ações além dos gatilhos disponíveis. Para obter mais informações, consulte [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).

## <a name="create-a-power-automate-flow-in-audience-insights"></a>Criar um fluxo do Power Automate nos insights de público-alvo

1. Nos insights de público-alvo, vá para **Administrador** > **Sistema**.

1. Na página **Sistema**, selecione a guia **Status**.

1. Na seção **Fontes de Dados**, selecione **Fluxos** e selecione **Criar um fluxo** na lista suspensa.
   > [!div class="mx-imgBorder"]
   > ![Conector do Power Automate mostrando a ação Criar um Fluxo](media/power-automate-connector-create-flow.png "Conector do Power Automate mostrando a ação Criar um Fluxo")

1. No Power Automate, selecione um dos gatilhos disponíveis para criar seu fluxo preferido. Se estiver criando seu primeiro fluxo, você precisará se autenticar com o conector do Power Automate primeiro.
