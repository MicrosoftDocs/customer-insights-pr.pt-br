---
title: Criar e gerenciar medidas
description: Defina medidas para analisar e refletir o desempenho da sua empresa.
ms.date: 02/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 202ea22d290be04e54ce9676b6b693162354607f
ms.sourcegitcommit: d3eb07dcc72624a2d5cfc95c7ea9faaa2c1b6001
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/16/2021
ms.locfileid: "5654718"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="1ef17-103">Definir e gerenciar medidas</span><span class="sxs-lookup"><span data-stu-id="1ef17-103">Define and manage measures</span></span>

<span data-ttu-id="1ef17-104">As medidas ajudam você a entender melhor os comportamentos dos clientes e o desempenho da empresa, recuperando valores relevantes de [perfis unificados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="1ef17-104">Measures help you to better understand customer behaviors and business performance by retrieving relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="1ef17-105">Por exemplo, uma empresa deseja ver o *gasto total por cliente* para entender o histórico de compras de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="1ef17-105">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history.</span></span> <span data-ttu-id="1ef17-106">Ou meça *vendas totais da empresa* para compreender a receita em nível agregado de toda a empresa.</span><span class="sxs-lookup"><span data-stu-id="1ef17-106">Or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="1ef17-107">As medidas são criadas por meio do construtor de medidas, uma plataforma de consulta de dados com vários operadores e opções de mapeamento simples.</span><span class="sxs-lookup"><span data-stu-id="1ef17-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="1ef17-108">Ele permite filtrar dados, agrupar resultados, detectar [caminhos de relacionamento de entidades](relationships.md) e exibir a saída.</span><span class="sxs-lookup"><span data-stu-id="1ef17-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="1ef17-109">Use o construtor de medidas para extrair insights e planejar atividades comerciais por meio da consulta de dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="1ef17-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="1ef17-110">Por exemplo, criar uma medida de *gasto total por cliente* e *retorno total por cliente* ajuda a identificar um grupo de clientes com alto gasto, mas alto retorno.</span><span class="sxs-lookup"><span data-stu-id="1ef17-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="1ef17-111">É possível [criar um segmento](segments.md) para realizar as próximas ações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="1ef17-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="create-a-measure"></a><span data-ttu-id="1ef17-112">Criar uma medida</span><span class="sxs-lookup"><span data-stu-id="1ef17-112">Create a measure</span></span>

<span data-ttu-id="1ef17-113">Esta seção explica como criar uma medida do zero.</span><span class="sxs-lookup"><span data-stu-id="1ef17-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="1ef17-114">Você pode criar uma medida com atributos de dados de entidades de dados que têm um relacionamento configurado para se conectar com a entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="1ef17-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="1ef17-115">Nos insights de público-alvo, vá para **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="1ef17-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="1ef17-116">Selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="1ef17-116">Select **New**.</span></span>

1. <span data-ttu-id="1ef17-117">Selecione **Editar nome** e forneça um **Nome** para a medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="1ef17-118">Se sua nova configuração de medida tiver apenas dois campos (por exemplo, CustomerID) e um cálculo, a saída será adicionada como uma nova coluna à entidade gerada pelo sistema chamada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="1ef17-118">If your new measure configuration has only two fields, for exmample, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="1ef17-119">E você poderá ver o valor da medida no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="1ef17-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="1ef17-120">Outras medidas vão gerar suas próprias entidades.</span><span class="sxs-lookup"><span data-stu-id="1ef17-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="1ef17-121">Na área de configuração, escolha a função de agregação no menu suspenso **Selecionar função**.</span><span class="sxs-lookup"><span data-stu-id="1ef17-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="1ef17-122">As funções de agregação incluem:</span><span class="sxs-lookup"><span data-stu-id="1ef17-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="1ef17-123">**Somar**</span><span class="sxs-lookup"><span data-stu-id="1ef17-123">**Sum**</span></span>
   - <span data-ttu-id="1ef17-124">**Média**</span><span class="sxs-lookup"><span data-stu-id="1ef17-124">**Average**</span></span>
   - <span data-ttu-id="1ef17-125">**Contagem**</span><span class="sxs-lookup"><span data-stu-id="1ef17-125">**Count**</span></span>
   - <span data-ttu-id="1ef17-126">**Contagem Exclusiva**</span><span class="sxs-lookup"><span data-stu-id="1ef17-126">**Count Unique**</span></span>
   - <span data-ttu-id="1ef17-127">**Máx**</span><span class="sxs-lookup"><span data-stu-id="1ef17-127">**Max**</span></span>
   - <span data-ttu-id="1ef17-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="1ef17-128">**Min**</span></span>
   - <span data-ttu-id="1ef17-129">**Primeiro**: pega o primeiro valor do registro de dados</span><span class="sxs-lookup"><span data-stu-id="1ef17-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="1ef17-130">**Último**: pega o último valor que foi adicionado ao registro de dados</span><span class="sxs-lookup"><span data-stu-id="1ef17-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. <span data-ttu-id="1ef17-132">Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="1ef17-133">Selecione a guia **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="1ef17-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="1ef17-134">Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir.</span><span class="sxs-lookup"><span data-stu-id="1ef17-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="1ef17-135">Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="1ef17-136">Você só pode selecionar um atributo por vez.</span><span class="sxs-lookup"><span data-stu-id="1ef17-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="1ef17-137">Você também pode selecionar um atributo de dados de uma medida existente selecionando a guia **Medidas**. Ou você pode pesquisar um nome de entidade ou medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="1ef17-138">Selecione **Adicionar** para adicionar o atributo selecionado à medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecione um atributo para usar nos cálculos.":::

1. <span data-ttu-id="1ef17-140">Para criar medidas mais complexas, você pode adicionar mais atributos ou usar operadores matemáticos em sua função de medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crie uma medida complexa com operadores matemáticos.":::

1. <span data-ttu-id="1ef17-142">Para adicionar filtros, selecione **Filtro** na área de configuração.</span><span class="sxs-lookup"><span data-stu-id="1ef17-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="1ef17-143">Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo que deseja usar para criar filtros.</span><span class="sxs-lookup"><span data-stu-id="1ef17-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="1ef17-144">Configure os operadores de filtro para definir o filtro para cada atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="1ef17-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="1ef17-145">Selecione **Aplicar** para adicionar os filtros à medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="1ef17-146">Para adicionar dimensões, selecione **Dimensão** na área de configuração.</span><span class="sxs-lookup"><span data-stu-id="1ef17-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="1ef17-147">As dimensões serão mostradas como colunas na entidade de saída da medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="1ef17-148">Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="1ef17-149">Por exemplo, cidade ou sexo.</span><span class="sxs-lookup"><span data-stu-id="1ef17-149">For example, city or gender.</span></span> <span data-ttu-id="1ef17-150">Por padrão, a dimensão *CustomerID* é selecionada para criar *medidas em nível de cliente*.</span><span class="sxs-lookup"><span data-stu-id="1ef17-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="1ef17-151">Você pode remover a dimensão padrão se quiser criar *medidas em nível de negócios*.</span><span class="sxs-lookup"><span data-stu-id="1ef17-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="1ef17-152">Selecione **Concluído** para adicionar as dimensões à medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="1ef17-153">Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade *Cliente*, você deverá escolher um dos [caminhos de relacionamento de entidade](relationships.md) identificados.</span><span class="sxs-lookup"><span data-stu-id="1ef17-153">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="1ef17-154">Os resultados da medição podem variar dependendo do caminho selecionado.</span><span class="sxs-lookup"><span data-stu-id="1ef17-154">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="1ef17-155">Selecione **Preferências de dados** e escolha o caminho da entidade que deve ser usado para identificar sua medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-155">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="1ef17-156">Se houver somente um único caminho para a entidade *Cliente*, este controle não será exibido.</span><span class="sxs-lookup"><span data-stu-id="1ef17-156">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="1ef17-157">Selecione **Concluído** para aplicar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="1ef17-157">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecione o caminho da entidade para a medida.":::

1. <span data-ttu-id="1ef17-159">Para adicionar mais cálculos para a medida, selecione **Novo cálculo**.</span><span class="sxs-lookup"><span data-stu-id="1ef17-159">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="1ef17-160">Você só pode usar entidades no mesmo caminho de entidade para novos cálculos.</span><span class="sxs-lookup"><span data-stu-id="1ef17-160">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="1ef17-161">Mais cálculos serão exibidos como novas colunas na entidade de saída de medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-161">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="1ef17-162">Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-162">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="1ef17-163">Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões.</span><span class="sxs-lookup"><span data-stu-id="1ef17-163">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="1ef17-164">A versão preliminar reage dinamicamente às mudanças na configuração.</span><span class="sxs-lookup"><span data-stu-id="1ef17-164">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="1ef17-165">Selecione **Executar** para calcular os resultados da medida configurada.</span><span class="sxs-lookup"><span data-stu-id="1ef17-165">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="1ef17-166">Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde.</span><span class="sxs-lookup"><span data-stu-id="1ef17-166">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="1ef17-167">Acesse **Medidas** para ver a medida recém-criada na lista.</span><span class="sxs-lookup"><span data-stu-id="1ef17-167">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="1ef17-168">Gerenciar suas medidas</span><span class="sxs-lookup"><span data-stu-id="1ef17-168">Manage your measures</span></span>

<span data-ttu-id="1ef17-169">Depois de [criar uma medida](#create-a-measure), você verá uma lista de medidas na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="1ef17-169">After [creating a measure](#create-a-measure), you see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="1ef17-170">Você encontrará informações sobre o tipo de medida, o criador, a data de criação, o status e o estado.</span><span class="sxs-lookup"><span data-stu-id="1ef17-170">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="1ef17-171">Ao selecionar uma medida da lista, você pode exibir a saída e baixar um arquivo .CSV.</span><span class="sxs-lookup"><span data-stu-id="1ef17-171">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="1ef17-172">Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.</span><span class="sxs-lookup"><span data-stu-id="1ef17-172">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="1ef17-173">![Ações para gerenciar medidas únicas](media/measure-actions.png "Ações para gerenciar medidas únicas")</span><span class="sxs-lookup"><span data-stu-id="1ef17-173">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="1ef17-174">Selecione uma medida da lista para as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="1ef17-174">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="1ef17-175">Selecione o nome da medida para ver seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="1ef17-175">Select the measure name to see its details.</span></span>
- <span data-ttu-id="1ef17-176">**Edite** a configuração da medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-176">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="1ef17-177">**Atualize** a medida com base nos dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="1ef17-177">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="1ef17-178">**Renomeie** a medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-178">**Rename** the measure.</span></span>
- <span data-ttu-id="1ef17-179">**Exclua** a medida.</span><span class="sxs-lookup"><span data-stu-id="1ef17-179">**Delete** the measure.</span></span>
- <span data-ttu-id="1ef17-180">**Ative** ou **Desative**.</span><span class="sxs-lookup"><span data-stu-id="1ef17-180">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="1ef17-181">Medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1ef17-181">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="1ef17-182">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="1ef17-182">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="1ef17-183">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="1ef17-183">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="1ef17-184">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="1ef17-184">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="1ef17-185">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="1ef17-185">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="1ef17-186">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="1ef17-186">Next step</span></span>

<span data-ttu-id="1ef17-187">Você pode usar as medidas existentes para criar [um segmento de cliente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="1ef17-187">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]