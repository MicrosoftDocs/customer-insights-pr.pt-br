---
title: Começar a usar o SDK para iOS
description: Aprenda a personalizar e executar o SDK para iOS
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: f05929435eeee9cf3f891ab18842c5861e39d5ba
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494216"
---
# <a name="get-started-with-the-ios-sdk"></a>Começar a usar o SDK para iOS

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este tutorial orienta você a instrumentalizar seu aplicativo iOS com um SDK de insights sobre engajamento do Dynamics 365 Customer Insights. Você começará a ver eventos no seu portal em cinco minutos ou antes.

## <a name="configuration-options"></a>Opções de configuração

As seguintes opções de configuração podem ser passadas para o SDK por meio do arquivo `EIConfig.plist` fornecido:

- **ingestionKey**: a chave de inserção usada para enviar eventos ao seu projeto.
- **autocollectAction**: um valor booliano para habilitar ou desabilitar a instrumentação automática do evento de ação.
- **autocollectView**: um valor booliano para habilitar ou desabilitar a instrumentação automática do evento de visualização.
- **endpointUrl**: o URL do ponto de extremidade ao qual os eventos serão direcionados.

## <a name="prerequisites"></a>Pré-requisitos

- Versão do Xcode 9 ou superior
- Versão do iOS 8.2 ou superior
- Uma chave de ingestão (consulte as instruções abaixo para obter)

## <a name="integrate-the-sdk-into-your-application"></a>Integrar o SDK em seu aplicativo

Para começar o processo, selecione o espaço de trabalho em que deseja trabalhar, selecione a plataforma móvel iOS e baixe o SDK.

- Use o alternador de espaço de trabalho no painel de navegação esquerdo para selecionar seu espaço de trabalho.

- Se você não tiver um espaço de trabalho existente, selecione **Novo Espaço de trabalho** e siga as etapas para criar um [novo espaço de trabalho](create-workspace.md).

- Após criar um espaço de trabalho, acesse **Administrador** > **Espaço de trabalho** e selecione **Guia de instalação**.

## <a name="configure-the-sdk"></a>Configurar o SDK

Após baixar o SDK, você pode trabalhar com ele no Xcode para habilitar e definir eventos. Há duas formas de fazer isso

### <a name="option-1-using-cocoapods-recommended"></a>Opção 1: usar o CocoaPods (recomendado)
O CocoaPods é um gerenciador de dependências para projetos Swift e Objective-C Cocoa. Usá-lo facilita a integração do SDK de insights de participação para iOS. O CocoaPods também permite atualizar para a versão mais recente do SDK de insights de participação. Veja como usar o CocoaPods para integrar o SDK de insights de participação em seu projeto Xcode. 

1. Instale o CocoaPods. 

1. Crie um novo arquivo chamado Podfile no diretório raiz do projeto e adicione as instruções a seguir nele. Substitua SEU_NOME_DE_PROJETO_DE_DESTINO pelo nome do seu projeto Xcode. 
```objectivec
platform :ios, '9.0'  

 target '${YOUR_TARGET_PROJECT_NAME}' do 

     use_frameworks!   

     pod 'EIObjC.framework.debug' 

     pod 'EIObjC.framework.release' 

 end 
```
A configuração do pod acima contém as versões de depuração e lançamento do SDK. Escolha o que for melhor para o seu projeto.

1. Instale o pod executando o seguinte comando:  `pod install --repo-update `

### <a name="option-2-using-download-link"></a>Opção 2: usar o link de download

1. Baixe o [SDK para iOS sobre insights de engajamento](https://download.pi.dynamics.com/sdk/EI-SDKs/ei-ios-sdk.zip) e coloque o arquivo `EIObjC.xcframework` na pasta `Frameworks`.

1. Se não existir uma pasta `Frameworks`, crie uma na pasta do projeto.

## <a name="enable-auto-instrumentation"></a>Habilitar a instrumentação automática
 
Você pode habilitar a instrumentação automaticamente facilmente sem usar códigos. Quando o projeto for executado, ele rastreará automaticamente os eventos `view` e `action` usando a chave de ingestão configurada. 

1. Atualize e inclua o arquivo `EIConfig.plist` fornecido na sua pasta de diretório do projeto para os seguintes campos:
    - ingestionKey = `"Your-Ingestion-Key"`
    - autocollectView = SIM
    - autocollectAction = SIM

2. Adicione o arquivo `EIConfig.plist` ao seu projeto no Xcode. 



Para desabilitar a instrumentação automática, atualize os seguintes campos no arquivo `EIConfig.plist` fornecido na pasta do diretório do seu projeto. 

```objectivec
'autocollectView' = NO (to disable)
'autocollectAction' = NO (to disable)
```


## <a name="implement-custom-events"></a>Implementar eventos personalizados

1. Abra o seu projeto no Xcode e navegue até as configurações **Gerais**. 
1. Adicione o `EIObjC.xcframework` ao projeto na seção "Estruturas, Bibliotecas e Conteúdo Incorporado".

1. Importe o arquivo de cabeçalho da estrutura em AppDelegate.m com o seguinte trecho:

    ```objectivec
    #import <EIObjC/EIObjC.h>
    ```

1. Inicialize o SDK de insights de engajamento no aplicativo: didFinishLaunchingWithOptions.
1. Copie o trecho do XML do **Guia de instalação**.

    ```objectivec
    NSError *error = [NSError new];
    id<EIIAnalytics> analytics = [EIAnalyticsProvider analyticsForIngestionKey:nil error:&error];
    ```

1. Rastreie um evento:

    ```objectivec
    EIEvent *event = [EIEvent new];
    event.name = @"video.log";
    [event setLongValue:320 forKey:@"duration"];
    [event setBoolValue:YES forKey:@"ad_shown"];
    [analytics trackEvent:event];
    ```

## <a name="set-user-details-for-your-event"></a>Definir detalhes de usuário para o seu evento

O SDK permite definir as informações do usuário que podem ser enviadas com cada evento. É possível especificar informações de usuário chamando a API `setUser:(nonnull EIUser *)user` no SDK.

Especificar detalhes do usuário no nível `Analytics` significa que todas as telemetrias terão essas informações. No entanto, se você especificar no nível do evento chamando a API `setUser:(nonnull EIUser *)user` no objeto EIEvent, somente esse evento específico conterá as informações.

A classe de dados `EIUser` contém estas propriedades NSString:

- **localId**: a ID local do usuário.
- **authId**: a ID do usuário autenticado.
- **authType**: o tipo de autenticação usado para obter a ID do usuário autenticado.
- **name**: o nome do usuário.
- **email**: o endereço de email do usuário.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
