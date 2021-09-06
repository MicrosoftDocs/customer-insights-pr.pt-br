---
title: Segmentos baseados na saída de previsão
description: Crie segmentos com base na entidade de saída de um modelo de previsão.
ms.date: 03/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b89754aea2b0da33f27dea5b26d212920f0c090885f951a37cf42ff11c7b6e93
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036405"
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

1. Selecione as reticências verticais ao lado do modelo que deseja revisar e selecione **Exibir**.

1. Na página de resultados, selecione **Criar segmento**. Para obter mais informações sobre a página de resultados, revise o artigo sobre o modelo.

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de tela da página de resultados de previsão com destaque na ação Criar segmento.":::

1. Crie um novo segmento com base na entidade de saída do modelo selecionado. Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).