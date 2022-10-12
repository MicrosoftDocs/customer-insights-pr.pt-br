---
title: Previsão da rotatividade de transações (contém vídeo)
description: Preveja se um cliente está em risco de não comprar mais seus produtos ou serviços.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: fd8df0f0a168ddfab9e8ad3af9e1f1fc0bc1b7a2
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610498"
---
# <a name="predict-transaction-churn"></a>Faça previsão de rotatividade de transações

A previsão de rotatividade transacional ajuda a prever se um cliente não comprará mais seus produtos ou serviços em uma determinada janela de tempo.

É necessário conhecimento de negócios para entender o que rotatividade significa para o seu negócio. Oferecemos suporte a definições de rotatividade baseadas em tempo, ou seja, um cliente é considerado um cliente com rotatividade após um período sem compras.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Para ambientes baseados em contas comerciais, podemos prever a rotatividade transacional para uma conta e também uma combinação de conta e outro nível de informação como categoria de produto. Por exemplo, adicionar uma dimensão pode ajudar a determinar a probabilidade com que a conta "Contoso" deixe de comprar a categoria de produto "material de escritório". Além disso, para contas comerciais, também podemos usar a IA para gerar uma lista de razões potenciais pelas quais uma conta provavelmente mudará para uma categoria de informações de nível secundário.

> [!TIP]
> Experimente a previsão de rotatividade de transações usando dados de exemplo: [Guia de exemplo de previsão de rotatividade de transações](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões de colaborador](permissions.md).
- Pelo menos 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos.
- Identificadores de clientes, um identificador exclusivo para associar as transações aos clientes.
- Dados de transação para pelo menos o dobro da janela de tempo selecionada, como dois a três anos de histórico de transações. Idealmente, pelo menos duas transações por cliente. O histórico da transações deve incluir:
  - **ID da transação**: identificador exclusivo de uma compra ou transação.
  - **Data da transação**: data da compra ou transação.
  - **Valor da transação**: quantia em moeda/valor numérico da transação.
  - **ID exclusiva do produto:** ID do produto ou serviço adquirido, se os seus dados estiverem em um nível de item de linha.
  - **Se esta transação foi uma devolução**: campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** for negativo, inferiremos uma devolução.
- Dados de atividade do cliente:
  - Identificadores de clientes, um identificador exclusivo para mapear atividades aos clientes.
  - **Chave primária:** identificador exclusivo para uma atividade. Por exemplo, uma visita a um site ou um registro de uso que mostra que o cliente experimentou uma amostra do seu produto.
  - **Carimbo de data/hora:** data e hora do evento identificado pela chave primária.
  - **Evento:** nome do evento que você deseja usar. Por exemplo, um campo denominado "UserAction" em um supermercado pode ser um cupom usado pelo cliente.
  - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo denominado "CouponValue" em um supermercado pode ser o valor da moeda do cupom.
- Menos de 20% de valores ausentes no campo de dados da entidade fornecida

Para contas comerciais (B2B), adicione dados do cliente alinhados a atributos mais estáticos para garantir que o modelo tenha o melhor desempenho:
- **Identificação do Cliente**: identificador exclusivo de um cliente.
- **Data de criação**: data em que o cliente foi adicionado inicialmente.
- **Estado ou Província**: localização do estado ou província de um cliente.
- **País:** país de um cliente.
- **Indústria:** tipo de setor de um cliente. Por exemplo, um campo denominado "Indústria" em uma torrefadora de café pode indicar se o cliente era varejista.
- **Classificação:** categorização de um cliente para sua empresa. Por exemplo, um campo denominado "ValueSegment" em uma torrefadora de café pode ser a camada do cliente com base no tamanho do cliente.

> [!NOTE]
> Para uma empresa com alta frequência de compra pelos clientes (em intervalos de algumas semanas), é recomendável selecionar uma janela de previsão e uma definição de rotatividade mais curtas. Para baixa frequência de compra (em intervalos de alguns meses ou uma vez por ano), escolha uma janela de previsão e uma definição de rotatividade mais longas.

## <a name="create-a-transaction-churn-prediction"></a>Crie uma previsão de rotatividade de transações

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Modelo de rotatividade de clientes**.

1. Selecione **Transação** para o tipo de rotatividade e depois **Introdução**.

1. **Nomear este modelo** e **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Avançar**

### <a name="define-customer-churn"></a>Definir rotatividade de clientes

Selecione **Salvar rascunho** a qualquer momento para salvar o previsão como rascunho. A previsão de rascunho é exibida na guia **Minhas previsões**.

1. Defina a **Janela de previsão**. Por exemplo, preveja o risco de rotatividade para seus clientes nos próximos 90 dias a fim de alinhá-lo aos seus esforços de retenção de marketing. A previsão do risco de rotatividade para um período mais longo ou mais curto pode dificultar a abordagem dos fatores no seu perfil de risco de rotatividade, mas depende dos requisitos comerciais específicos.

1. Insira o número de dias para definir a rotatividade no campo **Definição de rotatividade**. Por exemplo, se um cliente não fez compras nos últimos 30 dias, ele pode ser considerado como um cliente com rotatividade para sua empresa.

1. Selecione **Avançar**

### <a name="add-purchase-history"></a>Adicionar histórico de compras

1. Selecione **Adicionar dados** para **Histórico de transações do cliente**.

1. Selecione o tipo de atividade semântica, **SalesOrder** ou **SalesOrderLine**, que contém informações sobre o histórico de transações. Se a atividade não foi configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos da atividade tiverem sido mapeados semanticamente quando a atividade foi criada, escolha os atributos específicos ou a entidade em que você deseja que o cálculo se concentre. Se o mapeamento semântico não tiver ocorrido, selecione **Editar** e mapeie seus dados.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Painel lateral mostrando a escolha de atividades específicas no tipo semântico.":::

1. Selecione **Avançar** e revise os atributos necessários para este modelo.

1. Selecione **Salvar**.

1. Adicione mais atividades ou selecione **Avançar**.

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Adicionar outros dados (opcional)

1. Selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que contém os dados que você gostaria de usar. Se a atividade não foi configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos da atividade tiverem sido mapeados semanticamente quando a atividade foi criada, escolha os atributos específicos ou a entidade em que você deseja que o cálculo se concentre. Se o mapeamento semântico não tiver ocorrido, selecione **Editar** e mapeie seus dados.

1. Selecione **Avançar** e revise os atributos necessários para este modelo.

1. Selecione **Salvar**.

1. Selecione **Avançar**.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Selecione o nível de previsão

A maioria das previsões é criada no nível do cliente. Em algumas situações, isso pode não ser granular o suficiente para atender às suas necessidades de negócio. Use esse recurso para prever a rotatividade de uma filial de um cliente, por exemplo, em vez do cliente como um todo.

1. Selecione **Selecionar entidade para um nível secundário**. Se a opção não estiver disponível, certifique-se de ter concluído a seção anterior.

1. Expanda as entidades das quais deseja escolher o nível secundário ou use a caixa de filtro de pesquisa para filtrar as opções selecionadas.

1. Escolha o atributo que deseja usar como nível secundário e selecione **Adicionar**.

1. Selecione **Avançar**

> [!NOTE]
> As entidades disponíveis nesta seção são exibidas porque têm um relacionamento com a entidade que você escolheu na seção anterior. Se você não vir a entidade que deseja adicionar, verifique se ela tem um relacionamento válido presente em **Relacionamentos**. Apenas relacionamentos um-para-um e muitos-para-um são válidos para esta configuração.

### <a name="add-additional-data-optional"></a>Adicionar outros dados (opcional)

1. Selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que contém os dados que você gostaria de usar. Se a atividade não foi configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos da atividade tiverem sido mapeados semanticamente quando a atividade foi criada, escolha os atributos específicos ou a entidade em que você deseja que o cálculo se concentre. Se o mapeamento semântico não tiver ocorrido, selecione **Editar** e mapeie seus dados.

1. Selecione **Avançar** e revise os atributos necessários para este modelo.

1. Selecione **Salvar**.

1. Selecione **Avançar**.

1. Opcionalmente, selecione **Adicionar dados** como **Dados de clientes**.

1. Mapeie os atributos semânticos para campos em seus próprios dados de cliente, conforme identificado. Os dados nos campos usados não devem ser alterados com frequência para garantir o melhor desempenho do modelo. Por exemplo, a seleção de um campo para "Classificação" que mudasse a cada mês teria apenas o último valor utilizado na previsão, embora historicamente o mesmo valor pudesse não se aplicar ao cliente ao construir os padrões de previsão.

1. Selecione **Avançar**

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Forneça uma lista opcional de contas de referência

Adicione uma lista de seus clientes corporativos e contas que deseja usar como benchmarks. Os [detalhes para essas contas de referência](#view-prediction-results) incluem sua pontuação de rotatividade e os recursos mais influentes que impactaram sua previsão de rotatividade.

1. Selecione **+ Adicionar clientes**.

1. Escolha os clientes que atuam como referência.

1. Selecione **Avançar**

---

### <a name="set-update-schedule"></a>Definir cronograma de atualização

1. Para a etapa **Atualizações de dados**, escolha uma frequência para treinar novamente seu modelo. Essa configuração é importante para atualizar a precisão das previsões conforme novos dados são ingeridos para o Customer Insights. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuração do modelo

A etapa **Revisar e executar** mostra um resumo da configuração e oferece a chance de fazer alterações antes de criar a previsão.

1. Selecione **Editar** em qualquer uma das etapas para revisar e fazer alterações.

1. Se estiver satisfeito com as seleções, selecione **Salvar e executar** para iniciar a execução do modelo. Selecione **Concluído**. A guia **Minhas previsões** é exibida enquanto a previsão está sendo criada. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visualizar resultados de previsão

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Minhas previsões**, selecione a previsão que deseja visualizar.

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

Há três seções principais de dados na página de resultados:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

Há três seções principais de dados na página de resultados:

[!INCLUDE [predict-transaction-results](includes/predict-transaction-results.md)]

Uma página de informações **Análise de recursos influentes** contém quatro seções de dados:

- No painel direito, selecione um item de **Principais clientes** ou **Clientes de referência**. Ambas as listas são ordenadas pelo valor decrescente da pontuação da rotatividade, quer a pontuação seja apenas para o cliente ou uma pontuação combinada para os clientes e uma categoria de produto de nível secundário como a categoria de produto. O item selecionado determina o conteúdo desta página.

  - **Principais clientes**: lista de 10 clientes com maior risco de desligamento e menor risco de desligamento com base em suas pontuações de desligamento.
  - **Clientes de referência**: lista de até 10 clientes que foram selecionados durante a configuração do modelo.

- **Pontuação de rotatividade:** mostra a pontuação de rotatividade do item selecionado no painel direito.

- **Distribuição de risco de rotatividade:** mostra a distribuição do risco de rotatividade entre os clientes e o percentil em que se encontra o cliente selecionado.

- **Principais recursos que aumentam e diminuem o risco de rotatividade:** são listados os cinco principais recursos que aumentaram e diminuíram o risco de rotatividade para o item selecionado no painel direito. Exibe o valor do recurso para aquele item e sua influência na pontuação de rotatividade para cada recurso influente. O valor médio de cada recurso nos segmentos de clientes de baixa, média e alta rotatividade também é exibido. Ele ajuda a contextualizar melhor os valores dos recursos mais influentes para o item selecionado e compará-lo com segmentos de clientes de baixa, média e alta rotatividade.

  - Baixo: contas ou combinações de contas e nível secundário com uma pontuação de rotatividade entre 0 e 0,33.
  - Médio: contas ou combinações de contas e nível secundário com uma pontuação de rotatividade entre 0,33 e 0,66.
  - Alto: contas ou combinações de contas e nível secundário com uma pontuação de rotatividade maior que 0,66.

  Quando você prevê o desligamento no nível da conta, todas as contas são consideradas na derivação dos valores médios dos recursos para os segmentos de desligamento. Para previsões de rotatividade no nível secundário para cada conta, a derivação dos segmentos de rotatividade depende do nível secundário do item selecionado no painel lateral. Por exemplo, se um item tem um nível secundário de categoria de produto (material de escritório), então somente os itens que têm material de escritório como categoria de produto são considerados ao derivar os valores médios de característica para segmentos de rotatividade. Esta lógica é aplicada para garantir uma comparação justa dos valores das características do item com os valores médios em segmentos de baixa, média e alta rotatividade.

  Em alguns casos, o valor médio dos segmentos de baixa, média ou alta rotatividade está vazio ou não disponível porque não há itens que pertençam aos segmentos de rotatividade correspondentes com base na definição acima.

  A interpretação dos valores nas colunas de média baixa, média e alta é diferente para características categóricas como país/região ou setor. Como a noção de valor de recurso "média" não se aplica a recursos categóricos, os valores nessas colunas são a proporção de clientes em segmentos de baixa, média ou alta rotatividade que têm o mesmo valor do recurso categórico em comparação com o item selecionado no painel lateral.

---

 > [!NOTE]
 > Na entidade de saída para este modelo, *ChurnScore* exibe a probabilidade prevista de rotatividade e *IsChurn* é um rótulo binário baseado em *ChurnScore* com limite de 0,5. Se esse limite padrão não funcionar para seu cenário, [crie um novo segmento](segments.md#create-a-segment) com o limite desejado. Nem todos os clientes são necessariamente clientes ativos. Alguns deles podem não ter tido nenhuma atividade por um longo período e já são considerados com rotatividade, com base na sua definição de rotatividade. Prever o risco de desligamento para clientes que já se desligaram não é útil porque eles não são o público-alvo de interesse.
>
> Para ver a pontuação de rotatividade, vá para **Dados** > **Entidades** e visualize a guia de dados para a entidade de saída que você definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
