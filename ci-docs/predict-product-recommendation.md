---
title: Prever recomendações do produto
description: Preveja os produtos que um cliente provavelmente comprará ou com os quais interagirá.
ms.date: 09/30/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 0057d6796bb60db44d08b58d9e0daaf6e7c90fde
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610268"
---
# <a name="predict-product-recommendations"></a>Prever recomendações do produto

O modelo de recomendação de produto cria conjuntos de recomendações de produto preditivas. As recomendações são baseadas no comportamento de compra anterior e clientes com padrões de compra semelhantes. Este modelo é para consumidores individuais (B2C).

É necessário ter conhecimento de negócios sobre os diferentes tipos de produtos para sua empresa e como seus clientes interagem com eles. Apoiamos a recomendação de produtos que foram adquiridos anteriormente por seus clientes ou recomendações de novos produtos.

As recomendações de produtos podem estar sujeitas às leis e regulamentações locais e às expectativas dos clientes. O modelo não foi criado especificamente para levar isso em consideração. Entretanto, **você deve revisar as recomendações antes de fornecê-las aos seus clientes** para garantir a conformidade com todas as leis ou regulamentações aplicáveis e as expectativas dos clientes em relação ao que você pode recomendar.

A saída deste modelo fornece recomendações com base na ID do produto. Seu mecanismo de entrega precisa mapear as IDs de produto previstas para o conteúdo apropriado de modo que seus clientes sejam responsáveis por localização, conteúdo de imagem e outros conteúdos ou comportamentos específicos de negócios.

> [!TIP]
> Experimente a previsão de recomendação de produtos usando dados de exemplo: [Guia de exemplo para previsão de recomendação de produtos](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [permissões de Colaborador](permissions.md)
- Pelo menos 100 clientes, de preferência mais de 10.000 clientes.
- Identificador do cliente: um identificador exclusivo para fazer a correspondência das transações com um cliente individual
- Pelo menos um ano de dados transacionais, de preferência de dois a três anos para incluir alguma sazonalidade. Idealmente, pelo menos três ou mais transações por ID de cliente. O histórico da transações deve incluir:
  - **ID da transação**: identificador exclusivo de uma compra ou transação.
  - **Data da transação**: data da compra ou transação.
  - **Valor da transação:** valor numérico da compra ou da transação.
  - **ID exclusiva do produto:** ID do produto ou serviço adquirido, se os seus dados estiverem em um nível de item de linha.
  - **Compra ou devolução:** um campo booliano verdadeiro/falso em que o valor *verdadeiro* identifica que uma transação foi uma devolução. Se os dados da Compra ou Devolução não forem fornecidos para o modelo e o **Valor da transação** for negativo, inferiremos uma devolução.
- Uma entidade de dados do catálogo de produtos para usar como filtro de produto.

> [!NOTE]
> - O modelo requer o histórico de transações de seus clientes, onde transação é qualquer dado que descreva uma interação usuário-produto. Por exemplo, comprar um produto, assistir a uma aula ou participar de um evento.
> - Apenas uma entidade de histórico de transações pode ser configurada. Se houver várias entidades de compra, combine-as no Power Query antes da ingestão de dados.
> - Se ordem e detalhes da ordem forem entidades diferentes, junte-as antes de usar no modelo. O modelo não funciona com apenas uma ID de ordem ou ID de recebimento em uma entidade.

## <a name="create-a-product-recommendation-prediction"></a>Criar uma previsão de recomendação do produto

Selecione **Salvar rascunho** a qualquer momento para salvar o previsão como rascunho. A previsão de rascunho é exibida na guia **Minhas previsões**.

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Recomendações de produto (versão preliminar)**.

1. Selecione **Introdução**.

1. **Nomear este modelo** e **Nome da entidade de saída** para distingui-los de outros modelos ou entidades.

1. Selecione **Avançar**

### <a name="define-product-recommendation-preferences"></a>Definir preferências de recomendação de produto

1. Defina o **Número de produtos** que deseja recomendar a um cliente. Esse valor depende de como seu método de entrega preenche os dados.

1. Escolha se você deseja incluir produtos que os clientes compraram no passado no campo **Repetir compras esperadas**.

1. Defina a **Janela do passado** com o período que o modelo considera antes de recomendar o produto ao usuário novamente. Por exemplo, indique que um cliente adquire um laptop a cada dois anos. O modelo analisa o histórico de compras dos últimos dois anos e, se encontrar um item, o item será filtrado das recomendações.

1. Selecione **Avançar**.

### <a name="add-purchase-history"></a>Adicionar histórico de compras

1. Selecione **Adicionar dados** para **Histórico de transações do cliente**.

1. Selecione o tipo de atividade semântica **SalesOrderLine** que contém a transação necessária ou as informações do histórico de compras. Se a atividade não foi configurada, selecione **aqui** e crie-a.

1. Em **Atividades**, se os atributos da atividade tiverem sido mapeados semanticamente quando a atividade foi criada, escolha os atributos específicos ou a entidade em que você deseja que o cálculo se concentre. Se o mapeamento semântico não tiver ocorrido, selecione **Editar** e mapeie seus dados.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Painel lateral mostrando a escolha de atividades específicas no tipo semântico.":::

1. Selecione **Avançar** e revise os atributos necessários para este modelo.

1. Selecione **Salvar**.

1. Selecione **Avançar**

### <a name="add-product-information-and-filters"></a>Adicionar informações e filtros de produto

Às vezes, apenas alguns produtos são benéficos ou apropriados para o tipo de previsão que você cria. Use os filtros de produto para identificar um subconjunto de produtos com características específicas para recomendar aos seus clientes. O modelo usará todos os produtos disponíveis para aprender padrões, mas usará apenas os produtos que correspondam ao filtro de produto em sua saída.

1. Adicione sua entidade de catálogo de produtos que contém informações para cada produto. Mapeie as informações necessárias e selecione **Salvar**.

1. Selecione **Avançar**

1. Selecione **Filtros de produto**:

   - **Sem filtros**: usar todos os produtos na previsão de recomendação de produtos.

   - **Definir filtros de produto específicos**: usar produtos específicos na previsão de recomendação de produtos. No painel **Atributos do catálogo de produtos**, selecione os atributos da sua entidade Catálogo de Produtos que deseja incluir no filtro.

     :::image type="content" source="media/product-filters-sidepane.png" alt-text="Painel lateral que mostra os atributos na entidade do catálogo de produtos a serem selecionados para filtros de produto.":::

1. Escolha se você deseja que o filtro de produto use **e** ou **ou** para combinar logicamente sua seleção de atributos do catálogo de produtos.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Configuração de exemplo de filtros de produto combinados com conectores AND lógicos.":::

1. Selecione **Avançar**

### <a name="set-update-schedule"></a>Definir cronograma de atualização

1. Escolha uma frequência para treinar o modelo novamente. Essa configuração é importante para atualizar a precisão das previsões conforme novos dados são ingeridos para o Customer Insights. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**

### <a name="review-and-run-the-model-configuration"></a>Revisar e executar a configuração do modelo

A etapa **Revisar e executar** mostra um resumo da configuração e oferece a chance de fazer alterações antes de criar a previsão.

1. Selecione **Editar** em qualquer uma das etapas para revisar e fazer alterações.

1. Se estiver satisfeito com as seleções, selecione **Salvar e executar** para iniciar a execução do modelo. Selecione **Concluído**. A guia **Minhas previsões** é exibida enquanto a previsão está sendo criada. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-prediction-results"></a>Visualizar resultados de previsão

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Minhas previsões**, selecione a previsão que deseja visualizar.

Há cinco seções principais de dados na página de resultados.

- **Desempenho do modelo**: os níveis A, B ou C indicam o desempenho da previsão e podem ajudar você a tomar a decisão de usar os resultados armazenados na entidade de saída.
  
  :::image type="content" source="media/product-recommendation-modelperformance.PNG" alt-text="Imagem do resultado do desempenho do modelo com a classificação A.":::

  As classificações são determinadas com base nas seguintes regras:
  - **A** quando a métrica "Success @ K" for pelo menos 10% maior que a linha de base.
  - **B** quando a métrica "Success @ K" for de 0% a 10% maior que a linha de base.
  - **C** quando a métrica "Sucess @ K" for inferior à linha de base.
  - **Linha de base**: os principais produtos mais recomendados por contagem de compra em todos os clientes + regras aprendidas identificadas pelo modelo = um conjunto de recomendações para os clientes. As previsões são então comparadas aos principais produtos, calculadas pelo número de clientes que compraram o produto. Se um cliente tem pelo menos um produto em seus produtos recomendados que também foi visto nos produtos mais comprados, eles são considerados parte da linha de base. Por exemplo, se 10 desses clientes tivessem um produto recomendado comprado de um total de 100 clientes, a linha de base seria 10%.
  - **Success @ K**: as recomendações são criadas para todos os clientes e comparadas com o conjunto de validação de transações. Por exemplo, em um período de 12 meses, o mês 12 é reservado como um conjunto de dados de validação. Se o modelo fizesse a previsão de pelo menos um item que você compraria no mês 12 com base no que aprendeu nos 11 meses anteriores, o cliente aumentaria a métrica "Success @ K".

- **Produtos mais sugeridos (com contagem):** os cinco principais produtos previstos para seus clientes.
  
  :::image type="content" source="media/product-recommendation-topproducts.PNG" alt-text="Gráfico que mostra os 5 produtos mais recomendados.":::

- **Principais fatores de recomendação:** o modelo usa o histórico de transações dos clientes para fazer recomendações de produtos. Ele aprende padrões com base em compras anteriores e encontra semelhanças entre clientes e produtos. Essas semelhanças são então utilizadas para gerar recomendações de produtos.
  Os seguintes fatores podem influenciar uma recomendação de produto gerada pelo modelo.
  - **Transações anteriores**: um produto recomendado foi baseado em padrões de compra anteriores. Por exemplo, o modelo pode recomendar um *Mouse Surface Arc* se alguém comprou recentemente um *Surface Book 3* e uma *Caneta Surface*. O modelo aprendeu que, historicamente, muitos clientes compraram um *Mouse Surface Arc* depois de comprar um *Surface Book 3* e uma *Caneta Surface*.
  - **Similaridade do cliente**: um produto recomendado foi historicamente comprado por outros clientes que apresentam padrões de compra semelhantes. Por exemplo, John recebeu como recomendação o *Surface Headphones 2* porque Jennifer e Brad recentemente compraram o *Surface Headphones 2*. O modelo acredita que John é semelhante a Jennifer e Brad porque eles tiveram historicamente padrões de compra semelhantes.
  - **Similaridade do produto**: um produto recomendado é semelhante a outros produtos que o cliente comprou anteriormente. O modelo considera dois produtos semelhantes se tiverem sido comprados juntos ou por clientes semelhantes. Por exemplo, alguém recebe uma recomendação de uma *Unidade de Armazenamento USB* porque comprou anteriormente um *Adaptador USB-C para USB* e o modelo acredita que a *Unidade de Armazenamento USB* é semelhante ao *Adaptador USB-C para USB* com base em padrões de compra históricos.

  Toda recomendação de produto é influenciada por um ou mais desses fatores. A porcentagem de recomendações em que cada fator influenciador desempenhou um papel é visualizada em um gráfico. No exemplo a seguir, 100% das recomendações foram influenciadas por transações anteriores, 60% pela similaridade do cliente e 22% pela similaridade do produto. Passe o mouse sobre as barras do gráfico para ver a porcentagem exata em que os fatores influenciadores contribuíram.
  
  :::image type="content" source="media/product-recommendation-keyrecommendationfactors.png" alt-text="Principais fatores de recomendação aprendidos pelo modelo para gerar recomendações de produtos.":::

- **Estatísticas de dados**: uma visão geral do número de transações, clientes e produtos que o modelo considerou. Elas são baseadas nos dados de entrada que foram usados para aprender padrões e gerar recomendações de produtos.

  :::image type="content" source="media/product-recommendation-datastatistics.png" alt-text="Estatísticas de dados sobre dados de entrada usados pelo modelo para aprender padrões.":::
  
  O modelo usa todos os dados disponíveis para aprender padrões. Portanto, se você usar a filtragem de produto na configuração do modelo, esta seção mostra o número total de produtos que o modelo analisou para aprender padrões, que pode diferir do número de produtos que correspondem aos critérios de filtragem definidos. A filtragem aplica-se à saída gerada pelo modelo.

- **Recomendações de produtos de amostra:** uma amostra de recomendações que o modelo acha que provavelmente serão adquiridas pelo cliente. Se um catálogo de produtos for adicionado, as IDs dos produtos serão substituídas pelos nomes dos produtos.

  :::image type="content" source="media/product-recommendation-highconfidence.PNG" alt-text="Lista que mostra sugestões de alta confiança para um conjunto selecionado de clientes individuais.":::

> [!NOTE]
> Na entidade de saída para este modelo, *Pontuação* mostra a medida quantitativa da recomendação. O modelo recomenda produtos com uma pontuação mais alta em vez de produtos com uma pontuação mais baixa. Para ver a pontuação, vá para **Dados** > **Entidades** e visualize a guia de dados para a entidade de saída que você definiu para este modelo.

[!INCLUDE [footer-include](includes/footer-banner.md)]
