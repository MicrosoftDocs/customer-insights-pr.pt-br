---
title: Reconhecer eventos da Web de visitantes já autenticados com o recurso desconhecido a conhecido
description: O recurso desconhecido a conhecido permite que você associe eventos em um site a visitantes já autenticados.
ms.reviewer: mhart
ms.author: mkisel
author: mkisel11
ms.date: 7/15/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: overview
ms.manager: shellyha
ms.openlocfilehash: d1bbc3315b55e2ee233dc672456e0c27e4ad0fbd5937af09cc790c96ee274000
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036769"
---
# <a name="recognize-web-events-from-previously-authenticated-visitors"></a>Reconhecer eventos da Web de visitantes já autenticados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

O recurso **desconhecido a conhecido** em insights de participação permite associar eventos em um site a visitantes já autenticados. Se o recurso estiver desativado, os visitantes que fizeram a autenticação em um acesso anterior e depois saíram não serão identificados se não fizerem a autenticação novamente ao repetir o acesso. 

Por exemplo, uma pessoa acessou um site na semana passada, entrou em sua conta de usuário no site e navegou pelo catálogo de produtos. A pessoa retorna na semana seguinte para procurar mais produtos sem entrar em sua conta. O proprietário do site que usa o recurso **desconhecido a conhecido** saberia que foi a mesma pessoa que retornou e o que ela fez no site. Isso permite relatórios e análises mais precisos das atividades no site.

## <a name="enable-unknown-to-known"></a>Habilitar recurso desconhecido a conhecido

Você precisa ser um [administrador do espaço de trabalho](user-roles.md) para habilitar esse recurso. 

1. Em insights de participação, acesse **Administrador** > **Espaço de trabalho**. 
2. Selecione a guia **Configurações**.
3. Na seção **Desconhecido a conhecido**, defina o recurso como **Habilitado**.

![Habilitar recurso desconhecido a conhecido](media/U2Ktoggle.png "Habilitar recurso desconhecido a conhecido")

## <a name="adding-javascript-code-to-your-sites-tracking-snippet"></a>Adicionar código JavaScript ao trecho de rastreamento do site

Um site pode capturar **authId do usuário** com este exemplo de JavaScript usando o [SDK da Web de insights de participação](advanced-SDK-implementation.md). Para que o recurso **desconhecido a conhecido** funcione, você precisa capturar authId *e* habilitar userMapping:True em seu trecho do JavaScript como no exemplo abaixo.

```
[…]
window, document
{
src:"https://download.pi.dynamics.com/sdk/web/mspi-0.min.js",
name:"myproject",
cfg:{
ingestionKey:<paste your ingestion key>",
autoCapture:{
view:true,
click:true
},
userMapping: true
},
user:{
authId: getLoggedInUserId()*,
email: getLoggedInUserEmail()*,
authType: "MSA",
name: "Alex Jensen"
}
[…]
```

[!INCLUDE[footer-include](../includes/footer-banner.md)]
