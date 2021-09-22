---
title: Começar a usar o SDK para Android
description: Aprenda a personalizar e executar o SDK para Android
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 77e63929bbcc7ecff34a3839af525b76ec3c7f21173ddc5f8f2d69f11c25c441
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036904"
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

## <a name="step-1-integrate-the-sdk-into-your-application"></a>Etapa 1. Integrar o SDK em seu aplicativo
Para começar o processo, selecione o espaço de trabalho em que deseja trabalhar, selecione a plataforma móvel Android e baixe o SDK para Android.

- Use o alternador de espaço de trabalho no painel de navegação esquerdo para selecionar seu espaço de trabalho.

- Se você não tiver um espaço de trabalho existente, selecione **Novo Espaço de trabalho** e siga as etapas para criar um [novo espaço de trabalho](create-workspace.md).

## <a name="step-2-configure-the-sdk"></a>Etapa 2. Configurar o SDK

1. Após criar um espaço de trabalho, acesse **Administrador** > **Espaço de trabalho** e selecione **Guia de instalação**. 

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

1. Defina a configuração do SDK de insights sobre engajamento usando o arquivo `AndroidManifest.xml` localizado na pasta `manifests`. 
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

1. Habilite ou desabilite a captura automática de eventos `View` definindo o campo `autoCapture` acima como `true` ou `false`.

1. (Opcional) Outras configurações incluem definir o URL de coletor do ponto de extremidade. Elas podem ser adicionadas nos metadados da chave de ingestão no `AndroidManifest.xml`:
    ```xml
        <meta-data
            android:name="com.microsoft.engagementinsights.endpointUrl"
            android:value="https://some-endpoint-url.com" />
    ```

## <a name="step-3-initialize-the-sdk-from-mainactivity"></a>Etapa 3. Inicializar o SDK de MainActivity 

Após inicializar o SDK, você pode trabalhar com os eventos e suas propriedades no ambiente MainActivity.

    
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

### <a name="set-user-details-for-your-event-optional"></a>Definir detalhes de usuário para o seu evento (optional)

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
