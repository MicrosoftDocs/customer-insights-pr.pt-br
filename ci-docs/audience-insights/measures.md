---
title: Criar e gerenciar medidas
description: Defina medidas para analisar e refletir o desempenho da sua empresa.
ms.date: 09/30/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 39acca78c022bc15ebc15dc80f21fe175da04d4d
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622845"
---
# <a name="define-and-manage-measures"></a>Definir e gerenciar medidas

As medidas ajudam você a entender melhor os comportamentos dos clientes e o desempenho dos negócios. Elas analisam para valores relevantes de [perfis unificados](data-unification.md). Por exemplo, uma empresa deseja ver o *gasto total por cliente* para entender o histórico ou a medida de um cliente específico ou medir as *vendas totais da empresa* para entender a receita de nível agregado em toda a empresa.  

As medidas são criadas por meio do construtor de medidas, uma plataforma de consulta de dados com vários operadores e opções de mapeamento simples. Ele permite filtrar dados, agrupar resultados, detectar [caminhos de relacionamento de entidades](relationships.md) e exibir a saída.

Use o construtor de medidas para extrair insights e planejar atividades comerciais por meio da consulta de dados do cliente. Por exemplo, criar uma medida de *gasto total por cliente* e *retorno total por cliente* ajuda a identificar um grupo de clientes com alto gasto, mas alto retorno. É possível [criar um segmento](segments.md) para realizar as próximas ações recomendadas. 

## <a name="build-your-own-measure-from-scratch"></a>Criar sua própria medida do zero

Esta seção explica como criar uma medida do zero. Você pode construir uma medida com atributos de dados de entidades de dados que tenham um relacionamento estabelecido para se conectar com a entidade unificada de perfil de cliente.

# <a name="individual-customers-b2c"></a>[Consumidores individuais (B2C)](#tab/b2c)

1. Nos insights de público-alvo, vá para **Medidas**.

1. Selecione **Novo** e escolha **Crie sua própria**.

1. Selecione **Editar nome** e forneça um **Nome** para a medida. 

1. Na área de configuração, escolha a função de agregação no menu suspenso **Selecionar função**. As funções de agregação incluem: 
   - **Somar**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máximo**
   - **Mínimo**
   - **Primeiro**: usa o primeiro valor do registro de dados
   - **Último**: pega o último valor que foi adicionado ao registro de dados

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.
   
   1. Selecione a guia **Atributos**. 
   1. Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir. 
   1. Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida. Você só pode selecionar um atributo por vez.
   1. Você também pode selecionar um atributo de dados de uma medida existente selecionando a guia **Medidas** ou você pode pesquisar um nome de entidade ou medida. 
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecione um atributo para usar nos cálculos.":::

1. Para criar medidas mais complexas, você pode adicionar mais atributos ou usar operadores matemáticos em sua função de medida.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crie uma medida complexa com operadores matemáticos.":::

1. Para adicionar filtros, selecione **Filtro** na área de configuração. 
  
   1. Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo de lote que você deseja usar para criar filtros.
   1. Configure os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Para adicionar dimensões, selecione **Dimensão** na área de configuração. As dimensões serão mostradas como colunas na entidade de saída da medida.
 
   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida. Por exemplo, cidade ou sexo. Por padrão, a dimensão *CustomerID* é selecionada para criar *medidas em nível de cliente*. Você pode remover a dimensão padrão se quiser criar *medidas em nível de negócios*.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores em seus dados que você precisa substituir por um número inteiro, selecione **Regras**. Configure a regra e escolha apenas números inteiros como substituições. Por exemplo, substitua *nulo* por *0*.

1. Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade *Cliente*, você deverá escolher um dos [caminhos de relacionamento de entidade](relationships.md) identificados. Os resultados da medição podem variar dependendo do caminho selecionado. 
   
   1. Selecione **Caminho de relacionamento** e escolha o caminho da entidade que deve ser usado para identificar sua medida. Se houver somente um único caminho para a entidade *Cliente*, este controle não será exibido.
   1. Selecione **Concluído** para aplicar sua seleção. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecione o caminho da entidade para a medida.":::

1. Para adicionar mais cálculos para a medida, selecione **Novo cálculo**. Você só pode usar entidades no mesmo caminho de entidade para novos cálculos. Mais cálculos serão exibidos como novas colunas na entidade de saída de medida.

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A versão preliminar reage dinamicamente às mudanças na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde.

1. Acesse **Medidas** para ver a medida recém-criada na lista.

# <a name="business-accounts-b2b"></a>[Contas comerciais (B2B)](#tab/b2b)

1. Nos insights de público-alvo, vá para **Medidas**.

1. Selecione **Novo** e escolha **Crie sua própria**.

1. Selecione **Editar nome** e forneça um **Nome** para a medida. 

1. Na área de configuração, escolha a função de agregação no menu suspenso **Selecionar função**. As funções de agregação incluem: 
   - **Somar**
   - **Média**
   - **Contagem**
   - **Contagem Exclusiva**
   - **Máximo**
   - **Mínimo**
   - **Primeiro**: usa o primeiro valor do registro de dados
   - **Último**: pega o último valor que foi adicionado ao registro de dados

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.
   
   1. Selecione a guia **Atributos**. 
   1. Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir. 
   1. Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida. Você só pode selecionar um atributo por vez.
   1. Você também pode selecionar um atributo de dados de uma medida existente selecionando a guia **Medidas** ou você pode pesquisar um nome de entidade ou medida. 
   1. Selecione **Adicionar** para adicionar o atributo selecionado à medida.

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecione um atributo para usar nos cálculos.":::

1. Para criar medidas mais complexas, você pode adicionar mais atributos ou usar operadores matemáticos em sua função de medida.

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crie uma medida complexa com operadores matemáticos.":::

1. Para adicionar filtros, selecione **Filtro** na área de configuração. 
  
   1. Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo de lote que você deseja usar para criar filtros.
   1. Configure os operadores de filtro para definir o filtro para cada atributo selecionado.
   1. Selecione **Aplicar** para adicionar os filtros à medida.

1. Para adicionar dimensões, selecione **Dimensão** na área de configuração. As dimensões serão mostradas como colunas na entidade de saída da medida.
 
   1. Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida. Por exemplo, cidade ou sexo. Por padrão, a dimensão *CustomerID* é selecionada para criar *medidas em nível de cliente*. Você pode remover a dimensão padrão se quiser criar *medidas em nível de negócios*.
   1. Selecione **Concluído** para adicionar as dimensões à medida.

1. Se houver valores em seus dados que você precisa substituir por um número inteiro, selecione **Regras**. Configure a regra e escolha apenas números inteiros como substituições. Por exemplo, substitua *nulo* por *0*.

1. Você pode usar o alternador **Agrupar subcontas** se você [usar contas com hierarquias](relationships.md#set-up-account-hierarchies).
   - Se estiver definido como **Desligado**, a medida é calculada para cada conta. Cada conta obtém seu próprio resultado.
   - Se estiver definido como **Ligado**, selecione **Editar** para escolher a hierarquia da conta de acordo com as hierarquias ingeridas. A medida produzirá apenas um resultado porque está agregada a subcontas.

1. Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade *Cliente*, você deverá escolher um dos [caminhos de relacionamento de entidade](relationships.md) identificados. Os resultados da medição podem variar dependendo do caminho selecionado. 
   
   1. Selecione **Caminho de relacionamento** e escolha o caminho da entidade que deve ser usado para identificar sua medida. Se houver somente um único caminho para a entidade *Cliente*, este controle não será exibido.
   1. Selecione **Concluído** para aplicar sua seleção. 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecione o caminho da entidade para a medida.":::

1. Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.

1. Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões. A versão preliminar reage dinamicamente às mudanças na configuração.

1. Selecione **Executar** para calcular os resultados da medida configurada. Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde.

1. Acesse **Medidas** para ver a medida recém-criada na lista.

---

## <a name="use-a-template-to-build-a-measure"></a>Usar um modelo para criar uma medida

Você pode usar modelos predefinidos de medidas comumente usadas para criá-las. Descrições detalhadas dos modelos e uma experiência guiada ajudam na criação de medidas eficientes. Os modelos se baseiam em dados mapeados da entidade *Atividade Unificada*. Portanto, verifique se você configurou as [atividades de clientes](activities.md) antes de criar uma medida com base em um modelo.

# <a name="individual-customers-b2c"></a>[Consumidores individuais (B2C)](#tab/b2c)

Você pode usar modelos predefinidos de medidas comumente usadas para criá-las. Descrições detalhadas dos modelos e uma experiência guiada ajudam na criação de medidas eficientes. Os modelos se baseiam em dados mapeados da entidade *Atividade Unificada*. Portanto, verifique se você configurou as [atividades de clientes](activities.md) antes de criar uma medida com base em um modelo.

Modelos de medidas disponíveis: 
- Valor médio da transação (ATV)
- Valor total da transação
- Receita média diária
- Receita média anual
- Contagem de transações
- Pontos de fidelidade ganhos
- Pontos de fidelidade resgatados
- Saldo de pontos de fidelidade
- Período ativo do cliente
- Duração da associação ao programa de fidelidade
- Tempo desde a última compra

O procedimento a seguir descreve as etapas para criar uma nova medida usando um modelo.

1. Nos insights de público-alvo, vá para **Medidas**.

1. Selecione **Novo** e, em seguida, selecione **Escolher um modelo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de tela do menu suspenso ao criar uma nova medida com destaque no modelo.":::

1. Encontre o modelo que se adapta às suas necessidades e selecione **Escolher modelo**.

1. Revise os dados necessários e selecione **Começar** se você tiver todos os dados no local.

1. No painel **Editar nome**, defina o nome da sua medida e a entidade de saída. 

1. Selecione **Concluído**.

1. Na seção **Definir período**, defina o período dos dados a serem usados. Para escolher se você deseja que a nova medida aborde todo o conjunto de dados, selecione **O tempo todo**, ou que a medida se concentre em um **Período específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de tela mostrando a seção do período ao configurar uma medida com base em um modelo.":::

1. Na próxima seção, selecione **Adicionar dados** para escolher as atividades e mapear os dados correspondentes da sua entidade *Atividade Unificada*.

    1. Etapa 1 de 2: em **Tipo de atividade**, escolha o tipo da entidade que deseja usar. Para **Atividades**, selecione as entidades que deseja mapear.
    1. Etapa 2 de 2: escolha o atributo da entidade *Atividade Unificada* do componente exigido pela fórmula. Por exemplo, para Valor médio da transação, é o atributo que representa o Valor da transação. Para **Carimbo de data/hora da atividade**, escolha o atributo da entidade Atividade Unificada que representa a data e hora da atividade.
   
1. Depois que o mapeamento de dados for bem-sucedido, você poderá ver o status como **Concluído** e o nome das atividades e atributos mapeados.

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de tela de uma configuração de modelo de medida concluída.":::

1. Agora você pode selecionar **Executar** para calcular os resultados da medida. Para refiná-los mais tarde, selecione **Salvar rascunho**.

# <a name="business-accounts-b2b"></a>[Contas comerciais (B2B)](#tab/b2b)

Este recurso está disponível apenas para medidas criadas em ambientes com clientes individuais como público-alvo primário.

---

## <a name="manage-your-measures"></a>Gerenciar suas medidas

Você pode encontrar a lista de medidas na página **Medidas**.

Você encontrará informações sobre o tipo de medida, o criador, a data de criação, o status e o estado. Ao selecionar uma nova medida, na lista, você pode visualizar a saída e baixar um arquivo CSV.

Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.

> [!div class="mx-imgBorder"]
> ![Ações para gerenciar medidas únicas.](media/measure-actions.png "Ações para gerenciar medidas únicas.")

Selecione uma medida da lista para as seguintes opções:

- Selecione o nome da medida para ver seus detalhes.
- **Edite** a configuração da medida.
- **Atualize** a medida com base nos dados mais recentes.
- **Renomeie** a medida.
- **Exclua** a medida.
- **Ative** ou **Desative**. Medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Após selecionar **Ver detalhes** para uma ou mais tarefas do trabalho, você encontrará informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados com a tarefa.

## <a name="next-step"></a>Próxima etapa

Você pode usar medidas existentes para criar [um segmento de cliente](segments.md).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
