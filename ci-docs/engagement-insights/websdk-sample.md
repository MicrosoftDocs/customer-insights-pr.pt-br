---
title: Executar um exemplo de SDK da Web
description: Saiba como personalizar e executar um exemplo de SDK da Web.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 10/30/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 97e50a51231bcf05f3e381397f0cf41e49afc10e3c3674d7c709c8f521979e12
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036589"
---
# <a name="run-the-web-sdk-sample-for-dynamics-365-customer-insights-engagement-insights-capability"></a>Executar o exemplo de SDK da Web para o recurso de insights de interação do Dynamics 365 Customer Insights

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A biblioteca do SDK da Web do recurso de insights de interação é uma biblioteca JavaScript com código de exemplo que você pode usar no seu site.

## <a name="prerequisites"></a>Pré-requisitos

- Instalar o [Visual Studio Code](https://code.visualstudio.com/).
- [Instalar a extensão Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) no Visual Studio Code e se familiarizar com a execução do Live Server.
- Ter a [chave de ingestão](instrument-website.md).

## <a name="run-sample"></a>Executar exemplo

1. [Baixe o exemplo de SDK da Web](https://download.pi.dynamics.com/sdk/EngagementInsightsSamples/ei_websdk_sample.zip).

1. Descompacte o arquivo compactado `ei_websdk_sample.zip`.

1. Abra a pasta descompactada no Visual Studio Code.

1. No arquivo `ei_websdk_sample.html`, substitua a cadeia de caracteres “INGESTION_KEY” pela sua chave de ingestão do portal do recurso de insights de interação, e a cadeia de caracteres “NAME” pelo nome global no qual você deseja que o SDK seja instanciado. Substitua todas as ocorrências.

1. Abra o arquivo `ei_websdk_sample.html` usando o Live Server no Visual Studio Code selecionando **Ativar** na barra de status.

1. Ao abrir a página, um evento de exibição deve ser enviado automaticamente. Clicar em qualquer um dos botões da página enviará eventos de ação. O botão **Rastrear Eventos** também enviará eventos personalizados. Selecionar o botão **Ir para o Bing** enviará um evento de ação antes de navegar para o site do Bing.

1. Observe os eventos fluindo ao navegar para o seu espaço de trabalho. Este espaço de trabalho está associado à chave de ingestão inserida na Etapa 4.


[!INCLUDE[footer-include](../includes/footer-banner.md)]