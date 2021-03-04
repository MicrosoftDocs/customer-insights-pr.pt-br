---
title: Exportar dados do Customer Insights para o Google Ads
description: Saiba como configurar a conexão com o Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ba7c82e643ea0dc1897e0954e78646932cafffa3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268948"
---
# <a name="connector-for-google-ads-preview"></a>Conector para Google Ads (versão preliminar)

Exporte segmentos de perfis de clientes unificados para a lista de públicos-alvo do Google Ads e use-os para anunciar na Pesquisa do Google, no Gmail, no YouTube e na Rede de Display do Google. 

## <a name="prerequisites"></a>Pré-requisitos

-   Você deve ter uma [conta do Google Ads](https://ads.google.com/) e as credenciais de administrador correspondentes.
-   Há públicos-alvo existentes no Google Ads e as IDs correspondentes. Para obter mais informações, consulte [públicos-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Você deve ter [segmentos configurados](segments.md)
-   Os perfis de clientes unificados nos segmentos exportados contêm campos que representam endereço de email, nome e sobrenome

## <a name="connect-to-google-ads"></a>Conectar ao Google Ads

1. Vá para **Administrador** > **Exportar destinos**.

1. Em **Google Ads**, selecione **Configurar**.

1. Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.

1. Insira sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Insira seu **[token de desenvolvedor aprovado do Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Insira sua **[ID de público-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e selecione **Conectar** para inicializar a conexão com o Google Ads.

1. Selecione **Autenticar com o Google Ads** e forneça suas credenciais do Google Ads.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Captura de tela de exportação da conexão com o Google Ads":::

1. Selecione **Próximo** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. Repita as mesmas etapas para os campos **Nome** e **Sobrenome**.

1. Selecione os segmentos que você deseja exportar. Você pode exportar até 1 milhão de perfis de clientes no total para o Google Ads.

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab). No Google Ads, agora você pode encontrar seus segmentos em [públicos-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportação para o Google Ads.
- A exportação para o Google Ads é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode levar até 5 minutos devido a limitações do provedor. 
- A correspondência no Google Ads pode levar até 48 horas.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Google Ads, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Google Ads cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]