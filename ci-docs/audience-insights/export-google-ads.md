---
title: Exportar dados do Customer Insights para o Google Ads
description: Saiba como configurar a conexão e exportar para o Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f4c094e486577d00d8c0c64e8527829820b335f6
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759679"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos para o Google Ads (versão preliminar)

Exporte segmentos de perfis de clientes unificados para a lista de públicos-alvo do Google Ads e use-os para anunciar na Pesquisa do Google, no Gmail, no YouTube e na Rede de Display do Google. 

## <a name="prerequisites-for-connection"></a>Pré-requisitos para conexão

-   Você deve ter uma [conta do Google Ads](https://ads.google.com/) e as credenciais de administrador correspondentes.
-   Você deve ter um [token de Desenvolvedor do Google Ads aprovado](https://developers.google.com/google-ads/api/docs/first-call/dev-token) 
-   Você deve atender aos requisitos da [Política de Correspondência de Clientes](https://support.google.com/adspolicy/answer/6299717)
-   Você deve atender aos requisitos dos [tamanhos de listas de remarketing](https://support.google.com/google-ads/answer/7558048) 

-   Há públicos-alvo existentes no Google Ads e as IDs correspondentes. Para obter mais informações, consulte [públicos-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).
-   Você deve ter [segmentos configurados](segments.md)
-   Os perfis de clientes unificados nos segmentos exportados contêm campos que representam endereço de email, nome e sobrenome

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportação para o Google Ads.
- A exportação para o Google Ads é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode levar até 5 minutos devido a limitações do provedor. 
- A correspondência no Google Ads pode levar até 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexão com o Google Ads

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Google Ads** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.

1. Insira seu **[token de desenvolvedor aprovado do Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Autenticar com o Google Ads** e forneça suas credenciais do Google Ads.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Google Ads. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira sua **[ID de público-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e selecione **Conectar** para inicializar a conexão com o Google Ads.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. Repita as mesmas etapas para os campos **Nome** e **Sobrenome**.

1. Selecione os segmentos que você deseja exportar. Você pode exportar até 1 milhão de perfis de clientes no total para o Google Ads.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Google Ads, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Google Ads cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
