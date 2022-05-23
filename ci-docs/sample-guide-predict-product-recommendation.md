---
title: Guia de amostra para previsão de recomendação do produto
description: Use este guia de amostra para experimentar o modelo de previsão de recomendação do produto pronto para uso.
ms.date: 05/16/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-predictions
- ci-create-prediction
- customerInsights
ms.openlocfilehash: cc72cce15fa0c9e92dbf202c803e99514c9ce2b1
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762672"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guia de amostra para previsão de recomendação do produto

Explicaremos a você um exemplo de ponta a ponta de previsão de recomendação do produto usando os dados de exemplo fornecidos abaixo.

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que são vendidas por meio do site Contoso Coffee. O objetivo deles é entender quais produtos eles devem recomendar a seus clientes recorrentes. Saber o que os clientes estão mais **propenso a comprar**, pode ajudá-los a economizar esforços de marketing, concentrando-se em itens específicos.

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.
- Recomendamos que você implemente as seguintes etapas [em um novo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Revise os artigos [sobre ingestão de dados](data-sources.md) e [importação de fontes de dados usando conectores do Power Query](connect-power-query.md) especificamente. As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados do cliente da plataforma de comércio eletrônico

1. Crie uma fonte de dados chamada **Comércio eletrônico**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira a URL para contatos de eCommerce: [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo 'Nome' no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**

1. **Salvar** a fonte de dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**. Escolha o conector de **Texto/CSV** novamente.

1. Insira a URL para dados de **Compras Online** [https://aka.ms/ciadclassonline](https://aka.ms/ciadclassonline).

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel lateral, renomeie sua fonte de dados de **Consulta** para **eCommercePurchases**.

1. **Salvar** a fonte de dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados do cliente do esquema de fidelidade

1. Crie uma fonte de dados chamada **LoyaltyScheme**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira a URL para contatos de eCommerce [https://aka.ms/ciadclasscustomerloyalty](https://aka.ms/ciadclasscustomerloyalty).

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **loyCustomers**.

1. **Salvar** a fonte de dados.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-product-recommendation-prediction"></a>Tarefa 3 - Configurar previsão de recomendação de produto

Com os perfis de cliente unificados em vigor, agora podemos executar a previsão de recomendação de produtos.

1. Vá para **Inteligência** > **Previsão** escolha **Recomendação do produto**.

1. Selecione **Começar**.

1. Nomeie o modelo **Previsão do modelo de recomendação do produto OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Defina três condições para o modelo:

   - **Número de produtos**: Defina este valor como **5**. Esta configuração define quantos produtos você deseja recomendar aos seus clientes.

   - **Compras repetidas esperadas**: selecione **Sim** para indicar que deseja incluir produtos na recomendação que seus clientes compraram antes.

   - **Janela do passado:** Selecione pelo menos **365 dias**. Essa configuração define até que ponto o modelo retrocederá na atividade do cliente para usá-la como entrada para suas recomendações.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferências do modelo para o modelo de recomendação do produto.":::

1. Na etapa **Adicionar dados obrigatórios**, selecione **Adicionar dados**.

1. No painel **Adicionar dados**, escolha **SalesOrderLine** como a entidade do histórico de compras. Neste momento, provavelmente ainda não está configurada. Abra o link no painel para criar a atividade com as seguintes etapas:
   1. Insira um **Nome de atividade** e escolha *eCommercePurchases:eCommerce* como **Entidade de atividade**. A **Chave primária** é *PurchaseId*.
   1. Defina e nomeie o relacionamento com a *entidade eCommerceContacts:eCommerce* e escolha **ContactId** como a chave estrangeira.
   1. Para Unificação da atividade, defina **Atividade do evento** como *TotalPrice* e Carimbo de data/hora como *PurchasedOn*. Você pode especificar mais campos conforme descrito em [Atividades do cliente](activities.md).
   1. Para **Tipo de atividade**, escolha *SalesOrderLine*. Mapeie os campos de atividades a seguir:
      - ID de linha da ordem: PurchaseId
      - ID da Ordem: PurchaseId
      - Dados da ordem: PurchasedOn
      - ID do Produto: ProductId
      - Valor: TotalPrice
   1. Revise e conclua a atividade antes de voltar para a configuração do modelo.

1. De volta à etapa **Selecionar atividades**, escolha a atividade recém-criada na seção **Atividades**. Selecione **Avançar** e o mapeamento de atributos já estará preenchido. Selecione **Salvar**.

1. Neste guia de exemplo, ignoramos **Adicionar informações do produto** e **Filtros de produto** porque não temos dados de informações do produto.

1. Na etapa **Atualizações de dados**, defina o cronograma do modelo.

   O modelo precisa ser treinado regularmente para aprender novos padrões quando novos dados forem ingeridos. Para este exemplo, selecione **Mensal**.

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**. Levará alguns minutos para executar o modelo pela primeira vez.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Agora, você pode revisar as explicações do modelo de recomendação do produto. Para mais informações, consulte [Analisar um status de previsão e resultados](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tarefa 5 - Crie um segmento de produtos altamente comprados

Executar o modelo de produção cria uma nova entidade que você pode ver em **Dados** > **Entidades**.

Você pode criar um novo segmento com base na entidade criada pelo modelo.

1. Vá para **Segmentos**. Selecione **Novo** e escolha **Criar de Inteligência**.

   ![Criando um segmento com a saída do modelo.](media/segment-intelligence.png)

1. Selecione o ponto de extremidade **OOBSubscriptionChurnPrediction** e defina o segmento:

   - Campo: ProductID
   - Valor: selecione os três principais IDs de produto

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Criar um segmento a partir dos resultados do modelo.":::

Agora você tem um segmento atualizado dinamicamente que identifica os clientes que podem estar interessados em comprar os três produtos mais recomendados.

Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
