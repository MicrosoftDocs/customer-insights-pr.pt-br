---
title: Guia de amostra para previsão de recomendação do produto
description: Use este guia de amostra para experimentar o modelo de previsão de recomendação do produto pronto para uso.
ms.date: 09/19/2022
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
ms.openlocfilehash: 2b42a89e3f4ec8cf4f0769128b8536973365f1cb
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610130"
---
# <a name="product-recommendation-prediction-sample-guide"></a>Guia de amostra para previsão de recomendação do produto

Este guia dá a você um exemplo de ponta a ponta de previsão de recomendação do produto usando os dados de exemplo. Recomendamos que você teste esta previsão [em um novo ambiente](manage-environments.md).

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade. Eles vendem os produtos pelo site da Contoso Coffee. O objetivo deles é entender quais produtos eles devem recomendar a seus clientes recorrentes. Saber o que os clientes estão mais **propenso a comprar** pode ajudá-los a economizar esforços de marketing, concentrando-se em itens específicos.

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Revise os artigos [sobre ingestão de dados](data-sources.md) e [conexão a uma fonte de dados do Power Query](connect-power-query.md). As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados do cliente da plataforma de comércio eletrônico

1. Crie uma fonte de dados do Power Query chamada **Comércio eletrônico** e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico: https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **eCommerceContacts**.

1. **Salvar** a fonte de dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**. Escolha o conector de **Texto/CSV** novamente.

1. Insira a URL para dados de compras online https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel lateral, renomeie sua fonte de dados como **eCommercePurchases**.

1. **Salvar** a fonte de dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados do cliente do esquema de fidelidade

1. Crie uma fonte de dados chamada **LoyaltyScheme** e selecione o conector **Texto/CSV**.

1. Insira o URL para clientes fiéis https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **loyCustomers**.

1. **Salvar** a fonte de dados.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Revise o artigo [sobre da unificação de dados](data-unification.md). As informações a seguir pressupõem que você está familiarizado com a unificação de dados em geral.

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---create-transaction-history-activity"></a>Tarefa 3 - Criar atividade do histórico de transações

Revise o artigo [sobre as atividades do cliente](activities.md). As informações a seguir pressupõem que você está familiarizado com a criação de atividades em geral.

1. Crie uma atividade chamada **eCommercePurchases** com a entidade *eCommercePurchases:eCommerce* e sua chave primária, **PurchaseId**.

1. Crie uma relação entre *eCommerceCompras:eCommerce* e *eCommerceContatos:eCommerce* com **ContactID** como a chave estrangeira para conectar as duas entidades.

1. Selecione **TotalPrice** para a **EventActivity** e **PurchasedOn** para o **TimeStamp**.

1. Selecione **SalesOrderLine** para o **Tipo de atividade** e mapeie semanticamente os dados da atividade.

1. Execute a atividade.

## <a name="task-4---configure-product-recommendation-prediction"></a>Tarefa 4 - Configurar previsão de recomendação de produto

Com os perfis de cliente unificados em vigor e atividade criada, agora podemos executar a previsão de recomendação de produtos.

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Recomendações de produto (versão preliminar)**.

1. Selecione **Introdução**.

1. Nomeie o modelo **Previsão do modelo de recomendação do produto OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.

1. Selecione **Avançar**

1. Definir as preferências do modelo:
   - **Número de produtos**: **5** para definir quantos produtos você deseja recomendar aos seus clientes.
   - **Repetir compras esperadas**: **Sim** para incluir produtos adquiridos anteriormente na recomendação.
   - **Janela do passado:** **365 dias** para definir até onde o modelo olhará para trás antes de recomendar um produto novamente.

   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferências do modelo para o modelo de recomendação do produto.":::

1. Selecione **Avançar**

1. Na etapa **Adicionar histórico de compra**, selecione **Adicionar dados**.

1. Selecione **SalesOrderLine** e a entidade eCommercePurchases e selecione **Avançar**. Os dados necessários são preenchidos automaticamente a partir da atividade. Selecione **Salvar** e depois **Avançar**.

1. Ignore as etapas **Adicionar informações do produto** e **Filtros de produto** porque não temos dados de informações do produto.

1. Na etapa **Atualizações de dados**, selecione **Mensal** para o cronograma do modelo.

1. Selecione **Avançar**

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Revise as [explicações do modelo de recomendação do produto](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-purchased-products"></a>Tarefa 6 - Crie um segmento de produtos altamente comprados

Executar o modelo cria uma entidade, que é listada em **Dados** > **Entidades**. Você pode criar um novo segmento com base na entidade criada pelo modelo.

1. Na página de resultados, selecione **Criar segmento**.

1. Crie uma regra usando a entidade **OOBProductRecommendationModelPrediction** e defina o segmento:
   - **Campo**: ProductID
   - **Valor**: selecione os três principais IDs de produto

1. Selecione **Salvar** e **Execute** o segmento.

Agora você tem um segmento atualizado dinamicamente que identifica os clientes que podem estar interessados em comprar os cinco produtos mais recomendados. Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

> [!TIP]
> Você também pode criar um segmento para um modelo previsão na página **Segmentos** selecionando **Novo** e escolhendo **Criar de** > **Inteligência**. Para obter mais informações, confira [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
