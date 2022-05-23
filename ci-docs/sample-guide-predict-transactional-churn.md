---
title: Guia de amostra de previsão de rotatividade transacional
description: Use este guia de amostra para experimentar o modelo de previsão de rotatividade transacional pronto para uso.
ms.date: 05/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3edbf2a471313379c28db874d7f19c3265a23299
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741305"
---
# <a name="transactional-churn-prediction-sample-guide"></a>Guia de amostra de previsão de rotatividade transacional

Este guia mostrará a você um exemplo de ponta a ponta de previsão de rotatividade transacional no Customer Insights usando usando os dados fornecidos abaixo. Todos os dados usados neste guia não são dados reais do cliente e fazem parte do conjunto de dados da Contoso encontrado no ambiente de *Demonstração* dentro de sua Assinatura do Customer Insights.

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que são vendidas por meio do site Contoso Coffee. Seu objetivo é saber quais clientes que normalmente compram seus produtos com regularidade deixarão de ser clientes ativos nos próximos 60 dias. Saber qual de seus clientes está **propenso a rotacionar**, pode ajudá-los a economizar esforços de marketing, concentrando-se em mantê-los.

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

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar Data de Nascimento em Data.":::

1. No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**

1. Salvar a fonte de dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**. Escolha o conector de **Texto/CSV** novamente.

1. Insira o URL para dados de **Compras online** https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda
   
1. No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommercePurchases**.

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

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

[!INCLUDE [sample-guide-unification](includes/sample-guide-unification.md)]

## <a name="task-3---configure-transaction-churn-prediction"></a>Tarefa 3 - Configurar a previsão de rotatividade da transação

Com os perfis de cliente unificados em vigor, agora podemos executar a previsão de rotatividade de transações. Para obter etapas detalhadas, consulte o artigo [Previsão de rotatividade de transações](predict-transactional-churn.md). 

1. Vá para **Inteligência** > **Descobrir** e selecione usar o **Modelo de rotatividade do cliente**.

1. Selecione a opção **Transacional** e selecione **Iniciar**.

1. Nomeie o modelo **Previsão de rotatividade de transação OOB eCommerce** e a entidade de saída **OOBeCommerceChurnPrediction**.

1. Defina duas condições para o modelo de rotatividade:

   * **Amplitude da previsão**: **pelo menos 60** dias. Essa configuração define o quão longe no futuro queremos prever a rotatividade de clientes.

   * **Definição de rotatividade**: **pelo menos 60** dias. O período sem compra após o qual um cliente é considerado rotacionado.

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecione a janela de previsão de niveladores de modelo e definição de rotatividade.":::

1. Selecione **Histórico de Compras (obrigatório)** e selecione **Adicionar dados** para histórico de compra.

1. Adicione a entidade **eCommercePurchases : eCommerce** e mapeie os campos do eCommerce para os campos correspondentes exigidos pelo modelo.

1. Junte-se à entidade **eCommercePurchases : eCommerce** com **eCommerceContacts : eCommerce**.

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Junte-se a entidades de comércio eletrônico.":::

1. Selecione **Avançar** para definir o cronograma do modelo.

   O modelo precisa ser treinado regularmente para aprender novos padrões quando novos dados forem ingeridos. Para este exemplo, selecione **Mensal**.

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Agora você pode revisar as explicações do modelo de rotatividade. Para mais informações, consulte [Analisar um status de previsão e resultados](predict-transactional-churn.md#review-a-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a>Tarefa 5 - Crie um segmento de clientes de alto risco de rotatividade

Executar o modelo de produção cria uma nova entidade que você pode ver em **Dados** > **Entidades**.   

Você pode criar um novo segmento com base na entidade criada pelo modelo.

1.  Vá para **Segmentos**. Selecione **Novo** e escolha **Criar de** > **Inteligência**. 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Criando um segmento com a saída do modelo.":::

1. Selecione o ponto de extremidade **OOBeCommerceChurnPrediction** e defina o segmento: 
   - Campo: ChurnScore
   - Operador: maior que
   - Valor: 0,6

Agora você tem um segmento atualizado dinamicamente que identifica clientes com alto risco de rotatividade.

Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]
