---
title: Previsão de recomendação do produto
description: Preveja os produtos que um cliente provavelmente comprará ou com os quais interagirá.
ms.date: 05/09/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 9b3e60c49d294d031f43ef0594cb69707bb64019
ms.sourcegitcommit: 82f417cfb0a16600e9f552d7a21d598cc8f5a267
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/16/2022
ms.locfileid: "8762718"
---
# <a name="product-recommendation-prediction"></a>Previsão de recomendação do produto

O modelo de recomendação de produto cria conjuntos de recomendações de produto preditivas. As recomendações são baseadas no comportamento de compra anterior e clientes com padrões de compra semelhantes. Você pode criar novas previsões de recomendação de produto na página **Inteligência** > **Previsões**. Selecione **Minhas previsões** para ver outras previsões que você criou.

As recomendações de produtos podem estar sujeitas às leis e regulamentações locais e às expectativas dos clientes. O modelo não foi criado especificamente para levar isso em consideração.  Como usuário desse recurso preditivo, **você deve revisar as recomendações antes de fornecê-las aos seus clientes** para garantir a conformidade com todas as leis ou regulamentações aplicáveis e as expectativas dos clientes em relação ao que você pode recomendar.

Além disso, a saída deste modelo fornecerá recomendações com base na ID do produto. Seu mecanismo de entrega precisará mapear as IDs de produto previstas para o conteúdo apropriado de modo que seus clientes sejam responsáveis por localização, conteúdo de imagem e outros conteúdos ou comportamentos específicos de negócios.

## <a name="sample-guide"></a>Guia de amostra

Se estiver interessado em experimentar este recurso, mas não tiver dados para preencher os requisitos abaixo, você pode [criar uma implementação de amostra](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.

- Conhecimento de negócios para entender os diferentes tipos de produtos para sua empresa e como seus clientes interagem com eles. Apoiamos a recomendação de produtos que foram adquiridos anteriormente por seus clientes ou recomendações de novos produtos.

- Seu ambiente deve ser configurado para o público-alvo primário dos **consumidores individuais**.

- Dados sobre as transações, compras e seu histórico:
  - Identificadores de transação para distinguir compras ou transações.
  - Identificadores de cliente para mapear transações aos seus clientes.
  - Datas dos eventos de transação que especificam a transação ocorreu.
  - Informações da ID do Produto (Product ID) para a transação.
  - (Opcional) Uma entidade de dados do catálogo de produtos para usar um filtro de produto.
  - (Opcional) Se uma transação é uma devolução ou não.
  - O esquema de dados semânticos requer as seguintes informações:
    - **ID da transação:** um identificador exclusivo de uma compra ou transação.
    - **Data da transação:** a data da compra ou transação.
    - **Valor da transação:** o valor numérico da compra ou da transação.
    - **ID exclusiva do produto:** a ID do produto ou serviço adquirido, se os seus dados estiverem em um nível de item de linha.
    - (Opcional) **Compra ou devolução:** um campo booliano em que o valor *verdadeiro* identifica que uma transação foi uma devolução. Se os dados da Compra ou Devolução não forem fornecidos para o modelo e o **Valor da transação** for negativo, também usaremos essas informações para inferir uma devolução.
- Características de dados sugeridas:
  - Dados históricos suficientes: pelo menos um ano de dados transacionais, de preferência de dois a três anos para incluir alguma sazonalidade.
  - Várias compras por cliente: três ou mais transações por ID de Cliente
  - Número de clientes: pelo menos 100 clientes, de preferência mais de 10.000 clientes. O modelo falhará com menos de 100 clientes.

> [!NOTE]
>
> - O modelo requer o histórico de transações de seus clientes. A definição de uma transação é bastante flexível. Todos os dados que descrevem uma interação entre usuário e produto podem funcionar como uma entrada. Por exemplo, comprar um produto, assistir a uma aula ou participar de um evento.
> - Apenas uma entidade de histórico de transações pode ser configurada atualmente. Se houver várias entidades de compra, una-as no Power Query antes da ingestão de dados.
> - Se ordem e detalhes da ordem forem entidades diferentes, junte-as antes de usar no modelo. O modelo não funciona com apenas uma ID de ordem ou ID de recebimento em uma entidade.

## <a name="create-a-product-recommendation-prediction"></a>Criar uma previsão de recomendação do produto

1. No Customer Insights, acesse **Inteligência** > **Previsões**.

1. Selecione o bloco **Modelo de recomendações de produtos** e selecione **Usar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Bloco do modelo de recomendação do produto com o botão Usar este modelo.](media/product-recommendation-usethismodel.PNG "Bloco do modelo de recomendação do produto com o botão Usar este modelo")

1. Revise as informações sobre os requisitos do modelo. Se você tiver os dados necessários, selecione **Começar**.

### <a name="name-model"></a>Nomear modelo

1. Forneça um nome para o modelo para diferenciá-lo dos outros modelos.

1. Insira um nome para a entidade de saída usando apenas letras e números, sem espaços. Esse é o nome que a entidade de modelo usará. Em seguida, selecione **Próximo**.

### <a name="define-product-recommendation-configuration"></a>Definir configuração de recomendação de produto

1. Defina o **Número de produtos** que você deseja recomendar a um cliente. Esse valor depende de como seu método de entrega preenche os dados. Se você pode recomendar três produtos, defina esse valor adequadamente.

   >[!TIP]
   > Você pode selecionar **Salvar rascunho** a qualquer momento para salvar o previsão como rascunho. Você encontrará a previsão de rascunho na guia **Minhas previsões**.

1. Escolha se você deseja incluir produtos que os clientes compraram recentemente no campo **Repetir compras esperadas**.

1. Defina a **Janela do passado**. Esta configuração especifica o período que o modelo considera antes de recomendar o produto ao usuário novamente. Por exemplo, indique que um cliente adquire um laptop a cada dois anos. Essa janela examinará o histórico de compras dos últimos dois anos e, se encontrar um item, o item será filtrado das recomendações.

1. Selecione **Avançar**.

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** e escolha o tipo de atividade no painel lateral que contém a transação necessária ou as informações do histórico de compras.

1. Em **Escolher as atividades**, escolha as atividades específicas da atividade selecionada em que deseja que o cálculo se concentre.

   :::image type="content" source="media/product-recommendation-select-semantic-activity.PNG" alt-text="Painel lateral mostrando a escolha de atividades específicas no tipo semântico.":::

1. Se você ainda não mapeou a atividade para um tipo semântico, selecione **Editar** para fazer isso. A experiência guiada para mapear atividades semânticas é aberta. Mapeie seus dados para os campos correspondentes no tipo de atividade selecionado.

   :::image type="content" source="media/product-recommendation-set-activity-type.PNG" alt-text="Tipo de atividade de configuração de página.":::

1. Depois de mapear a atividade para o tipo semântico correspondente, selecione **Avançar** para prosseguir.

1. Mapeie os atributos semânticos para os campos necessários para executar o modelo.

1. Selecione **Salvar**.

1. Selecione **Avançar**

### <a name="configure-product-filters"></a>Configurar filtros de produto

Às vezes, apenas alguns produtos são benéficos ou apropriados para o tipo de previsão que você cria. Os filtros de produto permitem que você identifique um subconjunto de produtos com características específicas para recomendar aos seus clientes. O modelo usará todos os produtos disponíveis para aprender padrões, mas usará apenas os produtos que correspondam ao filtro de produto em sua saída.

1. Na etapa **Adicionar informações do produto**, adicione seu catálogo de produtos com informações para cada produto. Mapeie as informações necessárias e selecione **Avançar**.

1. Na etapa **Filtros de produto**, escolha entre as seguintes opções.

   - **Sem filtros**: usar todos os produtos na previsão de recomendação de produtos.

   - **Definir filtros de produto específicos**: usar produtos específicos na previsão de recomendação de produtos.

1. Selecione **Avançar**.

1. Se você optar por definir um filtro de produto, precisará defini-lo agora. No painel **Atributos do catálogo de produtos**, selecione os atributos da sua *entidade Catálogo de Produtos* que você deseja incluir no filtro.

   :::image type="content" source="media/product-filters-sidepane.png" alt-text="Painel lateral que mostra os atributos na entidade do catálogo de produtos a serem selecionados para filtros de produto.":::

1. Escolha se você deseja que o filtro de produto use conectores **and** ou **or** para combinar logicamente sua seleção de atributos do catálogo de produtos.

   :::image type="content" source="media/product-filters-sample.png" alt-text="Configuração de exemplo de filtros de produto combinados com conectores AND lógicos.":::

1. Selecione **Avançar**.

### <a name="set-update-schedule-and-review-configuration"></a>Definir o cronograma de atualizações e revisar a configuração

1. Defina uma frequência para treinar o modelo novamente. Essa configuração é importante para atualizar a precisão das previsões conforme novos dados são importados para o Customer Insights. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**.

1. Revise a configuração. Você pode voltar para qualquer parte da configuração da previsão selecionando **Editar** abaixo do valor exibido. Ou você pode selecionar uma etapa da configuração no indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Salvar e executar** para iniciar o processo de previsão. Na guia **Minhas previsões**, você pode ver o status das previsões. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Revisar o status e os resultados de uma previsão

1. Vá para a guia **Minhas previsões** em **Inteligência** > **Previsões**.
   > [!div class="mx-imgBorder"]
   > ![Exibição da página Minhas Previsões.](media/product-recommendation-mypredictions.PNG "Exibição da página Minhas Previsões")

1. Selecione a previsão que você deseja revisar.
   - **Nome da previsão:** O nome da previsão que foi fornecido ao criá-la.
   - **Tipo de previsão:** O tipo do modelo usado na previsão
   - **Entidade de saída:** Nome da entidade que armazenará a saída da previsão. Você pode encontrar uma entidade com esse nome em **Dados** > **Entidades**.
      *Pontuação* na entidade de saída é uma medida quantitativa da recomendação. O modelo recomenda produtos com uma pontuação mais alta em vez de produtos com uma pontuação mais baixa.
   - **Campo previsto:** este campo é preenchido apenas para alguns tipos de previsões e não é usado na previsão de Recomendação de Produtos.
   - **Status:** O status atual da execução da previsão.
        - **Na fila:** A previsão está aguardando a execução de outros processos.
        - **Atualizando:** A previsão está atualmente executando o estágio de "pontuação" do processamento para gerar resultados que fluirão para a entidade de saída.
        - **Falha:** a previsão falhou. Selecione **Logs** para obter mais detalhes.
        - **Êxito:** a previsão foi bem sucedida. Selecione **Exibir** nos três pontos verticais para revisar a previsão
   - **Editado:** A data em que a configuração da previsão foi alterada.
   - **Última atualização:** A data em que a previsão atualizou resultados na entidade de saída.

1. Selecione os três pontos verticais ao lado da previsão cujos resultados deseja revisar e selecione **Exibir**.
   > [!div class="mx-imgBorder"]
   > ![Exibição das opções no menu de três pontos verticais de uma previsão, que inclui editar, atualizar, exibir, logs e excluir.](media/product-recommendation-verticalellipses.PNG "Exibição das opções no menu de três pontos verticais para uma previsão, incluindo editar, atualizar, exibir, logs e excluir")

1. Há cinco seções principais de dados na página de resultados:
    1. **Desempenho do modelo de treinamento:** A, B ou C são pontuações possíveis. Essa pontuação indica o desempenho da previsão e pode ajudar você a decidir usar os resultados armazenados na entidade de saída.
        - As pontuações são determinadas com base nas seguintes regras:
            - **A** O modelo será considerado como qualidade **A** se a métrica "Success @ K" for pelo menos 10% superior à linha de base. 
            - **B** O modelo será considerado como qualidade **B** se a métrica "Success @ K" for 0% a 10% superior à linha de base.
            - **C** O modelo será considerado como qualidade **C** se a métrica "Success @ K" for inferior à linha de base.

               > [!div class="mx-imgBorder"]
               > ![Exibição do resultado do desempenho do modelo.](media/product-recommendation-modelperformance.PNG "Exibição do resultado de desempenho do modelo")
            - **Linha de base**: O modelo pega os principais produtos mais recomendados por contagem de compra em todos os clientes e usa regras aprendidas identificadas pelo modelo para criar um conjunto de recomendações para os clientes. As previsões são então comparadas aos principais produtos, calculadas pelo número de clientes que compraram o produto. Se um cliente tem pelo menos um produto em seus produtos recomendados que também foi visto nos produtos mais comprados, eles são considerados parte da linha de base. Se 10 desses clientes tivessem um produto recomendado comprado de um total de 100 clientes, a linha de base seria 10%.
            - **Success @ K**: Usando um conjunto de validação de período de transações, as recomendações são criadas para todos os clientes e comparadas com o conjunto de validação de transações. Por exemplo, em um período de 12 meses, o mês 12 pode ser reservado como um conjunto de dados de validação. Se o modelo fizesse a previsão de pelo menos um item que você compraria no mês 12 com base no que aprendeu nos 11 meses anteriores, o cliente aumentaria a métrica "Success @ K".

    1. **Produtos mais sugeridos (com contagem):** os cinco principais produtos previstos para seus clientes.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que mostra os 5 produtos mais recomendados.](media/product-recommendation-topproducts.PNG "Gráfico que mostra os 5 produtos mais recomendados")

    1. **Principais fatores de recomendação:** o modelo usa o histórico de transações dos clientes para fazer recomendações de produtos. Ele aprende padrões com base em compras anteriores e encontra semelhanças entre clientes e produtos. Essas semelhanças são então utilizadas para gerar recomendações de produtos.
    A seguir estão os fatores que podem influenciar uma recomendação de produto gerada pelo modelo.
        - **Transações anteriores**: no passado, os padrões de compra eram utilizados pelo modelo para gerar recomendações de produtos. Por exemplo, o modelo pode recomendar um *Mouse Surface Arc* se alguém comprou recentemente um *Surface Book 3* e uma *Caneta Surface*. O modelo aprendeu que, historicamente, muitos clientes compraram um *Mouse Surface Arc* depois de comprar um *Surface Book 3* e uma *Caneta Surface*.
        - **Similaridade do cliente**: um produto recomendado foi historicamente comprado por outros clientes que apresentam padrões de compra semelhantes. Por exemplo, John recebeu como recomendação o *Surface Headphones 2* porque Jennifer e Brad recentemente compraram o *Surface Headphones 2*. O modelo acredita que John é semelhante a Jennifer e Brad porque eles tiveram historicamente padrões de compra semelhantes.
        - **Similaridade do produto**: um produto recomendado é semelhante a outros produtos que o cliente comprou anteriormente. O modelo considera dois produtos semelhantes se tiverem sido comprados juntos ou por clientes semelhantes. Por exemplo, alguém recebe uma recomendação de uma *Unidade de Armazenamento USB* porque comprou anteriormente um *Adaptador USB-C para USB* e o modelo acredita que a *Unidade de Armazenamento USB* é semelhante ao *Adaptador USB-C para USB* com base em padrões de compra históricos.

        Toda recomendação de produto é influenciada por um ou mais desses fatores. A porcentagem de recomendações em que cada fator influenciador desempenhou um papel é visualizada em um gráfico. No exemplo a seguir, 100% das recomendações foram influenciadas por transações anteriores, 60% pela similaridade do cliente e 22% pela similaridade do produto. Passe o mouse sobre as barras do gráfico para ver a porcentagem exata em que os fatores influenciadores contribuíram.

        > [!div class="mx-imgBorder"]
        > ![Principais fatores de recomendação.](media/product-recommendation-keyrecommendationfactors.png "Principais fatores de recomendação aprendidos pelo modelo para gerar recomendações de produtos")

   1. **Estatísticas de dados**: fornecem uma visão geral do número de transações, clientes e produtos que o modelo considerou. Elas são baseadas nos dados de entrada que foram usados para aprender padrões e gerar recomendações de produtos.

      > [!div class="mx-imgBorder"]
      > ![Estatísticas de dados.](media/product-recommendation-datastatistics.png "Estatísticas de dados sobre dados de entrada usados pelo modelo para aprender padrões")

      Esta seção mostra estatísticas sobre os pontos de dados que foram usados pelo modelo para aprender padrões e gerar recomendações de produtos. A filtragem, conforme definida na configuração do modelo, será aplicada na saída gerada pelo modelo. No entanto, o modelo usa todos os dados disponíveis para aprender padrões. Portanto, se você usar a filtragem de produto na configuração do modelo, esta seção mostrará o número total de produtos que o modelo analisou para aprender padrões, que pode diferir do número de produtos que correspondem aos critérios de filtragem definidos.

   1. **Recomendações de produtos de alta confiança:** Uma amostra de recomendações fornecidas a seus clientes que o modelo acha que provavelmente serão adquiridas pelo cliente.    
      Se um catálogo de produtos for adicionado, as IDs dos produtos serão substituídas pelos nomes dos produtos. Os nomes dos produtos fornecem informações mais acionáveis e intuitivas sobre as previsões.
       > [!div class="mx-imgBorder"]
       > ![Lista que mostra sugestões de alta confiança para um conjunto selecionado de clientes individuais.](media/product-recommendation-highconfidence.PNG "Lista que mostra sugestões de alta confiança para um conjunto selecionado de clientes individuais")

## <a name="manage-predictions"></a>Gerenciar previsões

É possível otimizar, solucionar problemas, atualizar ou excluir previsões. Revise um relatório de usabilidade de dados de entrada para descobrir como fazer uma previsão mais rápida e confiável. Para obter mais informações, consulte [Gerenciar previsões](manage-predictions.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
