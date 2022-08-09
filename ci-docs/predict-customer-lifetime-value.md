---
title: Previsão do valor de permanência do cliente (CLV)
description: Preveja o potencial de receita para clientes ativos no futuro.
ms.date: 07/21/2022
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
ms.openlocfilehash: b6f6665d906cc96688efe84035336f64d2a39303
ms.sourcegitcommit: 80d8436d8c940f1267e6f26b221b8d7ce02ed26b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9186426"
---
# <a name="customer-lifetime-value-clv-prediction"></a>Previsão do valor de permanência do cliente (CLV)

Preveja o valor potencial (receita) que clientes ativos individuais trarão para o seu negócio por um período futuro definido. Este recurso pode ajudar você a atingir vários objetivos:

- Identificar clientes de alto valor e processar esse insight
- Criar segmentos de clientes estratégicos com base em seu valor potencial para executar campanhas personalizadas com vendas direcionadas, marketing e esforços de suporte
- Orientar o desenvolvimento de produtos com foco em recursos que aumentam o valor do cliente
- Otimizar as vendas ou estratégia de marketing e alocar o orçamento com mais precisão para alcançar o cliente
- Reconhecer e recompensar clientes de alto valor por meio de programas de fidelidade ou recompensas

## <a name="prerequisites"></a>Pré-requisitos

Antes de começar, reflita sobre o que CLV significa para o seu negócio. Atualmente, oferecemos suporte à previsão de CLV com base em transações. O valor previsto de um cliente é baseado no histórico de transações comerciais. Para criar a previsão, você precisa de pelo menos permissões de [Colaborador](permissions.md).

Como configurar e executar um modelo de CLV não leva muito tempo, considere a criação de vários modelos com preferências de entrada variadas e compare os resultados do modelo para ver qual cenário do modelo melhor se adapta às suas necessidades de negócios.

### <a name="data-requirements"></a>Requisitos de dados

Os dados a seguir são obrigatórios e, quando marcados como opcionais, são recomendados para aumentar o desempenho do modelo. Quanto mais dados o modelo puder processar, mais precisa será a previsão. Portanto, recomendamos que você ingira mais dados de atividade do cliente, se disponíveis.

- Identificador do cliente: identificador exclusivo para fazer a correspondência das transações com um cliente individual

- Histórico de transações: registro de transações históricas com o esquema de dados semânticos abaixo
    - **ID da transação**: identificador exclusivo de cada transação
    - **Data da transação**: data, de preferência um carimbo de hora de cada transação
    - **Valor da transação**: valor monetário (por exemplo, receita ou margem de lucro) de cada transação
    - **Rótulo atribuído a devoluções** (opcional): valor booleano que significa se a transação é uma devolução 
    - **ID do produto** (opcional): ID do produto envolvido na transação

- Dados adicionais (opcional), por exemplo
    - Atividades na Web: histórico de visitas ao site, histórico de email
    - Atividades de fidelidade: histórico de acúmulo e resgate de pontos de recompensa de fidelidade
    - Registro de SAC, chamada de serviço, reclamação ou histórico de devolução
    - Informações do perfil do cliente
- Dados sobre atividades do cliente (opcional):
    - Identificadores de atividades para diferenciar atividades do mesmo tipo
    - Identificadores de clientes para mapear atividades para os clientes
    - Informações de atividades que contêm o nome e a data da atividade
    - O esquema de dados semânticos para atividades inclui:
        - **Chave primária:** um identificador exclusivo para uma atividade
        - **Carimbo de data/hora:** a data e a hora do evento identificado pela chave primária
        - **Evento (nome da atividade)**: o nome do evento que você deseja usar
        - **Detalhes (quantidade ou valor)**: detalhes sobre a atividade do cliente

- Características de dados sugeridas:
    - Dados históricos suficientes: no mínimos um ano de dados transacionais. De preferência, dois a três anos de dados transacionais para prever o CLV para um ano.
    - Várias compras por cliente: idealmente, pelo menos duas a três transações por ID do cliente, de preferência em várias datas.
    - Número de clientes: pelo menos 100 clientes exclusivos, de preferência mais de 10.000 clientes. O modelo falhará com menos de 100 clientes e dados históricos insuficientes
    - Plenitude dos dados: menos de 20% dos valores ausentes nos campos obrigatórios dos dados de entrada

> [!NOTE]
> - O modelo requer o histórico de transações de seus clientes. Apenas uma entidade de histórico de transações pode ser configurada atualmente. Se houver várias entidades de compra/transação, você poderá uni-las no Power Query antes da ingestão de dados.
> - Porém, para dados adicionais de atividade do cliente (opcional), você pode adicionar quantas entidades de atividade do cliente quiser para serem consideradas pelo modelo.

## <a name="create-a-customer-lifetime-value-prediction"></a>Criar uma previsão do valor de permanência do cliente

1. Vá para **Inteligência** > **Previsões**.

1. Selecione o bloco **Valor de permanência do cliente** e selecione **Usar modelo**. 

1. No painel **Valor da permanência do cliente**, selecione **Introdução**.

1. **Nomear este modelo** e **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Avançar**.

### <a name="define-model-preferences"></a>Definir as preferências do modelo

1. Defina um **Período de previsão** para definir em que momento no futuro você deseja prever o CLV.    
   Por padrão, a unidade é definida como meses. Você pode alterá-la para anos para ter uma visão mais além no futuro.

   > [!TIP]
   > Para prever com precisão o CLV do período definido, você precisa de um período comparável de dados históricos. Por exemplo, se você deseja fazer previsões CLV para os próximos 12 meses, é recomendável ter pelo menos 18 a 24 meses de dados históricos.

1. Especifique o que **Clientes ativos** significa para sua empresa. Defina o período em que um cliente deve ter pelo menos uma transação para ser considerado ativo. O modelo prevê CLV somente para clientes ativos. 
   - **Permitir que o modelo calcule o intervalo de compras (recomendado)**: o modelo analisa seus dados e determina um período com base no histórico de compras.
   - **Definir intervalo manualmente**: se você tiver uma definição de negócio específica de um cliente ativo, escolha esta opção e defina o período apropriadamente.

1. Defina o percentil de **Cliente de alto valor** para permitir que o modelo forneça resultados que se encaixem na definição de seu negócio.
    - **Cálculo de modelo (recomendado)**: o modelo analisa seus dados e determina o que um cliente de alto valor pode ser para sua empresa com base no histórico de transações de seus clientes. O modelo usa uma regra heurística (inspirada na regra 80/20 ou princípio de Pareto) para encontrar a proporção de clientes de alto valor. A porcentagem de clientes que contribuíram com 80% da receita acumulada de sua empresa no período histórico são considerados clientes de alto valor. Geralmente, menos de 30-40% dos clientes contribuem com 80% da receita acumulada. Contudo, esse número pode variar dependendo de seu negócio e setor.    
    - **Porcentagem dos principais clientes ativos**: defina clientes de alto valor para sua empresa como um percentual dos principais clientes ativos pagantes. Por exemplo, você pode usar essa opção para definir os clientes de alto valor como os 20% principais dos futuros clientes pagantes.

    Se sua empresa define clientes de alto valor de uma maneira diferente, [gostaríamos de ouvir sua opinião](https://go.microsoft.com/fwlink/?linkid=2074172).

1. Selecione **Avançar** para prosseguir para a próxima etapa.

### <a name="add-required-data"></a>Adicionar dados necessários

1. Na etapa **Dados obrigatórios**, selecione **Adicionar dados** para **Histórico de transações do cliente** e escolha a entidade que fornece as informações do histórico de transações, conforme descrito nos [pré-requisitos](#prerequisites).

1. Mapeie os campos semânticos para atributos na sua entidade do histórico de compras e selecione **Avançar**.

   :::image type="content" source="media/clv-add-customer-data-mapping.png" alt-text="Imagem da etapa de configuração para mapear atributos de dados para os dados obrigatórios.":::
 
1. Se os campos abaixo não estiverem preenchidos, configure o relacionamento da sua entidade do histórico de compras com a entidade *Cliente* e selecione **Salvar**.
    1. Selecione a entidade do histórico de transações.
    1. Selecione o campo que identifica o cliente na entidade do histórico de compras. Ele precisa estar relacionado à ID do cliente primário da sua entidade Cliente.
    1. Selecione a entidade que corresponde à sua entidade de cliente principal.
    1. Insira um nome que descreva a relação.

      :::image type="content" source="media/clv-add-customer-data-relationship.png" alt-text="Imagem da etapa de configuração para definir o relacionamento com a entidade cliente.":::

1. Selecione **Avançar**

### <a name="add-optional-activity-data"></a>Adicionar dados opcionais de atividade

Os dados que refletem as principais interações do cliente (como Web, SAC e logs de eventos) adicionam contexto aos registros de transações. Mais padrões encontrados nos dados de atividade do cliente podem melhorar a precisão das previsões.

1. Na etapa **Dados adicionais (opcional)**, selecione **Adicionar dados** em **Aumentar insights do modelo com dados adicionais de atividade**. Escolha a entidade de atividade do cliente que fornece as informações de atividade do cliente, conforme descrito nos [pré-requisitos](#prerequisites).

1. Mapeie os campos semânticos para atributos na sua entidade de atividades do cliente e selecione **Avançar**.

   :::image type="content" source="media/clv-additional-data-mapping.png" alt-text="Imagem da etapa de configuração para mapear campos para dados adicionais.":::

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que você está adicionando. Escolha um dos tipos de atividade existentes ou adicione um novo tipo de atividade.

1. Configure o relacionamento da sua entidade de atividade do cliente com a entidade *Cliente*.

    1. Selecione o campo que identifica o cliente na tabela de atividades do cliente. Ele pode estar diretamente relacionado à ID do cliente principal da sua entidade *Cliente*.
    1. Selecione a entidade *Cliente* que corresponde à entidade *Cliente* primário.
    1. Insira um nome que descreva a relação.

   :::image type="content" source="media/clv-additional-data.png" alt-text="Imagem da etapa no fluxo de configuração para adicionar dados adicionais e configurar a atividade com exemplos preenchidos.":::

1. Selecione **Salvar**.
    Adicione mais dados se houver outras atividades do cliente que você deseja incluir.

1. Adicione dados opcionais do cliente ou selecione **Avançar**.

### <a name="add-optional-customer-data"></a>Adicionar dados opcionais do cliente

Selecione a partir de 18 atributos de perfil de cliente comumente usados para incluir como uma entrada para o modelo. Esses atributos podem levar a resultados de modelo mais personalizados, relevantes e práticos para seus casos de uso comercial.

Por exemplo: a Contoso Coffee deseja prever o valor da vida útil do cliente para direcionar aos clientes de lato valor uma oferta personalizada relacionada ao lançamento de sua nova máquina de café expresso. A Contoso usa o modelo CLV e adiciona todos os 18 atributos de perfil do cliente para ver quais fatores influenciam seus clientes de valor mais alto. Eles descobrem que a localização do cliente é o fator mais influenciável para esses clientes.
Com essas informações, eles organizam um evento local para o lançamento da máquina de café expresso e fazem parceira com fornecedores locais para ofertas personalizadas e uma experiência especial no evento. Sem essas informações, a Contoso poderia ter enviado somente emails de marketing genéricos e perdido a oportunidade de personalizar para esse segmento local de seus clientes de alto valor.

1. Na etapa **Dados adicionais (opcional)**, selecione **Adicionar dados** em **Aumentar ainda mais os insights do modelo com dados adicionais de clientes**.

1. Em **Entidade**, escolha **Customer : CustomerInsights** para selecionar a tabela de perfis unificados de cliente que mapeia para dados de atributo do clientes. Em **ID do Cliente**, escolha **System.Customer.CustomerId**.

1. Mapeie mais campos se os dados estiverem disponíveis em seus perfis unificados de cliente.

   :::image type="content" source="media/clv-optional-customer-profile-mapping.png" alt-text="Exemplo de campos mapeados para dados de perfil do cliente.":::

1. Selecione **Salvar** depois de mapear os atributos que o modelo deve usar para ajudar a prever o valor da vida útil do cliente.

1. Selecione **Avançar**

### <a name="set-update-schedule"></a>Definir cronograma de atualização

1. Na etapa **Agendamento de atualização de dados**, escolha a frequência para treinar novamente seu modelo com base nos dados mais recentes. Essa configuração é importante para atualizar a precisão de previsões à medida que novos dados são ingeridos no Customer Insights. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**.

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuração do modelo

1. Na etapa **Revisar os detalhes do seu modelo**, valide a configuração da previsão. Você pode voltar para qualquer parte da configuração da previsão selecionando **Editar** abaixo do valor exibido. Você também pode selecionar uma etapa de configuração no indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Salvar e executar** para iniciar a execução do modelo. Na guia **Minhas predições**, você pode ver o status do processo de previsão. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

## <a name="review-prediction-status-and-results"></a>Revisar o status e os resultados da previsão

### <a name="review-prediction-status"></a>Revisar o estado de previsão

1.  Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.
2.  Selecione a previsão que você deseja revisar.

- **Nome da previsão**: nome da previsão fornecido ao criá-la.
- **Tipo de previsão**: tipo de modelo usado para a previsão
- **Entidade de saída**: nome da entidade que armazenará a saída da previsão. Acesse **Dados** > **Entidades** para encontrar a entidade com esse nome.
- **Campo previsto:** este campo é preenchido apenas para alguns tipos de previsões e não é usado na previsão do valor de permanência do cliente.
- **Status**: status da execução da previsão.
    - **Enfileirada**: a previsão está aguardando a conclusão de outros processos.
    - **Atualizando**: a previsão está em execução no momento para criar resultados que fluirão para a entidade de saída.
    - **Falha**: a execução da previsão falhou. [Analisar os logs](manage-predictions.md#troubleshoot-a-failed-prediction) para obter mais detalhes.
    - **Êxito**: a previsão teve êxito. Selecione **Exibir** nas elipses verticais para revisar os resultados da previsão.
- **Editado**: a data em que a configuração da previsão foi alterada.
- **Última atualização**: a data em que a previsão atualizou resultados na entidade de saída.

### <a name="review-prediction-results"></a>Revisar os resultados de previsão

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione a previsão para a qual deseja revisar os resultados.

Há três seções principais de dados na página de resultados.

- **Desempenho do modelo de treinamento**: A, B ou C são classificações possíveis. Essa classificação indica o desempenho da previsão e pode ajudar você a tomar a decisão de usar os resultados armazenados na entidade de saída. Selecione **Saiba mais sobre esta pontuação** para entender melhor as métricas de desempenho do modelo subjacente e como a classificação final de desempenho do modelo foi derivada.
  
  :::image type="content" source="media/clv-model-score.png" alt-text="Imagem da caixa de informações de pontuação do modelo com a classificação A.":::

  Usando a definição de clientes de alto valor fornecida durante a configuração da predição, o sistema avalia como o modelo de IA se desempenhou na previsão de clientes de alto valor em comparação com um modelo de linha de base.    

  As classificações são determinadas com base nas seguintes regras:
  - **A** quando o modelo previu com precisão pelo menos 5% mais clientes de alto valor em comparação com o modelo de linha de base.
  - **B** quando o modelo previu com precisão entre 0 e 5% mais clientes de alto valor em comparação com o modelo de linha de base.
  - **C** quando o modelo previu com precisão menos clientes de alto valor em comparação com o modelo de linha de base.

  O painel **Classificação de modelo** mostra mais detalhes sobre o desempenho do modelo de IA e o modelo de linha de base. O modelo de linha de base usa uma abordagem não baseada em IA para calcular o valor de permanência do cliente com base principalmente no histórico de compras feitas pelos clientes.     
  A fórmula padrão usada para calcular o CLV pelo modelo de linha de base:    

  _**CLV para cada cliente** = Compra média mensal feita pelo cliente na janela do cliente ativo * Número de meses no período de previsão do CLV * Taxa de retenção geral de todos os clientes*_

  O modelo de IA é comparado ao modelo de linha de base com base em duas métricas de desempenho do modelo.
  
  - **Taxa de sucesso na previsão de clientes de alto valor**

    Veja a diferença na previsão de clientes de alto valor usando o modelo de IA em comparação com o modelo de linha de base. Por exemplo, uma taxa de sucesso de 84% significa que, de todos os clientes de alto valor nos dados de treinamento, o modelo de IA foi capaz de capturar 84% com precisão. Em seguida, comparamos essa taxa de sucesso com a taxa de sucesso do modelo de linha de base para relatar a mudança relativa. Este valor é usado para atribuir uma classificação ao modelo.

  - **Métricas de erro**
    
    Outra métrica permite revisar o desempenho geral do modelo em termos de erro na previsão de valores futuros. Usamos a métrica geral do raiz quadrada do erro-médio (RMSE) para avaliar esse erro. A RMSE é uma forma padrão de medir o erro de um modelo na previsão de dados quantitativos. A RMSE do modelo de IA é comparada à RMSE do modelo de linha de base e a diferença relativa é relatada.

  O modelo de IA prioriza a classificação precisa dos clientes de acordo com o valor que eles agregam ao seu negócio. Portanto, somente a taxa de sucesso de prever clientes de alto valor é usada para derivar a classificação final do modelo. A métrica de RMSE é sensível a exceções. Em cenários em que você tem uma pequena porcentagem de clientes com valores de compra extraordinariamente altos, a métrica de RMSE geral pode não fornecer uma imagem completa do desempenho do modelo.   

- **Valor de clientes por percentil**: usando sua definição de clientes de alto valor, os clientes são agrupados em baixo e alto valor, com base em suas previsões de CLV e mostrados em um gráfico. Ao passar o mouse sobre as barras no histograma, você pode ver o número de clientes em cada grupo e o CLV médio desse grupo. Esses dados podem ajudar se você deseja [criar segmentos de clientes](segments.md) com base em suas previsões de CLV.

- **Fatores mais influentes**: vários fatores são considerados na criação de previsão de CLV com base nos dados de entrada fornecidos ao modelo de IA. Cada um deles tem a sua importância calculada para as previsões agregadas criadas por um modelo. Você pode usar esses fatores para ajudar a validar os resultados de previsão. Esses fatores também fornecem mais informações sobre os fatores mais influentes que contribuíram para prever o CLV em todos os seus clientes.

## <a name="manage-predictions"></a>Gerenciar previsões

É possível otimizar, solucionar problemas, atualizar ou excluir previsões. Revise um relatório de usabilidade de dados de entrada para descobrir como fazer uma previsão mais rápida e confiável. Para obter mais informações, consulte [Gerenciar previsões](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
