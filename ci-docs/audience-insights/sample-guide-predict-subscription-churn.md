---
title: Guia de amostra para previsão de rotatividade de assinaturas
description: Use este guia de amostra para experimentar o modelo de previsão de rotatividade de assinatura pronto para uso.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269822"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a>Guia de amostra para previsão de rotatividade de assinaturas (versão preliminar)

Explicaremos a você um exemplo de ponta a ponta de previsão de rotatividade de assinatura usando os dados de amostra fornecidos abaixo. 

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que são vendidas por meio do site Contoso Coffee. Recentemente, eles começaram um negócio de assinatura para seus clientes obterem café regularmente. O objetivo deles é entender quais clientes assinantes podem cancelar sua assinatura nos próximos meses. Saber qual de seus clientes está **propenso a rotacionar**, pode ajudá-los a economizar esforços de marketing, concentrando-se em mantê-los.

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.
- Recomendamos que você implemente as seguintes etapas [em um novo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Reveja os artigos [sobre ingestão de dados](data-sources.md) e [importar fontes de dados usando Power Query conectores](connect-power-query.md), especificamente. As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral. 

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados do cliente da plataforma de comércio eletrônico

1. Crie uma fonte de dados chamada **Comércio eletrônico**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**

1. Salvar a fonte de dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados do cliente do esquema de fidelidade

1. Crie uma fonte de dados chamada **LoyaltyScheme**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **loyCustomers**.

1. Salvar a fonte de dados.

### <a name="ingest-subscription-information"></a>Ingerir informações de assinatura

1. Crie uma fonte de dados chamada **SubscriptionHistory**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadchurnsubscriptionhistory.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **SubscriptioID**: Número inteiro
   - **SubscriptionAmount**: Moeda
   - **SubscriptionEndDate**: Data/Hora
   - **SubscriptionStartDate**: Data/Hora
   - **TransactionDate**: Data/Hora
   - **IsRecurring**: Verdadeiro/Falso
   - **Is_auto_renew**: Verdadeiro/Falso
   - **RecurringFrequencyInMonths**: Número inteiro

1. No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **SubscriptionHistory**.

1. Salvar a fonte de dados.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dados do cliente de comentários do site

1. Crie uma fonte de dados chamada **Site da Web**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasswebsite.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **ReviewRating**: Número inteiro
   - **ReviewDate**: Data

1. No campo 'Nome' no painel direito, renomeie sua fonte de dados de **Consulta** para **webReviews**.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Depois de ingerir os dados, agora iniciamos o processo de **Mapear, Corresponder, Mesclar** para criar um perfil de cliente unificado. Para obter mais informações, consulte [Unificação de dados](data-unification.md).

### <a name="map"></a>Mapa 

1. Depois de ingerir os dados, mapeie os contatos dos dados de comércio eletrônico e de fidelidade para tipos de dados comuns. Vá para **Dados** > **Unificar** > **Mapear**.

1. Selecione as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**. 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unifique as fontes de dados de comércio eletrônico e fidelidade.":::

1. Selecione **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifique LoyaltyId como chave primária.":::

### <a name="match"></a>Corresponder

1. Vá para a guia **Corresponder** e selecione **Definir pedido**.

1. Na lista suspensa **Primário**, escolha **eCommerceContacts : eCommerce** como fonte primária e inclua todos os registros.

1. Na lista suspensa **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registros.

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificar correspondência de comércio eletrônico e fidelidade.":::

1. Selecione **Criar uma nova regra**

1. Adicione sua primeira condição usando FullName.

   * Para eCommerceContacts selecione **FullName** no menu suspenso.
   * Para loyCustomers selecione **FullName** no menu suspenso.
   * Selecione o menu suspenso **Normalizar** e escolha **Inserir (telefone, nome, endereço,...)**.
   * Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.

1. Digite o nome **FullName, Email** para a nova regra.

   * Adicione uma segunda condição para o endereço de e-mail selecionando **Adicionar condição**
   * Para a entidade eCommerceContacts, escolha **Email** no menu suspenso.
   * Para a entidade loyCustomers, escolha **Email** no menu suspenso. 
   * Deixe o campo Normalizar em branco. 
   * Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Regra de correspondência unificada para nome e email.":::

7. Selecione **Salvar** e **Executar**.

### <a name="merge"></a>Merge

1. Vá para a guia **Mesclar**.

1. Na entidade **ContactId** para **loyCustomers**, altere o nome de exibição para **ContactIdLOYALTY** para diferenciá-lo dos outros IDs ingeridos.

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid de loyalty id.":::

1. Selecione **Salvar** e **Executar** para iniciar o processo de mesclagem.


## <a name="task-3---configure-the-subscription-churn-prediction"></a>Tarefa 3 - Configurar a rotatividade de previsão de assinatura

Com os perfis de cliente unificados em vigor, agora podemos executar a previsão de rotatividade de assinatura. Para obter etapas detalhadas, consulte o artigo [Previsão de rotatividade de assinatura (versão preliminar)](predict-subscription-churn.md). 

1. Vá para **Inteligência** > **Descobrir** e selecione usar o **Modelo de rotatividade do cliente**.

1. Selecione a opção **Inscrição** e selecione **Iniciar**.

1. Nomeie o modelo **Previsão de rotatividade de transação de assinaturas OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.

1. Defina duas condições para o modelo de rotatividade:

   * **Dias desde o término da assinatura**: **pelo menos 60** dias. Se um cliente não tiver renovado a assinatura nesse período depois do término da assinatura, ele será considerado rotacionado. 

   * **Definição de rotatividade**: **pelo menos 93** dias. A duração em que o modelo prevê quais clientes podem se desligar. Quanto mais longe você olhar no futuro, menos precisos serão os resultados.

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecione a janela de previsão de niveladores de modelo e definição de rotatividade.":::

1. Selecione **Adicionar data necessária** e selecione **Adicionar dados** para histórico de assinaturas.

1. Adicione a entidade **Subscription : SubscriptionHistory** e mapeie os campos do eCommerce para os campos correspondentes exigidos pelo modelo.

1. Junte-se à entidade **Subscription : SubscriptionHistory** com **eCommerceContacts : eCommerce**, nomeie o relacionamento de **eCommerceSubscription**.

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Junte-se a entidades de comércio eletrônico.":::

1. Em Atividades do cliente, adicione a entidade **webReviews : Website** e mapeie os campos do webReviews para os campos correspondentes exigidos pelo modelo. 
   - Chave primária: ReviewId
   - Carimbo de data/hora: ReviewDate
   - Evento: ReviewRating

1. Configurar uma atividade para revisões do site. Selecione a atividade **Revisão** e junte-se à entidade **webReviews : Website** com **eCommerceContacts : eCommerce**.

1. Selecione **Avançar** para definir o cronograma do modelo.

   O modelo precisa ser treinado regularmente para aprender novos padrões quando novos dados forem ingeridos. Para este exemplo, selecione **Mensal**.

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Agora, você pode revisar as explicações do modelo de rotatividade de assinatura. Para mais informações, consulte [Analisar um status de previsão e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 5 - Crie um segmento de clientes de alto risco de rotatividade

Executar o modelo de produção cria uma nova entidade que você pode ver em **Dados** > **Entidades**.   

Você pode criar um novo segmento com base na entidade criada pelo modelo.

1.  Vá para **Segmentos**. Selecione **Novo** e escolha **Criar de** > **Inteligência**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Criando um segmento com a saída do modelo.":::

1. Selecione o ponto de extremidade **OOBSubscriptionChurnPrediction** e defina o segmento: 
   - Campo: ChurnScore
   - Operador: maior que
   - Valor: 0,6
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configure o segmento de rotatividade de assinaturas.":::

Agora, você tem um segmento que é atualizado dinamicamente que identifica clientes de alto risco de rotatividade para este negócio de assinatura.

Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]