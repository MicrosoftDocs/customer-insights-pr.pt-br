---
title: Criar e gerenciar segmentos
description: Criar segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: a1308f07ac3ba7d4b09931bab3d19b6dfaf479ee
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270342"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="bc96b-103">Criar e gerenciar segmentos</span><span class="sxs-lookup"><span data-stu-id="bc96b-103">Create and manage segments</span></span>

<span data-ttu-id="bc96b-104">Os segmentos permitem agrupar seus clientes com base em atributos demográficos, transacionais ou comportamentais.</span><span class="sxs-lookup"><span data-stu-id="bc96b-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="bc96b-105">Você pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para atingir suas metas de negócios.</span><span class="sxs-lookup"><span data-stu-id="bc96b-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="bc96b-106">Você pode definir filtros complexos em torno da entidade Perfil do Cliente e de entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="bc96b-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="bc96b-107">Cada segmento, após o processamento, cria um conjunto de registros do cliente que você pode exportar e executar.</span><span class="sxs-lookup"><span data-stu-id="bc96b-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="bc96b-108">Alguns [limites de serviço](service-limits.md) se aplicam.</span><span class="sxs-lookup"><span data-stu-id="bc96b-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="bc96b-109">Salvo indicação em contrário, todos os segmentos são **Segmentos dinâmicos**, que são atualizados em uma programação recorrente.</span><span class="sxs-lookup"><span data-stu-id="bc96b-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="bc96b-110">O exemplo a seguir ilustra a capacidade de segmentação.</span><span class="sxs-lookup"><span data-stu-id="bc96b-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="bc96b-111">Definimos um segmento para clientes que fizeram pedidos de pelo menos US$ 500 em mercadorias nos últimos 90 dias *e* que estão envolvidos em uma chamada de atendimento ao cliente escalonada.</span><span class="sxs-lookup"><span data-stu-id="bc96b-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bc96b-112">![Vários grupos](media/segmentation-group1-2.png "Vários grupos")</span><span class="sxs-lookup"><span data-stu-id="bc96b-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="bc96b-113">Criar um novo segmento</span><span class="sxs-lookup"><span data-stu-id="bc96b-113">Create a new segment</span></span>

<span data-ttu-id="bc96b-114">Os segmentos são gerenciados na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="bc96b-115">Nas informações de público-alvo, vá para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-115">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bc96b-116">Selecione **Novo** > **Segmento em branco**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-116">Select **New** > **Blank segment**.</span></span>

3. <span data-ttu-id="bc96b-117">No painel **Novo segmento**, escolha um tipo de segmento e forneça um **Nome**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="bc96b-118">Se preferir, forneça um nome para exibição e uma descrição que ajude a identificar o segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

4. <span data-ttu-id="bc96b-119">Selecione **Próximo** para ir até a página **Construtor de segmentos** onde você define um grupo.</span><span class="sxs-lookup"><span data-stu-id="bc96b-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="bc96b-120">Um grupo é um conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="bc96b-120">A group is a set of customers.</span></span>

5. <span data-ttu-id="bc96b-121">Escolha a entidade que tem o atributo pelo qual você deseja segmentar.</span><span class="sxs-lookup"><span data-stu-id="bc96b-121">Choose the entity that includes the attribute you want to segment by.</span></span>

6. <span data-ttu-id="bc96b-122">Escolha o atributo pelo qual você fará a segmentação.</span><span class="sxs-lookup"><span data-stu-id="bc96b-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="bc96b-123">Este atributo pode ter um dos quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.</span><span class="sxs-lookup"><span data-stu-id="bc96b-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

7. <span data-ttu-id="bc96b-124">Escolha um operador e um valor para o atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="bc96b-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc96b-125">![Filtro do grupo personalizado](media/customer-group-numbers.png "Filtro do grupo do cliente")</span><span class="sxs-lookup"><span data-stu-id="bc96b-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="bc96b-126">Número</span><span class="sxs-lookup"><span data-stu-id="bc96b-126">Number</span></span> |<span data-ttu-id="bc96b-127">Definição</span><span class="sxs-lookup"><span data-stu-id="bc96b-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="bc96b-128">1</span><span class="sxs-lookup"><span data-stu-id="bc96b-128">1</span></span>     |<span data-ttu-id="bc96b-129">Entity</span><span class="sxs-lookup"><span data-stu-id="bc96b-129">Entity</span></span>          |
   |<span data-ttu-id="bc96b-130">2</span><span class="sxs-lookup"><span data-stu-id="bc96b-130">2</span></span>     |<span data-ttu-id="bc96b-131">Atributo</span><span class="sxs-lookup"><span data-stu-id="bc96b-131">Attribute</span></span>          |
   |<span data-ttu-id="bc96b-132">3</span><span class="sxs-lookup"><span data-stu-id="bc96b-132">3</span></span>    |<span data-ttu-id="bc96b-133">Operador</span><span class="sxs-lookup"><span data-stu-id="bc96b-133">Operator</span></span>         |
   |<span data-ttu-id="bc96b-134">4</span><span class="sxs-lookup"><span data-stu-id="bc96b-134">4</span></span>    |<span data-ttu-id="bc96b-135">Valor</span><span class="sxs-lookup"><span data-stu-id="bc96b-135">Value</span></span>         |

8. <span data-ttu-id="bc96b-136">Se a entidade estiver conectada à entidade unificada do cliente por meio de [relacionamentos](relationships.md), você precisará definir o caminho do relacionamento para criar um segmento válido.</span><span class="sxs-lookup"><span data-stu-id="bc96b-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="bc96b-137">Adicione as entidades do caminho do relacionamento até poder selecionar a entidade **Cliente: CustomerInsights** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="bc96b-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="bc96b-138">Em seguida, escolha **Todos os registros** de cada condição.</span><span class="sxs-lookup"><span data-stu-id="bc96b-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc96b-139">![Caminho do relacionamento durante a criação do segmento](media/segments-multiple-relationships.png "Caminho do relacionamento durante a criação do segmento")</span><span class="sxs-lookup"><span data-stu-id="bc96b-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

9. <span data-ttu-id="bc96b-140">Selecione **Salvar** para salvar seu segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-140">Select **Save** to save your segment.</span></span> <span data-ttu-id="bc96b-141">Seu segmento será salvo e processado, se todos os requisitos forem validados.</span><span class="sxs-lookup"><span data-stu-id="bc96b-141">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="bc96b-142">Caso contrário, ele será salvo como rascunho.</span><span class="sxs-lookup"><span data-stu-id="bc96b-142">Otherwise, it will be saved as a draft.</span></span>

10. <span data-ttu-id="bc96b-143">Selecione **Voltar aos segmentos** voltar para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-143">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="bc96b-144">Gerenciar segmentos existentes</span><span class="sxs-lookup"><span data-stu-id="bc96b-144">Manage existing segments</span></span>

<span data-ttu-id="bc96b-145">Na página **Segmentos**, você pode visualizar todos os seus segmentos salvos e gerenciá-los.</span><span class="sxs-lookup"><span data-stu-id="bc96b-145">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="bc96b-146">Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-146">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="bc96b-147">Você pode classificar os segmentos em uma coluna selecionando o cabeçalho da coluna.</span><span class="sxs-lookup"><span data-stu-id="bc96b-147">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="bc96b-148">Use a caixa **Pesquisar** no canto superior direito para filtrar os segmentos.</span><span class="sxs-lookup"><span data-stu-id="bc96b-148">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bc96b-149">![Opções para gerenciar um segmento existente](media/segments-selected-segment.png "Opções para gerenciar um segmento existente")</span><span class="sxs-lookup"><span data-stu-id="bc96b-149">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="bc96b-150">As seguintes ações estão disponíveis quando você seleciona um segmento:</span><span class="sxs-lookup"><span data-stu-id="bc96b-150">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="bc96b-151">**Exiba** os detalhes do segmento, incluindo a tendência de contagem de membros, uma visualização dos membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-151">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="bc96b-152">**Edite** o segmento para alterar suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="bc96b-152">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="bc96b-153">**Atualize** o segmento para incluir os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bc96b-153">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="bc96b-154">**Ative** ou **desative** o segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-154">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="bc96b-155">Os segmentos têm dois estados possíveis: ativo ou inativo.</span><span class="sxs-lookup"><span data-stu-id="bc96b-155">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="bc96b-156">Esses estados são úteis ao editar um segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-156">These states come in handy when editing a segment.</span></span> <span data-ttu-id="bc96b-157">Para segmentos inativos, a definição do segmento existe, mas ainda não contém nenhum cliente.</span><span class="sxs-lookup"><span data-stu-id="bc96b-157">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="bc96b-158">Quando você ativa um segmento, o estado dele muda de "inativo" para "ativo" e ele começa a procurar clientes que correspondam à definição do segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-158">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="bc96b-159">Se uma [atualização programada](system.md#schedule-tab) estiver configurada, os segmentos inativos terão o **Status** listado como **Ignorado**, indicando que uma atualização nem mesmo foi tentada.</span><span class="sxs-lookup"><span data-stu-id="bc96b-159">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="bc96b-160">Quando um segmento inativo for ativado, ele será atualizado e incluído nas atualizações agendadas.</span><span class="sxs-lookup"><span data-stu-id="bc96b-160">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="bc96b-161">Como alternativa, você pode usar a funcionalidade **Agendar mais tarde** na lista suspensa **Ativar/desativar** para especificar data e hora futuras para a ativação e desativação de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="bc96b-161">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="bc96b-162">**Renomeie** o segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-162">**Rename** the segment.</span></span>
- <span data-ttu-id="bc96b-163">**Baixe** a lista de membros como um arquivo .CSV.</span><span class="sxs-lookup"><span data-stu-id="bc96b-163">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="bc96b-164">A opção **Adicionar a** envia a lista de IDs do cliente no segmento para processamento em outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="bc96b-164">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="bc96b-165">**Exclua** o segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-165">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="bc96b-166">Atualizar segmentos</span><span class="sxs-lookup"><span data-stu-id="bc96b-166">Refresh segments</span></span>

<span data-ttu-id="bc96b-167">Você pode atualizar todos os segmentos de uma vez, selecionando **Atualizar tudo** na página **Segmentos** ou você pode atualizar um ou vários segmentos ao selecioná-los e escolher **Atualizar** nas opções.</span><span class="sxs-lookup"><span data-stu-id="bc96b-167">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="bc96b-168">Como alternativa, você pode configurar uma atualização recorrente em **Admin** > **Sistema** > **Agendar**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-168">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="bc96b-169">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="bc96b-169">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="bc96b-170">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="bc96b-170">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="bc96b-171">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="bc96b-171">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="bc96b-172">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="bc96b-172">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="bc96b-173">Baixar e exportar segmentos</span><span class="sxs-lookup"><span data-stu-id="bc96b-173">Download and export segments</span></span>

<span data-ttu-id="bc96b-174">Você pode baixar seus segmentos para um arquivo CSV ou exportá-los para o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bc96b-174">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="bc96b-175">Baixar segmentos para um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="bc96b-175">Download segments to a CSV file</span></span>

1. <span data-ttu-id="bc96b-176">Nas informações de público-alvo, vá para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-176">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bc96b-177">Selecione as reticências no bloco de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="bc96b-177">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="bc96b-178">Selecione **Baixar como CSV** da lista suspensa de ações.</span><span class="sxs-lookup"><span data-stu-id="bc96b-178">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="bc96b-179">Exportar segmentos para o Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="bc96b-179">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="bc96b-180">Antes de exportar segmentos para o Dynamics 365 Sales, um administrador precisa [criar o destino de exportação](export-destinations.md) para o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="bc96b-180">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="bc96b-181">Nas informações de público-alvo, vá para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-181">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="bc96b-182">Selecione as reticências no bloco de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="bc96b-182">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="bc96b-183">Selecione **Adicionar a** na lista suspensa de ações e selecione o destino de exportação para o qual deseja enviar os dados.</span><span class="sxs-lookup"><span data-stu-id="bc96b-183">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="bc96b-184">Modo de rascunho para segmentos</span><span class="sxs-lookup"><span data-stu-id="bc96b-184">Draft mode for segments</span></span>

<span data-ttu-id="bc96b-185">Se nem todos os requisitos para processar um segmento forem atendidos, você poderá salvar o segmento como rascunho e acessá-lo na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-185">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="bc96b-186">Ele será salvo como um segmento inativo e não poderá ser ativado até que seja válido.</span><span class="sxs-lookup"><span data-stu-id="bc96b-186">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="bc96b-187">Adicionar mais condições a um grupo</span><span class="sxs-lookup"><span data-stu-id="bc96b-187">Add more conditions to a group</span></span>

<span data-ttu-id="bc96b-188">Para adicionar mais condições a um grupo, você pode usar dois operadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="bc96b-188">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="bc96b-189">Operador **E**: Ambas as condições devem ser atendidas como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="bc96b-189">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="bc96b-190">Esta opção é mais útil quando você define condições em diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="bc96b-190">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="bc96b-191">Operador **OU**: Qualquer uma das condições precisa ser atendida como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="bc96b-191">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="bc96b-192">Esta opção é mais útil quando você define várias condições para a mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="bc96b-192">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc96b-193">![Operador OU em que uma das condições precisa ser atendida](media/segmentation-either-condition.png "Operador OU em que uma das condições precisa ser atendida")</span><span class="sxs-lookup"><span data-stu-id="bc96b-193">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="bc96b-194">Atualmente é possível aninhar um operador **OU** sob um operador **E**, mas não o contrário.</span><span class="sxs-lookup"><span data-stu-id="bc96b-194">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="bc96b-195">Combinar vários grupos</span><span class="sxs-lookup"><span data-stu-id="bc96b-195">Combine multiple groups</span></span>

<span data-ttu-id="bc96b-196">Cada grupo produz um conjunto específico de clientes.</span><span class="sxs-lookup"><span data-stu-id="bc96b-196">Each group produces a specific set of customers.</span></span> <span data-ttu-id="bc96b-197">Você pode combinar esses grupos para incluir os clientes necessários para o seu caso de negócios.</span><span class="sxs-lookup"><span data-stu-id="bc96b-197">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="bc96b-198">Nos insights de público-alvo, vá para a página **Segmentos** e selecione um segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-198">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="bc96b-199">Selecione **Adicionar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-199">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc96b-200">![Grupo de clientes adicionar grupo](media/customer-group-add-group.png "Grupo de clientes adicionar grupo")</span><span class="sxs-lookup"><span data-stu-id="bc96b-200">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="bc96b-201">Selecione um dos seguintes operadores definidos: **União**, **Interseção** ou **Exceto**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-201">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bc96b-202">![Grupo de clientes adicionar união](media/customer-group-union.png "Grupo de clientes adicionar união")</span><span class="sxs-lookup"><span data-stu-id="bc96b-202">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="bc96b-203">Selecione um operador definido para definir um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="bc96b-203">Select a set operator to define a new group.</span></span> <span data-ttu-id="bc96b-204">Salve grupos diferentes para determinar quais dados são mantidos:</span><span class="sxs-lookup"><span data-stu-id="bc96b-204">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="bc96b-205">**União** une os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="bc96b-205">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="bc96b-206">**Interseção** sobrepõe os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="bc96b-206">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="bc96b-207">Apenas dados que são *comuns* para ambos os grupos é retido no grupo unificado.</span><span class="sxs-lookup"><span data-stu-id="bc96b-207">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="bc96b-208">**Exceto** combina os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="bc96b-208">**Except** combines the two groups.</span></span> <span data-ttu-id="bc96b-209">Apenas dados no grupo A que *não são comuns* a dados no grupo B são retidos.</span><span class="sxs-lookup"><span data-stu-id="bc96b-209">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="bc96b-210">Exibir histórico de processamento e membros do segmento</span><span class="sxs-lookup"><span data-stu-id="bc96b-210">View processing history and segment members</span></span>

<span data-ttu-id="bc96b-211">Você pode ver dados consolidados sobre um segmento revisando seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="bc96b-211">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="bc96b-212">Na página **Segmentos**, selecione o segmento que deseja revisar.</span><span class="sxs-lookup"><span data-stu-id="bc96b-212">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="bc96b-213">A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros.</span><span class="sxs-lookup"><span data-stu-id="bc96b-213">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="bc96b-214">Passe o mouse sobre os pontos de dados para ver a contagem de membros em uma data específica.</span><span class="sxs-lookup"><span data-stu-id="bc96b-214">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="bc96b-215">Você pode atualizar o período da visualização.</span><span class="sxs-lookup"><span data-stu-id="bc96b-215">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="bc96b-216">![Intervalo de tempo do segmento](media/segment-time-range.png "Intervalo de tempo do segmento")</span><span class="sxs-lookup"><span data-stu-id="bc96b-216">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="bc96b-217">A parte inferior contém uma lista dos membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-217">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="bc96b-218">Os campos que aparecem nesta lista são baseados nos atributos das entidades do seu segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-218">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="bc96b-219">A lista é uma visualização dos membros do segmento correspondentes e mostra os 100 primeiros registros do seu segmento, para que você possa avaliá-lo rapidamente e revisar suas definições, se necessário.</span><span class="sxs-lookup"><span data-stu-id="bc96b-219">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="bc96b-220">Para ver todos os registros correspondentes, você precisa [exportar o segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="bc96b-220">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="bc96b-221">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="bc96b-221">Quick segments</span></span>

<span data-ttu-id="bc96b-222">Além do construtor de segmento, há outro caminho para a criação de segmentos.</span><span class="sxs-lookup"><span data-stu-id="bc96b-222">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="bc96b-223">Os segmentos rápidos permitem criar rapidamente segmentos simples com um único operador e com insights instantâneos.</span><span class="sxs-lookup"><span data-stu-id="bc96b-223">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="bc96b-224">Na página **Segmentos**, selecione **Novo** > **Crie rapidamente a partir de**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-224">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="bc96b-225">Selecione a opção **Perfis** para criar um segmento baseado na entidade unificada do Cliente.</span><span class="sxs-lookup"><span data-stu-id="bc96b-225">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="bc96b-226">Selecione a opção **Medidas** para criar um segmento em cada um dos tipos de medidas de Atributo do Cliente que você criou anteriormente na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-226">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="bc96b-227">Selecione a opção **Inteligência** para criar um segmento em torno de uma das entidades de saída que você gerou usando os recursos **Previsões** ou **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-227">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="bc96b-228">Na caixa de diálogo **Novo segmento rápido**, selecione um atributo no menu suspenso **Campo**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-228">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="bc96b-229">O sistema fornecerá algumas informações adicionais que ajudarão a criar melhores segmentos de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="bc96b-229">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="bc96b-230">Para campos categóricos, mostraremos as 10 principais contagens de clientes.</span><span class="sxs-lookup"><span data-stu-id="bc96b-230">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="bc96b-231">Escolha um **Valor** e selecione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-231">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="bc96b-232">Para um atributo numérico, o sistema mostrará qual valor de atributo se enquadra no percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="bc96b-232">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="bc96b-233">Escolha um **Operador** e um **Valor** e selecione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-233">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="bc96b-234">O sistema fornecerá a você um **Tamanho estimado do segmento**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-234">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="bc96b-235">Você pode optar por gerar o segmento definido ou primeiro revisitá-lo para obter um tamanho de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="bc96b-235">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="bc96b-236">![Nome e estimativa para um segmento rápido](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="bc96b-236">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="bc96b-237">Forneça um **Nome** para seu segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-237">Provide a **Name** for your segment.</span></span> <span data-ttu-id="bc96b-238">Se preferir, forneça um **Nome para exibição**.</span><span class="sxs-lookup"><span data-stu-id="bc96b-238">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="bc96b-239">Selecione **Salvar** para criar seu segmento.</span><span class="sxs-lookup"><span data-stu-id="bc96b-239">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="bc96b-240">Depois que o segmento terminar o processamento, você poderá vê-lo como qualquer outro segmento criado.</span><span class="sxs-lookup"><span data-stu-id="bc96b-240">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="bc96b-241">Para os seguintes cenários, recomendamos o uso do construtor de segmentos, em vez do recursos de segmentos recomendados:</span><span class="sxs-lookup"><span data-stu-id="bc96b-241">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="bc96b-242">Criando segmentos com filtros em campos categóricos nos quais o operador é diferente do operador **É**</span><span class="sxs-lookup"><span data-stu-id="bc96b-242">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="bc96b-243">Criando segmentos com filtros em campos numéricos em que o operador é diferente dos operadores **Entre**, **Maior que** e **Menor que**</span><span class="sxs-lookup"><span data-stu-id="bc96b-243">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="bc96b-244">Criação de segmentos com filtros nos campos de tipo de data</span><span class="sxs-lookup"><span data-stu-id="bc96b-244">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc96b-245">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bc96b-245">Next steps</span></span>

<span data-ttu-id="bc96b-246">[Exportar um segmento](export-destinations.md) e explorar o [Cartão de Cliente](customer-card-add-in.md) e os [Conectores](export-power-bi.md) para obter insights no nível do cliente.</span><span class="sxs-lookup"><span data-stu-id="bc96b-246">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]