---
title: Exemplo de SDK do Android
description: Projeto de exemplo para aprender sobre o SDK do Android
author: britl
ms.reviewer: m-hartmann
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ba51961bc7f9555d7dba5b6a21c8636011438d75cba87bc132b896841c467a33
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035812"
---
# <a name="run-the-android-sdk-sample"></a>Executar o exemplo de SDK do Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este projeto de exemplo do Android ajuda você a entender como o SDK funciona em um aplicativo. Não é preciso gravar códigos. Basta adicionar uma chave de ingestão e você poderá ver os eventos no seu espaço de trabalho imediatamente.

## <a name="prerequisites"></a>Pré-requisitos

- [Android Studio](https://developer.android.com/studio)
- [Chave de ingestão](get-started-android.md)

## <a name="download-the-android-sdk-sample"></a>Baixe o exemplo de SDK do Android

1. [Baixe o exemplo de SDK de insights de participação do Android](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sample.zip).
1. Descompacte o arquivo compactado `ei-android-sample.zip`.
1. Abra a pasta descompactada no Android Studio.
1. No arquivo `AndroidManifest.xml`, substitua a cadeia de caracteres `"Your-Ingestion-Key"` pela sua chave de ingestão do espaço de trabalho a partir dos insights de participação em **Administração** > **Espaço de Trabalho** > **Guia de instalação**. 

   > [!NOTE]
   > Não é necessário substituir a seção `${applicationId}`. Ela é preenchida automaticamente.

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.eiandroidsdk.AnalyticsContentProvider"
           android:name="microsoft.dynamics.engagementinsights.eiandroidsdk.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Selecione **Executar** para iniciar o projeto de exemplo.
1. Visualize os eventos no seu espaço de trabalho.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
