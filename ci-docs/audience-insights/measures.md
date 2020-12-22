---
title: Criar e editar medidas
description: Defina medidas relacionadas ao cliente para analisar e refletir o desempenho de determinadas áreas de negócios.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405052"
---
# <a name="define-and-manage-measures"></a><span data-ttu-id="08073-103">Definir e gerenciar medidas</span><span class="sxs-lookup"><span data-stu-id="08073-103">Define and manage measures</span></span>

<span data-ttu-id="08073-104">As **Medidas** representam indicadores chave de desempenho (KPIs) que refletem o desempenho e a integridade de áreas de negócios específicas.</span><span class="sxs-lookup"><span data-stu-id="08073-104">**Measures** represent key performance indicators (KPIs) that reflect the performance and health of specific business areas.</span></span> <span data-ttu-id="08073-105">Os insights de público-alvo fornecem uma experiência intuitiva para criar diferentes tipos de medidas, usando um construtor de consultas que não exige a codificação nem a validação manual das suas medidas.</span><span class="sxs-lookup"><span data-stu-id="08073-105">Audience insights provides an intuitive experience for building different types of measures, using a query builder that doesn't require you to code or validate your measures manually.</span></span> <span data-ttu-id="08073-106">Você pode acompanhar suas medidas de negócios na **Home page**, consultar medidas para clientes específicos no **Cartão de Cliente** e usar medidas para definir segmentos do cliente na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="08073-106">You can track your business measures on the **Home** page, see measures for specific customers on the **Customer Card**, and use measures to define customer segments on the **Segments** page.</span></span>

## <a name="create-a-measure"></a><span data-ttu-id="08073-107">Criar uma medida</span><span class="sxs-lookup"><span data-stu-id="08073-107">Create a measure</span></span>

<span data-ttu-id="08073-108">Esta seção orienta você na criação de uma medida do zero.</span><span class="sxs-lookup"><span data-stu-id="08073-108">This section walks you through creating a measure from scratch.</span></span> <span data-ttu-id="08073-109">Você pode criar medidas com dados de várias fontes de dados conectadas através da entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="08073-109">You can build measures with data from multiple data sources that are connected through the Customer entity.</span></span> <span data-ttu-id="08073-110">Alguns [limites de serviço](service-limits.md) se aplicam.</span><span class="sxs-lookup"><span data-stu-id="08073-110">Some [service limits](service-limits.md) apply.</span></span>

1. <span data-ttu-id="08073-111">Nos insights de público-alvo, vá para **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="08073-111">In audience insights, go to **Measures**.</span></span>

2. <span data-ttu-id="08073-112">Selecione **Nova medida**.</span><span class="sxs-lookup"><span data-stu-id="08073-112">Select **New measure**.</span></span>

3. <span data-ttu-id="08073-113">Escolha a medida **Tipo**:</span><span class="sxs-lookup"><span data-stu-id="08073-113">Choose the measure **Type**:</span></span>

   - <span data-ttu-id="08073-114">**Atributo do cliente**: Um único campo por cliente que reflete uma pontuação, valor ou estado para o cliente.</span><span class="sxs-lookup"><span data-stu-id="08073-114">**Customer attribute**: A single field per customer that reflects a score, value, or state for the customer.</span></span> <span data-ttu-id="08073-115">Os atributos do cliente são criados como atributos em uma nova entidade gerada pelo sistema chamada **Customer_Measure**.</span><span class="sxs-lookup"><span data-stu-id="08073-115">Customer attributes are created as attributes in a new system-generated entity called **Customer_Measure**.</span></span>

   - <span data-ttu-id="08073-116">**Medida do cliente**: Informações sobre o comportamento do cliente com detalhamento por dimensões selecionadas.</span><span class="sxs-lookup"><span data-stu-id="08073-116">**Customer measure**: Insights on customer behavior with breakdown by selected dimensions.</span></span> <span data-ttu-id="08073-117">Uma nova entidade é gerada para cada medida, com vários registros por cliente.</span><span class="sxs-lookup"><span data-stu-id="08073-117">A new entity is generated for each measure, potentially with multiple records per customer.</span></span>

   - <span data-ttu-id="08073-118">**Medida de negócios**: Acompanha o desempenho e a integridade dos negócios.</span><span class="sxs-lookup"><span data-stu-id="08073-118">**Business measure**: Tracks your business performance and health of the business.</span></span> <span data-ttu-id="08073-119">As medidas de negócios podem ter duas saídas diferentes: uma saída numérica exibida na **Home page** ou uma nova entidade que você encontra na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="08073-119">Business measures can have two different outputs: a numeric output that shows on the **Home** page or a new entity that you find on the **Entities** page.</span></span>

4. <span data-ttu-id="08073-120">Forneça um **Nome** e um **Nome de exibição** opcional, depois selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="08073-120">Provide a **Name** and an optional **Display name**, then select **Next**.</span></span>

5. <span data-ttu-id="08073-121">Na seção **Entidades**, selecione a primeira entidade da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="08073-121">In the **Entities** section, select the first entity from the drop-down list.</span></span> <span data-ttu-id="08073-122">Nesse ponto, você deve decidir se são necessárias entidades adicionais como parte da sua definição de medida.</span><span class="sxs-lookup"><span data-stu-id="08073-122">At this point, you should decide whether additional entities are needed as part of your measure definition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="08073-123">![Definição de medida](media/measure-definition.png "Definição de medida")</span><span class="sxs-lookup"><span data-stu-id="08073-123">![Measure definition](media/measure-definition.png "Measure definition")</span></span>

   <span data-ttu-id="08073-124">Para adicionar mais entidades, selecione **Adicionar entidade** e selecione as entidades que você deseja usar para a medida.</span><span class="sxs-lookup"><span data-stu-id="08073-124">To add more entities, select **Add entity** and select entities you want to use for the measure.</span></span>

   > [!NOTE]
   > <span data-ttu-id="08073-125">Você pode selecionar somente as entidades que tenham um relacionamento com a entidade inicial.</span><span class="sxs-lookup"><span data-stu-id="08073-125">You can select only entities that have relationships to your starting entity.</span></span> <span data-ttu-id="08073-126">Para obter mais informações sobre como definir relacionamentos, consulte [Relacionamentos](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="08073-126">For more information about defining relationships, see [Relationships](relationships.md).</span></span>

6. <span data-ttu-id="08073-127">Se preferir, você pode configurar variáveis.</span><span class="sxs-lookup"><span data-stu-id="08073-127">Optionally, you can configure variables.</span></span> <span data-ttu-id="08073-128">Na seção **Variáveis**, selecione **Nova variável**.</span><span class="sxs-lookup"><span data-stu-id="08073-128">In the **Variables** section, select **New variable**.</span></span>

   <span data-ttu-id="08073-129">Variáveis são cálculos feitos em cada um dos registros selecionados.</span><span class="sxs-lookup"><span data-stu-id="08073-129">Variables are calculations that are made on each of your selected records.</span></span> <span data-ttu-id="08073-130">Por exemplo, somando ponto de venda (POS) e vendas on-line para cada um dos registros de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="08073-130">For example, summing point-of-sale (POS) and online sales for each of your customers' records.</span></span>

7. <span data-ttu-id="08073-131">Forneça um **Nome** para a variável.</span><span class="sxs-lookup"><span data-stu-id="08073-131">Provide a **Name** for the variable.</span></span>

8. <span data-ttu-id="08073-132">Na área **Expressão**, escolha um campo no qual será iniciado o cálculo.</span><span class="sxs-lookup"><span data-stu-id="08073-132">In the **Expression** area, choose a field to begin your calculation with.</span></span>

9. <span data-ttu-id="08073-133">Digite uma expressão na área **Expressão** ao escolher mais campos a serem incluídos no seu cálculo.</span><span class="sxs-lookup"><span data-stu-id="08073-133">Type an expression in the **Expression** area while choosing more fields to be included in your calculation.</span></span>

   > [!NOTE]
   > <span data-ttu-id="08073-134">No momento, só há suporte para expressões aritméticas.</span><span class="sxs-lookup"><span data-stu-id="08073-134">Currently, only arithmetic expressions are supported.</span></span> <span data-ttu-id="08073-135">Além disso, o cálculo de variáveis não é suportado para entidades de diferentes [caminhos da entidade](relationships.md).</span><span class="sxs-lookup"><span data-stu-id="08073-135">Additionally, variable calculation isn't supported for entities from different [entity paths](relationships.md).</span></span>

10. <span data-ttu-id="08073-136">Escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="08073-136">Select **Done**.</span></span>

11. <span data-ttu-id="08073-137">Na seção **Definição de medição**, você definirá como suas entidades escolhidas e variáveis calculadas são agregadas em uma nova entidade de medição ou atributo.</span><span class="sxs-lookup"><span data-stu-id="08073-137">In the **Measure definition** section, you'll define how your chosen entities and calculated variables are aggregated in a new measure entity or attribute.</span></span>

12. <span data-ttu-id="08073-138">Selecione **Nova dimensão**.</span><span class="sxs-lookup"><span data-stu-id="08073-138">Select **New dimension**.</span></span> <span data-ttu-id="08073-139">Você pode pensar em uma dimensão como uma função *agrupar por*.</span><span class="sxs-lookup"><span data-stu-id="08073-139">You can think of a dimension as a *group by* function.</span></span> <span data-ttu-id="08073-140">A saída de dados da sua entidade ou atributo de Medida será agrupada por todas as suas dimensões definidas.</span><span class="sxs-lookup"><span data-stu-id="08073-140">The data output of your Measure entity or attribute will be grouped by all of your defined dimensions.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="08073-141">![Escolha ciclo agregado](media/measures-businessreport-measure-definition2.png "Escolha ciclo agregado")</span><span class="sxs-lookup"><span data-stu-id="08073-141">![Choose aggregate cycle](media/measures-businessreport-measure-definition2.png "Choose aggregate cycle")</span></span>

    <span data-ttu-id="08073-142">Selecione ou insira as seguintes informações como parte da definição da sua dimensão:</span><span class="sxs-lookup"><span data-stu-id="08073-142">Select or enter the following information as part of your dimension's definition:</span></span>

    - <span data-ttu-id="08073-143">**Entidade**: Se você definir uma entidade de Medida, ela deverá incluir pelo menos um atributo.</span><span class="sxs-lookup"><span data-stu-id="08073-143">**Entity**: If you define a Measure entity, it should include at least one attribute.</span></span> <span data-ttu-id="08073-144">Se você definir um atributo Medida, ele incluirá apenas um atributo por padrão.</span><span class="sxs-lookup"><span data-stu-id="08073-144">If you define a Measure attribute, it will include only one attribute by default.</span></span> <span data-ttu-id="08073-145">Esta seleção é sobre como escolher a entidade que inclui esse atributo.</span><span class="sxs-lookup"><span data-stu-id="08073-145">This selection is about choosing the entity that includes that attribute.</span></span>
    - <span data-ttu-id="08073-146">**Campo**: Escolha o atributo específico a ser incluído na sua entidade ou atributo de Medida.</span><span class="sxs-lookup"><span data-stu-id="08073-146">**Field**: Choose the specific attribute to be included either in your Measure entity or attribute.</span></span>
    - <span data-ttu-id="08073-147">**Bucket**: Escolha se você deseja agregar dados diariamente, mensalmente ou anualmente.</span><span class="sxs-lookup"><span data-stu-id="08073-147">**Bucket**: Choose whether you want to aggregate data on a daily, monthly, or annual basis.</span></span> <span data-ttu-id="08073-148">É uma seleção obrigatória apenas se você tiver selecionado um atributo de tipo Data.</span><span class="sxs-lookup"><span data-stu-id="08073-148">It's a required selection only if you've selected a Date type attribute.</span></span>
    - <span data-ttu-id="08073-149">**Como**: Define o nome do seu novo campo.</span><span class="sxs-lookup"><span data-stu-id="08073-149">**As**: Defines the name of your new field.</span></span>
    - <span data-ttu-id="08073-150">**Nome para exibição**: Define o nome para exibição de seu campo.</span><span class="sxs-lookup"><span data-stu-id="08073-150">**Display name**: Defines the display name of your field.</span></span>

    > [!NOTE]
    > <span data-ttu-id="08073-151">Sua medida comercial será salva como uma entidade de número único e aparecerá na **Home page**, a menos que você adicione mais dimensões à sua medida.</span><span class="sxs-lookup"><span data-stu-id="08073-151">Your business measure will be saved as a single-number entity and will appear on the **Home** page unless you add more dimensions to your measure.</span></span> <span data-ttu-id="08073-152">Depois de adicionar mais dimensões, a medida *não* aparecerá na **Home page**.</span><span class="sxs-lookup"><span data-stu-id="08073-152">After adding more dimensions, the measure will *not* show up on the **Home** page.</span></span>

13. <span data-ttu-id="08073-153">Opcionalmente, adicione funções de agregação.</span><span class="sxs-lookup"><span data-stu-id="08073-153">Optionally, add aggregation functions.</span></span> <span data-ttu-id="08073-154">Qualquer agregação que você cria resulta em um novo valor dentro da sua entidade ou atributo de Medidas.</span><span class="sxs-lookup"><span data-stu-id="08073-154">Any aggregation that you create results in a new value within your Measures entity or attribute.</span></span> <span data-ttu-id="08073-155">As funções de agregação suportadas são: **Mín.**, **Máx.**, **Média**, **Mediano**, **Soma**, **Contagem Exclusiva**, **Primeira** (pega o primeiro registro de um valor de dimensão) e **Último** (pega o último registro adicionado a um valor de dimensão).</span><span class="sxs-lookup"><span data-stu-id="08073-155">Supported aggregation functions are: **Min**, **Max**, **Average**, **Median**, **Sum**, **Count Unique**, **First** (takes the first record of a dimension value), and **Last** (takes the last record added to a dimension value).</span></span>

14. <span data-ttu-id="08073-156">Selecione **Salvar** para salvar suas alterações na medida.</span><span class="sxs-lookup"><span data-stu-id="08073-156">Select **Save** to apply your changes to the measure.</span></span>

## <a name="manage-your-measures"></a><span data-ttu-id="08073-157">Gerenciar suas medidas</span><span class="sxs-lookup"><span data-stu-id="08073-157">Manage your measures</span></span>

<span data-ttu-id="08073-158">Depois de criar pelo menos uma medida, você verá uma lista de medidas na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="08073-158">After creating at least one measure, you'll see a list of measures on the **Measures** page.</span></span>

<span data-ttu-id="08073-159">Você encontrará informações sobre o tipo de medida, o criador, data e hora da criação, data e hora da última edição, status (se a medida está ativa, inativa ou com falha) e a data e hora da última atualização.</span><span class="sxs-lookup"><span data-stu-id="08073-159">You'll find information about the measure type, the creator, creation date and time, last edit date and time, status (whether the measure is active, inactive, or failed), and last refresh date and time.</span></span> <span data-ttu-id="08073-160">Ao selecionar uma medida da lista, você poderá visualizar sua saída.</span><span class="sxs-lookup"><span data-stu-id="08073-160">When you select a measure from the list, you can see a preview of its output.</span></span>

<span data-ttu-id="08073-161">Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.</span><span class="sxs-lookup"><span data-stu-id="08073-161">To refresh all of your measures at the same time, select **Refresh all** without selecting a specific measure.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="08073-162">![Ações para gerenciar medidas únicas](media/measure-actions.png "Ações para gerenciar medidas únicas")</span><span class="sxs-lookup"><span data-stu-id="08073-162">![Actions to manage single measures](media/measure-actions.png "Actions to manage single measures")</span></span>

<span data-ttu-id="08073-163">Como alternativa, selecione uma medida na lista e execute uma das seguintes ações:</span><span class="sxs-lookup"><span data-stu-id="08073-163">Alternatively, select a measure from the list and perform one of the following actions:</span></span>

- <span data-ttu-id="08073-164">Selecione o nome da medida para ver seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="08073-164">Select the measure name to see its details.</span></span>
- <span data-ttu-id="08073-165">**Edite** a configuração da medida.</span><span class="sxs-lookup"><span data-stu-id="08073-165">**Edit** the configuration of the measure.</span></span>
- <span data-ttu-id="08073-166">**Renomeie** a medida.</span><span class="sxs-lookup"><span data-stu-id="08073-166">**Rename** the measure.</span></span>
- <span data-ttu-id="08073-167">**Exclua** a medida.</span><span class="sxs-lookup"><span data-stu-id="08073-167">**Delete** the measure.</span></span>
- <span data-ttu-id="08073-168">Selecione as reticências (...) e, em seguida, **Atualizar** para iniciar o processo de atualização da medida.</span><span class="sxs-lookup"><span data-stu-id="08073-168">Select the ellipsis (...) and then **Refresh** to start the refresh process for the measure.</span></span>
- <span data-ttu-id="08073-169">Selecione as reticências (...) e, em seguida, use **Baixar** para obter um arquivo .CSV da medida.</span><span class="sxs-lookup"><span data-stu-id="08073-169">Select the ellipsis (...) and then **Download** to get a .CSV file of the measure.</span></span>

> [!TIP]
> <span data-ttu-id="08073-170">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="08073-170">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="08073-171">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="08073-171">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="08073-172">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="08073-172">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="08073-173">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="08073-173">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="08073-174">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="08073-174">Next step</span></span>

<span data-ttu-id="08073-175">Você pode usar medidas existentes para criar seu primeiro segmento de cliente na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="08073-175">You cam use existing measures to create your first customer segment on the **Segments** page.</span></span> <span data-ttu-id="08073-176">Para obter mais informações, consulte [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="08073-176">For more information, see [Segments](segments.md).</span></span>
