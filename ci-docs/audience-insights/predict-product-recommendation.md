---
title: Previsão de recomendação do produto
description: Preveja os produtos que um cliente provavelmente comprará ou com os quais interagirá.
ms.date: 02/15/2021
ms.reviewer: zacook
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 5a2eb2b4697e51a0abb933b654a9b0b150dfa6a3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270467"
---
# <a name="product-recommendation-prediction-preview"></a>Previsão de recomendação do produto (versão preliminar)

O modelo de recomendação de produto cria conjuntos de recomendações de produto preditivas. As recomendações são baseadas no comportamento de compra anterior e clientes com padrões de compra semelhantes. Você pode criar novas previsões de recomendação de produto na página **Inteligência** > **Previsões**. Selecione **Minhas previsões** para ver outras previsões que você criou.

As recomendações de produtos podem estar sujeitas às leis e regulamentações locais, bem como às expectativas do cliente, as quais o modelo não foi projetado especificamente para levar em consideração.  Como usuário desse recurso preditivo, **você deve revisar as recomendações antes de entregá-las aos seus clientes** para garantir que você está cumprindo todas as leis ou regulamentos aplicáveis, bem como as expectativas do cliente quanto ao que você pode recomendar. 

Além disso, a saída deste modelo fornecerá recomendações com base na ID do produto. Seu mecanismo de entrega precisará obter IDs de produto previstos e mapeá-los para o conteúdo apropriado para que seus clientes sejam responsáveis pela localização, conteúdo de imagem e outro conteúdo ou comportamento específico de negócios.

## <a name="sample-guide"></a>Guia de amostra

Se estiver interessado em experimentar este recurso, mas não tiver dados para preencher os requisitos abaixo, você pode [criar uma implementação de amostra](sample-guide-predict-product-recommendation.md).

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.
- Conhecimento de negócios para entender os diferentes tipos de produtos para sua empresa e como seus clientes interagem com eles. Apoiamos a recomendação de produtos que foram adquiridos anteriormente por seus clientes ou recomendações de novos produtos.
- Dados sobre as transações, compras e seu histórico:
    - Identificadores de transação para distinguir compras ou transações.
    - Identificadores de cliente para mapear transações aos seus clientes.
    - Datas dos eventos de transação que especificam a transação ocorreu.
    - (Opcional) Informações de ID do produto para a transação.
    - (Opcional) Se uma transação é uma devolução ou não.
    - O esquema de dados semânticos requer as seguintes informações:
        - **ID da transação:** um identificador exclusivo de uma compra ou transação.
        - **Data da transação:** a data da compra ou da transação.
        - **Valor da transação:** o valor numérico da compra ou da transação.
        - **ID exclusiva do produto:** a ID do produto ou serviço adquirido, se os seus dados estiverem em um nível de item de linha.
        - (Opcional) **Compra ou devolução:** um campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** for negativo, também usaremos essa informação para inferir uma devolução.


## <a name="create-a-product-recommendation-prediction"></a>Criar uma previsão de recomendação do produto

1. No Customer Insights, acesse **Inteligência** > **Previsões**.

1. Selecione o bloco **Modelo de recomendações do produto (versão preliminar)** e selecione **Usar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Bloco do modelo de recomendação do produto com o botão Usar este modelo](media/product-recommendation-usethismodel.PNG "Bloco do modelo de recomendação do produto com o botão Usar este modelo")

1. Revise as informações sobre os requisitos do modelo. Se você tiver os dados necessários, selecione **Começar**.

### <a name="name-model"></a>Nomear modelo

1. Forneça um nome para o modelo para diferenciá-lo dos outros modelos.

1. Insira um nome para a entidade de saída usando apenas letras e números, sem espaços. Esse é o nome que a entidade de modelo usará. Em seguida, selecione **Próximo**.

### <a name="define-product-recommendation-configuration"></a>Definir configuração de recomendação de produto

1. Defina o **Número de produtos** que você deseja recomendar a um cliente. Esse valor depende de como seu método de entrega preenche os dados. Se você pode recomendar três produtos, defina esse valor adequadamente.
   
   >[!TIP]
   > Você pode selecionar **Salvar e fechar** a qualquer momento para salvar a previsão como rascunho. Você encontrará a previsão de rascunho na guia **Minhas previsões**.

1. Escolha se deseja **Sugerir produtos que os clientes compraram recentemente**.

1. Se você selecionou *não* recomendar produtos comprados recentemente, defina a **Janela do passado**. Esta configuração especifica o período que o modelo considera antes de recomendar o produto ao usuário novamente. Por exemplo, indique que um cliente adquire um laptop a cada 2 anos. Esta janela examinará o histórico de compras dos últimos 2 anos e, se encontrar um item, o item será filtrado das recomendações.

1. Selecione **Avançar**

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** para **Histórico de transações do cliente** e escolha a entidade que fornece as informações do histórico de transações/compras, conforme descrito nos [pré-requisitos](#prerequisites).

1. Mapeie os campos semânticos para atributos na sua entidade do histórico de compras e selecione **Avançar**. Para obter descrições dos campos, observe os [pré-requisitos](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Defina o relacionamento da entidade](media/product-recommendation-purchasehistorymapping.PNG "Página de histórico de compras mostrando atributos semânticos que são mapeados para campos na entidade de histórico de compras selecionada")

1. Se os campos não estiverem preenchidos, configure o relacionamento da sua entidade do histórico de compras para a entidade *Cliente*.
    1. Selecione a **Entidade do histórico de compras**.
    1. Selecione o **Campo** que identifica o cliente na entidade do histórico de compras. Ele precisa estar relacionado à ID do cliente principal da sua entidade *Cliente*.
    1. Selecione a **Entidade Cliente** que corresponde à entidade do cliente primário.
    1. Insira um nome que descreva a relação.
       > [!div class="mx-imgBorder"]
       > ![Página do histórico de compras mostrando a criação de um relacionamento com o cliente](media/model-purchase-join.png "Página do histórico de compras mostrando a criação de um relacionamento com o cliente")

1. Selecione **Salvar**.

1. Selecione **Avançar**.

### <a name="set-schedule-and-review-configuration"></a>Defina o agendamento e revise a configuração

1. Defina uma frequência para treinar o modelo novamente. Essa configuração é importante para atualizar a precisão das previsões conforme novos dados são importados para o Customer Insights. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**.

1. Revise a configuração. Você pode voltar para qualquer parte da configuração da previsão selecionando **Editar** abaixo do valor exibido. Ou você pode selecionar uma etapa da configuração no indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Salvar e executar** para iniciar o processo de previsão. Na guia **Minhas previsões**, você pode ver o status das previsões. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Revisar o status e os resultados de uma previsão

1. Vá para a guia **Minhas previsões** em **Inteligência** > **Previsões**.
   > [!div class="mx-imgBorder"]
   > ![Exibição da página Minhas Previsões](media/product-recommendation-mypredictions.PNG "Exibição da página Minhas Previsões")

1. Selecione a previsão que você deseja revisar.
   - **Nome da previsão:** O nome da previsão que foi fornecido ao criá-la.
   - **Tipo de previsão:** O tipo do modelo usado na previsão
   - **Entidade de saída:** Nome da entidade que armazenará a saída da previsão. Você pode encontrar uma entidade com esse nome em **Dados** > **Entidades**.
   - **Campo previsto:** este campo é preenchido apenas para alguns tipos de previsões e não é usado na previsão de rotatividade.
   - **Status:** O status atual da execução da previsão.
        - **Na fila:** A previsão está aguardando a execução de outros processos.
        - **Atualizando:** A previsão está atualmente executando o estágio de "pontuação" do processamento para gerar resultados que fluirão para a entidade de saída.
        - **Falha:** a previsão falhou. Selecione **Logs** para obter mais detalhes.
        - **Êxito:** a previsão foi bem sucedida. Selecione **Exibir** nos três pontos verticais para revisar a previsão
   - **Editado:** A data em que a configuração da previsão foi alterada.
   - **Última atualização:** A data em que a previsão atualizou resultados na entidade de saída.

1. Selecione os três pontos verticais ao lado da previsão cujos resultados deseja revisar e selecione **Exibir**.
   > [!div class="mx-imgBorder"]
   > ![Exibição das opções no menu de três pontos verticais para uma previsão, incluindo editar, atualizar, exibir, logs e excluir](media/product-recommendation-verticalellipses.PNG "Exibição das opções no menu de três pontos verticais para uma previsão, incluindo editar, atualizar, exibir, logs e excluir")

1. Há três seções principais de dados na página de resultados:
    1. **Desempenho do modelo de treinamento:** A, B ou C são pontuações possíveis. Essa pontuação indica o desempenho da previsão e pode ajudar você a decidir usar os resultados armazenados na entidade de saída.
        - As pontuações são determinadas com base nas seguintes regras:
            - **A** O modelo será considerado como qualidade **A** se a métrica "Success @ K" for pelo menos 10% superior à linha de base. 
            - **B** O modelo será considerado como qualidade **B** se a métrica "Success @ K" for pelo menos 0 a 10% superior à linha de base.
            - **C** O modelo será considerado como qualidade **C** se a métrica "Success @ K" for pelo menor que a linha de base.
               
               > [!div class="mx-imgBorder"]
               > ![Exibição do resultado de desempenho do modelo](media/product-recommendation-modelperformance.PNG "Exibição do resultado de desempenho do modelo")
            - **Linha de base**: O modelo pega os principais produtos mais recomendados por contagem de compra em todos os clientes e usa regras aprendidas identificadas pelo modelo para criar um conjunto de recomendações para os clientes. As previsões são então comparadas aos principais produtos, calculadas pelo número de clientes que compraram o produto. Se um cliente tem pelo menos um produto em seus produtos recomendados que também foi visto nos produtos mais comprados, eles são considerados parte da linha de base. Se 10 desses clientes tivessem um produto recomendado comprado de um total de 100 clientes, a linha de base seria 10%.
            - **Success @ K**: Usando um conjunto de validação de período de transações, as recomendações são criadas para todos os clientes e comparadas com o conjunto de validação de transações. Por exemplo, em um período de 12 meses, o mês 12 pode ser reservado como um conjunto de dados de validação. Se o modelo fizesse a previsão de pelo menos um item que você compraria no mês 12 com base no que aprendeu nos 11 meses anteriores, o cliente aumentaria a métrica "Success @ K".
    
    1. **Produtos mais sugeridos (com contagem):** Os 5 principais produtos previstos para seus clientes.
       > [!div class="mx-imgBorder"]
       > ![Gráfico mostrando os 5 produtos mais recomendados](media/product-recommendation-topproducts.PNG "Gráfico mostrando os 5 produtos mais recomendados")
    
    1. **Recomendações de produtos de alta confiança:** Uma amostra de recomendações fornecidas a seus clientes que o modelo acha que provavelmente serão adquiridas pelo cliente.
       > [!div class="mx-imgBorder"]
       > ![Lista mostrando sugestões de alta confiança para um conjunto selecionado de clientes individuais](media/product-recommendation-highconfidence.PNG "Lista mostrando sugestões de alta confiança para um conjunto selecionado de clientes individuais")

## <a name="fix-a-failed-prediction"></a>Corrigir uma previsão com falha

1. Vá para a guia **Minhas previsões** em **Inteligência** > **Previsões**.

1. Selecione a previsão cujos logs de erro gostaria de exibir e selecione **Logs**.

1. Revise todos os erros. Há vários tipos de erros que podem ocorrer e eles descrevem qual condição causou o erro. Por exemplo, um erro causado por dados insuficientes para gerar uma previsão de forma precisa é geralmente resolvido ao carregar dados adicionais no Customer Insights.

## <a name="refresh-a-prediction"></a>Atualizar uma previsão

As previsões são atualizadas automaticamente na mesma [programação em que seus dados são atualizados](system.md#schedule-tab) conforme definido nas configurações.

1. Vá para a guia **Minhas previsões** em **Inteligência** > **Previsões**.

1. Selecione os três pontos verticais ao lado da previsão que deseja atualizar.

1. Selecione **Atualizar**.

## <a name="delete-a-prediction"></a>Excluir uma previsão

A exclusão de uma previsão também removerá sua entidade de saída.

1. Vá para a guia **Minhas previsões** em **Inteligência** > **Previsões**.

1. Selecione os três pontos verticais ao lado da previsão que deseja excluir.

1. Selecione **Excluir**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]