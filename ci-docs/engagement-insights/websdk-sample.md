---
title: Executar um exemplo de SDK da Web
description: Saiba como personalizar e executar um exemplo de SDK da Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 545f4a7e9660e339dee1070ad727d5d398eb6254
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606174"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Executar o exemplo de SDK da Web para o recurso de insights de interação do Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A biblioteca do SDK da Web do recurso de insights de interação é uma biblioteca JavaScript com código de exemplo que você pode usar no seu site.

## <a name="prerequisites"></a>Pré-requisitos

- Instalar o [Visual Studio Code](https://code.visualstudio.com/).
- [Instalar a extensão Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) no Visual Studio Code e se familiarizar com a execução do Live Server.
- Você deve ter um [espaço de trabalho de insights de engajamento](create-workspace.md).

## <a name="run-sample"></a>Executar exemplo

1. [Baixe o exemplo de SDK da Web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descompacte o arquivo compactado `ei_websdk_sample.zip`.

1. Abra a pasta descompactada no Visual Studio Code.

1. Acesse o portal de insights de engajamento do seu espaço de trabalho. Selecione **Admin** > **Espaço de trabalho** e daí **Guia de instalação**. Siga a primeira opção e selecione **Copiar código** para copiar o snippet de código JavaScript.

1. No arquivo `ei_websdk_sample.html`, cole o snippet de código que você acabou de copiar nesta linha:

   - <-- COLAR O SNIPPET DE CÓDIGO JAVASCRIPT DO PORTAL DE INSIGHTS DE ENGAJAMENTO AQUI ABAIXO DESTA LINHA -->

1. Abra o arquivo `ei_websdk_sample.html` usando o Live Server no Visual Studio Code selecionando **Ativar** na barra de status.

1. Ao abrir a página, um evento de exibição deve ser enviado automaticamente. Clicar em qualquer um dos botões da página enviará eventos de ação. O botão **Rastrear Eventos** também enviará eventos personalizados. Selecionar o botão **Ir para o Bing** enviará um evento de ação antes de navegar para o site do Bing.

1. Observe os eventos fluindo ao navegar para o seu espaço de trabalho. Este espaço de trabalho está associado à chave de ingestão inserida na Etapa 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
