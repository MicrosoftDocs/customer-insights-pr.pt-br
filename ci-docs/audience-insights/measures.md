---
title: Criar e gerenciar medidas
description: Defina medidas para analisar e refletir o desempenho da sua empresa.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wameng
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 402e5ef3515bce0e6f56788781b7bd909738aaa6
ms.sourcegitcommit: b833e333745d321edeaf96d3ed14458cbce02ff1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049236"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="91fdf-103">Definir e gerenciar medidas</span><span class="sxs-lookup"><span data-stu-id="91fdf-103">Define and manage measures</span></span>

<span data-ttu-id="91fdf-104">As medidas ajudam você a entender melhor os comportamentos dos clientes e o desempenho dos negócios.</span><span class="sxs-lookup"><span data-stu-id="91fdf-104">Measures help you to better understand customer behaviors and business performance.</span></span> <span data-ttu-id="91fdf-105">Elas analisam para valores relevantes de [perfis unificados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="91fdf-105">They look at relevant values from [unified profiles](data-unification.md).</span></span> <span data-ttu-id="91fdf-106">Por exemplo, uma empresa deseja ver o *total de gastos por cliente* para entender o histórico de compras do cliente individual ou medir o *total de vendas da empresa* para entender a receita de nível agregado em todo o negócio.</span><span class="sxs-lookup"><span data-stu-id="91fdf-106">For example, a business wants to see the *total spend per customer* to understand individual customer’s purchase history or measure *total sales of the company* to understand the aggregate-level revenue in the whole business.</span></span>  

<span data-ttu-id="91fdf-107">As medidas são criadas por meio do construtor de medidas, uma plataforma de consulta de dados com vários operadores e opções de mapeamento simples.</span><span class="sxs-lookup"><span data-stu-id="91fdf-107">Measures are created using the measure builder, a data query platform with various operators and simple mapping options.</span></span> <span data-ttu-id="91fdf-108">Ele permite filtrar dados, agrupar resultados, detectar [caminhos de relacionamento de entidades](relationships.md) e exibir a saída.</span><span class="sxs-lookup"><span data-stu-id="91fdf-108">It lets you filter the data, group results, detect [entity relationship paths](relationships.md), and preview the output.</span></span>

<span data-ttu-id="91fdf-109">Use o construtor de medidas para extrair insights e planejar atividades comerciais por meio da consulta de dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="91fdf-109">Use the measure builder to plan business activities by querying customer data and extract insights.</span></span> <span data-ttu-id="91fdf-110">Por exemplo, criar uma medida de *gasto total por cliente* e *retorno total por cliente* ajuda a identificar um grupo de clientes com alto gasto, mas alto retorno.</span><span class="sxs-lookup"><span data-stu-id="91fdf-110">For example, creating a measure of *total spend per customer* and *total return per customer* helps identify a group of customers with high spend yet high return.</span></span> <span data-ttu-id="91fdf-111">É possível [criar um segmento](segments.md) para realizar as próximas ações recomendadas.</span><span class="sxs-lookup"><span data-stu-id="91fdf-111">You can [create a segment](segments.md) to drive next best actions.</span></span> 

## <a name="build-your-own-measure-from-scratch"></a><span data-ttu-id="91fdf-112">Criar sua própria medida do zero</span><span class="sxs-lookup"><span data-stu-id="91fdf-112">Build your own measure from scratch</span></span>

<span data-ttu-id="91fdf-113">Esta seção explica como criar uma medida do zero.</span><span class="sxs-lookup"><span data-stu-id="91fdf-113">This section walks you through creating a new measure from scratch.</span></span> <span data-ttu-id="91fdf-114">Você pode criar uma medida com atributos de dados de entidades de dados que têm um relacionamento configurado para se conectar com a entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="91fdf-114">You can build a measure with data attributes from data entities that have a relationship set up to connect with the Customer entity.</span></span> 

1. <span data-ttu-id="91fdf-115">Nos insights de público-alvo, vá para **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-115">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="91fdf-116">Selecione **Novo** e escolha **Crie sua própria**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-116">Select **New** and choose **Build your own**.</span></span>

1. <span data-ttu-id="91fdf-117">Selecione **Editar nome** e forneça um **Nome** para a medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-117">Select **Edit name** and provide a **Name** for the measure.</span></span> 
   > [!NOTE]
   > <span data-ttu-id="91fdf-118">Se a nova configuração de medida tiver somente dois campos, por exemplo, CustomerID e um cálculo, a saída será adicionada como uma nova coluna à entidade gerada pelo sistema chamada Customer_Measure.</span><span class="sxs-lookup"><span data-stu-id="91fdf-118">If your new measure configuration has only two fields, for example, CustomerID and one calculation, the output will be added as a new column to the system generated entity called Customer_Measure.</span></span> <span data-ttu-id="91fdf-119">E você poderá ver o valor da medida no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="91fdf-119">And you will be able to see the measure’s value in the unified customer profile.</span></span> <span data-ttu-id="91fdf-120">Outras medidas vão gerar suas próprias entidades.</span><span class="sxs-lookup"><span data-stu-id="91fdf-120">Other measures will generate their own entities.</span></span>

1. <span data-ttu-id="91fdf-121">Na área de configuração, escolha a função de agregação no menu suspenso **Selecionar função**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-121">In the configuration area, choose the aggregation function from the **Select Function** drop-down menu.</span></span> <span data-ttu-id="91fdf-122">As funções de agregação incluem:</span><span class="sxs-lookup"><span data-stu-id="91fdf-122">Aggregation functions include:</span></span> 
   - <span data-ttu-id="91fdf-123">**Somar**</span><span class="sxs-lookup"><span data-stu-id="91fdf-123">**Sum**</span></span>
   - <span data-ttu-id="91fdf-124">**Média**</span><span class="sxs-lookup"><span data-stu-id="91fdf-124">**Average**</span></span>
   - <span data-ttu-id="91fdf-125">**Contagem**</span><span class="sxs-lookup"><span data-stu-id="91fdf-125">**Count**</span></span>
   - <span data-ttu-id="91fdf-126">**Contagem Exclusiva**</span><span class="sxs-lookup"><span data-stu-id="91fdf-126">**Count Unique**</span></span>
   - <span data-ttu-id="91fdf-127">**Máx**</span><span class="sxs-lookup"><span data-stu-id="91fdf-127">**Max**</span></span>
   - <span data-ttu-id="91fdf-128">**Min**</span><span class="sxs-lookup"><span data-stu-id="91fdf-128">**Min**</span></span>
   - <span data-ttu-id="91fdf-129">**Primeiro**: pega o primeiro valor do registro de dados</span><span class="sxs-lookup"><span data-stu-id="91fdf-129">**First**: takes the first value of the data record</span></span>
   - <span data-ttu-id="91fdf-130">**Último**: pega o último valor que foi adicionado ao registro de dados</span><span class="sxs-lookup"><span data-stu-id="91fdf-130">**Last**: takes the last value that was added to the data record</span></span>

   :::image type="content" source="media/measure-operators.png" alt-text="Operadores para cálculos de medidas.":::

1. <span data-ttu-id="91fdf-132">Selecione **Adicionar atributo** para selecionar os dados necessários para criar esta medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-132">Select **Add attribute** to select the data you need to create this measure.</span></span>
   
   1. <span data-ttu-id="91fdf-133">Selecione a guia **Atributos**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-133">Select the **Attributes** tab.</span></span> 
   1. <span data-ttu-id="91fdf-134">Entidade de dados: escolha a entidade que inclui o atributo que você deseja medir.</span><span class="sxs-lookup"><span data-stu-id="91fdf-134">Data entity: Choose the entity that includes the attribute you want to measure.</span></span> 
   1. <span data-ttu-id="91fdf-135">Atributo de dados: escolha o atributo que deseja usar na função de agregação para calcular a medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-135">Data attribute: Choose the attribute you want to use in the aggregation function to calculate the measure.</span></span> <span data-ttu-id="91fdf-136">Você só pode selecionar um atributo por vez.</span><span class="sxs-lookup"><span data-stu-id="91fdf-136">You can only select one attribute at a time.</span></span>
   1. <span data-ttu-id="91fdf-137">Você também pode selecionar um atributo de dados de uma medida existente selecionando a guia **Medidas**. Ou você pode pesquisar um nome de entidade ou medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-137">You can also select a data attribute from an existing measure by selecting the **Measures** tab. Or, you can search for an entity or measure name.</span></span> 
   1. <span data-ttu-id="91fdf-138">Selecione **Adicionar** para adicionar o atributo selecionado à medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-138">Select **Add** to add the selected attribute to the measure.</span></span>

   :::image type="content" source="media/measure-attribute-selection.png" alt-text="Selecione um atributo para usar nos cálculos.":::

1. <span data-ttu-id="91fdf-140">Para criar medidas mais complexas, você pode adicionar mais atributos ou usar operadores matemáticos em sua função de medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-140">To build more complex measures, you can add more attributes or use math operators on your measure function.</span></span>

   :::image type="content" source="media/measure-math-operators.png" alt-text="Crie uma medida complexa com operadores matemáticos.":::

1. <span data-ttu-id="91fdf-142">Para adicionar filtros, selecione **Filtro** na área de configuração.</span><span class="sxs-lookup"><span data-stu-id="91fdf-142">To add filters, select the **Filter** in the configuration area.</span></span> 
  
   1. <span data-ttu-id="91fdf-143">Na seção **Adicionar atributo** do painel **Filtros**, selecione o atributo que deseja usar para criar filtros.</span><span class="sxs-lookup"><span data-stu-id="91fdf-143">In **Add attribute** section of the **Filters** pane, select the attribute you want to use to create filters.</span></span>
   1. <span data-ttu-id="91fdf-144">Configure os operadores de filtro para definir o filtro para cada atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="91fdf-144">Set the filter operators to define the filter for every selected attribute.</span></span>
   1. <span data-ttu-id="91fdf-145">Selecione **Aplicar** para adicionar os filtros à medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-145">Select **Apply** to add the filters to the measure.</span></span>

1. <span data-ttu-id="91fdf-146">Para adicionar dimensões, selecione **Dimensão** na área de configuração.</span><span class="sxs-lookup"><span data-stu-id="91fdf-146">To add dimensions, select **Dimension** in the configuration area.</span></span> <span data-ttu-id="91fdf-147">As dimensões serão mostradas como colunas na entidade de saída da medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-147">Dimensions will show as columns in the measure output entity.</span></span>
   1. <span data-ttu-id="91fdf-148">Selecione **Editar dimensões** para adicionar atributos de dados pelos quais você deseja agrupar os valores de medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-148">Select **Edit dimensions** to add data attributes you want to group the measure values by.</span></span> <span data-ttu-id="91fdf-149">Por exemplo, cidade ou sexo.</span><span class="sxs-lookup"><span data-stu-id="91fdf-149">For example, city or gender.</span></span> <span data-ttu-id="91fdf-150">Por padrão, a dimensão *CustomerID* é selecionada para criar *medidas em nível de cliente*.</span><span class="sxs-lookup"><span data-stu-id="91fdf-150">By default, the *CustomerID* dimension is selected to create *customer-level measures*.</span></span> <span data-ttu-id="91fdf-151">Você pode remover a dimensão padrão se quiser criar *medidas em nível de negócios*.</span><span class="sxs-lookup"><span data-stu-id="91fdf-151">You can remove the default dimension if you want to create *business-level measures*.</span></span>
   1. <span data-ttu-id="91fdf-152">Selecione **Concluído** para adicionar as dimensões à medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-152">Select **Done** to add the dimensions to the measure.</span></span>

1. <span data-ttu-id="91fdf-153">Se houver valores nos seus dados que precisem ser substituídos por um número inteiro, por exemplo, substitua *nulo* por *0* e selecione **Regras**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-153">If there are values in your data that you need to replace with an integer, for example, replace *null* with *0*, select **Rules**.</span></span> <span data-ttu-id="91fdf-154">Configure a regra e escolha apenas números inteiros como substituições.</span><span class="sxs-lookup"><span data-stu-id="91fdf-154">Configure the rule and make sure that you choose only whole numbers as replacements.</span></span>

1. <span data-ttu-id="91fdf-155">Se houver vários caminhos entre a entidade de dados que você mapeou e a entidade *Cliente*, você deverá escolher um dos [caminhos de relacionamento de entidade](relationships.md) identificados.</span><span class="sxs-lookup"><span data-stu-id="91fdf-155">If there are multiple paths between the data entity you mapped and the *Customer* entity, you have to choose one of the identified [entity relationship paths](relationships.md).</span></span> <span data-ttu-id="91fdf-156">Os resultados da medição podem variar dependendo do caminho selecionado.</span><span class="sxs-lookup"><span data-stu-id="91fdf-156">Measure results can vary depending on the selected path.</span></span> 
   1. <span data-ttu-id="91fdf-157">Selecione **Preferências de dados** e escolha o caminho da entidade que deve ser usado para identificar sua medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-157">Select **Data preferences** and choose the entity path that should be used to identify your measure.</span></span> <span data-ttu-id="91fdf-158">Se houver somente um único caminho para a entidade *Cliente*, este controle não será exibido.</span><span class="sxs-lookup"><span data-stu-id="91fdf-158">If there's only a single path to the *Customer* entity, this control won't show.</span></span>
   1. <span data-ttu-id="91fdf-159">Selecione **Concluído** para aplicar sua seleção.</span><span class="sxs-lookup"><span data-stu-id="91fdf-159">Select **Done** to apply your selection.</span></span> 

   :::image type="content" source="media/measures-data-preferences.png" alt-text="Selecione o caminho da entidade para a medida.":::

1. <span data-ttu-id="91fdf-161">Para adicionar mais cálculos para a medida, selecione **Novo cálculo**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-161">To add more calculations for the measure, select **New calculation**.</span></span> <span data-ttu-id="91fdf-162">Você só pode usar entidades no mesmo caminho de entidade para novos cálculos.</span><span class="sxs-lookup"><span data-stu-id="91fdf-162">You can only use entities on the same entity path for new calculations.</span></span> <span data-ttu-id="91fdf-163">Mais cálculos serão exibidos como novas colunas na entidade de saída de medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-163">More calculations will show as new columns in the measure output entity.</span></span>

1. <span data-ttu-id="91fdf-164">Selecione **...** no cálculo para **Duplicar**, **Renomear** ou **Remover** um cálculo de uma medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-164">Select **...** on the calculation to **Duplicate**, **Rename**, or **Remove** a calculation from a measure.</span></span>

1. <span data-ttu-id="91fdf-165">Na área **Versão preliminar**, você verá o esquema de dados da entidade de saída da medida, incluindo filtros e dimensões.</span><span class="sxs-lookup"><span data-stu-id="91fdf-165">In the **Preview** area, you'll see the data schema of the measure output entity, including filters and dimensions.</span></span> <span data-ttu-id="91fdf-166">A versão preliminar reage dinamicamente às mudanças na configuração.</span><span class="sxs-lookup"><span data-stu-id="91fdf-166">The preview reacts dynamically to changes in the configuration.</span></span>

1. <span data-ttu-id="91fdf-167">Selecione **Executar** para calcular os resultados da medida configurada.</span><span class="sxs-lookup"><span data-stu-id="91fdf-167">Select **Run** to calculate results for the configured measure.</span></span> <span data-ttu-id="91fdf-168">Selecione **Salvar e fechar** se você deseja manter a configuração atual e executar a medida mais tarde.</span><span class="sxs-lookup"><span data-stu-id="91fdf-168">Select **Save and close** if you want to keep the current configuration and run the measure later.</span></span>

1. <span data-ttu-id="91fdf-169">Acesse **Medidas** para ver a medida recém-criada na lista.</span><span class="sxs-lookup"><span data-stu-id="91fdf-169">Go to **Measures** to see the newly created measure in the list.</span></span>

## <a name="use-a-template-to-build-a-measure"></a><span data-ttu-id="91fdf-170">Usar um modelo para criar uma medida</span><span class="sxs-lookup"><span data-stu-id="91fdf-170">Use a template to build a measure</span></span>

<span data-ttu-id="91fdf-171">Você pode usar modelos predefinidos de medidas comumente usadas para criá-las.</span><span class="sxs-lookup"><span data-stu-id="91fdf-171">You can use predefined templates of commonly used measures to create them.</span></span> <span data-ttu-id="91fdf-172">Descrições detalhadas dos modelos e uma experiência guiada ajudam na criação de medidas eficientes.</span><span class="sxs-lookup"><span data-stu-id="91fdf-172">Detailed descriptions of the templates and a guided experience help you with efficient measure creation.</span></span> <span data-ttu-id="91fdf-173">Os modelos se baseiam em dados mapeados da entidade *Atividade Unificada*.</span><span class="sxs-lookup"><span data-stu-id="91fdf-173">Templates build on mapped data from the *Unified Activity* entity.</span></span> <span data-ttu-id="91fdf-174">Portanto, verifique se você configurou as [atividades de clientes](activities.md) antes de criar uma medida com base em um modelo.</span><span class="sxs-lookup"><span data-stu-id="91fdf-174">So make sure you have configured [customer activities](activities.md) before you create a measure from a template.</span></span>

<span data-ttu-id="91fdf-175">Modelos de medidas disponíveis:</span><span class="sxs-lookup"><span data-stu-id="91fdf-175">Available measure templates:</span></span> 
- <span data-ttu-id="91fdf-176">Valor médio da transação (ATV)</span><span class="sxs-lookup"><span data-stu-id="91fdf-176">Average transaction value (ATV)</span></span>
- <span data-ttu-id="91fdf-177">Valor total da transação</span><span class="sxs-lookup"><span data-stu-id="91fdf-177">Total transaction value</span></span>
- <span data-ttu-id="91fdf-178">Receita diária média</span><span class="sxs-lookup"><span data-stu-id="91fdf-178">Average daily revenue</span></span>
- <span data-ttu-id="91fdf-179">Receita média anual</span><span class="sxs-lookup"><span data-stu-id="91fdf-179">Average yearly revenue</span></span>
- <span data-ttu-id="91fdf-180">Contagem de transações</span><span class="sxs-lookup"><span data-stu-id="91fdf-180">Transaction count</span></span>
- <span data-ttu-id="91fdf-181">Pontos de fidelidade ganhos</span><span class="sxs-lookup"><span data-stu-id="91fdf-181">Loyalty points earned</span></span>
- <span data-ttu-id="91fdf-182">Pontos de fidelidade resgatados</span><span class="sxs-lookup"><span data-stu-id="91fdf-182">Loyalty points redeemed</span></span>
- <span data-ttu-id="91fdf-183">Saldo de pontos de fidelidade</span><span class="sxs-lookup"><span data-stu-id="91fdf-183">Loyalty points balance</span></span>
- <span data-ttu-id="91fdf-184">Período ativo do cliente</span><span class="sxs-lookup"><span data-stu-id="91fdf-184">Active customer lifespan</span></span>
- <span data-ttu-id="91fdf-185">Duração da associação ao programa de fidelidade</span><span class="sxs-lookup"><span data-stu-id="91fdf-185">Loyalty membership duration</span></span>
- <span data-ttu-id="91fdf-186">Tempo desde a última compra</span><span class="sxs-lookup"><span data-stu-id="91fdf-186">Time since last purchase</span></span>

<span data-ttu-id="91fdf-187">O procedimento a seguir descreve as etapas para criar uma nova medida usando um modelo.</span><span class="sxs-lookup"><span data-stu-id="91fdf-187">The following procedure outlines the steps to build a new measure using a template.</span></span>

1. <span data-ttu-id="91fdf-188">Nos insights de público-alvo, vá para **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-188">In audience insights, go to **Measures**.</span></span>

1. <span data-ttu-id="91fdf-189">Selecione **Novo** e, em seguida, selecione **Escolher um modelo**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-189">Select **New** and select **Choose a template**.</span></span>

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de tela do menu suspenso ao criar uma nova medida com destaque no modelo.":::

1. <span data-ttu-id="91fdf-191">Encontre o modelo que se adapta às suas necessidades e selecione **Escolher modelo**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-191">Find the template that fits your need and select **Choose template**.</span></span>

1. <span data-ttu-id="91fdf-192">Revise os dados necessários e selecione **Começar** se você tiver todos os dados no local.</span><span class="sxs-lookup"><span data-stu-id="91fdf-192">Review the required data and select **Get started** if you have all the data in place.</span></span>

1. <span data-ttu-id="91fdf-193">No painel **Editar nome**, defina o nome da sua medida e a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="91fdf-193">In the **Edit name** pane, set the name for your measure and the output entity.</span></span> 

1. <span data-ttu-id="91fdf-194">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-194">Select **Done**.</span></span>

1. <span data-ttu-id="91fdf-195">Na seção **Definir período**, defina o período dos dados a serem usados.</span><span class="sxs-lookup"><span data-stu-id="91fdf-195">In the **Set time period** section, define the time frame of the data to use.</span></span> <span data-ttu-id="91fdf-196">Escolha se você deseja que a nova medida cubra todo o conjunto de dados, selecionando **Todo o tempo**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-196">Choose if you want the new measure to cover the entire data set by selecting **All time**.</span></span> <span data-ttu-id="91fdf-197">Ou se você quiser que a medida se concentre em um **Período específico**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-197">Or if you want the measure to focus on a **Specific time period**.</span></span>

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de tela mostrando a seção do período ao configurar uma medida com base em um modelo.":::

1. <span data-ttu-id="91fdf-199">Na próxima seção, selecione **Adicionar dados** para escolher as atividades e mapear os dados correspondentes da sua entidade *Atividade Unificada*.</span><span class="sxs-lookup"><span data-stu-id="91fdf-199">In the next section, select **Add data** to choose the activities and map the corresponding data from your *Unified Activity* entity.</span></span>

    1. <span data-ttu-id="91fdf-200">Etapa 1 de 2: em **Tipo de atividade**, escolha o tipo da entidade que deseja usar.</span><span class="sxs-lookup"><span data-stu-id="91fdf-200">Step 1 of 2: Under **Activity type**, choose the type of the entity you want to use.</span></span> <span data-ttu-id="91fdf-201">Para **Atividades**, selecione as entidades que deseja mapear.</span><span class="sxs-lookup"><span data-stu-id="91fdf-201">For **Activities**, select the entities you want to map.</span></span>
    1. <span data-ttu-id="91fdf-202">Etapa 2 de 2: escolha o atributo da entidade *Atividade Unificada* do componente exigido pela fórmula.</span><span class="sxs-lookup"><span data-stu-id="91fdf-202">Step 2 of 2: Choose the attribute from the *Unified Activity* entity for the component required by the formula.</span></span> <span data-ttu-id="91fdf-203">Por exemplo, para Valor médio da transação, é o atributo que representa o Valor da transação.</span><span class="sxs-lookup"><span data-stu-id="91fdf-203">For example, for Average transaction value, it's the attribute representing the Transaction value.</span></span> <span data-ttu-id="91fdf-204">Para **Carimbo de data/hora da atividade**, escolha o atributo da entidade Atividade Unificada que representa a data e hora da atividade.</span><span class="sxs-lookup"><span data-stu-id="91fdf-204">For **Activity timestamp**, choose the attribute from the Unified Activity entity that represents the date and time of the activity.</span></span>
   
1. <span data-ttu-id="91fdf-205">Depois que o mapeamento de dados for bem-sucedido, você poderá ver o status como **Concluído** e o nome das atividades e atributos mapeados.</span><span class="sxs-lookup"><span data-stu-id="91fdf-205">Once the data mapping is successful, you can see the status as **Complete** and the name of the mapped activities and attributes.</span></span>

   :::image type="content" source="media/measure-template-configured.png" alt-text="Captura de tela de uma configuração de modelo de medida concluída.":::

1. <span data-ttu-id="91fdf-207">Agora você pode selecionar **Executar** para calcular os resultados da medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-207">You can now select **Run** to calculate the results of the measure.</span></span> <span data-ttu-id="91fdf-208">Para refiná-los mais tarde, selecione **Salvar rascunho**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-208">To refine it later, select **Save draft**.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="91fdf-209">Gerenciar suas medidas</span><span class="sxs-lookup"><span data-stu-id="91fdf-209">Manage your measures</span></span>

<span data-ttu-id="91fdf-210">Você pode encontrar a lista de medidas na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-210">You can find the list of measures on the **Measures** page.</span></span>

<span data-ttu-id="91fdf-211">Você encontrará informações sobre o tipo de medida, o criador, a data de criação, o status e o estado.</span><span class="sxs-lookup"><span data-stu-id="91fdf-211">You'll find information about the measure type, the creator, creation date, status, and state.</span></span> <span data-ttu-id="91fdf-212">Ao selecionar uma medida da lista, você pode exibir a saída e baixar um arquivo .CSV.</span><span class="sxs-lookup"><span data-stu-id="91fdf-212">When you select a measure from the list, you can preview the output and download a .CSV file.</span></span>

<span data-ttu-id="91fdf-213">Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.</span><span class="sxs-lookup"><span data-stu-id="91fdf-213">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="91fdf-214">![Ações para gerenciar medidas únicas](media/measure-actions.png "Ações para gerenciar medidas únicas")</span><span class="sxs-lookup"><span data-stu-id="91fdf-214">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="91fdf-215">Selecione uma medida da lista para as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="91fdf-215">Select a measure from the list for the following options:</span></span>

- <span data-ttu-id="91fdf-216">Selecione o nome da medida para ver seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="91fdf-216">Select the measure name to see its details.</span></span>
- <span data-ttu-id="91fdf-217">**Edite** a configuração da medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-217">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="91fdf-218">**Atualize** a medida com base nos dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="91fdf-218">**Refresh** the measure based on the latest data.</span></span>
- <span data-ttu-id="91fdf-219">**Renomeie** a medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-219">**Rename** the measure.</span></span>
- <span data-ttu-id="91fdf-220">**Exclua** a medida.</span><span class="sxs-lookup"><span data-stu-id="91fdf-220">**Delete** the measure.</span></span>
- <span data-ttu-id="91fdf-221">**Ative** ou **Desative**.</span><span class="sxs-lookup"><span data-stu-id="91fdf-221">**Activate** or **Deactivate**.</span></span> <span data-ttu-id="91fdf-222">Medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="91fdf-222">Inactive measures won't get refreshed during a [scheduled refresh](system.md#schedule-tab).</span></span>

> [!TIP]
> <span data-ttu-id="91fdf-223">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="91fdf-223">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="91fdf-224">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="91fdf-224">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="91fdf-225">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="91fdf-225">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="91fdf-226">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="91fdf-226">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="91fdf-227">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="91fdf-227">Next step</span></span>

<span data-ttu-id="91fdf-228">Você pode usar as medidas existentes para criar [um segmento de cliente](segments.md).</span><span class="sxs-lookup"><span data-stu-id="91fdf-228">You cam use existing measures to create [a customer segment](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
