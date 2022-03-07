---
title: Gerenciar cookies e consentimento do usuário para armazenar dados do usuário no Dynamics 365 Customer Insights
description: Entenda como os cookies e o consentimento do usuário são usados para identificar os visitantes do site.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 09/27/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 018263220d4628690e9f0beb8453e58b0356d099
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228971"
---
# <a name="manage-cookies-and-user-consent"></a>Gerenciar cookies e consentimento do usuário

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

O recurso insights de participação do Dynamics 365 Customer Insights usa cookies e (`localStorage`) chaves para identificar visitantes de sites.

Cookies são pequenos arquivos que armazenam bits de informações sobre as interações de um usuário com o site. Eles são armazenados em navegadores da Web. Quando os usuários visitam um site para o qual seus usuários armazenaram cookies, o navegador envia essas informações ao servidor, que retorna informações exclusivas do usuário. Essa é a tecnologia que permite, por exemplo, a um carrinho de compras online manter itens selecionados nele, mesmo que um usuário navegue para fora do site.

## <a name="user-consent"></a>Consentimento do usuário

O [Regulamento Geral sobre a Proteção de Dados (RGPD)](/dynamics365/get-started/gdpr/) é um regulamento da União Europeia (UE) que determina como as organizações devem lidar com a privacidade e a segurança de seus usuários. Os cookies geralmente armazenam ou coletam "dados pessoais", como um identificador online, que é coberto pelo RGPD. Se a sua empresa emprega e/ou vende para titulares de dados da UE, o RGPD afeta você. [Saiba mais sobre como a Microsoft pode ajudá-lo a estar em conformidade com o RGPD](https://www.microsoft.com/trust-center/privacy/gdpr-faqs).

Para permitir que o SDK de insights de interação armazene cookies ou outras informações confidenciais, você deve especificar se os seus usuários consentiram. Isso ocorre na inicialização do SDK definindo um campo de `userConsent` na configuração.

Se você indicar que não há consentimento do usuário, o SDK não armazenará nenhum dado e não enviará eventos que possam ser usados para rastrear o comportamento do usuário. Todos os dados armazenados anteriormente serão excluídos do navegador.

Se nenhum valor de consentimento do usuário for especificado, o SDK presumirá que o usuário consentiu. Isso significa que, se você (como nosso cliente) não especificar um valor para o consentimento do usuário no SDK, os dados serão coletados. No entanto, se você especificar que o valor para o consentimento do usuário precisa ser "verdadeiro", os dados não serão coletados se um usuário recusar ou deixar de fornecer consentimento explícito.

Abaixo encontra-se um trecho de código para inicializar o SDK da Web com o consentimento do usuário:
```js
<script>
  (function(a,t,i){var e="MSEI";var s="Analytics";var o=e+"queue";a[o]=a[o]||[];var r=a[e]||function(n){var t={};t[s]={};function e(e){while(e.length){var r=e.pop();t[s][r]=function(e){return function(){a[o].push([e,n,arguments])}}(r)}}var r="track";var i="set";e([r+"Event",r+"View",r+"Action",i+"Property",i+"User","initialize","teardown"]);return t}(i.name);var n=i.name;if(!a[e]){a[n]=r[s];a[o].push(["new",n]);setTimeout(function(){var e="script";var r=t.createElement(e);r.async=1;r.src=i.src;var n=t.getElementsByTagName(e)[0];n.parentNode.insertBefore(r,n)},1)}else{a[n]=new r[s]}if(i.user){a[n].setUser(i.user)}if(i.props){for(var c in i.props){a[n].setProperty(c,i.props[c])}}a[n].initialize(i.cfg)})(window,document,{
    src:"https://download.pi.dynamics.com/sdk/web/msei-1.min.js",
    name:"EiJS",
    cfg:{
      ingestionKey:"YOUR-INGESTIONKEY",
      autoCapture:{
        view:true,
        click:true
      },
      userConsent: true
    }
  });
</script>
```

## <a name="visitor-data-storage-in-engagement-insights-capability"></a>Armazenamento de dados de visitantes no recurso de insights de interação

### <a name="cookies"></a>Biscoitos

- _msei
    - Armazena a ID do usuário anônimo. Esse cookie é definido no domínio do cliente e expira em 365 dias.

### <a name="local-storage"></a>Armazenamento local

O recurso insights de participação também faz uso de chaves (`localStorage`) para rastrear dados não confidenciais. Esses dados são totalmente armazenados no próprio navegador, sem tráfego enviado ou recebido nos seus servidores.

- *EISession.Id*
    - Armazena informações sobre a sessão de usuário em andamento, como ID da sessão, quando ela foi iniciada e quando expira.
- *EISession.Previous*
    - Armazena a URL da página visitada anteriormente na sessão atual.

As chaves no armazenamento local não expiram automaticamente e elas são redefinidas durante a próxima sessão do SDK.

## <a name="deleting-cookies"></a>Excluir cookies

Seus clientes podem excluir manualmente os cookies e as chaves de armazenamento local a qualquer momento por meio das configurações do navegador.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
