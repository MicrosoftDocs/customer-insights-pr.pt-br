---
title: Prever o valor de permanência do cliente (CLV)
description: Preveja o potencial de receita para clientes ativos no futuro.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- ci-custom-models
- customerInsights
ms.openlocfilehash: f27462ac327027e50e23387ac9f75a671db9a86d
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610360"
---
# <a name="predict-customer-lifetime-value-clv"></a>Prever o valor de permanência do cliente (CLV)

Preveja o valor potencial (receita) que clientes ativos individuais trarão para o seu negócio por um período futuro definido. Essa previsão ajudará você a:

- Identificar clientes de alto valor e processar esse insight.
- Criar segmentos de clientes estratégicos com base em seu valor potencial para executar campanhas personalizadas com vendas direcionadas, marketing e esforços de suporte.
- Orientar o desenvolvimento de produtos com foco em recursos que aumentam o valor do cliente.
- Otimizar as vendas ou estratégia de marketing e alocar o orçamento com mais precisão para alcançar o cliente.
- Reconhecer e recompensar clientes de alto valor por meio de programas de fidelidade ou recompensas.

Determinar o que o CLV significa para o seu negócio. Oferecemos suporte à previsão de CLV com base em transações. O valor previsto de um cliente é baseado no histórico de transações comerciais. Considere a criação de vários modelos com preferências de entrada variadas e compare os resultados do modelo para ver qual cenário do modelo melhor se adapta às suas necessidades de negócios.

> [!TIP]
> Experimente a previsão de CLV usando dados de exemplo: [Guia de amostra de previsão do valor da vida útil do cliente (CLV)](sample-guide-predict-clv.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos permissões de [Colaborador](permissions.md)
- Pelo menos 100 clientes exclusivos, de preferência mais de 10.000 clientes
- Identificador do cliente: um identificador exclusivo para fazer a correspondência das transações com um cliente individual
- Pelo menos um ano de histórico de transação, de preferência, de dois a três anos. Pelo menos duas a três transações por ID do cliente, de preferência em várias datas. O histórico da transações deve incluir:
  - **ID da transação**: identificador exclusivo de cada transação
  - **Data da transação**: data ou carimbo de hora de cada transação
  - **Valor da transação**: valor monetário (por exemplo, receita ou margem de lucro) de cada transação
  - **Rótulo atribuído a devoluções**: valor booleano verdadeiro/fulso que significa se a transação é uma devolução
  - **ID do produto**: ID do produto envolvido na transação
- Dados sobre atividades do cliente:
  - **Chave primária:** identificador exclusivo para uma atividade
  - **Carimbo de data/hora:** data e hora do evento identificado pela chave primária
  - **Evento (nome da atividade)**: o nome do evento que você deseja usar
  - **Detalhes (quantidade ou valor)**: detalhes sobre a atividade do cliente
- Dados adicionais, como:
  - Atividades na Web: histórico de visitas ao site ou histórico de email
  - Atividades de fidelidade: histórico de acúmulo e resgate de pontos de recompensa de fidelidade
  - Registro de SAC: chamada de serviço, reclamação ou histórico de devolução
  - Informações do perfil do cliente
- Menos de 20% de valores ausentes nos campos obrigatórios

> [!NOTE]
> Apenas uma entidade de histórico de transações pode ser configurada. Se houver várias entidades de compra ou transação, você poderá combiná-las no Power Query antes da ingestão de dados.

## <a name="create-a-customer-lifetime-value-prediction"></a>Criar uma previsão do valor de permanência do cliente

Selecione **Salvar rascunho** a qualquer momento para salvar o previsão como rascunho. A previsão de rascunho é exibida na guia **Minhas previsões**.

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Valor de permanência do cliente**.

1. Selecione **Introdução**.

1. **Nomear este modelo** e **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Avançar**.

### <a name="define-model-preferences"></a>Definir as preferências do modelo

1. Defina um **Período de previsão** para definir em que momento no futuro você deseja prever o CLV. Por padrão, a unidade é definida como meses.

   > [!TIP]
   > Para prever com precisão o CLV do período definido, é necessário um período comparável de dados históricos. Por exemplo, se você deseja fazer previsões CLV para os próximos 12 meses, é recomendável ter pelo menos 18 a 24 meses de dados históricos.

1. Defina o período em que um cliente deve ter pelo menos uma transação para ser considerado ativo. O modelo prevê CLV somente para **Clientes ativos**.
   - **Permitir que o modelo calcule o intervalo de compras (recomendado)**: o modelo analisa seus dados e determina um período com base no histórico de compras.
   - **Definir intervalo manualmente**: período para sua definição de um cliente ativo.

1. Defina o percentil de **Cliente de alto valor**.
    - **Cálculo do modelo (recomendado)**: o modelo usa a regra 80/20. A porcentagem de clientes que contribuíram com 80% da receita acumulada de sua empresa no período histórico são considerados clientes de alto valor. Geralmente, menos de 30-40% dos clientes contribuem com 80% da receita acumulada. Contudo, esse número pode variar dependendo de seu negócio e setor.
    - **Percentual dos principais clientes ativos**: percentil específico para um cliente de alto valor. Por exemplo, digite **25** para definir os clientes de alto valor como os 25% principais dos futuros clientes pagantes.

    Se sua empresa define clientes de alto valor de uma maneira diferente, [gostaríamos de ouvir sua opinião](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Selecione **Avançar**

### <a name="add-required-data"></a>Adicionar dados obrigatórios

1. Selecione **Adicionar dados** para **Histórico de transações do cliente**.

1. Selecione o tipo de atividade semântica, **SalesOrder** ou **SalesOrderLine**, que contém o histórico de transações. Se a atividade não foi configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos da atividade tiverem sido mapeados semanticamente quando a atividade foi criada, escolha os atributos específicos ou a entidade em que você deseja que o cálculo se concentre. Se o mapeamento semântico não tiver ocorrido, selecione **Editar** e mapeie seus dados.
  
   :::image type="content" source="media/CLV-add-required.PNG" alt-text="Adicionar os dados necessários para o modelo de CLV":::

1. Selecione **Avançar** e revise os atributos necessários para este modelo.

1. Selecione **Salvar**.

1. Adicione mais atividades ou selecione **Avançar**.

### <a name="add-optional-activity-data"></a>Adicionar dados opcionais de atividade

Os dados que refletem as principais interações do cliente (como Web, SAC e logs de eventos) adicionam contexto aos registros de transações. Mais padrões encontrados nos dados de atividade do cliente podem melhorar a precisão das previsões.

1. Selecione **Adicionar dados** em **Melhorar os insights do modelo com dados adicionais de atividade**.

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que você está adicionando. Se a atividade não foi configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos da atividade tiverem sido mapeados quando a atividade foi criada, escolha os atributos específicos ou a entidade em que você deseja que o cálculo se concentre. Se o mapeamento não tiver ocorrido, selecione **Editar** e mapeie seus dados.

1. Selecione **Avançar** e revise os atributos necessários para este modelo.

1. Selecione **Salvar**.

1. Selecione **Avançar**

1. [Adicione dados opcionais do cliente](#add-optional-customer-data) ou selecione **Avançar** e vá para [Definir o cronograma de atualização](#set-update-schedule).

### <a name="add-optional-customer-data"></a>Adicionar dados opcionais do cliente

Selecione a partir de 18 atributos de perfil de cliente comumente usados para incluir como uma entrada para o modelo. Esses atributos podem levar a resultados de modelo mais personalizados, relevantes e práticos para seus casos de uso comercial.

Por exemplo: a Contoso Coffee deseja prever o valor da vida útil do cliente para direcionar aos clientes de lato valor uma oferta personalizada relacionada ao lançamento de sua nova máquina de café expresso. A Contoso usa o modelo CLV e adiciona todos os 18 atributos de perfil do cliente para ver quais fatores influenciam seus clientes de valor mais alto. Eles descobrem que a localização do cliente é o fator mais influenciável para esses clientes.
Com essas informações, eles organizam um evento local para o lançamento da máquina de café expresso e fazem parceira com fornecedores locais para ofertas personalizadas e uma experiência especial no evento. Sem essas informações, a Contoso poderia ter enviado somente emails de marketing genéricos e perdido a oportunidade de personalizar para esse segmento local de seus clientes de alto valor.

1. Selecione **Adicionar dados** em **Melhorar ainda mais os insights do modelo com dados adicionais do cliente**.

1. Por **Entidade**, escolha **Cliente: CustomerInsights** para selecionar o perfil de cliente unificado que mapeia para dados de atributo do cliente. Em **ID do Cliente**, escolha **System.Customer.CustomerId**.

1. Mapeie mais campos se os dados estiverem disponíveis em seus perfis unificados de cliente.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exemplo de campos mapeados para dados de perfil do cliente.":::

1. Selecione **Salvar**.

1. Selecione **Avançar**

### <a name="set-update-schedule"></a>Definir cronograma de atualização

1. Escolha a frequência para treinar novamente seu modelo com base nos dados mais recentes. Essa configuração é importante para atualizar a precisão das previsões conforme novos dados são ingeridos para o Customer Insights. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuração do modelo

A etapa **Revisar e executar** mostra um resumo da configuração e oferece a chance de fazer alterações antes de criar a previsão.

1. Selecione **Editar** em qualquer uma das etapas para revisar e fazer alterações.

1. Se estiver satisfeito com as seleções, selecione **Salvar e executar** para iniciar a execução do modelo. Selecione **Concluído**. A guia **Minhas previsões** é exibida enquanto a previsão está sendo criada. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visualizar resultados de previsão

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Minhas previsões**, selecione a previsão que deseja visualizar.

Há três seções principais de dados na página de resultados.

- **Desempenho da previsão de treinamento**: os níveis A, B ou C indicam o desempenho da previsão e podem ajudar você a tomar a decisão de usar os resultados armazenados na entidade de saída.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imagem da caixa de informações de pontuação do modelo com a classificação A.":::

  O Customer Insights avalia como o modelo de IA se saiu ao prever os clientes de alto valor em comparação a um modelo de linha de base.

  As classificações são determinadas com base nas seguintes regras:
  - **A** quando o modelo previu com precisão pelo menos 5% mais clientes de alto valor em comparação com o modelo de linha de base.
  - **B** quando o modelo previu com precisão entre 0 e 5% mais clientes de alto valor em comparação com o modelo de linha de base.
  - **C** quando o modelo previu com precisão menos clientes de alto valor em comparação com o modelo de linha de base.
  
  Selecione [**Saiba mais sobre esta pontuação**](#learn-about-the-score) para abrir o painel **Classificação de modelo**, que mostra mais detalhes sobre o desempenho do modelo de IA e o modelo de linha de base. Isso ajudará você a entender melhor as métricas de desempenho do modelo subjacente e como a classificação final de desempenho do modelo foi derivada. O modelo de linha de base usa uma abordagem não baseada em IA para calcular o valor de permanência do cliente com base principalmente no histórico de compras feitas pelos clientes.

- **Valor dos clientes por percentil**: os clientes de baixo e alto valor são exibidos em um gráfico. Passe o mouse sobre as barras no histograma para pode ver o número de clientes em cada grupo e o CLV médio desse grupo. Outra opção é [criar segmentos de clientes](prediction-based-segment.md) com base em suas previsões de CLV.
  
   :::image type="content" source="media/CLV-value-percent.png" alt-text="Valor de clientes por percentil para modelo de CLV":::

- **Fatores mais influentes**: vários fatores são considerados na criação de previsão de CLV com base nos dados de entrada fornecidos ao modelo de IA. Cada um deles tem a sua importância calculada para as previsões agregadas criadas por um modelo. Use esses fatores para ajudar a validar os resultados de previsão. Esses fatores também fornecem mais informações sobre os fatores mais influentes que contribuíram para prever o CLV em todos os seus clientes.
  
   :::image type="content" source="media/CLV-influence-factors.png" alt-text="Fatores mais influentes para modelo de CLV":::

### <a name="learn-about-the-score"></a>Saiba mais sobre a pontuação

A fórmula padrão usada para calcular o CLV pelo modelo de linha de base:

 _**CLV para cada cliente** = Compra média mensal feita pelo cliente na janela do cliente ativo * Número de meses no período de previsão do CLV * Taxa de retenção geral de todos os clientes_

O modelo de IA é comparado ao modelo de linha de base com base em duas métricas de desempenho do modelo.
  
- **Taxa de sucesso na previsão de clientes de alto valor**

  Veja a diferença na previsão de clientes de alto valor usando o modelo de IA em comparação com o modelo de linha de base. Por exemplo, uma taxa de sucesso de 84% significa que, de todos os clientes de alto valor nos dados de treinamento, o modelo de IA foi capaz de capturar 84% com precisão. Em seguida, comparamos essa taxa de sucesso com a taxa de sucesso do modelo de linha de base para relatar a mudança relativa. Este valor é usado para atribuir uma classificação ao modelo.

- **Métricas de erro**

  Veja o desempenho geral do modelo em termos de erro na previsão de valores futuros. Usamos a métrica geral do raiz quadrada do erro-médio (RMSE) para avaliar esse erro. A RMSE é uma forma padrão de medir o erro de um modelo na previsão de dados quantitativos. A RMSE do modelo de IA é comparada à RMSE do modelo de linha de base e a diferença relativa é relatada.

O modelo de IA prioriza a classificação precisa dos clientes de acordo com o valor que eles agregam ao seu negócio. Portanto, somente a taxa de sucesso de prever clientes de alto valor é usada para derivar a classificação final do modelo. A métrica de RMSE é sensível a exceções. Em cenários em que você tem uma pequena porcentagem de clientes com valores de compra extraordinariamente altos, a métrica de RMSE geral pode não fornecer uma imagem completa do desempenho do modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
