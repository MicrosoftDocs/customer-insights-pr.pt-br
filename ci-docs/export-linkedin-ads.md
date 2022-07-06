---
title: Exportar segmentos para o LinkedIn Ads (versão preliminar)
description: Saiba como configurar a conexão e exportar para o LinkedIn Ads.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e6ad3901f7b8dc1ae8edc54c0b09a99b01be34cd
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050842"
---
# <a name="export-segments-to-linkedin-ads-preview"></a>Exportar segmentos para o LinkedIn Ads (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o LinkedIn Ads para criar públicos-alvo correspondentes. Use os públicos-alvo correspondentes para a segmentação de empresas e a segmentação de contatos.

## <a name="prerequisites"></a>Pré-requisitos

-   Você deve ter uma [conta do LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e as credenciais de administrador correspondentes.
-   Você tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis de cliente nos segmentos exportados contêm um campo com um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Seu segmento no Customer Insights precisa conter pelo menos 300 perfis exclusivos. 
- Você pode exportar até 100.000 perfis de clientes por exportação para o LinkedIn Ads.
- A exportação para o LinkedIn Ads está limitada a segmentos.
- Exportar até 100.000 perfis de clientes para o LinkedIn Ads pode levar até 10 minutos para ser concluído. 

## <a name="set-up-the-connection-to-linkedin-ads"></a>Configurar a conexão ao LinkedIn Ads

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **LinkedIn Ads** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça sua [ID da conta do LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o Monitor de Campanha.

1. Selecione **Autenticar com o LinkedIn** e forneça suas credenciais de administrador do LinkedIn Campaign Manager.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você poderá configurar uma exportação se tiver acesso a uma conexão desse tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do LinkedIn Ads. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Escolha se deseja exportar dados para fazer a [segmentação de contatos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou a [segmentação de empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) no LinkedIn. 

1. Nã seção **Correspondência de dados**, para segmentação de contato, selecione pelo menos um campo que representa o endereço de email de um cliente, ID de anúncio da Apple, ID de anúncio do Google, ID de usuário do Google ou nome e sobrenome. Se você escolher a segmentação da empresa, selecione pelo menos um campo que represente o nome da empresa, domínio de e-mail, URL da página do LinkedIn, símbolo de ação ou site. Campos adicionais podem ser selecionados para definir melhor sua exportação. 

1. Selecione os segmentos que você deseja exportar. Os públicos-alvo correspondentes no LinkedIn Campaign Manager serão criados automaticamente com o nome dos segmentos que você selecionou para exportação. Cada segmento resultará em um público-alvo correspondente separado. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o LinkedIn Ads, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados que podem ser confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o LinkedIn Ads atenda a todas as obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
