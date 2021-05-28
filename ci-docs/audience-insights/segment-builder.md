---
title: Criar e gerenciar segmentos
description: Criar segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 550e509a24701fe5fcdeb9d54311872dc954156c
ms.sourcegitcommit: 72603fb39c4d5dbca71128815a2e1692542ea4dc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2021
ms.locfileid: "6064923"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="335a1-103">Criar e gerenciar segmentos</span><span class="sxs-lookup"><span data-stu-id="335a1-103">Create and manage segments</span></span>

<span data-ttu-id="335a1-104">Defina filtros complexos em torno da entidade unificada do cliente e suas entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="335a1-104">Define complex filters around the unified customer entity and its related entities.</span></span> <span data-ttu-id="335a1-105">Cada segmento, após o processamento, cria um conjunto de registros do cliente que você pode exportar e executar.</span><span class="sxs-lookup"><span data-stu-id="335a1-105">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="335a1-106">Os segmentos são gerenciados na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="335a1-106">Segments are managed on the **Segments** page.</span></span> 

<span data-ttu-id="335a1-107">O exemplo a seguir ilustra a capacidade de segmentação.</span><span class="sxs-lookup"><span data-stu-id="335a1-107">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="335a1-108">Definimos um segmento para clientes que fizeram pedidos de pelo menos US$ 500 em mercadorias nos últimos 90 dias *e* que estão envolvidos em uma chamada de atendimento ao cliente escalonada.</span><span class="sxs-lookup"><span data-stu-id="335a1-108">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de tela da interface do usuário do criador de segmentos com dois grupos que especificam um segmento de cliente.":::

## <a name="create-a-new-segment"></a><span data-ttu-id="335a1-110">Criar um novo segmento</span><span class="sxs-lookup"><span data-stu-id="335a1-110">Create a new segment</span></span>

<span data-ttu-id="335a1-111">Há várias maneiras de criar um novo segmento.</span><span class="sxs-lookup"><span data-stu-id="335a1-111">There are multiple ways to create a new segment.</span></span> <span data-ttu-id="335a1-112">Esta seção descreve como criar um *segmento em branco* do zero.</span><span class="sxs-lookup"><span data-stu-id="335a1-112">This section describes how to create a *blank segment* from scratch.</span></span> <span data-ttu-id="335a1-113">Você também pode criar um *segmento rápido* com base em entidades existentes ou usar modelos de Aprendizado de Máquina para ter *segmentos sugeridos*.</span><span class="sxs-lookup"><span data-stu-id="335a1-113">You can also create a *quick segment* based on existing entities or make use of machine learning models to get *suggested segments*.</span></span> <span data-ttu-id="335a1-114">Mais informações: [Visão geral de segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="335a1-114">More information: [Segments overview](segments.md).</span></span>

<span data-ttu-id="335a1-115">Ao criar um segmento, você pode salvar um rascunho.</span><span class="sxs-lookup"><span data-stu-id="335a1-115">While creating a segment, you can save a draft.</span></span> <span data-ttu-id="335a1-116">Ele será salvo como um segmento inativo, e não pode ser ativado se for finalizado com uma configuração válida.</span><span class="sxs-lookup"><span data-stu-id="335a1-116">It will be saved as an inactive segment, and can't be activated it finished with a valid configuration.</span></span>

1. <span data-ttu-id="335a1-117">Vá para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="335a1-117">Go to the **Segments** page.</span></span>

1. <span data-ttu-id="335a1-118">Selecione **Novo** > **Segmento em branco**.</span><span class="sxs-lookup"><span data-stu-id="335a1-118">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="335a1-119">No painel **Novo segmento**, escolha um tipo de segmento:</span><span class="sxs-lookup"><span data-stu-id="335a1-119">In the **New segment** pane, choose a segment type:</span></span>

   - <span data-ttu-id="335a1-120">**Segmentos dinâmicos** [atualizar](segments.md#refresh-segments) em uma agenda recorrente.</span><span class="sxs-lookup"><span data-stu-id="335a1-120">**Dynamic segments** [refresh](segments.md#refresh-segments) on a recurring schedule.</span></span>
   - <span data-ttu-id="335a1-121">Os **Segmentos estáticos** são executados depois da criação.</span><span class="sxs-lookup"><span data-stu-id="335a1-121">**Static segments** run once when you create it.</span></span>

1. <span data-ttu-id="335a1-122">Forneça um **Nome da entidade de saída** para o segmento.</span><span class="sxs-lookup"><span data-stu-id="335a1-122">Provide an **Output entity name** for the segment.</span></span> <span data-ttu-id="335a1-123">Se preferir, forneça um nome para exibição e uma descrição que ajude a identificar o segmento.</span><span class="sxs-lookup"><span data-stu-id="335a1-123">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="335a1-124">Selecione **Próximo** para ir até a página **Construtor de segmentos** onde você define um grupo.</span><span class="sxs-lookup"><span data-stu-id="335a1-124">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="335a1-125">Um grupo é um conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="335a1-125">A group is a set of customers.</span></span>

1. <span data-ttu-id="335a1-126">Escolha a entidade que tem o atributo pelo qual você deseja segmentar.</span><span class="sxs-lookup"><span data-stu-id="335a1-126">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="335a1-127">Escolha o atributo pelo qual você fará a segmentação.</span><span class="sxs-lookup"><span data-stu-id="335a1-127">Choose the attribute to segment by.</span></span> <span data-ttu-id="335a1-128">Este atributo pode ter um dos quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.</span><span class="sxs-lookup"><span data-stu-id="335a1-128">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="335a1-129">Escolha um operador e um valor para o atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="335a1-129">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="335a1-130">![Filtro do grupo personalizado](media/customer-group-numbers.png "Filtro do grupo do cliente")</span><span class="sxs-lookup"><span data-stu-id="335a1-130">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="335a1-131">Número</span><span class="sxs-lookup"><span data-stu-id="335a1-131">Number</span></span> |<span data-ttu-id="335a1-132">Definição</span><span class="sxs-lookup"><span data-stu-id="335a1-132">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="335a1-133">0</span><span class="sxs-lookup"><span data-stu-id="335a1-133">1</span></span>     |<span data-ttu-id="335a1-134">Entity</span><span class="sxs-lookup"><span data-stu-id="335a1-134">Entity</span></span>          |
   |<span data-ttu-id="335a1-135">2</span><span class="sxs-lookup"><span data-stu-id="335a1-135">2</span></span>     |<span data-ttu-id="335a1-136">Atributo</span><span class="sxs-lookup"><span data-stu-id="335a1-136">Attribute</span></span>          |
   |<span data-ttu-id="335a1-137">3</span><span class="sxs-lookup"><span data-stu-id="335a1-137">3</span></span>    |<span data-ttu-id="335a1-138">Operador</span><span class="sxs-lookup"><span data-stu-id="335a1-138">Operator</span></span>         |
   |<span data-ttu-id="335a1-139">4</span><span class="sxs-lookup"><span data-stu-id="335a1-139">4</span></span>    |<span data-ttu-id="335a1-140">Valor</span><span class="sxs-lookup"><span data-stu-id="335a1-140">Value</span></span>         |

   1. <span data-ttu-id="335a1-141">Para adicionar mais condições a um grupo, você pode usar dois operadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="335a1-141">To add more conditions to a group, you can use two logical operators:</span></span>

      - <span data-ttu-id="335a1-142">Operador **E**: Ambas as condições devem ser atendidas como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="335a1-142">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="335a1-143">Esta opção é mais útil quando você define condições em diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="335a1-143">This option is most useful when you define conditions across different entities.</span></span>

      - <span data-ttu-id="335a1-144">Operador **OU**: Qualquer uma das condições precisa ser atendida como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="335a1-144">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="335a1-145">Esta opção é mais útil quando você define várias condições para a mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="335a1-145">This option is most useful when you define multiple conditions for the same entity.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="335a1-146">![Operador OU em que uma das condições precisa ser atendida](media/segmentation-either-condition.png "Operador OU em que uma das condições precisa ser atendida")</span><span class="sxs-lookup"><span data-stu-id="335a1-146">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

      <span data-ttu-id="335a1-147">Atualmente é possível aninhar um operador **OU** sob um operador **E**, mas não o contrário.</span><span class="sxs-lookup"><span data-stu-id="335a1-147">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

   1. <span data-ttu-id="335a1-148">Cada grupo corresponde a um conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="335a1-148">Each group matches set of customers.</span></span> <span data-ttu-id="335a1-149">Você pode combinar grupos para incluir os clientes que são necessários para o seu caso de negócios.</span><span class="sxs-lookup"><span data-stu-id="335a1-149">You can combine groups to include the customers required for your business case.</span></span>    
   <span data-ttu-id="335a1-150">Selecione **Adicionar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="335a1-150">Select **Add Group**.</span></span>

      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="335a1-151">![Grupo de clientes adicionar grupo](media/customer-group-add-group.png "Grupo de clientes adicionar grupo")</span><span class="sxs-lookup"><span data-stu-id="335a1-151">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

   1. <span data-ttu-id="335a1-152">Selecione um dos operadores de conjunto: **União**, **Interseção** ou **Exceto**.</span><span class="sxs-lookup"><span data-stu-id="335a1-152">Select one of the set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="335a1-153">![Grupo de clientes adicionar união](media/customer-group-union.png "Grupo de clientes adicionar união")</span><span class="sxs-lookup"><span data-stu-id="335a1-153">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   - <span data-ttu-id="335a1-154">**União** une os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="335a1-154">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="335a1-155">**Interseção** sobrepõe os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="335a1-155">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="335a1-156">Apenas dados que são *comuns* para ambos os grupos é retido no grupo unificado.</span><span class="sxs-lookup"><span data-stu-id="335a1-156">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="335a1-157">**Exceto** combina os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="335a1-157">**Except** combines the two groups.</span></span> <span data-ttu-id="335a1-158">Apenas dados no grupo A que *não são comuns* a dados no grupo B são retidos.</span><span class="sxs-lookup"><span data-stu-id="335a1-158">Only data in group A that *is not common* to data in group B is retained.</span></span>

1. <span data-ttu-id="335a1-159">Se a entidade estiver conectada à entidade unificada do cliente por meio de [relacionamentos](relationships.md), você precisará definir o caminho do relacionamento para criar um segmento válido.</span><span class="sxs-lookup"><span data-stu-id="335a1-159">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="335a1-160">Adicione as entidades do caminho do relacionamento até poder selecionar a entidade **Cliente: CustomerInsights** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="335a1-160">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="335a1-161">Depois, escolha **Todos os registros** para cada etapa.</span><span class="sxs-lookup"><span data-stu-id="335a1-161">Then, choose **All records** for each step.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="335a1-162">![Caminho do relacionamento durante a criação do segmento](media/segments-multiple-relationships.png "Caminho do relacionamento durante a criação do segmento")</span><span class="sxs-lookup"><span data-stu-id="335a1-162">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="335a1-163">Por padrão, os segmentos geram uma entidade de saída que contém todos os atributos dos perfis de clientes que correspondem aos filtros definidos.</span><span class="sxs-lookup"><span data-stu-id="335a1-163">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="335a1-164">Se um segmento for baseado em entidades diferentes da entidade *Cliente*, você poderá adicionar mais atributos dessas entidades à entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="335a1-164">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="335a1-165">Selecione **Atributos do projeto** para escolher os atributos que serão anexados à entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="335a1-165">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  
  
   <span data-ttu-id="335a1-166">Exemplo: um segmento é baseado em uma entidade que contém dados da atividade do cliente que estão relacionados à entidade *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="335a1-166">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="335a1-167">O segmento busca todos os clientes que ligaram para o suporte técnico nos últimos 60 dias.</span><span class="sxs-lookup"><span data-stu-id="335a1-167">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="335a1-168">Você pode optar por anexar a duração da chamada e o número de chamadas a todos os registros do cliente correspondentes na entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="335a1-168">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="335a1-169">Essas informações podem ser úteis para enviar um email com links úteis para artigos de ajuda online e perguntas frequentes para clientes que ligam com frequência.</span><span class="sxs-lookup"><span data-stu-id="335a1-169">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

   > [!NOTE]
   > - <span data-ttu-id="335a1-170">Os atributos projetados funcionam somente para entidades que tenham um relacionamento um-para-muitos com a entidade do cliente.</span><span class="sxs-lookup"><span data-stu-id="335a1-170">Projected attributes only work for entities that have a one-to-many relationship with the customer entity.</span></span> <span data-ttu-id="335a1-171">Por exemplo, um cliente pode ter várias assinaturas.</span><span class="sxs-lookup"><span data-stu-id="335a1-171">For example, one customer can have multiple subscriptions.</span></span>
   > - <span data-ttu-id="335a1-172">Você só pode projetar atributos a partir de uma entidade que seja usada em cada grupo de consulta de segmento que você está construindo.</span><span class="sxs-lookup"><span data-stu-id="335a1-172">You can only project attributes from an entity that is used in every group of segment query you are building.</span></span>
   > - <span data-ttu-id="335a1-173">Os atributos projetados são fatorados com o uso de operadores de conjunto.</span><span class="sxs-lookup"><span data-stu-id="335a1-173">Projected attributes are factored in when using set operators.</span></span>

1. <span data-ttu-id="335a1-174">Selecione **Salvar** para salvar seu segmento.</span><span class="sxs-lookup"><span data-stu-id="335a1-174">Select **Save** to save your segment.</span></span> <span data-ttu-id="335a1-175">Seu segmento será salvo e processado, se todos os requisitos forem validados.</span><span class="sxs-lookup"><span data-stu-id="335a1-175">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="335a1-176">Caso contrário, ele será salvo como rascunho.</span><span class="sxs-lookup"><span data-stu-id="335a1-176">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="335a1-177">Selecione **Voltar aos segmentos** voltar para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="335a1-177">Select **Back to segments** to go back to the **Segments** page.</span></span>



## <a name="quick-segments"></a><span data-ttu-id="335a1-178">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="335a1-178">Quick segments</span></span>

<span data-ttu-id="335a1-179">Segmentos rápidos lhe permitem construir segmentos simples com um único operador rapidamente para insights mais rápidos.</span><span class="sxs-lookup"><span data-stu-id="335a1-179">Quick segments let you build simple segments with a single operator quickly for faster insights.</span></span>

1. <span data-ttu-id="335a1-180">Na página **Segmentos**, selecione **Novo** > **Criar a partir de**.</span><span class="sxs-lookup"><span data-stu-id="335a1-180">On the **Segments** page, select **New** > **Create from**.</span></span>

   - <span data-ttu-id="335a1-181">Selecione a opção **Perfis** para criar um segmento baseado na entidade *unificada do cliente*.</span><span class="sxs-lookup"><span data-stu-id="335a1-181">Select the **Profiles** option to build a segment that is based on the *unified customer* entity.</span></span>
   - <span data-ttu-id="335a1-182">Selecione a opção **Medidas** para construir um segmento em torno das medidas que você já criou.</span><span class="sxs-lookup"><span data-stu-id="335a1-182">Select the **Measures** option to build a segment around  measures you have previously created.</span></span>
   - <span data-ttu-id="335a1-183">Selecione a opção **Inteligência** para criar um segmento em torno de uma das entidades de saída que você gerou usando os recursos **Previsões** ou **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="335a1-183">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="335a1-184">Na caixa de diálogo **Novo segmento rápido**, selecione um atributo no menu suspenso **Campo**.</span><span class="sxs-lookup"><span data-stu-id="335a1-184">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="335a1-185">O sistema fornecerá algumas informações adicionais que ajudarão a criar melhores segmentos de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="335a1-185">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="335a1-186">Para campos categóricos, mostraremos as 10 principais contagens de clientes.</span><span class="sxs-lookup"><span data-stu-id="335a1-186">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="335a1-187">Escolha um **Valor** e selecione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="335a1-187">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="335a1-188">Para um atributo numérico, o sistema mostrará qual valor de atributo se enquadra no percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="335a1-188">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="335a1-189">Escolha um **Operador** e um **Valor** e selecione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="335a1-189">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="335a1-190">O sistema fornecerá a você um **Tamanho estimado do segmento**.</span><span class="sxs-lookup"><span data-stu-id="335a1-190">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="335a1-191">Você pode optar por gerar o segmento definido ou primeiro revisitá-lo para obter um tamanho de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="335a1-191">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="335a1-192">![Nome e estimativa para um segmento rápido](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="335a1-192">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="335a1-193">Forneça um **Nome** para seu segmento.</span><span class="sxs-lookup"><span data-stu-id="335a1-193">Provide a **Name** for your segment.</span></span> <span data-ttu-id="335a1-194">Se preferir, forneça um **Nome para exibição**.</span><span class="sxs-lookup"><span data-stu-id="335a1-194">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="335a1-195">Selecione **Salvar** para criar seu segmento.</span><span class="sxs-lookup"><span data-stu-id="335a1-195">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="335a1-196">Depois que o segmento terminar o processamento, você poderá vê-lo como qualquer outro segmento criado.</span><span class="sxs-lookup"><span data-stu-id="335a1-196">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

## <a name="next-steps"></a><span data-ttu-id="335a1-197">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="335a1-197">Next steps</span></span>

<span data-ttu-id="335a1-198">[Exportar um segmento](export-destinations.md) e explorar o [Cartão de Cliente](customer-card-add-in.md) e os [Conectores](export-power-bi.md) para obter insights no nível do cliente.</span><span class="sxs-lookup"><span data-stu-id="335a1-198">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
