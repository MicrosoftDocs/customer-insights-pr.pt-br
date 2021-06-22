---
title: Visão geral sobre os cenários de predição com suporte
description: Cenários de previsão e opções cobertos pelo aplicativo Dynamics 365 Customer Insights.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: get-started
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 69ae945b22819521db217508c6fc232876346747
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095683"
---
# <a name="predictions-overview"></a><span data-ttu-id="04324-103">Visão geral das previsões</span><span class="sxs-lookup"><span data-stu-id="04324-103">Predictions overview</span></span>

<span data-ttu-id="04324-104">O Dynamics 365 Customer Insights é fornecido com várias opções que aproveitam a IA e o aprendizado de máquina para prever dados.</span><span class="sxs-lookup"><span data-stu-id="04324-104">Dynamics 365 Customer Insights comes with a variety of options that leverage AI and machine learning to predict data.</span></span> 

## <a name="out-of-box-models"></a><span data-ttu-id="04324-105">Modelos prontos para uso</span><span class="sxs-lookup"><span data-stu-id="04324-105">Out-of-box models</span></span>

<span data-ttu-id="04324-106">A maneira mais fácil de começar com dados de previsão são os modelos predefinidos, geralmente chamados de modelos prontos para uso.</span><span class="sxs-lookup"><span data-stu-id="04324-106">The easiest way to start with predicting data are predefined models, often referred to as out-of-box models.</span></span> <span data-ttu-id="04324-107">Eles exigem apenas determinados dados e estrutura para gerar insights rapidamente.</span><span class="sxs-lookup"><span data-stu-id="04324-107">They only require certain data and structure to generate insights quickly.</span></span> <span data-ttu-id="04324-108">Atualmente, os seguintes modelos estão disponíveis:</span><span class="sxs-lookup"><span data-stu-id="04324-108">Currently, the following models are available:</span></span> 
- <span data-ttu-id="04324-109">[Valor da permanência do cliente](predict-customer-lifetime-value.md): prevê a receita potencial de um cliente durante toda a interação com uma empresa.</span><span class="sxs-lookup"><span data-stu-id="04324-109">[Customer lifetime value](predict-customer-lifetime-value.md): Predicts the potential revenue of a customer throughout the entire interaction with a business.</span></span> 
- <span data-ttu-id="04324-110">[Recomendação de produto](predict-product-recommendation.md): sugere conjuntos de recomendações de produtos preditivos com base no comportamento de compra e clientes com padrões de compra semelhantes.</span><span class="sxs-lookup"><span data-stu-id="04324-110">[Product recommendation](predict-product-recommendation.md): Suggests sets of predictive product recommendations based on purchase behavior and customers with similar purchase patterns.</span></span>
- <span data-ttu-id="04324-111">[Rotatividade da assinatura](predict-subscription-churn.md): prevê se um cliente está em risco por não usar mais os produtos ou serviços de assinatura de sua empresa.</span><span class="sxs-lookup"><span data-stu-id="04324-111">[Subscription churn](predict-subscription-churn.md): Predicts whether a customer is at risk for no longer using your company’s subscription products or services.</span></span>
- <span data-ttu-id="04324-112">[Rotatividade transacional](predict-transactional-churn.md): prevê se um cliente não comprará mais seus produtos ou serviços em determinado período.</span><span class="sxs-lookup"><span data-stu-id="04324-112">[Transactional churn](predict-transactional-churn.md): Predict if a customer will no longer purchase your products or services in a certain time frame.</span></span>

## <a name="azure-machine-learning-integration"></a><span data-ttu-id="04324-113">Integração do Azure Machine Learning</span><span class="sxs-lookup"><span data-stu-id="04324-113">Azure Machine Learning integration</span></span>

<span data-ttu-id="04324-114">Se uma organização já usa cenários de aprendizado de máquina com base em experimentos do Azure Machine Learning, o recurso de modelos personalizados no Customer Insights ajuda a conectar os pontos.</span><span class="sxs-lookup"><span data-stu-id="04324-114">If an organization already uses machine learning scenarios based on Azure Machine Learning experiments, the custom models feature in Customer Insights helps to connect the dots.</span></span> <span data-ttu-id="04324-115">Crie fluxos de trabalho que ajudem você a escolher os dados dos quais deseja gerar insights e mapeie os resultados para seus perfis de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="04324-115">Create workflows that help you choose the data you want to generate insights from and map the results to your unified customer profiles.</span></span> <span data-ttu-id="04324-116">Para obter mais informações, consulte [Modelos personalizados de aprendizado de máquina](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="04324-116">For more information, see [Custom machine learning models](custom-models.md).</span></span>

## <a name="ai-builder-prediction"></a><span data-ttu-id="04324-117">Previsão do AI Builder</span><span class="sxs-lookup"><span data-stu-id="04324-117">AI Builder prediction</span></span>

<span data-ttu-id="04324-118">Às vezes, os conjuntos de dados estão incompletos e alguns valores estão faltando.</span><span class="sxs-lookup"><span data-stu-id="04324-118">Sometimes, data sets are incomplete and some values are missing.</span></span> <span data-ttu-id="04324-119">O Customer Insights pode ajudar a prever valores ausentes para a entidade e os segmentos do cliente.</span><span class="sxs-lookup"><span data-stu-id="04324-119">Customer Insights can help to predict missing values for the Customer entity and segments.</span></span> <span data-ttu-id="04324-120">Para obter mais informações, consulte [Concluir seus dados parciais com previsões](predictions.md).</span><span class="sxs-lookup"><span data-stu-id="04324-120">For more information, see [Complete your partial data with predictions](predictions.md).</span></span>
