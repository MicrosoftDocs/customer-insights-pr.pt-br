---
title: Guia de amostra para previsão de rotatividade de assinaturas
description: Use este guia de amostra para experimentar o modelo de previsão de rotatividade de assinatura pronto para uso.
ms.date: 09/19/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: wameng
manager: shellyha
searchScope:
- ci-create-prediction
- customerInsights
ms.openlocfilehash: 7e754be9a2cb9450949c6b3667bbd37aa39cf0bf
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609992"
---
# <a name="subscription-churn-prediction-sample-guide"></a>Guia de amostra para previsão de rotatividade de assinaturas

Este guia dará a você um exemplo de ponta a ponta de previsão de rotatividade de assinatura usando os dados de amostra. Recomendamos que você teste esta previsão [em um novo ambiente](manage-environments.md).

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade. Eles vendem os produtos pelo site da Contoso Coffee. Recentemente, eles começaram um negócio de assinatura para seus clientes obterem café regularmente. O objetivo deles é entender quais clientes assinantes podem cancelar sua assinatura nos próximos meses. Saber qual de seus clientes está **propenso a rotacionar**, pode ajudá-los a economizar esforços de marketing, concentrando-se em mantê-los.

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Revise os artigos [sobre ingestão de dados](data-sources.md) e [conexão a uma fonte de dados do Power Query](connect-power-query.md). As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados do cliente da plataforma de comércio eletrônico

1. Crie uma fonte de dados do Power Query chamada **Comércio eletrônico** e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **eCommerceContacts**

1. Salvar a fonte de dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados do cliente do esquema de fidelidade

1. Crie uma fonte de dados chamada **LoyaltyScheme** e selecione o conector **Texto/CSV**.

1. Insira o URL para clientes de fidelidade https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **loyCustomers**.

1. Salvar a fonte de dados.

### <a name="ingest-subscription-information"></a>Ingerir informações de assinatura

1. Crie uma fonte de dados chamada **SubscriptionHistory** e selecione o conector **Texto/CSV**.

1. Digite o URL para assinaturas https://aka.ms/ciadchurnsubscriptionhistory.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **SubscriptioID**: Número inteiro
   - **SubscriptionAmount**: Moeda
   - **SubscriptionEndDate**: Data/Hora
   - **SubscriptionStartDate**: Data/Hora
   - **TransactionDate**: Data/Hora
   - **IsRecurring**: Verdadeiro/Falso
   - **Is_auto_renew**: Verdadeiro/Falso
   - **RecurringFrequencyInMonths**: Número inteiro

1. No campo **Nome** no painel direito, renomeie sua fonte de dados de para **SubscriptionHistory**.

1. Salvar a fonte de dados.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dados do cliente de comentários do site

1. Crie uma fonte de dados chamada **Website** e selecione o conector **Texto/CSV**.

1. Digite a URL para avaliações do site https://aka.ms/ciadclasswebsite.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **ReviewRating**: Número inteiro
   - **ReviewDate**: Data

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **webReviews**.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Revise o artigo [sobre da unificação de dados](data-unification.md). As informações a seguir pressupõem que você está familiarizado com a unificação de dados em geral.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tarefa 3 - Criar atividade do histórico de transações

Revise o artigo [sobre as atividades do cliente](activities.md). As informações a seguir pressupõem que você está familiarizado com a criação de atividades em geral.

1. Crie uma atividade chamada **SubscriptionHistory** com a entidade *Assinatura* e sua chave primária, **CustomerId**.

1. Crie uma relação entre *SubscriptionHistory:Subscription* e *eCommerceContacts:eCommerce* com **CustomerID** como a chave estrangeira para conectar as duas entidades.

1. Selecione **SubscriptionType** para a **EventActivity** e **SubscriptionEndDate** para o **TimeStamp**.

1. Selecione **Subscription** para o **Tipo de atividade** e mapeie semanticamente os dados da atividade.

1. Execute a atividade.

1. Adicione outra atividade e mapeie os nomes de seus campos para os campos correspondentes:
   - Entidade de atividade do cliente: Reviews:Website
   - Chave primária: Website.Reviews.ReviewId
   - Carimbo de data/hora: Website.Reviews.ReviewDate
   - Evento (nome da atividade): Website.Reviews.ActivityTypeDisplay
   - Detalhes (quantidade ou valor): Website.Reviews.ReviewRating

1. Execute a atividade.

## <a name="task-4---configure-the-subscription-churn-prediction"></a>Tarefa 4 - Configurar a rotatividade de previsão de assinatura

Com os perfis de cliente unificados em vigor e a atividade criada, execute a previsão de rotatividade de assinatura. Para obter etapas detalhadas, consulte [Previsão da rotatividade de assinaturas](predict-subscription-churn.md).

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Modelo de rotatividade de clientes**.

1. Selecione **Assinatura** para o tipo de rotatividade e depois **Introdução**.

1. Nomeie o modelo **Previsão de rotatividade de transação de assinaturas OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.

1. Definir as preferências do modelo:
   - **Dias desde que a assinatura terminou**: **60** dias para indicar que um cliente é considerado desligado se não renovar a assinatura nesse período após o término da assinatura.
   - **Dias para olhar para o futuro para prever a rotatividade**: **93** dias, que é a duração que o modelo prevê que clientes podem se desligar. Quanto mais longe você olhar no futuro, menos precisos serão os resultados.

   :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecione as preferências do modelo e a definição de rotatividade.":::

1. Selecione **Avançar**

1. Na etapa **Dados obrigatórios**, selecione **Adicionar dados** para fornecer o histórico de assinaturas.

1. Selecione **Assinatura** e a entidade SubscriptionHistory e selecione **Avançar**. Os dados necessários são preenchidos automaticamente a partir da atividade. Selecione **Salvar**.

1. Em Atividades do cliente, selecione **Adicionar dados**.

1. Para este exemplo, adicione a atividade de avaliação da web.

1. Selecione **Avançar**

1. Na etapa **Atualizações de dados**, selecione **Mensal** para o cronograma do modelo.

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Revise as explicações do modelo de rotatividade de assinatura. Para mais informações, consulte [Analisar resultados de previsão](predict-subscription-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 6 - Crie um segmento de clientes de alto risco de rotatividade

Executar o modelo cria uma entidade, que é listada em **Dados** > **Entidades**. Você pode criar um novo segmento com base na entidade criada pelo modelo.

1. Na página de resultados, selecione **Criar segmento**.

1. Crie uma regra usando a entidade **OOBSubscriptionChurnPrediction** e defina o segmento:
   - **Campo**: ChurnScore
   - **Operador**: maior que
   - **Valor**: 0.6

1. Selecione **Salvar** e **Execute** o segmento.

Agora, você tem um segmento que é atualizado dinamicamente que identifica clientes de alto risco de rotatividade para este negócio de assinatura. Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

> [!TIP]
> Você também pode criar um segmento para um modelo previsão na página **Segmentos** selecionando **Novo** e escolhendo **Criar de** > **Inteligência**. Para obter mais informações, confira [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
