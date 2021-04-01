---
title: Preencher dados parciais usando previsões
description: Use previsões para preencher dados incompletos dos clientes.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 3342328b9eead9bdcb8b41f119a1d0a5823001c8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595887"
---
# <a name="complete-your-partial-data-with-predictions"></a>Concluir seus dados parciais com previsões

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

As previsões permitem criar facilmente valores previstos que podem melhorar sua compreensão de um cliente. Na página **Inteligência** > **Previsões** , é possível selecionar **Minhas previsões** para ver as previsões que você configurou em outras partes dos insights de público-alvo e personalizá-las ainda mais.

> [!NOTE]
> Você não poderá usar esse recurso se o seu ambiente usar o armazenamento do Azure Data Lake Gen 2.
>
> O recurso de previsões usa meios automatizados para avaliar dados e fazer previsões com base nesses dados e, portanto, tem a capacidade de ser usado como um método de criação de perfil, pois esse termo é definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD"). O uso desse recurso pelo cliente para processar dados pode estar sujeito ao RGPD ou a outras leis ou regulamentos. Você é responsável por garantir que o uso do Dynamics 365 Customer Insights, incluindo as previsões, esteja em conformidade com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

## <a name="prerequisites"></a>Pré-requisitos

Antes de sua organização poder usar o recurso de previsões, verifique se os seguintes pré-requisitos foram atendidos:

1. Sua organização tem uma instância [configurada no Common Data Service](/ai-builder/build-model#prerequisites) e está na mesma organização que o Customer Insights.

2. Seu ambiente está anexado à sua instância do Common Data Service.

Se você estiver [criando o primeiro ambiente](manage-environments.md), configure-o no diálogo **Criar um ambiente** e selecione **Avançado**. Se você já criou um ambiente, vá para as configurações e selecione **Avançado**. De qualquer forma, na seção **Usar previsões**, insira a URL da instância do Common Data Service à qual você deseja anexar seu ambiente.

## <a name="create-a-prediction-in-the-customer-entity"></a>Criar uma previsão na entidade Cliente

1. Nos insights de público-alvo, vá para **Dados** > **Entidades**.

2. Selecione a entidade **Cliente**.

3. Na entidade **Cliente: CustomerInsights**, selecione a guia **Campos**.

4. Localize o nome do atributo para o qual deseja prever valores e selecione o ícone **Visão geral** na coluna **Resumo**.
   > [!div class="mx-imgBorder"]
   > ![Ícone de Visão geral](media/intelligence-overviewicon.png "Ícone de Visão geral")

5. Se houver uma alta taxa de valores ausentes para o seu atributo, selecione **Prever valores ausentes** para prosseguir com sua previsão.
   > [!div class="mx-imgBorder"]
   > ![Status da visão geral com o botão prever valores ausentes mostrado](media/intelligence-overviewpredictmissingvalues.png "Status da visão geral com o botão prever valores ausentes mostrado")

6. Forneça um **Nome de exibição** e um **Nome da entidade de saída** para os resultados da previsão.

7. Uma lista de opções preenchida previamente mostrará onde você pode mapear os valores para uma categoria prevista. Nesse caso, suas únicas opções de categoria serão 0 ou 1, pois mapeiam para verdadeiro/falso ou a natureza binária da previsão. Na coluna Categoria, mapeie os valores do campo que você deseja classificar como "0" na previsão final para "0" e os itens que você deseja classificar como "1" na previsão final para o "1".
   > [!div class="mx-imgBorder"]
   > ![Exemplo mostrando valores de campo mapeado para categorias](media/intelligence-categorymapping.png "Exemplo mostrando valores de campo mapeado para categorias")

8. Selecione **Concluído** e a previsão será processada. O processamento levará algum tempo, dependendo do tamanho e da complexidade dos dados. Os resultados estarão disponíveis em uma nova entidade com base no **Nome da entidade de saída** da previsão que você criou.

## <a name="create-a-prediction-while-creating-a-segment"></a>Criar uma previsão ao criar um segmento

Também é possível prever valores ausentes para um atributo específico à sua escolha ao criar um segmento. Especificamente, quando você cria rapidamente um segmento com base na sua entidade Cliente ou na entidade Medida_do_Cliente unificadas.

Como parte desse fluxo, você escolherá um atributo específico para basear seu segmento, como Satisfação do Cliente ou Valor da Compra. Na criação do segmento, o sistema sugere um método para prever quaisquer valores ausentes para esse atributo.

1. Nos insights de público-alvo, vá para **Segmentos** e selecione o bloco **Perfis**.

2. Escolha um **Campo** para criar um segmento e selecione um **Operador** e selecione **Revisar**.

3. Forneça um **Nome** e um **Nome de exibição** para o segmento.

4. Selecione **Salvar**.

5. Se o segmento que criou tiver dados incompletos no campo de origem, você poderá optar por prever os valores ausentes.
   > [!div class="mx-imgBorder"]
   > ![Botão Previsão](media/segments-predictoption.png "Botão Previsão")

6. Forneça um **Nome de exibição** e um **Nome da entidade de saída** para os resultados da previsão.

7. Escolha **Concluído**. Sua previsão será gerada pouco tempo depois em uma nova entidade com o nome que você forneceu para o **Nome da entidade de saída**.

## <a name="view-a-prediction"></a>Exibir uma previsão

1. Nos insights de público-alvo, vá para **Inteligência** > **Previsões** > **Minhas previsões**.

2. Selecione a previsão que você deseja revisar.

3. Selecione as reticências na coluna **Ações** e escolha **Exibir**.

4. Você verá alguns pontos de dados na exibição de sua previsão.
   > [!div class="mx-imgBorder"]
   > ![Página Previsões](media/intelligence-predictionsviewpage.png "Página Previsões")

   - **Valores previstos** mostra o mapeamento criado durante o Valor de campo para a fase Mapeamento de categoria. Esses são os valores em seu conjunto de dados que foram mapeados para uma categoria específica.
   -**Principais influenciadores** são os fatores em seu conjunto de dados que mais provavelmente influenciarão a confiança da previsão do Valor de campo que está sendo mapeado para uma categoria específica.
   - **Desempenho** indica como estão as previsões. Selecione o link para saber mais.
   - **Visualização** exibe amostras do conjunto de dados de saída de sua previsão e a probabilidade, ou nossa confiança, do valor previsto em que 0 é incerto e 1 é certo.

## <a name="update-a-prediction"></a>Atualizar uma previsão

1. Nos insights de público-alvo, vá para **Inteligência** > **Previsões** > **Minhas previsões**.

2. Selecione a previsão que você quer atualizar e selecione o ícone **Atualização**.

3. A previsão será agendada para processamento. Você pode ver a hora em que foi atualizada pela última vez na coluna **Atualizado** da página **Previsões**.

## <a name="edit-a-prediction"></a>Editar uma previsão

Depois de criar uma previsão, você poderá personalizar o modelo no AI Builder para aumentar a eficácia do seu modelo.  

1. Nos insights de público-alvo, vá para **Inteligência** > **Previsões** > **Minhas previsões**.

2. Selecione a previsão que você deseja editar.

3. Selecione as reticências na coluna **Ações** e escolha **Exibir**.

4. Selecione **Personalizar no AI Builder**.

5. Atualize seu modelo no AI Builder. [Saiba mais sobre o gerenciamento de modelos no AI Builder](/ai-builder/manage-model#retrain-and-republish-existing-models).

A próxima execução da sua previsão usará o modelo atualizado que você criou.

> [!NOTE]
> Novos modelos criados no AI Builder não serão exibidos nos insights de público-alvo, a menos que o modelo tenha sido criado a partir das experiências listadas acima.

## <a name="remove-a-prediction"></a>Remover uma previsão

1. Nos insights de público-alvo, vá para **Inteligência** > **Previsões** > **Minhas previsões**.

2. Selecione a previsão que você deseja excluir.

3. Selecione as reticências na coluna **Ações** e escolha **Excluir**.

4. Confirme a exclusão.

## <a name="troubleshooting"></a>Solução de Problemas

Se você não conseguir concluir o processo anexo do Common Data Service por causa de um erro, tente concluí-lo manualmente. Há dois problemas conhecidos que podem ocorrer no processo de anexo:

- A solução Complemento do Cartão do Cliente não foi instalada.
    1. Siga as instruções para [instalar e configurar a solução](customer-card-add-in.md).

- As permissões de aplicativo não foram concedidas.
    1. Vá para [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).
    1. Selecione **Ambientes**.
    1. Selecione as reticências ao lado do ambiente ao qual você deseja adicionar a permissão e selecione **Configurações**.
    1. Expanda **Usuários e permissões** e selecione **Usuários**.
    1. Selecione **+ Novo** e selecione **Usuário**.
    1. Selecione **Usuário do Aplicativo** se ainda não estiver selecionado e insira as seguintes informações:
        - **Nome de usuário:** cihelp@microsoft.com
        - **ID do Aplicativo:** 38c77d00-5fcb-4cce-9d93-af4738258e3c
        - **Nome:** Cliente
        - **Sobrenome:** Insights
        - **Email Principal:** cihelp@microsoft.com
    1. Selecione **Salvar e fechar**.
    1. Selecione o usuário que você acabou de criar.
    1. Selecione **Gerenciar funções** na barra de menus superior.
    1. Selecione **Administrador do Sistema** e selecione **OK**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]