---
title: Guia de amostra de previsão de rotatividade transacional
description: Use este guia de amostra para experimentar o modelo de previsão de rotatividade transacional pronto para uso.
ms.date: 09/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0ccc32b6e5e96adf6f2fa8c6d52960a07d1513f3
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609670"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guia de amostra de previsão de rotatividade transacional

Este guia dará a você um exemplo de ponta a ponta de previsão de rotatividade transacional usando os dados de amostra. Recomendamos que você teste esta previsão [em um novo ambiente](manage-environments.md).

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade. Eles vendem os produtos pelo site da Contoso Coffee. Seu objetivo é saber quais clientes que normalmente compram seus produtos com regularidade deixarão de ser clientes ativos nos próximos 60 dias. Saber qual de seus clientes está **propenso a rotacionar**, pode ajudá-los a economizar esforços de marketing, concentrando-se em mantê-los.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões de colaborador](permissions.md).

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Revise os artigos [sobre ingestão de dados](data-sources.md) e [conexão a uma fonte de dados do Power Query](connect-power-query.md). As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados do cliente da plataforma de comércio eletrônico

1. Crie uma fonte de dados chamada **Comércio eletrônico** e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscontacts.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar Data de Nascimento em Data.":::

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **eCommerceContacts**

1. Salvar a fonte de dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**. Escolha o conector de **Texto/CSV** novamente.

1. Insira a URL para dados de compras online https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel direito, renomeie sua fonte de dados para **eCommercePurchases**.

1. Salvar a fonte de dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados do cliente do esquema de fidelidade

1. Crie uma fonte de dados chamada **LoyaltyScheme** e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **loyCustomers**.

1. Salvar a fonte de dados.

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

## <a name="task-4---configure-transaction-churn-prediction"></a>Tarefa 4 - Configurar a previsão de rotatividade da transação

Com os perfis de cliente unificados em vigor e a atividade criada, agora podemos executar a previsão de rotatividade de transações.

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Modelo de rotatividade de clientes**.

1. Selecione **Transacional** para o tipo de rotatividade e depois **Introdução**.

1. Nomeie o modelo **Previsão de rotatividade de transação OOB eCommerce** e a entidade de saída **OOBeCommerceChurnPrediction**.

1. Selecione **Avançar**

1. Definir as preferências do modelo:

   - **Janela de previsão**: **60** dias para definir o quão longe no futuro queremos prever a rotatividade de clientes.

   - **Definição de rotatividade**: **60** dias para indicar o período sem compra após o qual um cliente é considerado rotacionado.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecione a janela de previsão de preferências de modelo e definição de rotatividade.":::

1. Selecione **Avançar**

1. Selecione **Histórico de Compras (obrigatório)** e selecione **Adicionar dados** para histórico de compra.

1. Selecione **SalesOrderLine** e a entidade eCommercePurchases e selecione **Avançar**. Os dados necessários são preenchidos automaticamente a partir da atividade. Selecione **Salvar** e depois **Avançar**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Junte-se a entidades de comércio eletrônico.":::

1. Pule a etapa **Dados adicionais (opcional)**.

1. Na etapa **Atualizações de dados**, selecione **Mensal** para o cronograma do modelo.

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Revise as explicações do modelo de rotatividade. Para mais informações, consulte [Analisar resultados de previsão](predict-transactional-churn.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 6 - Crie um segmento de clientes de alto risco de rotatividade

Executar o modelo de modelo cria uma entidade, que é listada em **Dados** > **Entidades**. Você pode criar um novo segmento com base na entidade criada pelo modelo.

1. Na página de resultados, selecione **Criar segmento**.

1. Crie uma regra usando a entidade **OOBeCommerceChurnPrediction** e defina o segmento:
   - **Campo**: ChurnScore
   - **Operador**: maior que
   - **Valor**: 0.6

1. Selecione **Salvar** e **Execute** o segmento.

Agora você tem um segmento atualizado dinamicamente que identifica clientes com alto risco de rotatividade. Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

> [!TIP]
> Você também pode criar um segmento para um modelo previsão na página **Segmentos** selecionando **Novo** e escolhendo **Criar de** > **Inteligência**. Para obter mais informações, confira [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
