---
title: Criar um segmento com base em um modelo de previsão
description: Crie segmentos com base na entidade de saída de um modelo de previsão.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: ed9c6247a1f9148628dc9b5217484e98a576224e
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610406"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a>Criar um segmento com base em um modelo de previsão (versão preliminar)

Os resultados das previsões às vezes se aplicam somente a um subconjunto dos seus clientes. Aumente a personalização das recomendações criando segmentos com base nos resultados dos modelos de previsão. Por exemplo, talvez você queira fornecer recomendações específicas aos clientes que preferem um determinado tipo de serviço.

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.

- Uma recomendação de produto, rotatividade transacional, rotatividade de assinatura ou modelo de valor de permanência do cliente configurado no Customer Insights. Revise os requisitos para configurar os diferentes modelos:

  - [Modelo de recomendação de produto](predict-product-recommendation.md)
  - [Modelo de rotatividade de assinatura](predict-subscription-churn.md)
  - [Modelo de rotatividade transacional](predict-transactional-churn.md)
  - [Modelo de valor de permanência do cliente](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a>Criar um segmento de cliente com base em previsões

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione o modelo que deseja revisar e selecione **Visualizar**.

1. Na página de resultados, selecione **Criar segmento**. Para obter mais informações sobre a página de resultados, revise o artigo sobre o modelo.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de tela da página de resultados de previsão com destaque na ação Criar segmento.":::

1. Crie um novo segmento usando atributos de saída do modelo selecionado. Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

> [!TIP]
> Você também pode criar um segmento para um modelo previsão na página **Segmentos** selecionando **Novo** e escolhendo **Criar de** > **Inteligência**. Para obter mais informações, confira [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
