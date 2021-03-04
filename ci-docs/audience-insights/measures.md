---
title: Criar e gerenciar medidas
description: Defina medidas para analisar e refletir o desempenho da sua empresa.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 5bcee3b4c51880740715575b18fd7a4dbf87e6d0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269914"
---
# <a name="define-and-manage-measures"></a>Definir e gerenciar medidas

As medidas ajudam você a entender melhor os comportamentos dos clientes e o desempenho da empresa, recuperando valores relevantes de [perfis unificados](data-unification.md). Por exemplo, uma empresa deseja ver o *gasto total por cliente* para entender o histórico de compras de cada cliente. Ou meça *vendas totais da empresa* para compreender a receita em nível agregado de toda a empresa.  

As medidas são criadas por meio do construtor de medidas, uma plataforma de consulta de dados com vários operadores e opções de mapeamento simples. Ele permite filtrar dados, agrupar resultados, detectar [caminhos de relacionamento de entidades](relationships.md) e exibir a saída.

Use o construtor de medidas para extrair insights e planejar atividades comerciais por meio da consulta de dados do cliente. Por exemplo, criar uma medida de *gasto total por cliente* e *retorno total por cliente* ajuda a identificar um grupo de clientes com alto gasto, mas alto retorno. É possível [criar um segmento](segments.md) para realizar as próximas ações recomendadas. 

## <a name="create-a-measure"></a>Criar uma medida

Esta seção explica como criar uma medida do zero. Você pode criar uma medida com atributos de dados de entidades de dados que têm um relacionamento configurado para se conectar com a entidade Cliente. 

1. Nos insights de público-alvo, vá para **Medidas**.

1. Selecione **Novo**.

1. Selecione **Editar nome** e forneça um **Nome** para a medida. 
   > [!NOTE]
   > Se sua nova configuração de medida tiver apenas dois campos (por exemplo, CustomerID) e um cálculo, a saída será adicionada como uma nova coluna à entidade gerada pelo sistema chamada Customer_Measure. E você poderá ver o valor da medida no perfil de cliente unificado. Outras medidas vão gerar suas próprias entidades.

1. Na área de configuração, escolha a função de agregação no menu suspenso **Selecionar função**. As funções de agregação incluem: 
   - **Somar**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máx**
   - **Min**
   - **Primeiro**: pega o primeiro valor do registro de dados
   - **Último**: pega o último valor que foi adicionado ao registro de dados

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.
   
   1. Selecione a guia **Atributos**. 
   1. Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir. 
   1. Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida. Você só pode selecionar um atributo por vez.
   1. Você também pode selecionar um atributo de dados de uma medida existente selecionando a guia **Medidas**. Ou você pode pesquisar um nome de entidade ou medida. 
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecione um atributo para usar nos cálculos.":::

1. Para criar medidas mais complexas, você pode adicionar mais atributos ou usar operadores matemáticos em sua função de medida.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crie uma medida complexa com operadores matemáticos.":::

1. Para adicionar filtros, selecione **Filtro** na área de configuração. 
  
   1. Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo que deseja usar para criar filtros.
   1. Configure os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Para adicionar dimensões, selecione **Dimensão** na área de configuração. As dimensões serão mostradas como colunas na entidade de saída da medida.
   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida. Por exemplo, cidade ou sexo. Por padrão, a dimensão *CustomerID* é selecionada para criar *medidas em nível de cliente*. Você pode remover a dimensão padrão se quiser criar *medidas em nível de negócios*.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade Cliente, você deve escolher um dos [caminhos de relacionamento de entidade](relationships.md) identificados. Os resultados da medição podem variar dependendo do caminho selecionado.
   1. Selecione **Preferências de dados** e escolha o caminho da entidade que deve ser usado para identificar sua medida.
   1. Selecione **Concluído** para aplicar sua seleção. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecione o caminho da entidade para a medida.":::

1. Para adicionar mais cálculos para a medida, selecione **Novo cálculo**. Você só pode usar entidades no mesmo caminho de entidade para novos cálculos. Mais cálculos serão exibidos como novas colunas na entidade de saída de medida.

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A versão preliminar reage dinamicamente às mudanças na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde.

1. Acesse **Medidas** para ver a medida recém-criada na lista.

## <a name="manage-your-measures"></a>Gerenciar suas medidas

Depois de [criar uma medida](#create-a-measure), você verá uma lista de medidas na página **Medidas**.

Você encontrará informações sobre o tipo de medida, o criador, a data de criação, o status e o estado. Ao selecionar uma medida da lista, você pode exibir a saída e baixar um arquivo .CSV.

Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.

> [!div class="mx-imgBorder"]
> ![Ações para gerenciar medidas únicas](media/measure-actions.png "Ações para gerenciar medidas únicas")

Selecione uma medida da lista para as seguintes opções:

- Selecione o nome da medida para ver seus detalhes.
- **Edite** a configuração da medida.
- **Atualize** a medida com base nos dados mais recentes.
- **Renomeie** a medida.
- **Exclua** a medida.
- **Ative** ou **Desative**. Medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="next-step"></a>Próxima etapa

Você pode usar as medidas existentes para criar [um segmento de cliente](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]