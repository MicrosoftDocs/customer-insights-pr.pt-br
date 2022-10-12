---
title: Prever rotatividade de assinaturas (contém vídeo)
description: Preveja se um cliente está em risco de não usar mais os produtos ou serviços de assinatura da sua empresa.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 7464707864c418bfcc625ddfd245622131434b33
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610222"
---
# <a name="predict-subscription-churn"></a>Prever a rotatividade de assinaturas

Preveja se um cliente está em risco de não usar mais os produtos ou serviços de assinatura da sua empresa. Os dados da assinatura incluem assinaturas ativas e inativas de cada cliente, portanto, há várias entradas por ID de cliente.

É necessário conhecimento de negócios para entender o que rotatividade significa para o seu negócio. Oferecemos suporte a definições de rotatividade com base no tempo, o que significa que o cliente é considerado rotativo por um período após o término da assinatura.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Experimente a previsão de rotatividade de assinatura usando dados de exemplo: [Guia de exemplo para previsão de rotatividade de assinatura](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões de colaborador](permissions.md).
- Pelo menos 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos.
- Identificadores de clientes, um identificador exclusivo para associar as assinaturas aos clientes.
- Dados de assinatura de pelo menos o dobro da janela de tempo selecionada. De preferência, de dois a três anos de dados de assinatura. O histórico da assinatura deve incluir:
  - **ID da Assinatura:** identificador exclusivo de uma assinatura.
  - **Data de Término da Assinatura:** data em que a assinatura do cliente expira.
  - **Data de Início da Assinatura:** data de início da assinatura do cliente.
  - **Data da Transação:** data em que ocorreu uma alteração na assinatura. Por exemplo, um cliente comprou ou cancelou a assinatura.
  - **É uma assinatura recorrente:** campo booliano verdadeiro/falso que determina se a assinatura será renovada com a mesma ID de assinatura sem intervenção do cliente.
  - **Frequência de Recorrência (em meses):** para assinaturas recorrentes, o mês em que a assinatura será renovada. Por exemplo, uma assinatura anual renovada automaticamente para um cliente todos os anos e é renovada por mais um ano tem o valor igual a 12.
  - **Valor da Assinatura**: valor da moeda que o cliente pela renovação da assinatura. Isso pode ajudar a identificar padrões de diferentes níveis de assinatura.
- Você precisará de pelo menos dois registros de atividades para 50% dos clientes para os quais deseja calcular a rotatividade. As atividade do cliente devem incluir:
  - **Chave primária:** identificador exclusivo para uma atividade. Por exemplo, o acesso a um site ou um registro de uso que mostra que o cliente assistiu ao episódio de um programa de TV.
  - **Carimbo de data/hora:** data e hora do evento identificado pela chave primária.
  - **Evento:** nome do evento que você deseja usar. Por exemplo, um campo chamado "UserAction" em um serviço de streaming de vídeo pode ter o valor "Visualizado".
  - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo chamado "ShowTitle" em um serviço de streaming de vídeo pode ter o valor de um vídeo que o cliente assistiu.
- Menos de 20% de valores ausentes no campo de dados da entidade fornecida.

## <a name="create-a-subscription-churn-prediction"></a>Crie uma previsão de rotatividade de assinaturas

Selecione **Salvar rascunho** a qualquer momento para salvar o previsão como rascunho. A previsão de rascunho é exibida na guia **Minhas previsões**.

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Modelo de rotatividade de clientes**.

1. Selecione **Assinatura** para o tipo de rotatividade e depois **Introdução**.

1. **Nomear este modelo** e **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Avançar**

### <a name="define-customer-churn"></a>Definir rotatividade de clientes

1. Insira o número de **Dias desde o término da assinatura** que a sua empresa considera um cliente em um estado rotativo. Esse período geralmente é associado a atividades comerciais como ofertas ou outros esforços de marketing para tentar fidelizar o cliente.

1. Digite o número de **Dias para olhar para o futuro para prever a rotatividade**. Por exemplo, preveja o risco de rotatividade para seus clientes nos próximos 90 dias a fim de alinhá-lo aos seus esforços de retenção de marketing. Prever o risco de rotatividade para períodos mais longos ou mais curtos pode dificultar ainda mais a abordagem dos fatores no seu perfil de risco de rotatividade, dependendo dos requisitos comerciais específicos.

1. Selecione **Avançar**

### <a name="add-required-data"></a>Adicionar dados obrigatórios

1. Selecione **Adicionar dados** para **Histórico de assinaturas**.

1. Selecione o tipo de atividade semântica **Assinatura** que contém as informações necessárias do histórico de assinaturas. Se a atividade não foi configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos da atividade tiverem sido mapeados semanticamente quando a atividade foi criada, escolha os atributos específicos ou a entidade em que você deseja que o cálculo se concentre. Se o mapeamento semântico não tiver ocorrido, selecione **Editar** e mapeie seus dados.
  
   :::image type="content" source="media/subscription-churn-required.png" alt-text="Adicionar os dados necessários para o Modelo de rotatividade de assinatura":::

1. Selecione **Avançar** e revise os atributos necessários para este modelo.

1. Selecione **Salvar**.

1. Selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que fornece as informações de atividade do cliente. Se a atividade não foi configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos da atividade tiverem sido mapeados semanticamente quando a atividade foi criada, escolha os atributos específicos ou a entidade em que você deseja que o cálculo se concentre. Se o mapeamento semântico não tiver ocorrido, selecione **Editar** e mapeie seus dados.

1. Selecione **Avançar** e revise os atributos necessários para este modelo.

1. Selecione **Salvar**.

1. Adicione mais atividades ou selecione **Avançar**.

### <a name="set-update-schedule"></a>Definir cronograma de atualização

1. Escolha a frequência para treinar o modelo novamente. Essa configuração é importante para atualizar a precisão de previsões à medida que novos dados são ingeridos no Customer Insights. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuração do modelo

A etapa **Revisar e executar** mostra um resumo da configuração e oferece a chance de fazer alterações antes de criar a previsão.

1. Selecione **Editar** em qualquer uma das etapas para revisar e fazer alterações.

1. Se estiver satisfeito com as seleções, selecione **Salvar e executar** para iniciar a execução do modelo. Selecione **Concluído**. A guia **Minhas previsões** é exibida enquanto a previsão está sendo criada. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visualizar resultados de previsão

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Minhas previsões**, selecione a previsão que deseja visualizar.

Há três seções principais de dados na página de resultados:

- **Desempenho da previsão de treinamento**: os níveis A, B ou C indicam o desempenho da previsão e podem ajudar você a tomar a decisão de usar os resultados armazenados na entidade de saída.
  
  :::image type="content" source="media/subscription-churn-modelperformance.PNG" alt-text="Imagem da caixa de informações de pontuação do modelo com a classificação A.":::

  As classificações são determinadas com base nas seguintes regras:
  - **A** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é maior do que a taxa de rotatividade média histórica em pelo menos 10%.
  - **B** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é maior do que a taxa de rotatividade média histórica em pelo menos 10%.
  - **C** quando o modelo previu com precisão menos de 50% das previsões totais ou quando a porcentagem de previsões precisas para clientes com rotatividade for menor que a taxa média histórica de churn.
  
- **Probabilidade de rotatividade (número de clientes)**: grupos de clientes com base no risco previsto de rotatividade. Opcionalmente, [crie segmentos de clientes](prediction-based-segment.md) com alto risco de rotatividade. Esses segmentos ajudam a entender qual deve ser o limite para a assinatura do segmento.  

  :::image type="content" source="media/subscription-churn-resultdistribution.PNG" alt-text="Gráfico mostrando a distribuição dos resultados de rotatividade, divididos em intervalos de 0-100%":::

- **Fatores mais influentes:** Muitos fatores são levados em consideração ao criar a previsão. Cada um dos fatores tem sua importância calculada para as previsões agregadas que um modelo cria. Use esses fatores para ajudar a validar os resultados de previsão. Ou use essas informações posteriormente para [criar segmentos](.//prediction-based-segment.md) que podem ajudar a influenciar o risco de rotatividade dos clientes.

  :::image type="content" source="media/subscription-churn-influentialfactors.PNG" alt-text="Lista que mostra os fatores influentes e a importância deles na previsão de resultados de rotatividade.":::

> [!NOTE]
> Na entidade de saída para este modelo, *ChurnScore* é a probabilidade prevista de rotatividade e *IsChurn* é um rótulo binário baseado em *ChurnScore* com limite de 0,5. Se esse limite padrão não funcionar para seu cenário, [crie um novo segmento](segments.md) com o limite desejado. Para ver a pontuação de rotatividade, vá para **Dados** > **Entidades** e visualize a guia de dados para a entidade de saída que você definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
