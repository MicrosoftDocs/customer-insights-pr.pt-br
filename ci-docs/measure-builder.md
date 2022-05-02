---
title: Criar novas medidas com o construtor de medidas
description: Crie medidas do zero para analisar as principais métricas sobre seu negócio.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-builder
- customerInsights
ms.openlocfilehash: 6370df0287362a5512a837cdb588f5d20ef03d3b
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645688"
---
# <a name="use-measure-builder-to-create-measures-from-scratch"></a>Usar o construtor de medidas para criar medidas a partir do zero

Este artigo explica como criar uma nova [medida](measures.md) do zero. O construtor de medidas permite definir cálculos usando operadores matemáticos, funções de agregação e filtros. Você pode construir uma medida com atributos de entidades que estão relacionadas à entidade *Cliente* unificada.

A criação de medidas em ambientes B2C e B2B funciona da mesma maneira. No entanto, se for um ambiente B2B [usa contas com hierarquias](relationships.md#set-up-account-hierarchies), você poderá optar por agregar a medida nas subcontas relacionadas.

Você também pode criar rapidamente uma medida escolhendo entre um conjunto de medidas comumente usadas e predefinidas. Para obter mais informações, consulte [Usar um modelo para construir uma medida](measure-templates.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

Você pode criar medidas no nível de clientes individuais (atributo do cliente, medida do cliente) ou no nível do negócio/da organização (medida de negócios). O atributo do cliente e a medida do cliente são dois tipos que permitem acompanhar o desempenho por cliente. Por exemplo, o gasto total de cada cliente. As medidas de negócios permitem que você acompanhe o desempenho por negócio. Por exemplo, a receita total da empresa.

- Atributo do cliente: gera a saída como um novo atributo, que é salvo como uma nova coluna na entidade gerada pelo sistema chamada *Customer_Measure*. Ao atualizar um atributo do cliente, todos os outros atributos do cliente na entidade *Customer_Measure* são atualizados simultaneamente. Além disso, os atributos do cliente são mostrados no cartão do perfil do cliente. Depois de executado ou salvo, o atributo do cliente não poderá ser alterado para uma medida do cliente.

- Medida do cliente: gera a saída como sua própria entidade e você não poderá alterá-la para um atributo do cliente depois de executada ou salva. As medidas do cliente não são exibidas no cartão do perfil do cliente.

- Medida de negócios: gera a saída como sua própria entidade e é exibida na home page do seu ambiente do Customer Insights.

1. Acesse **Medidas**.

1. Selecione **Novo** e escolha **Crie sua própria**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tela de configuração vazia para uma medida B2C." lightbox="media/measure-b2c.png":::

1. Para acompanhar o desempenho em nível de negócios, alterne **Tipo de medida** para **Nível de negócios**. **Nível de cliente** está selecionado por padrão. **Nível de cliente** adiciona automaticamente o atributo *CustomerId* a Dimensões enquanto **Nível de negócios** automaticamente o remove.

1. Na área de configuração, escolha a função de agregação no menu suspenso **Selecionar função**. As funções de agregação incluem:
   - **Somar**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máximo**
   - **Mínimo**
   - **Primeiro**: usa o primeiro valor do registro de dados
   - **Último**: pega o último valor que foi adicionado ao registro de dados
   - **ArgMax**: encontra o registro de dados que fornece o valor máximo de uma função de destino
   - **ArgMin**: encontra o registro de dados que fornece o valor mínimo de uma função de destino

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.

   1. Selecione a guia **Atributos**.
   1. Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir.
   1. Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida. Você só pode selecionar um atributo por vez.
   1. Você também pode selecionar um atributo de dados de uma medida existente selecionando a guia **Medidas** ou você pode pesquisar um nome de entidade ou medida.
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

1. Para criar medidas mais complexas, você pode adicionar mais atributos ou usar operadores matemáticos em sua função de medida.

1. Para adicionar filtros, selecione **Filtro** na área de configuração. A aplicação de filtros usará somente os registros que correspondem aos filtros para calcular a medida.
  
   1. Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo de lote que você deseja usar para criar filtros.
   1. Configure os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Selecione **Dimensão** para escolher mais campos que serão adicionados como colunas à entidade de saída de medida.

   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida. Por exemplo, cidade ou sexo.
   > [!TIP]
   > Se você selecionou **Nível de cliente** como o **Tipo de medida**, o atributo *CustomerId* já foi adicionado. Se você remover o atributo, **Tipo de medida** alternará para **Nível de negócios**.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores em seus dados que você precisa substituir por um número inteiro, selecione **Regras**. Configure a regra e escolha apenas números inteiros como substituições. Por exemplo, substitua *nulo* por *0*.

1. Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade *Cliente*, você deverá escolher um dos [caminhos de relacionamento de entidade](relationships.md) identificados. Os resultados da medição podem variar dependendo do caminho selecionado.

   1. Selecione **Caminho de relacionamento** e escolha o caminho da entidade que deve ser usado para identificar sua medida. Se houver somente um único caminho para a entidade *Cliente*, este controle não será exibido.
   1. Selecione **Concluído** para aplicar sua seleção.

1. Para adicionar mais cálculos para a medida, selecione **Novo cálculo**. Você só pode usar entidades no mesmo caminho de entidade para novos cálculos. Mais cálculos serão exibidos como novas colunas na entidade de saída de medida.

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A versão preliminar reage dinamicamente às mudanças na configuração.

1. Selecione **Editar detalhes** ao lado de Medida sem título. Forneça um nome para a medida. Opcionalmente, adicione [marcas](work-with-tags-columns.md#manage-tags) à medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Editar caixa de diálogo de detalhes":::

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde.

1. Acesse **Medidas** para ver a medida recém-criada na lista.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

Você pode criar medidas no nível de contas individuais (medida do cliente) ou no nível de todas as contas (medida de negócios).

- Medida do cliente: gera a saída como sua própria entidade. As medidas do cliente não são exibidas no cartão do perfil do cliente.

- Medida de negócios: gera a saída como sua própria entidade e é exibida na home page do seu ambiente do Customer Insights.

1. Acesse **Medidas**.

1. Selecione **Nova**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tela de configuração vazia para uma medida B2B. ":::

1. Na área de configuração, escolha a função de agregação no menu suspenso **Selecionar função**. As funções de agregação incluem:
   - **Somar**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máximo**
   - **Mínimo**
   - **Primeiro**: usa o primeiro valor do registro de dados
   - **Último**: pega o último valor que foi adicionado ao registro de dados

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.

   1. Selecione a guia **Atributos**.
   1. Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir.
   1. Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida. Você só pode selecionar um atributo por vez.
   1. Você também pode selecionar um atributo de dados de uma medida existente selecionando a guia **Medidas** ou você pode pesquisar um nome de entidade ou medida.
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

1. Para criar medidas mais complexas, você pode adicionar mais atributos ou usar operadores matemáticos em sua função de medida.

1. Para adicionar filtros, selecione **Filtro** na área de configuração. A aplicação de filtros usará somente os registros que correspondem aos filtros para calcular a medida.
  
   1. Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo de lote que você deseja usar para criar filtros.
   1. Configure os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Selecione **Dimensão** para escolher mais campos que serão adicionados como colunas à entidade de saída de medida.

   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida. Por exemplo, cidade ou sexo.
      > [!TIP]
      > Se você selecionou **Nível de cliente** como o **Tipo de medida**, o atributo *CustomerId* já foi adicionado. Se você remover o atributo, **Tipo de medida** mudará para **Nível de negócios**.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores em seus dados que você precisa substituir por um número inteiro, selecione **Regras**. Configure a regra e escolha apenas números inteiros como substituições. Por exemplo, substitua *nulo* por *0*.

1. Você pode usar o alternador **Agrupar subcontas** se você [usar contas com hierarquias](relationships.md#set-up-account-hierarchies).
   - Se estiver definido como **Desligado**, a medida é calculada para cada conta. Cada conta obtém seu próprio resultado.
   - Se estiver definido como **Ligado**, selecione **Editar** para escolher a hierarquia da conta de acordo com as hierarquias ingeridas. A medida produzirá apenas um resultado porque está agregada a subcontas.

1. Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade *Cliente*, você deverá escolher um dos [caminhos de relacionamento de entidade](relationships.md) identificados. Os resultados da medição podem variar dependendo do caminho selecionado.

   1. Selecione **Caminho de relacionamento** e escolha o caminho da entidade que deve ser usado para identificar sua medida. Se houver somente um único caminho para a entidade *Cliente*, este controle não será exibido.
   1. Selecione **Concluído** para aplicar sua seleção.

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A versão preliminar reage dinamicamente às mudanças na configuração.

1. Selecione **Editar detalhes** ao lado de Medida sem título. Forneça um nome para a medida. Opcionalmente, adicione [marcas](work-with-tags-columns.md#manage-tags) à medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Editar caixa de diálogo de detalhes":::

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde.

1. Acesse **Medidas** para ver a medida recém-criada na lista.
