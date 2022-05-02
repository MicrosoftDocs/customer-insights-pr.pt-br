---
title: Guia de amostra para previsão de recomendação do produto
description: Use este guia de amostra para experimentar o modelo de previsão de recomendação do produto pronto para uso.
ms.date: 02/10/2021
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
ms.openlocfilehash: 1115bab13bdca4a308a8d9eb5a1dc270801d16be
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645670"
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

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

5. No campo 'Nome' no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**

6. **Salvar** a fonte de dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**. Escolha o conector de **Texto/CSV** novamente.

1. Insira o URL para dados de **Compras online** https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel lateral, renomeie sua fonte de dados de **Consulta** para **eCommercePurchases**.

1. **Salvar** a fonte de dados.


### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados do cliente do esquema de fidelidade

1. Crie uma fonte de dados chamada **LoyaltyScheme**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **loyCustomers**.

1. **Salvar** a fonte de dados.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Depois de ingerir os dados, agora começamos o processo de unificação de dados para criar um perfil de cliente unificado. Para obter mais informações, consulte [Unificação de dados](data-unification.md).

### <a name="map"></a>Mapa

1. Depois de ingerir os dados, mapeie os contatos dos dados de comércio eletrônico e de fidelidade para tipos de dados comuns. Vá para **Dados** > **Unificar** > **Mapear**.

2. Selecione as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.

   ![unifique as fontes de dados de comércio eletrônico e fidelidade.](media/unify-ecommerce-loyalty.png)

3. Selecione **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.

   ![Unifique LoyaltyId como chave primária.](media/unify-loyaltyid.png)

### <a name="match"></a>Corresponder

1. Vá para a guia **Corresponder** e selecione **Definir pedido**.

2. Na lista suspensa **Primária**, escolha **eCommerceContacts : eCommerce** como sua fonte primária e inclua todos os registros.

3. Na lista suspensa **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registros.

   ![Unificar correspondência de comércio eletrônico e fidelidade.](media/unify-match-order.png)

4. Selecione **Criar uma nova regra**

5. Adicione sua primeira condição usando FullName.

   - Para eCommerceContacts, selecione **FullName** na lista suspensa.
   - Para loyCustomers, selecione **FullName** na lista suspensa.
   - Selecione o menu suspenso **Normalizar** e escolha **Inserir (telefone, nome, endereço,...)**.
   - Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.

6. Digite o nome **FullName, Email** para a nova regra.

   - Adicione uma segunda condição para o endereço de e-mail selecionando **Adicionar condição**
   - Para a entidade eCommerceContacts, selecione **Email** na lista suspensa.
   - Para a entidade loyCustomers, selecione **Email** na lista suspensa.
   - Deixe o campo Normalizar em branco.
   - Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.

   ![Regra de correspondência unificada para nome e email.](media/unify-match-rule.png)

7. Selecione **Salvar** e **Executar**.

### <a name="merge"></a>Merge

1. Vá para a guia **Mesclar**.

1. Na entidade **ContactId** para **loyCustomers**, altere o nome de exibição para **ContactIdLOYALTY** para diferenciá-lo dos outros IDs ingeridos.

   ![renomear contactid de loyalty id.](media/unify-merge-contactid.png)

1. Selecione **Salvar** e **Executar** para iniciar o processo de mesclagem.

## <a name="task-3---configure-product-recommendation-prediction"></a>Tarefa 3 - Configurar previsão de recomendação de produto

Com os perfis de cliente unificados em vigor, agora podemos executar a previsão de rotatividade de assinatura.

1. Vá para **Inteligência** > **Previsão** escolha **Recomendação do produto**.

1. Selecione **Começar**.

1. Nomeie o modelo **Previsão do modelo de recomendação do produto OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Defina três condições para o modelo:

   - **Número de produtos**: Defina este valor como **5**. Esta configuração define quantos produtos você deseja recomendar aos seus clientes.

   - **Compras repetidas esperadas**: selecione **Sim** para indicar que deseja incluir produtos na recomendação que seus clientes compraram antes.

   - **Janela do passado:** Selecione pelo menos **365 dias**. Essa configuração define até que ponto o modelo retrocederá na atividade do cliente para usá-la como entrada para suas recomendações.
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferências do modelo para o modelo de recomendação do produto.":::

1. Selecione **Dados obrigatórios** e **Adicionar dados** para histórico de compras.

1. Adicione a entidade **eCommercePurchases : eCommerce** e mapeie os campos do eCommerce para os campos correspondentes exigidos pelo modelo.

1. Junte-se à entidade **eCommercePurchases : eCommerce** com **eCommerceContacts : eCommerce**.

   ![Junte-se a entidades de comércio eletrônico.](media/model-purchase-join.png)

1. Selecione **Avançar** para definir o cronograma do modelo.

   O modelo precisa ser treinado regularmente para aprender novos padrões quando novos dados forem ingeridos. Para este exemplo, selecione **Mensal**.

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**.


## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Agora, você pode revisar as explicações do modelo de recomendação do produto. Para mais informações, consulte [Analisar um status de previsão e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-purchased-products"></a>Tarefa 5 - Crie um segmento de produtos altamente comprados

Executar o modelo de produção cria uma nova entidade que você pode ver em **Dados** > **Entidades**.

Você pode criar um novo segmento com base na entidade criada pelo modelo.

1. Vá para **Segmentos**. Selecione **Novo** e escolha **Criar de** > **Inteligência**.

   ![Criando um segmento com a saída do modelo.](media/segment-intelligence.png)

1. Selecione o ponto de extremidade **OOBSubscriptionChurnPrediction** e defina o segmento:

   - Campo: ProductID
   - Operador: Valor
   - Valor: selecione os três principais IDs de produto

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Criar um segmento a partir dos resultados do modelo.":::

Agora você tem um segmento que é atualizado dinamicamente que identifica os clientes que estão mais dispostos a comprar os três produtos mais recomendados 

Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
