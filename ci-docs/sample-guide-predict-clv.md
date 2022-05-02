---
title: Exemplo de guia de previsão do valor de permanência do cliente
description: Use este exemplo de guia para testar o modelo de previsão do valor de permanência do cliente.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 9f8d1d0f0757d8003ad3859fab75362f3988cd00
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645671"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a>Exemplo de guia de previsão do valor de permanência do cliente (CLV)

Este guia orientará você usando um exemplo completo de previsão do valor de permanência do cliente (CLV) no Customer Insights por meio de dados de exemplo.

## <a name="scenario"></a>Cenário

A Contoso é uma empresa que produz café e máquinas de café de alta qualidade. Eles vendem os produtos pelo site da Contoso Coffee. A empresa quer entender o valor (receita) que seus clientes podem gerar nos próximos 12 meses. Saber o valor esperado de seus clientes nos próximos 12 meses a ajudará a direcionar seus esforços de marketing para clientes de alto valor.

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.
- Recomendamos que você implemente as seguintes etapas [em um novo ambiente](manage-environments.md).

## <a name="task-1---ingest-data"></a>Tarefa 1 - Ingerir dados

Revise os artigos [sobre ingestão de dados](data-sources.md) e [importação de fontes de dados usando conectores do Power Query](connect-power-query.md). As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.

### <a name="ingest-customer-data-from-ecommerce-platform"></a>Ingerir dados do cliente da plataforma de comércio eletrônico

1. Crie uma fonte de dados chamada **Comércio eletrônico**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:
   - **DateOfBirth**: Data
   - **CreatedOn**: Data/Hora/Zona

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. No campo 'Nome' no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**

1. **Salvar** a fonte de dados.

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

### <a name="ingest-customer-data-from-website-reviews"></a>Ingerir dados do cliente de comentários do site

1. Crie uma fonte de dados chamada **Site da Web**, escolha a opção de importação e selecione o conector **Texto/CSV**.

1. Insira o URL para contatos de comércio eletrônico https://aka.ms/CI-ILT/WebReviews.

1. Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.

1. Atualize o tipo de dados para as colunas listadas abaixo:

   - **ReviewRating**: número decimal
   - **ReviewDate**: Data

1. No campo "Nome" no painel direito, renomeie sua fonte de dados de **Consulta** para **Avaliações**.

1. **Salvar** a fonte de dados.

## <a name="task-2---data-unification"></a>Tarefa 2 - Unificação de dados

Depois de ingerir os dados, agora começamos o processo de unificação de dados para criar um perfil de cliente unificado. Para obter mais informações, consulte [Unificação de dados](data-unification.md).

### <a name="map"></a>Mapa

1. Depois de ingerir os dados, mapeie os contatos dos dados de comércio eletrônico e de fidelidade para tipos de dados comuns. Vá para **Dados** > **Unificar** > **Mapear**.

1. Selecione as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**. Em seguida, selecione **Aplicar**.

   ![unifique as fontes de dados de comércio eletrônico e fidelidade.](media/unify-ecommerce-loyalty.png)

1. Selecione **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.

   ![Unifique LoyaltyId como chave primária.](media/unify-loyaltyid.png)

1. Selecione **Salvar**.

### <a name="match"></a>Corresponder

1. Vá para a guia **Corresponder** e selecione **Definir pedido**.

1. Na lista suspensa **Primária**, escolha **eCommerceContacts : eCommerce** como sua fonte primária e inclua todos os registros.

1. Na lista suspensa **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registros.

   ![Unificar correspondência de comércio eletrônico e fidelidade.](media/unify-match-order.png)

1. Selecione **Adicionar regra**

1. Adicione sua primeira condição usando FullName.

   - Para eCommerceContacts, selecione **FullName** na lista suspensa.
   - Para loyCustomers, selecione **FullName** na lista suspensa.
   - Selecione a caixa suspensa **Normalizar** e escolha **Tipo (Telefone, Nome, Endereço, ...)**.
   - Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.

1. Digite o nome **FullName, Email** para a nova regra.

   - Adicione uma segunda condição para o endereço de e-mail selecionando **Adicionar condição**
   - Para a entidade eCommerceContacts, selecione **Email** na lista suspensa.
   - Para a entidade loyCustomers, selecione **Email** na lista suspensa.
   - Deixe o campo Normalizar em branco.
   - Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.

   ![Regra de correspondência unificada para nome e email.](media/unify-match-rule.png)

1. Selecione **Concluído**.

1. Selecione **Salvar** e **Executar**.

### <a name="merge"></a>Mesclagem

1. Vá para a guia **Mesclar**.

1. Na entidade **ContactId** para **loyCustomers**, altere o nome de exibição para **ContactIdLOYALTY** para diferenciá-lo dos outros IDs ingeridos.

   ![renomear contactid de loyalty id.](media/unify-merge-contactid.png)

1. Selecione **Salvar** e **Executar mesclagem e processos downstream**.

## <a name="task-3---configure-customer-lifetime-value-prediction"></a>Tarefa 3 - Configurar a previsão do valor de permanência do cliente

Com os perfis de cliente unificados em vigor, agora podemos executar a previsão do valor de permanência do cliente. Para obter etapas detalhadas, consulte [Previsão do Valor da Permanência do Cliente](predict-customer-lifetime-value.md).

1. Acesse **Inteligência**  > **Previsões** e selecione o **Modelo de valor de permanência do cliente**.

1. Acesse as informações no painel lateral e selecione **Introdução**.

1. Nomeie o modelo **OOB eCommerce CLV Prediction** e a entidade de saída **OOBeCommerceCLVPrediction**.

1. Defina as preferências do modelo para o modelo CLV:
   - **Período de previsão**: **12 meses ou 1 ano**. Essa configuração define o quão longe no futuro prever o valor de permanência do cliente.
   - **Clientes ativos**: especifique o que os clientes ativos significam para o seu negócio. Defina o período histórico em que um cliente deve ter pelo menos uma transação para ser considerado ativo. O modelo prevê CLV somente para clientes ativos. Escolha entre deixar o modelo calcular o período com base nos dados históricos da transação ou fornecer um período específico. Neste exemplo de guia, **deixamos que o modelo calcule o intervalo de compra**, que é a opção padrão.
   - **Clientes de Alto Valor**: defina os clientes de alto valor como um percentual dos clientes que pagam mais. O modelo usa essa entrada para fornecer resultados que se encaixam na definição de negócios de clientes de alto valor. Você pode optar por deixar o modelo definir clientes de alto valor. Ele usa uma regra heurística que deriva o percentil. Você também pode definir clientes de alto valor como um percentual dos principais clientes futuros pagantes. Neste exemplo de guia, definimos manualmente os clientes de alto valor como **30% dos principais clientes pagantes ativos** e selecionamos **Avançar**.

    :::image type="content" source="media/clv-model-preferences.png" alt-text="As preferências são a etapa da experiência guiada para o modelo CLV.":::

1. Na etapa **Dados obrigatórios**, selecione **Adicionar dados** para fornecer os dados do histórico de transações.

1. Adicione a entidade **eCommercePurchases : eCommerce** e mapeie os atributos exigidos pelo modelo:
   - ID da transação: eCommerce.eCommercePurchases.PurchaseId
   - Data da transação: eCommerce.eCommercePurchases.PurchasedOn
   - Valor da transação: eCommerce.eCommercePurchases.TotalPrice
   - ID do produto: eCommerce.eCommercePurchases.ProductId

1. Selecione **Avançar**.

1. Configure a relação entre a entidade **eCommercePurchases : eCommerce** e **eCommerceContacts : eCommerce**.

1. A etapa **Dados adicionais (opcional)** permite adicionar mais dados de atividades do cliente. Esses dados podem ajudar a obter mais informações sobre as interações do cliente com sua empresa, o que pode contribuir para o CLV. Adicionar as principais interações do cliente, como logs da Web, logs de SAC ou histórico do programa de recompensas, pode melhorar a precisão das previsões. Selecione **Adicionar dados** para incluir mais dados de atividade do cliente.

1. Adicione a entidade de atividade do cliente e mapeie os nomes de seus campos para os campos correspondentes exigidos pelo modelo:
   - Entidade de atividade do cliente: Reviews:Website
   - Chave primária: Website.Reviews.ReviewId
   - Carimbo de data/hora: Website.Reviews.ReviewDate
   - Evento (nome da atividade): Website.Reviews.ActivityTypeDisplay
   - Detalhes (quantidade ou valor): Website.Reviews.ReviewRating

1. Selecione **Avançar** e configure a atividade e a relação entre os dados da transação e os dados do cliente:  
   - Tipo de atividade: escolha existente
   - Rótulo da atividade: revisão
   - Rótulo correspondente: Website.Reviews.UserId
   - Entidade do cliente: eCommerceContacts:eCommerce
   - Relacionamento: WebsiteReviews

1. Selecione **Avançar** para definir o cronograma do modelo.

   O modelo precisa ser treinado regularmente para aprender novos padrões quando há novos dados ingeridos. Neste exemplo, escolha **Mensal**.

1. Depois de revisar todos os detalhes, selecione **Salvar e executar**.

## <a name="task-4---review-model-results-and-explanations"></a>Tarefa 4 - Revise os resultados e explicações do modelo

Deixe o modelo concluir o treinamento e a pontuação dos dados. Em seguida, você pode revisar os resultados e explicações do modelo CLV. Para mais informações, consulte [Analisar um status de previsão e resultados](predict-customer-lifetime-value.md#review-prediction-status-and-results).

## <a name="task-5---create-a-segment-of-high-value-customers"></a>Tarefa 5 - Criar um segmento de clientes de alto valor

Executar o modelo cria uma entidade, que é listada em **Dados** > **Entidades**. Você pode criar um segmento de cliente com base na entidade criada pelo modelo.

1. Vá para **Segmentos**. 

1. Selecione **Novo** e escolha **Criar de** > **Inteligência**.

   ![Criando um segmento com a saída do modelo.](media/segment-intelligence.png)

1. Selecione a entidade **OOBeCommerceCLVPrediction** e defina o segmento:
  - Campo: CLVScore
  - Operador: maior que
  - Valor: 1500

1. Selecione **Revisar** e **Salvar** o segmento.

Agora você tem um segmento que identifica os clientes que devem gerar mais de US $ 1.500 de receita nos próximos 12 meses. Este segmento é atualizado dinamicamente se mais dados forem ingeridos.

Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).
