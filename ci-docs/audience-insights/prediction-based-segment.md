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
ms.openlocfilehash: 488db1af865ce600ec012716327d053bee33aff8
ms.sourcegitcommit: a95c82f46c23f625cb34fceba021ccc70d4b1df6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "5741415"
---
# <a name="create-a-segment-based-on-a-prediction-model-preview"></a><span data-ttu-id="81e68-103">Criar um segmento com base em um modelo de previsão (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="81e68-103">Create a segment based on a prediction model (preview)</span></span>

<span data-ttu-id="81e68-104">Os resultados das previsões às vezes se aplicam somente a um subconjunto dos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="81e68-104">The results of predictions sometimes only apply to a subset of your customers.</span></span> <span data-ttu-id="81e68-105">Aumente a personalização das recomendações criando segmentos com base nos resultados dos modelos de previsão.</span><span class="sxs-lookup"><span data-stu-id="81e68-105">Increase the personalization of recommendations by creating segments from results of prediction models.</span></span> <span data-ttu-id="81e68-106">Por exemplo, talvez você queira fornecer recomendações específicas aos clientes que preferem um determinado tipo de serviço.</span><span class="sxs-lookup"><span data-stu-id="81e68-106">For example, you may want to give specific recommendations to customers that prefer a certain type of service.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="81e68-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="81e68-107">Prerequisites</span></span>

- <span data-ttu-id="81e68-108">Por último, [Permissões de colaborador](permissions.md) em Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="81e68-108">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>

- <span data-ttu-id="81e68-109">Uma recomendação de produto, rotatividade transacional, rotatividade de assinatura ou modelo de valor de permanência do cliente configurado no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="81e68-109">A product recommendation, transactional churn, subscription churn, or customer lifetime value model configured in Customer Insights.</span></span> <span data-ttu-id="81e68-110">Revise os requisitos para configurar os diferentes modelos:</span><span class="sxs-lookup"><span data-stu-id="81e68-110">Review the requirements to set up the different models:</span></span>

  - [<span data-ttu-id="81e68-111">Modelo de recomendação de produto</span><span class="sxs-lookup"><span data-stu-id="81e68-111">Product recommendation model</span></span>](predict-product-recommendation.md)
  - [<span data-ttu-id="81e68-112">Modelo de rotatividade de assinatura</span><span class="sxs-lookup"><span data-stu-id="81e68-112">Subscription churn model</span></span>](predict-subscription-churn.md)
  - [<span data-ttu-id="81e68-113">Modelo de rotatividade transacional</span><span class="sxs-lookup"><span data-stu-id="81e68-113">Transactional churn model</span></span>](predict-transactional-churn.md)
  - [<span data-ttu-id="81e68-114">Modelo de valor de permanência do cliente</span><span class="sxs-lookup"><span data-stu-id="81e68-114">Customer lifetime value model</span></span>](predict-customer-lifetime-value.md)

## <a name="create-a-customer-segment-based-on-predictions"></a><span data-ttu-id="81e68-115">Criar um segmento de cliente com base em previsões</span><span class="sxs-lookup"><span data-stu-id="81e68-115">Create a customer segment based on predictions</span></span>

1. <span data-ttu-id="81e68-116">Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="81e68-116">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="81e68-117">Selecione as reticências verticais ao lado do modelo que deseja revisar e selecione **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="81e68-117">Select the vertical ellipses next to the model you want to review and select **View**.</span></span>

1. <span data-ttu-id="81e68-118">Na página de resultados, selecione **Criar segmento**.</span><span class="sxs-lookup"><span data-stu-id="81e68-118">On the results page, select **Create segment**.</span></span> <span data-ttu-id="81e68-119">Para obter mais informações sobre a página de resultados, revise o artigo sobre o modelo.</span><span class="sxs-lookup"><span data-stu-id="81e68-119">For more information about the results page, review the article about the model.</span></span>

   :::image type="content" source="media/prediction-create-segment.png" alt-text="Captura de tela da página de resultados de previsão com destaque na ação Criar segmento.":::

1. <span data-ttu-id="81e68-121">Crie um novo segmento com base na entidade de saída do modelo selecionado.</span><span class="sxs-lookup"><span data-stu-id="81e68-121">Create a new segment based on the output entity of the selected model.</span></span> <span data-ttu-id="81e68-122">Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="81e68-122">For more information, see [Create and manage segments](segments.md).</span></span>