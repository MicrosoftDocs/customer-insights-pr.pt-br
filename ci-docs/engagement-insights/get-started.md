---
title: Introdução ao recurso de insights de interação
description: Uma visão geral dos recursos de ajuda para começar rapidamente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: c435810e712bbbf69f8f1cfb582fc0a971566de6
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8225530"
---
# <a name="get-started-with-dynamics-365-customer-insights-engagement-insights-capability-public-preview"></a>Introdução ao recurso de insights de interação do Dynamics 365 Customer Insights (versão preliminar pública)

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

O recurso de insights de interação permite coletar e avaliar o comportamento dos clientes no seu site da Web. Ele se integra ao recurso de insights do público para que você possa ver análises comportamentais avançadas em tempo real junto com os relatórios de perfil do cliente. Os links deste artigo o ajudam a configurar e definir rapidamente seu ambiente.

## <a name="step-1-review-prerequisites"></a>Etapa 1: Revisar os pré-requisitos

Primeiro, você deve ter uma conta de usuário ativa do Microsoft Azure Active Directory (AAD). Depois, leia os artigos a seguir antes de configurar um espaço de trabalho de insights de interações.

- Revise e concorde com os [Termos de serviço](terms-of-service.md) da Microsoft.  
- Leia o artigo [Gerenciar cookies e consentimento do usuário](user-consent-storage.md). Posteriormente, avalie se você precisa atualizar a notificação de consentimento do usuário. Se você não tinha cookies "não essenciais" anteriormente, provavelmente precisará atualizar a política do seu site.
- Reveja o [glossário](glossary.md) para obter uma introdução rápida aos principais termos e conceitos.

## <a name="step-2-explore-engagement-insights"></a>Etapa 2: Explorar os insights de interação

A primeira vez que você acessa insights de participação, pode definir as configurações, revisar políticas e explorar a capacidade.

1. Entre no [portal de capacidade de insights de participação](https://home.ci.ai.dynamics.com/app/engagement-insights) usando sua conta de usuário Microsoft AAD (escola ou trabalho).

1. Selecione sua região e marque a caixa se quiser optar por receber atualizações e ofertas por email.

1. Reveja os **Termos de uso de insights de engajamento (versão preliminar)** e **Declaração de privacidade** e, depois, selecione **Explorar a demonstração** para aceitar essas configurações.

1. Explore o produto usando um conjunto de dados de exemplo.

##  <a name="step-3-set-up-a-workspace-and-create-reports"></a>Etapa 3: Configure um espaço de trabalho e crie relatórios

Um espaço de trabalho é onde você pode exibir a atividade do usuário em tempo real e armazenar e gerenciar relatórios. Adicione o código ao seu site da Web para começar a coletar *eventos*, os dados de atividade que vêm dos usuários.

1. [Crie um espaço de trabalho](create-workspace.md) e adicione membros.

1. Adicione o código ao seu [site](instrument-website.md) ou [aplicativo móvel](developer-resources.md#capture-events-from-mobile-apps) para ver a atividade do usuário chegando ao seu espaço de trabalho.

1. Veja um [relatório em tempo real](view-reports.md) que mostra usuários ativos por navegador, dispositivo, sistema operacional, local e idioma. Você também pode criar [relatórios personalizados](custom-reports.md) para criar suas próprias visualizações.

1. Crie [ dimensões](dimensions.md) para classificar os visitantes por usuários novos e recorrentes, [métricas](metrics.md) para ajudar a entender melhor o comportamento do usuário e [segmentos](segments.md) para identificar subconjuntos de visitantes com base nas características ou interações do site.
    
## <a name="step-4-export-data-to-other-channels"></a>Etapa 4: Exportar dados para outros canais

Você pode criar *eventos refinados* (uma visão virtual) de seus dados de análise da Web. Em seguida, filtre e exporte os dados para o Azure Data Lake Storage. Você pode ingerir os dados exportados como um fonte de dados.

1. [Crie eventos refinados](refined-events.md) para exportação.

1. [Exporte os dados](export-events.md) para o Azure Data Lake Storage.

1. [Crie um link entre insights do público-alvo e insights de participação](integrate-audience-insights-engagement-insights.md) para compartilhar dados entre os dois recursos.

1. [Reconhecer eventos da Web de usuários autenticados anteriormente](unknown-to-known.md) com o recurso **desconhecido para conhecido**.

1. Aprenda como [excluir e exportar dados de eventos contendo informações pessoais](delete-export-personal-data.md).

## <a name="step-5-create-and-manage-funnel-reports"></a>Etapa 5: Crie e gerencie relatórios de funil

Um relatório em forma de funil coleta informações sobre as etapas que ocorrem durante uma jornada do cliente por meio de seu site ou aplicativo móvel. Além de criar relatórios de perfil prontos para uso e relatórios personalizados, você pode criar um relatório de funil para identificar a jornada dos seus clientes antes de fazerem uma compra. 

1. [Crie um relatório de funil](funnel-reports.md) para decisões fundamentadas e identificar áreas de otimização e melhorias de processos.

1. Crie relatórios de funil em vários canais, depois de instrumentar seu aplicativo móvel com os insights de engajamento[Android SDK](get-started-android.md) ou [iOS SDK](get-started-ios.md).

1. Use [insights de funil](funnel-reports.md#funnel-insights) para ter insights mais profundos sobre o comportamento do cliente sobre as etapas no relatório de funil.
 
## <a name="step-6-stay-connected"></a>Etapa 6: Permanecer conectado

Agradecemos sua participação ativa e consideramos todos os comentários relevantes no desenvolvimento de versões futuras. Compartilhe seus comentários e relate problemas por um destes canais:
- [Comunidade](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Enviar comentários](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Solicitação de suporte](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
