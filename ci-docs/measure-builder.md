---
title: Criar medidas com o construtor de medidas
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
ms.openlocfilehash: fac00b8a1b4ca6e09dd29abe46dfe240adcc029e
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170835"
---
# <a name="create-measures-with-measure-builder"></a>Criar medidas com o construtor de medidas

O construtor de medidas permite que você defina os cálculos usando operadores matemáticos, funções de agregação e filtros. Defina medidas usando atributos das entidades relacionadas à entidade unificada *Cliente*.

A criação de medidas em ambientes B2C e B2B funciona da mesma maneira. No entanto, se o seu ambiente B2B [usar contas com hierarquias](relationships.md#set-up-account-hierarchies), escolha se deseja agregar a medida em todas as subcontas relacionadas.

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

Crie medidas no nível de clientes individuais (Atributo do cliente, medida do cliente) ou no nível do negócio/da organização (medida de negócios). Atributo do cliente e medida de negócios permitem que você rastreie o desempenho por cliente. Por exemplo, o gasto total de cada cliente. Medidas de negócios rastreiam o desempenho por negócio. Por exemplo, a receita total da empresa.

- Atributo do cliente: gera a saída como um novo atributo, que é salvo como uma nova coluna na entidade gerada pelo sistema chamada *Customer_Measure*. Ao atualizar um atributo do cliente, todos os outros atributos do cliente na entidade *Customer_Measure* são atualizados simultaneamente. Além disso, os atributos do cliente são mostrados no cartão do perfil do cliente. Depois de executado ou salvo, você poderá alterar um atributo do cliente para uma medida de negócios.

- Medida do cliente: gera a saída como sua própria entidade e você não poderá alterá-la para um atributo do cliente depois de executada ou salva. As medidas do cliente não são exibidas no cartão do perfil do cliente.

- Medida de negócios: gera a saída como sua própria entidade e mostra a home page de seu ambiente do Customer Insights

1. Acesse **Medidas**.

1. Selecione **Novo** > **Criar seu próprio**.

   :::image type="content" source="media/measure-b2c.png" alt-text="Tela de configuração vazia para uma medida B2C." lightbox="media/measure-b2c.png":::

1. Selecione **Editar detalhes** ao lado de Medida sem título. Forneça um nome para a medida. Opcionalmente, adicione [marcas](work-with-tags-columns.md#manage-tags) à medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Editar caixa de diálogo de detalhes":::

1. Selecione **Concluído**.

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

1. Selecione **Adicionar atributo** para selecionar os dados para criar a medida.

   1. Selecione a guia **Atributos**.
   1. Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir.
   1. Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida. Você só pode selecionar um atributo por vez.
   1. Opcionalmente, escolha um atributo de dados a partir de uma medida existente selecionando a guia **Medidas** ou procure uma entidade ou nome de medida.
   1. Selecione **Adicionar**.

1. Para criar medidas mais complexas, adicione mais atributos ou use operadores matemáticos na função de sua medida.

1. Para adicionar filtros, selecione **Filtro** na área de configuração. A aplicação de filtros usará somente os registros que correspondem aos filtros para calcular a medida.
  
   1. Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo de lote que você deseja usar para criar filtros.
   1. Configure os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar**.

1. Selecione **Dimensão** para escolher mais campos a serem adicionados como colunas à entidade de saída da medida.

   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida. Por exemplo, cidade ou sexo.
      > [!TIP]
      > Se você selecionou **Nível de cliente** como o **Tipo de medida**, o atributo *CustomerId* já foi adicionado. Se você remover o atributo, **Tipo de medida** alternará para **Nível de negócios**.
   1. Selecione **Concluído**.

1. Se houver valores que devem ser substituídos por um inteiro em seu dados, selecione **Regras**. Configure a regra e escolha apenas números inteiros como substituições. Por exemplo, substitua *nulo* por *0*.

1. Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade *Cliente*, escolha um dos [caminhos de relacionamento de entidade](relationships.md) identificados. Os resultados da medição podem variar dependendo do caminho selecionado.

   1. Selecione **Caminho de relacionamento** e escolha o caminho da entidade que deve ser usado para identificar sua medida. Se houver somente um único caminho para a entidade *Cliente*, este controle não será exibido.
   1. Selecione **Concluído**.

1. Para adicionar mais cálculos para a medida, selecione **Novo cálculo**. Só use entidades no mesmo caminho de entidade para novos cálculos. Mais cálculos serão exibidos como novas colunas na entidade de saída de medida. Opcionalmente, selecione **Editar nome** para criar um nome para o cálculo.

1. Selecione as reticências verticais (&vellip;) no cálculo para **Duplicar** ou **Remover** um cálculo da medida.

1. Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A versão preliminar reage dinamicamente às mudanças na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde. A página **Medidas** será exibida.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

Crie medidas no nível de contas individuais (medida do cliente) ou no nível de todas as contas (medida de negócios).

- Medida do cliente: gera a saída como sua própria entidade. As medidas do cliente não são exibidas no cartão do perfil do cliente.

- Medida de negócios: gera a saída como sua própria entidade e mostra a home page de seu ambiente do Customer Insights

1. Acesse **Medidas**.

1. Selecione **Nova**.

   :::image type="content" source="media/measure-b2b.png" alt-text="Tela de configuração vazia para uma medida B2B. ":::

1. Selecione **Editar detalhes** ao lado de Medida sem título. Forneça um nome para a medida. Opcionalmente, adicione [marcas](work-with-tags-columns.md#manage-tags) à medida. 
   :::image type="content" source="media/measures_edit_details.png" alt-text="Editar caixa de diálogo de detalhes":::

1. Selecione **Concluído**.

1. Na área de configuração, escolha a função de agregação no menu suspenso **Selecionar função**. As funções de agregação incluem:
   - **Somar**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máximo**
   - **Mínimo**
   - **Primeiro**: usa o primeiro valor do registro de dados
   - **Último**: pega o último valor que foi adicionado ao registro de dados

1. Selecione **Adicionar atributo** para selecionar os dados para criar a medida.

   1. Selecione a guia **Atributos**.
   1. Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir.
   1. Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida. Você só pode selecionar um atributo por vez.
   1. Opcionalmente, escolha um atributo de dados a partir de uma medida existente selecionando a guia **Medidas** ou procure uma entidade ou nome de medida.
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

1. Para criar medidas mais complexas, adicione mais atributos ou use operadores matemáticos na função de sua medida.

1. Para adicionar filtros, selecione **Filtro** na área de configuração. A aplicação de filtros usará somente os registros que correspondem aos filtros para calcular a medida.
  
   1. Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo de lote que você deseja usar para criar filtros.
   1. Configure os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Selecione **Dimensão** para escolher mais campos a serem adicionados como colunas à entidade de saída da medida.

   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida. Por exemplo, cidade ou sexo.
      > [!TIP]
      > O atributo *CustomerId* já está adicionado indicando que isso é um tipo de medida no nível do cliente. Se você remover o atributo, o tipo de medida será alterado para o nível de negócios.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores que devem ser substituídos por um inteiro em seu dados, selecione **Regras**. Configure a regra e escolha apenas números inteiros como substituições. Por exemplo, substitua *nulo* por *0*.

1. Se você [usar contas com hierarquias](relationships.md#set-up-account-hierarchies), examine **Acumular subcontas**.
   - Se estiver definido como **Desligado**, a medida é calculada para cada conta. Toda conta obtém seu próprio resultado.
   - Se estiver definido como **Ligado**, selecione **Editar** para escolher a hierarquia da conta de acordo com as hierarquias ingeridas. A medida renderá somente um resultado porque ele está agregado com subcontas.

1. Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade *Cliente*, escolha um dos [caminhos de relacionamento de entidade](relationships.md) identificados. Os resultados da medição podem variar dependendo do caminho selecionado.

   1. Selecione **Caminho de relacionamento** e escolha o caminho da entidade que deve ser usado para identificar sua medida. Se houver somente um único caminho para a entidade *Cliente*, este controle não será exibido.
   1. Selecione **Concluído** para aplicar sua seleção.

1. Selecione as reticências verticais (&vellip;) no cálculo para **Duplicar** ou **Remover** um cálculo da medida.

1. Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A versão preliminar reage dinamicamente às mudanças na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde. A página **Medidas** será exibida.

---

## <a name="next-step"></a>Próxima etapa

Use medidas existentes para criar [um segmento do cliente](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
