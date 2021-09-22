---
title: Executar a amostra de SDK do iOS
description: Projeto de amostra para saber mais sobre o SDK para iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 053e626d06d3e17b39b448987410058e45e8ae0385f3ecdef40314cb46ae4bf4
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036814"
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
