---
title: Cenários avançados de SDK da Web
description: Cenários avançados a serem considerados ao instrumentar seu site com um SDK.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: a083d8215f295af0884257a016b62b8c7e4ab2c7
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227184"
---
# <a name="advanced-web-sdk-instrumentation"></a>Instrumentação avançada do SDK da Web

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo orienta você pelos cenários avançados a serem considerados ao [instrumentar seu site](instrument-website.md) com um SDK de recurso de insights de participação do Dynamics 365 Customer Insights.

## <a name="setting-user-details-for-your-event"></a>Definindo os detalhes do usuário para seu evento

O SDK permite definir as informações do usuário que podem ser enviadas com cada evento. Você pode especificar os detalhes do usuário em uma propriedade chamada `user` (os dados esperados para esta propriedade são o objeto `IUser`), semelhante a `src`, `name` e `cfg` na configuração do snippet de código.

O objeto `IUser` contém as seguintes propriedades de cadeia de caracteres:

- **localId**: a ID local do usuário.
- **authId**: a ID do usuário autenticado.
- **authType**: o tipo de autenticação usado para obter a ID do usuário autenticado.
- **name**: o nome do usuário.
- **email**: o endereço de email do usuário.

O exemplo a seguir mostra um snippet de código enviando informações do usuário. Onde você vir funções precedidas por um símbolo de asterisco (*), substitua a função pela sua implementação personalizada:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    user:{
      authId: getLoggedInUserId()*,
      email: getLoggedInUserEmail()*,
      authType: "MSA",
      name: "John Doe"
    }
[…]
```

Você também pode especificar que as informações do usuário chamando a API `setUser(user: IUser)`. A telemetria enviada após chamar a API `setUser` conterá as informações do usuário.

## <a name="adding-custom-properties-for-each-event"></a>Adicionando propriedades personalizadas para cada evento

O SDK permite especificar propriedades personalizadas que podem ser enviadas com cada evento. Você pode especificar as propriedades personalizadas como um objeto contendo pares de chave/valor (o valor pode ser do tipo `string | number | boolean`). Você pode adicionar o objeto a uma propriedade chamada `props`, semelhante a `src`, `name` e `cfg` na configuração do trecho de código.

O exemplo a seguir mostra um snippet de código enviando propriedades personalizadas:

```
[…]
window, document
{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"myproject",
    cfg:{
      ingestionKey:<paste your ingestion key>",
      autoCapture:{
        view:true,
        click:true
      }
    },
    props:{
      "key_name_string": "value",
      "key_name_number": 10,
      "key_name_bool": true
    }
[…]
```

Você também pode especificar propriedades personalizadas individualmente chamando a API `setProperty(name: string, value: string | number | boolean)`.

## <a name="sending-custom-events"></a>Enviando eventos personalizados

É possível usar o SDK para enviar eventos personalizados. Você deve especificar um nome para o evento e as propriedades a serem enviadas com o evento.

O exemplo a seguir mostra um snippet de código rastreando um evento personalizado. O "NOME" é o valor na chave `name` na configuração trecho. Ele também é o nome da variável no objeto da janela em que o SDK é carregado.

```
window["NAME"].trackEvent({
    name: "event_name",
    properties: {
        "duration": 320,
        "name": "getting_started",
        "ad_shown": true
    }
});
```


[!INCLUDE[footer-include](../includes/footer-banner.md)]
