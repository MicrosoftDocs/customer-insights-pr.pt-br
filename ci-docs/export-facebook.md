---
title: Exportar segmentos para o Gerenciador de anúncios do Facebook (versão preliminar) (contém vídeo)
description: Saiba como configurar a conexão e exportar para o Gerenciador de Anúncios do Facebook.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c7a4b1be1c959d70fad929b56452169b40e5b592
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724566"
---
# <a name="export-segments-to-facebook-ads-manager-preview"></a>Exportar segmentos para o Gerenciador de anúncios do Facebook (versão preliminar)

Exporte segmentos de perfis unificados de clientes para o Gerenciador de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclua uma [conta comercial do Facebook](https://business.facebook.com/).
- Privilégios de administrador na [conta do Facebook Ads](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).
- Os Termos de Público-alvo Personalizado precisam ser aceitos pelo usuário que configura a conexão no Customer Insights.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 10 milhões de perfis de cliente por exportação para o Gerenciador de Anúncios do Facebook, o que pode levar até 90 minutos.
- Apenas segmentos.
- A integração de anúncios do Facebook não é compatível com usuários com mais de 25 contas de anúncios.
- Tipo de *lista de cliente* do Facebook somente em [públicos-alvo personalizados](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
  > [!NOTE]
  > Em alguns casos, você poderá ver públicos-alvo personalizados de diferentes tipos na lista suspensa. Se você selecionar um tipo diferente que não seja *lista de clientes*, a exportação falhará.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurar conexão com o Gerenciador de Anúncios do Facebook

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Gerenciador de Anúncios do Facebook**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. [Permita que os colaboradores usem a conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autenticar com Anúncios do Facebook:

   1. Selecione **Continuar com o Facebook** para entrar com sua conta do Facebook Ads.

   1. Conceda permissão a **ads_management** depois de autenticar com o Facebook.

   1. Selecione a Conta de Anúncios do **Facebook** na qual você deseja trabalhar.

   1. Selecione um **Público-alvo personalizado existente** na lista suspensa ou crie um **Novo público-alvo personalizado**.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Gerenciador de Anúncios do Facebook. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. No campo **Conectar dados**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar para o Gerenciador de Anúncios do Facebook.

1. Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.
   > [!TIP]
   > É mais provável obter uma correspondência se você selecionar **Email** como identificador principal. Adicionar identificadores adicionais pode melhorar a correspondência.

1. Selecione **Adicionar atributo** para mapear mais atributos para enviar para o Gerenciador de Anúncios do Facebook. Os atributos do Facebook Ads Manager são mapeados para os seguintes nomes amigáveis: **FN** = **Nome**, **LN** = **Sobrenome**, **FI** = **Primeira inicial**, **PHONE** = **Telefone**, **GEN** = **Gênero**, **DOB** = **Data de nascimento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal / CEP**, **COUNTRY** = **País / Região**

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
