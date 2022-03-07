---
title: Comece com o recurso de insights do público-alvo no Dynamics 365 Customer Insights
description: Uma visão geral de insights do público-alvo ajuda a começar rapidamente a usar recursos.
ms.reviewer: mhart
ms.author: mhart
author: m-hartmann
ms.date: 08/31/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 2776b2292560f9ea61a06d2b1b7bc7811d35c860
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353699"
---
# <a name="get-started-with-dynamics-365-customer-insights-audience-insights-capability"></a>Comece com o recurso de insights do público-alvo no Dynamics 365 Customer Insights

Insights de público-alvo podem ajudá-lo a ter uma compreensão mais profunda dos clientes. Conecte dados de várias fontes transacionais, comportamentais e observacionais para criar uma visão do cliente em 360 graus. Use essas informações para gerar experiências e processos centrados no cliente. Unificar e entender dados de clientes, além de utilizá-los para ações e insights inteligentes.

## <a name="step-1-create-an-environment"></a>Etapa 1: Criar um ambiente

Para começar, primeiro você precisa criar um ambiente para trabalhar. Se sua organização já adquiriu uma licença, consulte [Crie um ambiente](create-environment.md). Para iniciar uma avaliação de insights do público-alvo, consulte [Configure um ambiente de avaliação](../trial-signup.md). 

## <a name="step-2-explore-audience-insights"></a>Etapa2: Explorar insights de público-alvo

A primeira vez que você entra em insights do público-alvo, pode definir as configurações e explorar o produto.

1. [Entrar em insights do público-alvo](https://home.ci.ai.dynamics.com) usando sua conta de usuário do Microsoft Azure Active Directory (AAD).

1. [Altere o ambiente](manage-environments.md#switch-environments) para ver dados de demonstração e [explore insights do público-alvo](home.md).

##  <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Etapa 3: Ingerir, unificar e configurar relacionamentos para seus dados

Perfis unificados são a base para obter insights e agir sobre os dados. Traga dados de várias fontes e execute o processo de unificação de dados para combinar perfis unificados. Especifique relacionamentos entre as entidades ingeridas usando recursos de enriquecimento para adicionar informações aos perfis. 

1. Ingira dados criando fontes de dados a partir de várias opções. Escolher entre [Conectores do Power Query](connect-power-query.md), uma [Pasta do Common Data Model](connect-common-data-model.md) ou o [Microsoft Dataverse](/dynamics365/customer-insights/audience-insights/connect-dataverse-managed-lake). 

1. Execute o [processo de unificação de dados](data-unification.md) passando pelas fases [mapear](map-entities.md), [corresponder](match-entities.md) e [mesclar](merge-entities.md).

1. Familiarize-se com as [entidades criadas pelo sistema](entities.md) e crie [relacionamentos entre as entidades ingeridas](relationships.md).
    
## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Etapa 4: Aprimorar perfis unificados com previsões, atividades e medidas

Com a configuração de perfis unificados, você pode aprimorar seus dados e aumentar ainda mais as informações que eles fornecem.

1. Escolha a partir de uma biblioteca em expansão de fornecedores de enriquecimento para [enriquecer dados do cliente](enrichment-hub.md).

1. Use [modelos prontos para uso](predictions-overview.md) para prever a probabilidade de rotatividade ou as receitas esperadas.

1. [Configure atividades](activities.md) com base em dados ingeridos e visualize interações com clientes em uma linha do tempo cronológica. 

1. [Crie medidas](measures.md) para avaliar objetivos de negócios e KPIs.
 
## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Etapa 5: Criar segmentos e ativar dados por meio de várias opções de exportação

Agora que os dados estão completos e contêm uma ampla gama de informações sobre clientes, é hora de procurar formas de agir sobre esses dados. 

1. [Crie segmentos](segments.md), subconjuntos da base de clientes, para garantir que suas ações sejam relevantes para os clientes-alvo.

1. Navegue pelo catálogo em expansão de [opções de exportação](export-destinations.md) em que você pode usar dados do cliente. Por exemplo, você pode usar dados para gerenciar promoções e alcançar o marketing digital.

1. Reveja as opções de integração; por exemplo, com a [conexão direta com insights de participação](../engagement-insights/integrate-audience-insights-engagement-insights.md) ou com outros aplicativos Dynamics 365 com o [suplemento do Cartão do Cliente](customer-card-add-in.md).  


[!INCLUDE[footer-include](../includes/footer-banner.md)]