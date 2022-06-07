---
title: Exportar dados do Customer Insights para o Gerenciador de Anúncios do Facebook (contém vídeo)
description: Saiba como configurar a conexão e exportar para o Gerenciador de Anúncios do Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f610ab1af83bfd512ec1861e7dc76ebb2eecfcbb
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645690"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a>Exportar lista de segmentos para o Gerenciador de Anúncios do Facebook (versão preliminar)

Exporte segmentos de perfis unificados de clientes para o Gerenciador de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO1aN]

## <a name="prerequisites-for-connection"></a>Pré-requisitos para conexão

- Você precisa ter uma [**Conta do Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclua uma [**Conta de negócios do Facebook**](https://business.facebook.com/).
- Você precisa ser um administrador na [**Conta do Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 10 milhão de perfis de cliente por exportação para o Facebook Ads Manager.
- A exportação para o Gerenciador de Anúncios do Facebook é limitada a segmentos.
- Crie ou atualize públicos personalizados no Facebook do tipo *lista de clientes* apenas.
- Exportar segmentos com um total de 10 milhões de perfis de clientes pode levar até 90 minutos para ser concluído.

## <a name="set-up-connection-to-facebook-ads-manager"></a>Configurar conexão com o Gerenciador de Anúncios do Facebook

Para que os usuários possam criar uma exportação, um administrador deve configurar a conexão com o serviço e permitir que os colaboradores usem essa conexão.

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Gerenciador de Anúncios do Facebook** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Autenticar com Anúncios do Facebook: 

   1. Selecione **Continuar com o Facebook** para entrar com sua conta do Facebook Ads.

   1. Conceda permissão a **ads_management** depois de autenticar com o Facebook.

   1. Selecione a Conta de Anúncios do **Facebook** na qual você deseja trabalhar.

   1. Selecione um **Público-alvo personalizado existente** na lista suspensa ou crie um **Novo público-alvo personalizado**. Para obter mais informações, consulte [**Público no Gerenciador de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).
      > [!NOTE]
      > Você só pode criar ou atualizar públicos personalizados no Facebook do tipo *lista de clientes* com esta exportação. Em alguns casos, você vê públicos-alvo de diferentes tipos na lista suspensa. A seleção de um tipo diferente de *lista de clientes* resultará em uma exportação com falha. 

1. Examine a **Conformidade e privacidade dos dados** e selecione **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**. 

1. Em **Conexão para exportação**, escolha uma conexão da seção do **Gerenciador de Anúncios do Facebook**. Se você não vir este nome de seção, significa que não há conexões desse tipo disponíveis para você.

1. No campo **Escolher identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar para o Gerenciador de Anúncios do Facebook. 

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.

1. Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.
   > [!TIP]
   > É mais provável obter uma correspondência se você selecionar **Email** como identificador principal. Adicionar identificadores adicionais pode melhorar a correspondência.

1. Selecione **Adicionar atributo** para mapear mais atributos para enviar para o Gerenciador de Anúncios do Facebook. Os atributos do Facebook Ads Manager são mapeados para os seguintes nomes amigáveis: **FN** = **Nome**, **LN** = **Sobrenome**, **FI** = **Primeira inicial**, **PHONE** = **Telefone**, **GEN** = **Gênero**, **DOB** = **Data de nascimento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal / CEP**, **COUNTRY** = **País / Região**

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). 

Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Gerenciador de Anúncios do Facebook, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Gerenciador de Anúncios do Facebook cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]