---
title: Exportar segmentos para o Google Ads (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Google Ads.
ms.date: 03/31/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: b7f08936d7d90322cb4e62396a2961fe06273b76
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080829"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos para o Google Ads (versão preliminar)

Exporte segmentos de perfis de cliente unificados para uma lista de público-alvo do Google Ads e use-os para criar anúncios no Pesquisa Google, Gmail, YouTube e Google Display Network. 


## <a name="prerequisites-for-connection"></a>Pré-requisitos para conexão

-   Você deve ter uma [conta do Google Ads](https://ads.google.com/) e as credenciais de administrador correspondentes.
-   Você atende aos requisitos da [Política de correspondência de clientes](https://support.google.com/adspolicy/answer/6299717).
-   Você atende aos requisitos dos [tamanhos de lista de remarketing](https://support.google.com/google-ads/answer/7558048).
-   Você deve ter [segmentos configurados](segments.md).
-   Os perfis de clientes unificados nos segmentos exportados contêm campos que representam um endereço de e-mail, telefone, ID de anunciante móvel, ID de usuário de terceiros ou endereço.

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação para o Google Ads é limitada a segmentos.
- Exportar segmentos com um total de 1 milhão de perfis de clientes pode levar até 30 minutos devido às limitações do fornecedor. 
- A correspondência no Google Ads pode levar até 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexão com o Google Ads

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Google Ads** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Autenticar com o Google Ads** e forneça suas credenciais do Google Ads.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Google Ads. Se você não vir este nome de seção, significa que não há conexões desse tipo disponíveis para você.

1. Se você quiser criar um novo público, deixe o campo ID do público-alvo do Google em branco. Vamos criar automaticamente um novo público na sua conta do Google Ads e usar o nome do segmento exportado. Se você quiser atualizar um público-alvo existente do Google Ads, insira seu [ID do público-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)

1. Na seção **Correspondência de dados**, selecione um ou mais campos de dados para exportar e selecione o campo que representa os campos de dados correspondentes no Customer Insights.

1. Selecione os segmentos que você deseja exportar. 

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). 

Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Google Ads, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Google Ads cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]
