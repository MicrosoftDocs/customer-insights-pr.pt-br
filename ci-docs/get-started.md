---
title: Introdução ao Dynamics 365 Customer Insights
description: Uma visão geral do Customer Insights ajuda os recursos a começar rapidamente.
ms.reviewer: v-wendysmith
ms.author: mhart
author: m-hartmann
ms.date: 04/12/2022
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 1c925110f40319df77940d1c32f24a99504d6ec6
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011965"
---
# <a name="get-started-with-dynamics-365-customer-insights"></a>Introdução ao Dynamics 365 Customer Insights

O Customer Insights pode ajudá-lo a compreender melhor os clientes. Conecte dados de várias fontes transacionais, comportamentais e observacionais para criar uma visão do cliente em 360 graus. Use essas informações para gerar experiências e processos centrados no cliente. Unificar e entender dados de clientes, além de utilizá-los para ações e insights inteligentes.

## <a name="step-1-create-an-environment"></a>Etapa 1: Criar um ambiente

Primeiro, crie um ambiente para trabalhar. Se sua organização já adquiriu uma licença, consulte [Crie um ambiente](create-environment.md). Para iniciar uma avaliação do Customer Insights, consulte [Configurar um ambiente de teste](trial-signup.md).

## <a name="step-2-explore-customer-insights"></a>Etapa 2: Explorar o Customer Insights

Na primeira vez que você entrar no Customer Insights, defina as configurações e explorar o produto.

1. [Entre no Customer Insights](https://home.ci.ai.dynamics.com) usando sua conta de usuário do Microsoft Azure Active Directory (AAD).

1. Altere o ambiente para ver dados de demonstração e [explorar o Customer Insights](home.md).

## <a name="step-3-ingest-unify-and-set-up-relationships-for-your-data"></a>Etapa 3: Ingerir, unificar e configurar relacionamentos para seus dados

Perfis unificados são a base para obter insights e agir sobre os dados. Traga dados de várias fontes e execute o processo de unificação de dados para combinar perfis unificados. Especifique relacionamentos entre as entidades ingeridas e use recursos de enriquecimento para adicionar informações aos perfis.

1. Ingira dados criando fontes de dados a partir de várias opções. Escolha entre [Azure Data Lake Storage, incluindo o Common Data Model](connect-common-data-model.md), [Azure Synapse Analytics](connect-synapse.md), [Microsoft Dataverse](connect-dataverse-managed-lake.md) ou [conectores do Power Query](connect-power-query.md).

1. Execute o [processo de unificação de dados](data-unification.md) ao identificar os [campos de origem](map-entities.md), removendo [duplicatas](remove-duplicates.md), [condições correspondentes](match-entities.md) e [campos de unificação](merge-entities.md).

1. Familiarize-se com as [entidades criadas pelo sistema](entities.md) e crie [relacionamentos entre as entidades ingeridas](relationships.md).

## <a name="step-4-enhance-unified-profiles-with-predictions-activities-and-measures"></a>Etapa 4: Aprimorar perfis unificados com previsões, atividades e medidas

Com perfis unificados configurados, enriqueça seus dados e aumente ainda mais as informações que eles fornecem.

1. Escolha a partir de uma biblioteca em expansão de fornecedores de enriquecimento para [enriquecer dados do cliente](enrichment-hub.md).

1. Use [modelos prontos para uso](predictions-overview.md) para prever a probabilidade de rotatividade ou as receitas esperadas.

1. [Configure atividades](activities.md) com base em dados ingeridos e visualize interações com clientes em uma linha do tempo cronológica.

1. [Crie medidas](measures.md) para avaliar objetivos de negócios e KPIs.

## <a name="step-5-create-segments-and-activate-data-through-various-export-options"></a>Etapa 5: Criar segmentos e ativar dados por meio de várias opções de exportação

Agora que seus dados estão completos e contêm uma ampla variedade de informações sobre seus clientes, procure maneiras de agir nesses dados.

1. [Crie segmentos](segments.md), subconjuntos da base de clientes, para garantir que suas ações sejam relevantes para os clientes-alvo.

1. Navegue pelo catálogo em expansão de [opções de exportação](export-destinations.md) em que você pode usar dados do cliente. Por exemplo, você pode usar dados para gerenciar promoções e alcançar o marketing digital.

1. Revise as opções de integração, por exemplo, para outros aplicativos do Dynamics 365 com o [Complemento do Cartão do Cliente](customer-card-add-in.md).  


[!INCLUDE [footer-include](includes/footer-banner.md)]
