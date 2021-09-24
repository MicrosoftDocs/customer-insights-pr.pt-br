---
title: Começar a usar o SDK para Android
description: Aprenda a personalizar e executar o SDK para Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a060ac60db71a7b0fb8c0d7a3b0e266004fbee6a
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494260"
---
# <a name="get-started-with-the-android-sdk"></a>Começar a usar o SDK para Android

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este tutorial orienta você no processo de instrumentalizar seu aplicativo Android com um SDK de insights sobre engajamento do Dynamics 365 Customer Insights. Você começará a ver eventos no seu portal em cinco minutos ou antes.

## <a name="configuration-options"></a>Opções de configuração
As seguintes opções de configuração podem ser passadas para o SDK:

- **ingestionKey**: a chave de inserção é usada para enviar eventos ao seu espaço de trabalho.

## <a name="prerequisites"></a>Pré-requisitos

- Android Studio

- Nível mínimo da API do Android: 16 (Jelly Bean)

- Uma chave de ingestão (consulte as instruções abaixo sobre como obter)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar o SDK em seu aplicativo
Para começar o processo, selecione o espaço de trabalho em que deseja trabalhar, selecione a plataforma móvel Android e baixe o SDK para Android.

- Use o alternador de espaço de trabalho no painel de navegação esquerdo para selecionar seu espaço de trabalho.

- Se você não tiver um espaço de trabalho existente, selecione **Novo Espaço de trabalho** e siga as etapas para criar um [novo espaço de trabalho](create-workspace.md).

- Após criar um espaço de trabalho, acesse **Administrador** > **Espaço de trabalho** e selecione **Guia de instalação**. 

## <a name="configure-the-sdk"></a>Configurar o SDK

Depois de baixar o SDK, você pode trabalhar com ele no Android Studio para habilitar e definir eventos. Há duas formas de fazer isso:
### <a name="option-1-using-jitpack-recommended"></a>Opção 1: usar JitPack (recomendado)
1. Adicione o repositório JitPack ao `build.gradle` raiz:
    ```gradle
    allprojects {
        repositories {
            ...
            maven { url 'https://jitpack.io' }
        }
    }
    ```

1. Adicione a dependência:
    ```gradle
    dependencies {
        implementation 'com.github.microsoft:engagementinsights-sdk-android:1.0.0'
        api 'com.google.code.gson:gson:2.8.1'
    }
    ```

### <a name="option-2-using-download-link"></a>Opção 2: usar o link de download
1. Baixe o [SDK para Android sobre insights de engajamento](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-android-sdk.zip) e coloque o arquivo `eiandroidsdk-debug.aar` na pasta `libs`.

1. Abra seu arquivo `build.gradle` de nível de projeto e adicione os seguintes trechos:
    ```gradle
    dependencies {
        implementation(name: 'eiandroidsdk-debug', ext: 'aar')
        api 'com.google.code.gson:gson:2.8.1'
    }

    repositories {
        flatDir {
            dirs 'libs'
        }
    }
    ```

1. Adicione permissão para rede e internet no arquivo `AndroidManifest.xml` localizado na pasta `manifests`. 
    ```xml
    <manifest>
        ...
        <uses-permission android:name="android.permission.INTERNET" />
        <uses-permission android:name="android.permission.ACCESS_NETWORK_STATE" />
    ```
    
1. Defina a configuração do SDK de insights de participação por meio do arquivo `AndroidManifest.xml`. 

## <a name="enable-auto-instrumentation"></a>Habilitar a instrumentação automática
1. Copie o trecho do XML do **Guia de instalação**. O campo `Your-Ingestion-Key` deve ser preenchido automaticamente.

   > [!NOTE]
   > Não é necessário substituir a seção `${applicationId}`. Ela é preenchida automaticamente.
   

   ```xml
   <application>
   ...
       <provider
           android:authorities="${applicationId}.com.microsoft.engagementinsights.AnalyticsContentProvider"
           android:name="com.microsoft.engagementinsights.AnalyticsContentProvider" />
       <meta-data
           android:name="com.microsoft.engagementinsights.ingestionKey"
           android:value="Your-Ingestion-Key" />
       <meta-data
           android:name="com.microsoft.engagementinsights.autoCapture"
           android:value="true" />
   ...
   </application>
   ```

1. Habilite ou desabilite a captura automática de eventos `View` definindo o campo `autoCapture` acima como `true` ou `false`. Atualmente, eventos `Action` precisam ser adicionados manualmente.

1. (Opcional) Outras configurações incluem definir o URL de coletor do ponto de extremidade. Elas podem ser adicionadas nos metadados da chave de ingestão no `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="implement-custom-events"></a>Implementar eventos personalizados

Depois de inicializar o SDK, você pode trabalhar com eventos e suas propriedades no ambiente `MainActivity`.

    
Java:
```java
Analytics analytics = new Analytics();
```

Kotlin:
```kotlin
var analytics = Analytics()
```

### <a name="set-property-for-all-events-optional"></a>Definir propriedade para todos os eventos (opcional)
    
Java:
```java
analytics.setProperty("year", 2021);
```

Kotlin:
```kotlin
analytics.setProperty("year", 2021)
```

Os seguintes tipos de dados têm suporte para propriedades de evento de contexto:
- Cadeia de Caracteres
- Data
- Duplo
- Longo
- Boolean
- UUID

### <a name="track-an-event"></a>Acompanhar um evento

Java:
```java
Event event = new Event("video");
event.setProperty("duration", 320);
event.setProperty("ad_shown", true);
analytics.trackEvent(event);
```

Kotlin:
```kotlin
var event = Event("video")
event.setProperty("duration", 320)
event.setProperty("ad_shown", true)
analytics.trackEvent(event)
```

## <a name="set-user-details-for-your-event-optional"></a>Definir detalhes de usuário para o seu evento (optional)

O SDK permite definir as informações do usuário que podem ser enviadas com cada evento. É possível especificar informações de usuário chamando a API `setUser(user: User)` no nível `Analytics`.

Java:
```java
User user = new User();
user.setName("testuser");
user.setEmail("abc@xyz.com");
analytics.setUser(user);
```

Kotlin:
```kotlin
var user = User()
user.name = "testuser"
user.email = "abc@xyz.com"
analytics.setUser(user)
```

A classe de dados `User` contém estas propriedades de cadeia de caracteres:

- **localId**: a ID local do usuário.
- **authId**: a ID do usuário autenticado.
- **authType**: o tipo de autenticação usado para obter o ID de usuário autenticado.
- **name**: o nome do usuário.
- **email**: o endereço de email do usuário.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
