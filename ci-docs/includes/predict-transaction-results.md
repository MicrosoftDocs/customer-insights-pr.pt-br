---
ms.openlocfilehash: a67714de5aae80a0080c0e631ae6f8986eb2a003
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9611093"
---
- **Desempenho da previsão de treinamento**: os níveis A, B ou C indicam o desempenho da previsão e podem ajudar você a tomar a decisão de usar os resultados armazenados na entidade de saída.

  As classificações são determinadas com base nas seguintes regras:
  - **A** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é maior do que a taxa de linha de base em pelo menos 10%.
  - **B** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é até 10% maior do que a linha de base.
  - **C** quando o modelo previu com precisão menos de 50% das previsões totais ou quando a porcentagem de previsões precisas para clientes com rotatividade é menor do que a linha de base.
  - **Linha de base** usa a entrada de janela de tempo da previsão para o modelo (por exemplo, um ano) e cria diferentes frações de tempo dividindo-a por 2 até atingir um mês ou menos. Ele usa essas frações para criar uma regra de negócios para clientes que não compraram nesse período. Esses clientes são considerados clientes com rotatividade. A regra de negócios baseada em tempo com a maior capacidade de prever quem tem propensão à rotatividade é escolhida como modelo de linha de base.

- **Probabilidade de rotatividade (número de clientes)**: grupos de clientes com base no risco previsto de rotatividade. Opcionalmente, [crie segmentos de clientes](../prediction-based-segment.md) com alto risco de rotatividade. Esses segmentos ajudam a entender qual deve ser o limite para a assinatura do segmento.

- **Fatores mais influentes**: muitos fatores são levados em consideração ao criar a previsão. Cada um dos fatores tem sua importância calculada para as previsões agregadas que um modelo cria. Use esses fatores para ajudar a validar os resultados de previsão. Ou use essas informações posteriormente para [criar segmentos](../prediction-based-segment.md) que podem ajudar a influenciar o risco de rotatividade dos clientes.