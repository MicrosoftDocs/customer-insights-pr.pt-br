---
title: Introdução ao recurso de insights de interação
description: Uma visão geral dos recursos de ajuda para começar rapidamente.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 08/31/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 644b125f5d140627d357630ded88dd6838d6edb7
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494580"
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

1. Reveja os **Termos de uso de insights de participação (versão preliminar)** e **Declaração de privacidade** e, depois, selecione **Explorar a demonstração** para aceitar essas configurações.

1. Explore o produto usando um conjunto de dados de exemplo.

##  <a name="step-3-set-up-a-workspace-and-add-code-to-your-website"></a>Etapa 3: Configurar um espaço de trabalho e adicionar o código ao seu site da Web

Um espaço de trabalho é onde você pode exibir a atividade do usuário em tempo real e armazenar e gerenciar relatórios. Adicione o código ao seu site da Web para começar a coletar *eventos*, os dados de atividade que vêm dos usuários.

1. [Crie um espaço de trabalho](create-workspace.md) e adicione membros.

1. [Adicione código ao seu site](instrument-website.md) ou [aplicativo móvel](developer-resources.md#capture-events-from-mobile-apps) para ver a atividade de usuário que chega ao seu espaço de trabalho.

1. Veja um [relatório em tempo real](view-reports.md) que mostra usuários ativos por navegador, dispositivo, sistema operacional, local e idioma. Você também pode criar [relatórios personalizados](custom-reports.md) para criar suas próprias visualizações.
    
## <a name="step-4-export-data-to-other-channels"></a>Etapa 4: Exportar dados para outros canais

Você pode criar *eventos refinados* (uma visão virtual) de seus dados de análise da Web. Em seguida, filtre e exporte os dados para o Azure Data Lake Storage. Você pode ingerir os dados exportados como um fonte de dados. Para obter mais informações, consulte [Criar um link entre insights do público-alvo e insights de participação](integrate-audience-insights-engagement-insights.md).

1. [Crie eventos refinados](refined-events.md) para exportação.

1. [Exporte os dados](export-events.md) para o Data Lake Storage.

1. [Crie um link entre insights do público-alvo e insights de participação](integrate-audience-insights-engagement-insights.md) para compartilhar dados entre os dois recursos.

1. Aprenda como [excluir e exportar dados de eventos contendo informações pessoais](delete-export-personal-data.md).
 
## <a name="step-5-stay-connected"></a>Etapa 5: Permanecer conectado

Agradecemos sua participação ativa e consideramos todos os comentários relevantes no desenvolvimento de versões futuras. Compartilhe seus comentários e relate problemas por um destes canais:
- [Comunidade](https://go.microsoft.com/fwlink/?linkid=2141648)
- [Enviar comentários](https://go.microsoft.com/fwlink/?linkid=2143222)
- [Solicitação de suporte](https://go.microsoft.com/fwlink/?linkid=2145734) 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
