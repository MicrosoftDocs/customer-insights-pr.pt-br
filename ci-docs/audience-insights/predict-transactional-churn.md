---
title: Previsão da rotatividade de transações (contém vídeo)
description: Preveja se um cliente está em risco de não comprar mais seus produtos ou serviços.
ms.date: 01/13/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 602a86a67006925faac00add8e089d28f7071c14
ms.sourcegitcommit: 15b1521041149716f8031cfa6d0dc61a56a5e2ff
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/13/2022
ms.locfileid: "7967733"
---
# <a name="transaction-churn-prediction-preview"></a>Previsão de rotatividade de transações (versão preliminar)

A previsão de rotatividade transacional ajuda a prever se um cliente não comprará mais seus produtos ou serviços em uma determinada janela de tempo. Você pode criar novas previsões de rotatividade em **Inteligência** > **Previsões**. Selecione **Minhas previsões** para ver outras previsões que você criou. 

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6Eg]

Para ambientes baseados em contas comerciais, podemos prever a rotatividade transacional para uma conta e também uma combinação de conta e outro nível de informação como categoria de produto. Adicionar uma dimensão pode ajudar a descobrir como é provável que a conta "Contoso" deixe de comprar a categoria de produto "material de escritório". Além disso, para contas comerciais, também podemos usar a IA para gerar uma lista de razões potenciais pelas quais uma conta provavelmente mudará para uma categoria de informações de nível secundário.

> [!TIP]
> Experimente o tutorial para uma previsão de rotatividade de transações usando dados de amostra: [guia de amostra de previsão de rotatividade de transações (versão preliminar)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.
- Conhecimento de negócios para entender o que rotatividade significa para o seu negócio. Oferecemos suporte a definições de rotatividade baseadas em tempo, ou seja, um cliente é considerado um cliente com rotatividade após um período sem compras.
- Dados sobre as transações/compras e seu histórico:
    - Identificadores de transação para distinguir compras/transações.
    - Identificadores de cliente para corresponder transações aos seus clientes.
    - Datas dos eventos de transação, que definem as datas em que a transação ocorreu.
    - O esquema de dados semânticos para compras/transações requer as seguintes informações:
        - **ID da transação**: um identificador exclusivo de uma compra ou transação.
        - **Data da transação**: data da compra ou transação.
        - **Valor da transação**: quantia em moeda/valor numérico da transação/item.
        - (Opcional) **ID exclusiva do produto**: ID do produto ou serviço adquirido se os seus dados estiverem em um nível de item de linha.
        - (Opcional) **Se esta transação foi uma devolução**: campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** for negativo, também usaremos essa informação para inferir uma devolução.
- (Opcional) Dados sobre atividades do cliente:
    - Identificadores de atividades para diferenciar atividades do mesmo tipo.
    - Identificadores de clientes para mapear atividades para os clientes.
    - Informações de atividades que contêm o nome e a data da atividade.
    - O esquema de dados semânticos para atividades do cliente inclui:
        - **Chave primária:** Um identificador exclusivo para uma atividade. Por exemplo, uma visita a um site ou um registro de uso que mostra que o cliente experimentou uma amostra do seu produto.
        - **Carimbo de data/hora:** A data e a hora do evento identificado pela chave primária.
        - **Evento:** O nome do evento que você deseja usar. Por exemplo, um campo denominado "UserAction" em um supermercado pode ser um cupom usado pelo cliente.
        - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo denominado "CouponValue" em um supermercado pode ser o valor da moeda do cupom.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.
- Conhecimento de negócios para entender o que rotatividade significa para o seu negócio. Oferecemos suporte a definições de rotatividade baseadas em tempo, ou seja, um cliente é considerado um cliente com rotatividade após um período sem compras.
- Dados sobre as transações/compras e seu histórico:
    - Identificadores de transação para distinguir compras/transações.
    - Identificadores de cliente para corresponder transações aos seus clientes.
    - Datas dos eventos de transação, que definem as datas em que a transação ocorreu.
    - O esquema de dados semânticos para compras/transações requer as seguintes informações:
        - **ID da transação**: um identificador exclusivo de uma compra ou transação.
        - **Data da transação**: data da compra ou transação.
        - **Valor da transação**: quantia em moeda/valor numérico da transação/item.
        - (Opcional) **ID exclusiva do produto**: ID do produto ou serviço adquirido se os seus dados estiverem em um nível de item de linha.
        - (Opcional) **Se esta transação foi uma devolução**: campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** for negativo, também usaremos essa informação para inferir uma devolução.
- (Opcional) Dados sobre atividades do cliente:
    - Identificadores de atividades para diferenciar atividades do mesmo tipo.
    - Identificadores de clientes para mapear atividades para os clientes.
    - Informações de atividades que contêm o nome e a data da atividade.
    - O esquema de dados semânticos para atividades do cliente inclui:
        - **Chave primária:** Um identificador exclusivo para uma atividade. Por exemplo, uma visita a um site ou um registro de uso que mostra que o cliente experimentou uma amostra do seu produto.
        - **Carimbo de data/hora:** A data e a hora do evento identificado pela chave primária.
        - **Evento:** O nome do evento que você deseja usar. Por exemplo, um campo denominado "UserAction" em um supermercado pode ser um cupom usado pelo cliente.
        - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo denominado "CouponValue" em um supermercado pode ser o valor da moeda do cupom.
- (Opcional) Dados sobre seus clientes:
    - Esses dados devem ser alinhados a atributos mais estáticos para garantir o melhor desempenho do modelo.
    - O esquema de dados semânticos para dados do cliente inclui:
        - **Identificação do Cliente**: identificador exclusivo de um cliente.
        - **Data de criação**: data em que o cliente foi adicionado inicialmente.
        - **Estado ou Província**: localização do estado ou província de um cliente.
        - **País:** o país de um cliente.
        - **Indústria:** o tipo de setor de um cliente. Por exemplo, um campo denominado "Indústria" em uma torrefadora de café pode indicar se o cliente era varejista.
        - **Classificação:** a categorização de um cliente para sua empresa. Por exemplo, um campo denominado "ValueSegment" em uma torrefadora de café pode ser a camada do cliente com base no tamanho do cliente.

---

- Características de dados sugeridas:
    - Dados históricos suficientes: dados de transação de pelo menos o dobro da janela de tempo selecionada. De preferência, de dois a três anos do histórico de transações. 
    - Várias compras por cliente: idealmente, pelo menos duas transações por cliente.
    - Número de clientes: pelo menos 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos. O modelo falhará com menos de 10 clientes e dados históricos insuficientes.
    - Integridade dos dados: menos de 20% de valores ausentes no campo de dados da entidade fornecida.

> [!NOTE]
> Para uma empresa com alta frequência de compra pelos clientes (em intervalos de algumas semanas), é recomendável selecionar uma janela de previsão e uma definição de rotatividade mais curtas. Para baixa frequência de compra (em intervalos de alguns meses ou uma vez por ano), escolha uma janela de previsão e uma definição de rotatividade mais longas.

## <a name="create-a-transaction-churn-prediction"></a>Crie uma previsão de rotatividade de transações

1. No Customer Insights, acesse **Inteligência** > **Previsões**.

1. Selecione o bloco **Modelo de rotatividade de clientes (versão preliminar)** e, em seguida, selecione **Usar este modelo**.

1. No painel **Modelo de rotatividade de clientes (versão preliminar)**, escolha **Transação** e selecione **Introdução**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de tela com a opção de transação selecionada no painel do modelo de rotatividade do cliente.":::
 
### <a name="name-model"></a>Nomear modelo

1. Forneça um nome para o modelo para diferenciá-lo dos outros modelos.

1. Forneça um nome para a entidade de saída usando somente letras e números, sem espaços. Esse é o nome que a entidade de modelo usará. 

1. Selecione **Avançar**

### <a name="define-customer-churn"></a>Definir rotatividade de clientes

1. Defina a **Janela de previsão**. Por exemplo, preveja o risco de rotatividade para seus clientes nos próximos 90 dias a fim de alinhá-lo aos seus esforços de retenção de marketing. A previsão do risco de rotatividade para um período mais longo ou mais curto pode dificultar a abordagem dos fatores no seu perfil de risco de rotatividade, mas depende dos requisitos comerciais específicos.
   >[!TIP]
   > Você pode selecionar **Salvar rascunho** a qualquer momento para salvar o previsão como rascunho. Você encontrará o rascunho da previsão na guia **Minhas previsões** para continuar.

1. Insira o número de dias para definir a rotatividade no campo **Definição de rotatividade**. Por exemplo, se um cliente não fez compras nos últimos 30 dias, ele pode ser considerado como um cliente com rotatividade para sua empresa. 

1. Selecione **Avançar** para continuar.

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** e escolha o tipo de atividade no painel lateral que contém a transação necessária ou as informações do histórico de compras.

1. Em **Selecionar atividades**, escolha as atividades específicas a partir do tipo de atividade selecionado no qual você deseja concentrar o cálculo.

   :::image type="content" source="media/transaction-churn-select-activity.PNG" alt-text="Painel lateral mostrando a escolha de atividades específicas no tipo semântico.":::

   Se você ainda não mapeou a atividade para um tipo semântico, selecione **Editar** para fazer isso. A experiência guiada para mapear atividades semânticas é aberta. Mapeie seus dados para os campos correspondentes no tipo de atividade selecionado.

1. Mapeie os atributos semânticos para os campos necessários para executar o modelo. Se os campos abaixo não estiverem preenchidos, configure o relacionamento da sua entidade do histórico de compras com a entidade *Cliente*. Selecione **Salvar**.

1. Na etapa **Adicionar dados necessários**, selecione **Avançar** para continuar se você não quiser adicionar mais atividades.


# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

### <a name="add-additional-data-optional"></a>Adicionar outros dados (opcional)

Configure o relacionamento da sua entidade de atividade do cliente com a entidade *Cliente*.

1. Selecione o campo que identifica o cliente na tabela de atividades do cliente. Ele pode estar diretamente relacionado à ID do cliente principal da sua entidade *Cliente*.

1. Selecione a entidade que é sua entidade *Cliente* primária.

1. Insira um nome que descreva a relação.

#### <a name="customer-activities"></a>Atividades do cliente

1. Opcionalmente, selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que contém os dados que você gostaria de usar e, em seguida, selecione uma ou mais atividades na seção **Atividades**.

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está configurando. Selecione **Criar novo** e escolha um tipo de atividade disponível ou crie um novo.

1. Selecione **Próximo** e **Salvar**.

1. Se você tiver outras atividades do cliente que gostaria de incluir, repita as etapas acima.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

### <a name="select-prediction-level"></a>Selecione o nível de previsão

A maioria das previsões é criada no nível do cliente. Em algumas situações, isso pode não ser granular o suficiente para atender às suas necessidades de negócio. Você pode usar esse recurso para prever a rotatividade de uma filial de um cliente, por exemplo, em vez do cliente como um todo.

1. Para criar uma previsão em um nível mais granular do que o do cliente, escolha **Selecionar a entidade para um nível secundário**. Se a opção não estiver disponível, certifique-se de ter concluído a seção anterior.

1. Expanda as entidades das quais deseja escolher o nível secundário ou use a caixa de filtro de pesquisa para filtrar as opções selecionadas.

1. Escolha o atributo que deseja usar como nível secundário e selecione **Adicionar**.

1. Selecione **Avançar**

> [!NOTE]
> As entidades disponíveis nesta seção são exibidas porque têm um relacionamento com a entidade que você escolheu na seção anterior. Se você não vir a entidade que deseja adicionar, verifique se ela tem um relacionamento válido presente em **Relacionamentos**. Apenas relacionamentos um-para-um e muitos-para-um são válidos para esta configuração.

### <a name="add-additional-data-optional"></a>Adicionar outros dados (opcional)

Configure o relacionamento da sua entidade de atividade do cliente com a entidade *Cliente*.

1. Selecione o campo que identifica o cliente na tabela de atividades do cliente. Ele pode estar diretamente relacionado à ID do cliente principal da sua entidade *Cliente*.

1. Selecione a entidade que é sua entidade *Cliente* primária.

1. Insira um nome que descreva a relação.

#### <a name="customer-activities"></a>Atividades do cliente

1. Opcionalmente, selecione **Adicionar dados** para **Atividades do cliente**.

1. Selecione o tipo de atividade semântica que contém os dados que você gostaria de usar e, em seguida, selecione uma ou mais atividades na seção **Atividades**.

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está configurando. Selecione **Criar novo** e escolha um tipo de atividade disponível ou crie um novo.

1. Selecione **Próximo** e **Salvar**.

1. Se você tiver outras atividades do cliente que gostaria de incluir, repita as etapas acima.

#### <a name="customers-data"></a>Dados de clientes

1. Opcionalmente, selecione **Adicionar dados** como **Dados de clientes**.

1. Mapeie os atributos semânticos para campos em seus próprios dados de cliente, conforme identificado. Os dados nos campos usados não devem ser alterados com frequência para garantir o melhor desempenho do modelo. Por exemplo, a seleção de um campo para "Classificação" que mudasse a cada mês teria apenas o último valor utilizado na previsão, embora historicamente o mesmo valor pudesse não se aplicar ao cliente ao construir os padrões de previsão.

1. Selecione **Avançar**

### <a name="provide-an-optional-list-of-benchmark-accounts"></a>Forneça uma lista opcional de contas de referência

Adicione uma lista de seus clientes corporativos e contas que deseja usar como benchmarks. Você terá [detalhes para essas contas de referência](#review-a-prediction-status-and-results) incluindo sua pontuação de rotatividade e os recursos mais influentes que impactaram sua previsão de rotatividade.

1. Selecione **+ Adicionar clientes**.

1. Escolha os clientes que atuam como referência.

1. Selecione **Avançar** para continuar.

---

### <a name="set-schedule-and-review-configuration"></a>Definir agenda e revisar configuração

1. Defina uma frequência para treinar o modelo novamente. Essa configuração é importante para atualizar a precisão das previsões à medida que novos dados são ingeridos. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**.

1. Revise a configuração da previsão. Você pode voltar às etapas anteriores selecionando **Editar** sob o valor mostrado. Ou você pode selecionar uma etapa da configuração no indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Salvar e executar** para iniciar o processo de previsão. Na guia **Minhas previsões**, você pode ver o status das previsões. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Revisar o status e os resultados de uma previsão

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione a previsão que você deseja revisar.
   - **Nome da previsão**: nome da previsão fornecido ao criá-la.
   - **Tipo de previsão**: tipo de modelo usado para a previsão
   - **Entidade de saída**: nome da entidade que armazenará a saída da previsão. Você pode encontrar uma entidade com esse nome em **Dados** > **Entidades**.
     Na entidade de saída, *ChurnScore* é a probabilidade prevista de rotatividade e *IsChurn* é um rótulo binário baseado em *ChurnScore* com limite de 0,5. O limite padrão pode não funcionar para o seu cenário. [Criar um novo segmento](segments.md#create-a-new-segment) com o limite de sua preferência.
     Nem todos os clientes são necessariamente clientes ativos. Alguns deles podem não ter tido nenhuma atividade por um longo período e já são considerados com rotatividade, com base na sua definição de rotatividade. Prever o risco de desligamento para clientes que já se desligaram não é útil porque eles não são o público-alvo de interesse.
   - **Campo previsto**: este campo é preenchido apenas para alguns tipos de previsões e não é usado na previsão de rotatividade.
   - **Status**: status da execução da previsão.
        - **Na fila**: a previsão está aguardando a execução de outros processos.
        - **Atualizando**: a previsão está em execução no momento para produzir resultados que fluirão para a entidade de saída.
        - **Falha**: a execução da previsão falhou. [Analisar os logs](manage-predictions.md#troubleshoot-a-failed-prediction) para obter mais detalhes.
        - **Êxito**: a previsão teve êxito. Selecione **Exibir** nos três pontos verticais para revisar a previsão
   - **Editado**: a data em que a configuração da previsão foi alterada.
   - **Última atualização**: a data em que a previsão atualizou resultados na entidade de saída.

1. Selecione os três pontos verticais ao lado da previsão cujos resultados deseja revisar e selecione **Exibir**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Exibir controle para ver os resultados de uma previsão.":::

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

1. Há três seções principais de dados na página de resultados:
   - **Desempenho do modelo de treinamento**: A, B ou C são pontuações possíveis. Essa pontuação indica o desempenho da previsão e pode ajudar você a decidir usar os resultados armazenados na entidade de saída. As pontuações são determinadas com base nas seguintes regras: 
        - **A** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é maior do que a taxa de linha de base em pelo menos 10%.
            
        - **B** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é até 10% maior do que a linha de base.
            
        - **C** quando o modelo previu com precisão menos de 50% das previsões totais ou quando a porcentagem de previsões precisas para clientes com rotatividade é menor do que a linha de base.
               
        - **Linha de base** usa a entrada de janela de tempo da previsão para o modelo (por exemplo, um ano) e o modelo cria diferentes frações de tempo dividindo-a por 2 até atingir um mês ou menos. Ele usa essas frações para criar uma regra de negócios para clientes que não compraram nesse período. Esses clientes são considerados clientes com rotatividade. A regra de negócios baseada em tempo com a maior capacidade de prever quem tem propensão à rotatividade é escolhida como modelo de linha de base.
            
    - **Probabilidade de rotatividade (número de clientes)**: grupos de clientes com base no risco previsto de rotatividade. Esses dados podem ajudar você mais tarde, se quiser criar um segmento de clientes com alto risco de rotatividade. Esses segmentos ajudam a entender qual deve ser o limite para a assinatura do segmento.
       
    - **Fatores mais influentes**: muitos fatores são levados em consideração ao criar a previsão. Cada um dos fatores tem sua importância calculada para as previsões agregadas que um modelo cria. Você pode usar esses fatores para ajudar a validar os resultados de sua previsão ou usar essas informações mais tarde para [criar segmentos](segments.md) que podem ajudar a influenciar o risco de rotatividade dos clientes.


# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

1. Há três seções principais de dados na página de resultados:
   - **Desempenho do modelo de treinamento**: A, B ou C são pontuações possíveis. Essa pontuação indica o desempenho da previsão e pode ajudar você a decidir usar os resultados armazenados na entidade de saída. As pontuações são determinadas com base nas seguintes regras: 
        - **A** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é maior do que a taxa de linha de base em pelo menos 10%.
            
        - **B** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é até 10% maior do que a linha de base.
            
        - **C** quando o modelo previu com precisão menos de 50% das previsões totais ou quando a porcentagem de previsões precisas para clientes com rotatividade é menor do que a linha de base.
               
        - **Linha de base** usa a entrada de janela de tempo da previsão para o modelo (por exemplo, um ano) e o modelo cria diferentes frações de tempo dividindo-a por 2 até atingir um mês ou menos. Ele usa essas frações para criar uma regra de negócios para clientes que não compraram nesse período. Esses clientes são considerados clientes com rotatividade. A regra de negócios baseada em tempo com a maior capacidade de prever quem tem propensão à rotatividade é escolhida como modelo de linha de base.
            
    - **Probabilidade de rotatividade (número de clientes)**: grupos de clientes com base no risco previsto de rotatividade. Esses dados podem ajudar você mais tarde, se quiser criar um segmento de clientes com alto risco de rotatividade. Esses segmentos ajudam a entender qual deve ser o limite para a assinatura do segmento.
       
    - **Fatores mais influentes**: muitos fatores são levados em consideração ao criar a previsão. Cada um dos fatores tem sua importância calculada para as previsões agregadas que um modelo cria. Você pode usar esses fatores para ajudar a validar os resultados de sua previsão ou usar essas informações mais tarde para [criar segmentos](segments.md) que podem ajudar a influenciar o risco de rotatividade dos clientes.


1. Para contas corporativas, você encontrará uma página de informações **Análise de características influentes**. Ela contém quatro seções de dados:

    - O item selecionado no painel direito determina o conteúdo desta página. Selecione um item de **Principais clientes** ou **Clientes de referência**. Ambas as listas são ordenadas pelo valor decrescente da pontuação da rotatividade, quer a pontuação seja apenas para o cliente ou uma pontuação combinada para os clientes e uma categoria de produto de nível secundário como a categoria de produto.
        
        - **Principais clientes**: lista de 10 clientes com maior risco de desligamento e menor risco de desligamento com base em suas pontuações de desligamento. 
        - **Clientes de referência**: lista de até 10 clientes que foram selecionados durante a configuração do modelo.
 
    - **Pontuação de rotatividade:** mostra a pontuação de rotatividade do item selecionado no painel direito.
    
    - **Distribuição de risco de rotatividade:** mostra a distribuição do risco de rotatividade entre os clientes e o percentil em que se encontra o cliente selecionado. 
    
    - **Principais recursos que aumentam e diminuem o risco de rotatividade:** para o item selecionado no painel direito, são listados os cinco principais recursos que aumentaram e diminuíram o risco de rotatividade. Para cada recurso influente, você encontra o valor do recurso para aquele item e sua influência na pontuação de rotatividade. O valor médio de cada recurso nos segmentos de clientes de baixa, média e alta rotatividade também é exibido. Ele ajuda a contextualizar melhor os valores dos recursos mais influentes para o item selecionado e compará-lo com segmentos de clientes de baixa, média e alta rotatividade.

       - Baixo: contas ou combinações de contas e nível secundário com uma pontuação de rotatividade entre 0 e 0,33
       - Médio: contas ou combinações de contas e nível secundário com uma pontuação de rotatividade entre 0,33 e 0,66
       - Alto: contas ou combinações de contas e nível secundário com uma pontuação de rotatividade maior que 0,66
    
       Quando você prevê o desligamento no nível da conta, todas as contas são consideradas na derivação dos valores médios dos recursos para os segmentos de desligamento. Para previsões de rotatividade no nível secundário para cada conta, a derivação dos segmentos de rotatividade depende do nível secundário do item selecionado no painel lateral. Por exemplo, se um item tem um nível secundário de categoria de produto = material de escritório, então somente os itens que têm material de escritório como categoria de produto são considerados ao derivar os valores médios de característica para segmentos de rotatividade. Esta lógica é aplicada para garantir uma comparação justa dos valores das características do item com os valores médios em segmentos de baixa, média e alta rotatividade.

       Em alguns casos, o valor médio dos segmentos de baixa, média ou alta rotatividade está vazio ou não disponível porque não há itens que pertençam aos segmentos de rotatividade correspondentes com base na definição acima.
       
       > [!NOTE]
       > A interpretação dos valores nas colunas de média baixa, média e alta é diferente para características categóricas como país/região ou setor. Como a noção de valor de recurso "média" não se aplica a recursos categóricos, os valores nessas colunas são a proporção de clientes em segmentos de baixa, média ou alta rotatividade que têm o mesmo valor do recurso categórico em comparação com o item selecionado no painel lateral.

---

## <a name="manage-predictions"></a>Gerenciar previsões

É possível otimizar, solucionar problemas, atualizar ou excluir previsões. Revise um relatório de usabilidade de dados de entrada para descobrir como fazer uma previsão mais rápida e confiável. Para mais informações, vá para [Gerenciar previsões](manage-predictions.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
