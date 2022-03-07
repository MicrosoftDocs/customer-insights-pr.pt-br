---
title: Executar a amostra de SDK do iOS
description: Projeto de amostra para saber mais sobre o SDK para iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bbe4ba648952a8081af4c8f2610276809fa5efeb
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232828"
---
# <a name="run-the-ios-sdk-sample"></a>Executar a amostra de SDK do iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

O projeto de amostra para iOS ajuda você a entender como o SDK funciona em um aplicativo. Não é preciso gravar códigos. Basta adicionar uma chave de ingestão e você poderá ver os eventos no seu espaço de trabalho imediatamente.

## <a name="prerequisites"></a>Pré-requisitos

- [Versão do Xcode 9 ou superior](https://developer.apple.com/xcode/downloads/)
- [Chave de ingestão](get-started-ios.md)

## <a name="download-the-ios-sdk-sample"></a>Baixar a amostra de SDK do iOS

1. [Baixar o SDK de amostra dos insights sobre engajamento para iOS](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sample.zip).
1. Descompacte o arquivo compactado `ei-ios-sample.zip`.
1. Abra o projeto de aplicativo de exemplo no Xcode.
1. No arquivo `EIConfig.plist`, substitua a cadeia de caracteres `“YOUR-INGESTION-KEY”` no campo `ingestionKey` pela sua chave de ingestão do espaço de trabalho nos insights sobre engajamento em **Administrador** > **Espaço de trabalho** > **Guia de instalação**.
1. Selecione **Executar** para iniciar o projeto de exemplo.
1. Visualize os eventos no seu espaço de trabalho.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
