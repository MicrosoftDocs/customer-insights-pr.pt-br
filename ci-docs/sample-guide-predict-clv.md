---
title: Exemplo de guia de previsão do valor de permanência do cliente (CLV)
description: Use este exemplo de guia para testar o modelo de previsão do valor de permanência do cliente.
ms.date: 09/15/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: fec43b279326daa17fb179181f5e310c99d48bb7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609624"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Exemplo de guia de previsão do valor de permanência do cliente (CLV)

Este guia orienta você usando um exemplo completo de previsão do valor de permanência do cliente (CLV) no Customer Insights por meio de dados de exemplo. Recomendamos que você teste esta previsão [em um novo ambiente](manage-environments.md).

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade. Eles vendem os produtos pelo site da Contoso Coffee. A empresa quer entender o valor (receita) que seus clientes podem gerar nos próximos 12 meses. Saber o valor esperado de seus clientes nos próximos 12 meses a ajudará a direcionar seus esforços de marketing para clientes de alto valor.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões de colaborador](permissions.md).

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

1. **Salvar** a fonte de dados.

### <a name="ingest-online-purchase-data"></a>Ingerir dados de compra online

1. Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**. Escolha o conector de **Texto/CSV** novamente.

1. Insira o URL para dados de **Compras online** https://aka.ms/ciadclassonline.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **PurchasedOn**: Data/Hora
   - **TotalPrice**: Moeda

1. No campo **Nome** no painel lateral, renomeie sua fonte de dados como **eCommercePurchases**.

1. **Salvar** a fonte de dados.

### <a name="ingest-customer-data-from-loyalty-schema"></a>Ingerir dados do cliente do esquema de fidelidade

1. Crie uma fonte de dados chamada **LoyaltyScheme** e selecione o conector **Texto/CSV**.

1. Insira o URL para clientes de fidelidade https://aka.ms/ciadclasscustomerloyalty.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **RewardsPoints**: Número inteiro
   - **CreatedOn**: Data/Hora

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **loyCustomers**.

1. **Salvar** a fonte de dados.

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dados do cliente de comentários do site

1. Crie uma fonte de dados chamada **Website** e selecione o conector **Texto/CSV**.

1. Digite a URL para avaliações do site https://aka.ms/CI-ILT/WebReviews.

1. Ao editar os dados, selecione **Transformar** e então **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **ReviewRating**: número decimal
   - **ReviewDate**: Data

1. No campo **Nome** no painel direito, renomeie sua fonte de dados como **Avaliações**.

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

1. Adicione outra atividade e mapeie os nomes de seus campos para os campos correspondentes:
   - **Entidade de atividade**: Reviews:Website
   - **Chave primária**: ReviewId
   - **Carimbo de data/hora**: ReviewDate
   - **Atividade do evento**: ActivityTypeDisplay
   - **Detalhe adicional**: ReviewRating
   - **Tipo de atividade**: Avaliação

1. Execute a atividade.

## <a name="task-4---configure-customer-lifetime-value-prediction"></a>Tarefa 4 - Configurar a previsão do valor de permanência do cliente

Com os perfis unificados de cliente em vigor e a atividade criada, execute a previsão do valor de permanência do cliente (CLV). Para obter etapas detalhadas, consulte [Previsão do Valor da Permanência do Cliente](predict-customer-lifetime-value.md).

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Valor de permanência do cliente**.

1. Selecione **Introdução**.

1. Nomeie o modelo **OOB eCommerce CLV Prediction** e a entidade de saída **OOBeCommerceCLVPrediction**.

1. Definir as preferências do modelo:
   - **Período de previsão**: **12 meses ou 1 ano** para definir em que momento no futuro você deseja prever o CLV.
   - **Clientes ativos**: **Permitir que o modelo calcule o intervalo de compra**, que é o período em que um cliente deve ter pelo menos uma transação para ser considerado ativo.
   - **Cliente de Alto Valor**: defina manualmente os clientes de alto valor como **principais 30% dos clientes ativos**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="As preferências são a etapa da experiência guiada para o modelo CLV.":::

1. Selecione **Avançar**

1. Na etapa **Dados obrigatórios**, selecione **Adicionar dados** para fornecer os dados do histórico de transações.

    :::image type="content" source="media/clv-model-required.png" alt-text="Adicione a etapa de dados necessária da experiência guiada para o modelo CLV.":::

1. Selecione **SalesOrderLine** e a entidade eCommercePurchases e selecione **Avançar**. Os dados necessários são preenchidos automaticamente a partir da atividade. Selecione **Salvar** e depois **Avançar**.

1. A etapa **Dados adicionais (opcional)** permite adicionar mais dados de atividades do cliente para obter mais insight sobre interações do cliente. Para este exemplo, selecione **Adicionar dados** e adicione a atividade de avaliação da web.

1. Selecione **Avançar**

1. Na etapa **Atualizações de dados**, selecione **Mensal** para o cronograma do modelo.

1. Selecione **Avançar**

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**.

## <a name="task-5---review-model-results-and-explanations"></a>Tarefa 5 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Revise os [resultados e explicações do modelo de CLV](predict-customer-lifetime-value.md#view-prediction-results).

## <a name="task-6---create-a-segment-of-high-value-customers"></a>Tarefa 6 - Criar um segmento de clientes de alto valor

Executar o modelo cria uma entidade, que é listada em **Dados** > **Entidades**. Você pode criar um segmento de cliente com base na entidade criada pelo modelo.

1. Na página de resultados, selecione **Criar segmento**.

1. Crie uma regra usando a entidade **OOBeCommerceCLVPrediction** e defina o segmento:
   - **Campo**: CLVScore
   - **Operador**: maior que
   - **Valor**: 1500

1. Selecione **Salvar** e **Execute** o segmento.

Agora você tem um segmento que identifica os clientes que devem gerar mais de US $ 1.500 de receita nos próximos 12 meses. Este segmento é atualizado dinamicamente se mais dados forem ingeridos. Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

> [!TIP]
> Você também pode criar um segmento para um modelo previsão na página **Segmentos** selecionando **Novo** e escolhendo **Criar de** > **Inteligência**. Para obter mais informações, confira [Criar um novo segmento com segmentos rápidos](segment-quick.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
