---
title: Visão geral sobre os cenários de predição com suporte
description: Cenários de previsão e opções cobertos pelo aplicativo Dynamics 365 Customer Insights.
ms.date: 12/21/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: c692785c7d81ab660ba2e07411e986c67c1a5d0a
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8228171"
---
# <a name="predictions-overview"></a>Visão geral das previsões

O Dynamics 365 Customer Insights é fornecido com várias opções que aproveitam a IA e o aprendizado de máquina para prever dados. 

## <a name="out-of-box-models"></a>Modelos prontos para uso

A maneira mais fácil de começar com dados de previsão são os modelos predefinidos, geralmente chamados de modelos prontos para uso. Eles exigem apenas determinados dados e estrutura para gerar insights rapidamente. Atualmente, os seguintes modelos estão disponíveis: 

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

- [Valor da permanência do cliente](predict-customer-lifetime-value.md): prevê a receita potencial de um cliente durante toda a interação com uma empresa.
- [Recomendação de produto](predict-product-recommendation.md): sugere conjuntos de recomendações de produtos preditivos com base no comportamento de compra e clientes com padrões de compra semelhantes.
- [Rotatividade da assinatura](predict-subscription-churn.md): prevê se um cliente está em risco por não usar mais os produtos ou serviços de assinatura de sua empresa.
- [Rotatividade transacional](predict-transactional-churn.md): prevê se um cliente não comprará mais seus produtos ou serviços em determinado período.
- [Análise de sentimento](sentiment-analysis.md): analise o sentimento dos comentários do cliente e identifique os aspectos comerciais que são frequentemente mencionados.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

- [Rotatividade transacional](predict-transactional-churn.md): prevê se um cliente não comprará mais seus produtos ou serviços em determinado período.

---


## <a name="azure-machine-learning-integration"></a>Integração do Azure Machine Learning

Se uma organização já usa cenários de aprendizado de máquina com base em experimentos do Azure Machine Learning, o recurso de modelos personalizados no Customer Insights ajuda a conectar os pontos. Crie fluxos de trabalho que ajudem você a escolher os dados dos quais deseja gerar insights e mapeie os resultados para seus perfis de cliente unificados. Para obter mais informações, consulte [Modelos personalizados de aprendizado de máquina](custom-models.md).

## <a name="ai-builder-prediction"></a>Previsão do AI Builder

Às vezes, os conjuntos de dados estão incompletos e alguns valores estão faltando. O Customer Insights pode ajudar a prever valores ausentes para a entidade e os segmentos do cliente. Para obter mais informações, consulte [Concluir seus dados parciais com previsões](predictions.md).
