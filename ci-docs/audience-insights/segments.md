---
title: Criar e gerenciar segmentos
description: Criar segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 03/02/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 4a6e8a3216a2c0738d60247054afa9fc18412f55
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597037"
---
# <a name="create-and-manage-segments"></a><span data-ttu-id="13473-103">Criar e gerenciar segmentos</span><span class="sxs-lookup"><span data-stu-id="13473-103">Create and manage segments</span></span>

<span data-ttu-id="13473-104">Os segmentos permitem agrupar seus clientes com base em atributos demográficos, transacionais ou comportamentais.</span><span class="sxs-lookup"><span data-stu-id="13473-104">Segments let you group your customers based on demographic, transactional, or behavioral attributes.</span></span> <span data-ttu-id="13473-105">Você pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para atingir suas metas de negócios.</span><span class="sxs-lookup"><span data-stu-id="13473-105">You can use segments to target promotional campaigns, sales activities, and customer support actions to achieve your business goals.</span></span>

<span data-ttu-id="13473-106">Você pode definir filtros complexos em torno da entidade Perfil do Cliente e de entidades relacionadas.</span><span class="sxs-lookup"><span data-stu-id="13473-106">You can define complex filters around the Customer Profile entity and its related entities.</span></span> <span data-ttu-id="13473-107">Cada segmento, após o processamento, cria um conjunto de registros do cliente que você pode exportar e executar.</span><span class="sxs-lookup"><span data-stu-id="13473-107">Each segment, after processing, creates a set of customer records that you can export and take action on.</span></span> <span data-ttu-id="13473-108">Alguns [limites de serviço](service-limits.md) se aplicam.</span><span class="sxs-lookup"><span data-stu-id="13473-108">Some [service limits](service-limits.md) apply.</span></span>

<span data-ttu-id="13473-109">Salvo indicação em contrário, todos os segmentos são **Segmentos dinâmicos**, que são atualizados em uma programação recorrente.</span><span class="sxs-lookup"><span data-stu-id="13473-109">Unless stated otherwise, all segments are **Dynamic segments**, which are refreshed on a recurring schedule.</span></span>

<span data-ttu-id="13473-110">O exemplo a seguir ilustra a capacidade de segmentação.</span><span class="sxs-lookup"><span data-stu-id="13473-110">The following example illustrates the segmentation capability.</span></span> <span data-ttu-id="13473-111">Definimos um segmento para clientes que fizeram pedidos de pelo menos US$ 500 em mercadorias nos últimos 90 dias *e* que estão envolvidos em uma chamada de atendimento ao cliente escalonada.</span><span class="sxs-lookup"><span data-stu-id="13473-111">We've defined a segment for customers who ordered at least $500 of goods in the last 90 days *and* who were involved in a customer service call that got escalated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="13473-112">![Vários grupos](media/segmentation-group1-2.png "Vários grupos")</span><span class="sxs-lookup"><span data-stu-id="13473-112">![Multiple groups](media/segmentation-group1-2.png "Multiple groups")</span></span>

## <a name="create-a-new-segment"></a><span data-ttu-id="13473-113">Criar um novo segmento</span><span class="sxs-lookup"><span data-stu-id="13473-113">Create a new segment</span></span>

<span data-ttu-id="13473-114">Os segmentos são gerenciados na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="13473-114">Segments are managed on the **Segments** page.</span></span>

1. <span data-ttu-id="13473-115">Nas informações de público-alvo, vá para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="13473-115">In audience insights, go to the **Segments** page.</span></span>

1. <span data-ttu-id="13473-116">Selecione **Novo** > **Segmento em branco**.</span><span class="sxs-lookup"><span data-stu-id="13473-116">Select **New** > **Blank segment**.</span></span>

1. <span data-ttu-id="13473-117">No painel **Novo segmento**, escolha um tipo de segmento e forneça um **Nome**.</span><span class="sxs-lookup"><span data-stu-id="13473-117">In the **New segment** pane, choose a segment type and provide a **Name**.</span></span>

   <span data-ttu-id="13473-118">Se preferir, forneça um nome para exibição e uma descrição que ajude a identificar o segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-118">Optionally, provide a display name, and a description that helps identifying the segment.</span></span>

1. <span data-ttu-id="13473-119">Selecione **Próximo** para ir até a página **Construtor de segmentos** onde você define um grupo.</span><span class="sxs-lookup"><span data-stu-id="13473-119">Select **Next** to get to the **Segment builder** page where you define a group.</span></span> <span data-ttu-id="13473-120">Um grupo é um conjunto de clientes.</span><span class="sxs-lookup"><span data-stu-id="13473-120">A group is a set of customers.</span></span>

1. <span data-ttu-id="13473-121">Escolha a entidade que tem o atributo pelo qual você deseja segmentar.</span><span class="sxs-lookup"><span data-stu-id="13473-121">Choose the entity that includes the attribute you want to segment by.</span></span>

1. <span data-ttu-id="13473-122">Escolha o atributo pelo qual você fará a segmentação.</span><span class="sxs-lookup"><span data-stu-id="13473-122">Choose the attribute to segment by.</span></span> <span data-ttu-id="13473-123">Este atributo pode ter um dos quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.</span><span class="sxs-lookup"><span data-stu-id="13473-123">This attribute can have one of four value types: numerical, string, date, or Boolean.</span></span>

1. <span data-ttu-id="13473-124">Escolha um operador e um valor para o atributo selecionado.</span><span class="sxs-lookup"><span data-stu-id="13473-124">Choose an operator and a value for the selected attribute.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="13473-125">![Filtro do grupo personalizado](media/customer-group-numbers.png "Filtro do grupo do cliente")</span><span class="sxs-lookup"><span data-stu-id="13473-125">![Custom group filter](media/customer-group-numbers.png "Customer group filter")</span></span>

   |<span data-ttu-id="13473-126">Número</span><span class="sxs-lookup"><span data-stu-id="13473-126">Number</span></span> |<span data-ttu-id="13473-127">Definição</span><span class="sxs-lookup"><span data-stu-id="13473-127">Definition</span></span>  |
   |---------|---------|
   |<span data-ttu-id="13473-128">1</span><span class="sxs-lookup"><span data-stu-id="13473-128">1</span></span>     |<span data-ttu-id="13473-129">Entity</span><span class="sxs-lookup"><span data-stu-id="13473-129">Entity</span></span>          |
   |<span data-ttu-id="13473-130">2</span><span class="sxs-lookup"><span data-stu-id="13473-130">2</span></span>     |<span data-ttu-id="13473-131">Atributo</span><span class="sxs-lookup"><span data-stu-id="13473-131">Attribute</span></span>          |
   |<span data-ttu-id="13473-132">3</span><span class="sxs-lookup"><span data-stu-id="13473-132">3</span></span>    |<span data-ttu-id="13473-133">Operador</span><span class="sxs-lookup"><span data-stu-id="13473-133">Operator</span></span>         |
   |<span data-ttu-id="13473-134">4</span><span class="sxs-lookup"><span data-stu-id="13473-134">4</span></span>    |<span data-ttu-id="13473-135">Valor</span><span class="sxs-lookup"><span data-stu-id="13473-135">Value</span></span>         |

8. <span data-ttu-id="13473-136">Se a entidade estiver conectada à entidade unificada do cliente por meio de [relacionamentos](relationships.md), você precisará definir o caminho do relacionamento para criar um segmento válido.</span><span class="sxs-lookup"><span data-stu-id="13473-136">If the entity is connected to the unified customer entity through [relationships](relationships.md), you need to define the relationship path to create a valid segment.</span></span> <span data-ttu-id="13473-137">Adicione as entidades do caminho do relacionamento até poder selecionar a entidade **Cliente: CustomerInsights** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="13473-137">Add the entities from the relationship path until you can select the **Customer:CustomerInsights** entity from the dropdown.</span></span> <span data-ttu-id="13473-138">Em seguida, escolha **Todos os registros** de cada condição.</span><span class="sxs-lookup"><span data-stu-id="13473-138">Then, choose **All records** for each condition.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="13473-139">![Caminho do relacionamento durante a criação do segmento](media/segments-multiple-relationships.png "Caminho do relacionamento durante a criação do segmento")</span><span class="sxs-lookup"><span data-stu-id="13473-139">![Relationship path during segment creation](media/segments-multiple-relationships.png "Relationship path during segment creation")</span></span>

1. <span data-ttu-id="13473-140">Por padrão, os segmentos geram uma entidade de saída que contém todos os atributos dos perfis de clientes que correspondem aos filtros definidos.</span><span class="sxs-lookup"><span data-stu-id="13473-140">By default, segments generate an output entity that contains all attributes of customer profiles which match the defined filters.</span></span> <span data-ttu-id="13473-141">Se um segmento for baseado em entidades diferentes da entidade *Cliente*, você poderá adicionar mais atributos dessas entidades à entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="13473-141">If a segment is based on other entities than the *Customer* entity, you can add more attributes from these entities to the output entity.</span></span> <span data-ttu-id="13473-142">Selecione **Atributos do projeto** para escolher os atributos que serão anexados à entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="13473-142">Select **Project attributes** to choose the attributes that will be appended to the output entity.</span></span>  

   
   <span data-ttu-id="13473-143">Exemplo: um segmento é baseado em uma entidade que contém dados da atividade do cliente que estão relacionados à entidade *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="13473-143">Example: A segment is based on an entity that contains customer activity data which is related to the *Customer* entity.</span></span> <span data-ttu-id="13473-144">O segmento busca todos os clientes que ligaram para o suporte técnico nos últimos 60 dias.</span><span class="sxs-lookup"><span data-stu-id="13473-144">The segment looks for all customers that called the help desk in the last 60 days.</span></span> <span data-ttu-id="13473-145">Você pode optar por anexar a duração da chamada e o número de chamadas a todos os registros do cliente correspondentes na entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="13473-145">You can choose to append the call duration and the number of calls to all matching customer records in the output entity.</span></span> <span data-ttu-id="13473-146">Essas informações podem ser úteis para enviar um email com links úteis para artigos de ajuda online e perguntas frequentes para clientes que ligam com frequência.</span><span class="sxs-lookup"><span data-stu-id="13473-146">This information might be useful to send an email with helpful links to online help articles and FAQs to customers who called frequently.</span></span>

1. <span data-ttu-id="13473-147">Selecione **Salvar** para salvar seu segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-147">Select **Save** to save your segment.</span></span> <span data-ttu-id="13473-148">Seu segmento será salvo e processado, se todos os requisitos forem validados.</span><span class="sxs-lookup"><span data-stu-id="13473-148">Your segment will be saved and processed if all requirements are validated.</span></span> <span data-ttu-id="13473-149">Caso contrário, ele será salvo como rascunho.</span><span class="sxs-lookup"><span data-stu-id="13473-149">Otherwise, it will be saved as a draft.</span></span>

1. <span data-ttu-id="13473-150">Selecione **Voltar aos segmentos** voltar para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="13473-150">Select **Back to segments** to go back to the **Segments** page.</span></span>

## <a name="manage-existing-segments"></a><span data-ttu-id="13473-151">Gerenciar segmentos existentes</span><span class="sxs-lookup"><span data-stu-id="13473-151">Manage existing segments</span></span>

<span data-ttu-id="13473-152">Na página **Segmentos**, você pode visualizar todos os seus segmentos salvos e gerenciá-los.</span><span class="sxs-lookup"><span data-stu-id="13473-152">On the **Segments** page, you can view all your saved segments and manage them.</span></span>

<span data-ttu-id="13473-153">Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-153">Each segment is represented by a row that includes additional information about the segment.</span></span>

<span data-ttu-id="13473-154">Você pode classificar os segmentos em uma coluna selecionando o cabeçalho da coluna.</span><span class="sxs-lookup"><span data-stu-id="13473-154">You can sort the segments in a column by selecting the column heading.</span></span>

<span data-ttu-id="13473-155">Use a caixa **Pesquisar** no canto superior direito para filtrar os segmentos.</span><span class="sxs-lookup"><span data-stu-id="13473-155">Use the **Search** box in the top-right corner to filter the segments.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="13473-156">![Opções para gerenciar um segmento existente](media/segments-selected-segment.png "Opções para gerenciar um segmento existente")</span><span class="sxs-lookup"><span data-stu-id="13473-156">![Options to manage an existing segment](media/segments-selected-segment.png "Options to manage an existing segment")</span></span>

<span data-ttu-id="13473-157">As seguintes ações estão disponíveis quando você seleciona um segmento:</span><span class="sxs-lookup"><span data-stu-id="13473-157">The following action are available when you select a segment:</span></span>

- <span data-ttu-id="13473-158">**Exiba** os detalhes do segmento, incluindo a tendência de contagem de membros, uma visualização dos membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-158">**View** the segment details, including member count trend a preview of segment members.</span></span>
- <span data-ttu-id="13473-159">**Edite** o segmento para alterar suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="13473-159">**Edit** the segment to change its properties.</span></span>
- <span data-ttu-id="13473-160">**Criar duplicidade** de um segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-160">**Create duplicate** of a segment.</span></span> <span data-ttu-id="13473-161">Você pode optar por editar suas propriedades imediatamente ou simplesmente salvar a duplicidade.</span><span class="sxs-lookup"><span data-stu-id="13473-161">You can choose to edit its properties right away or simply save the duplicate.</span></span>
- <span data-ttu-id="13473-162">**Atualize** o segmento para incluir os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="13473-162">**Refresh** the segment to include the latest data.</span></span>
- <span data-ttu-id="13473-163">**Ative** ou **desative** o segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-163">**Activate** or **Deactivate** the segment.</span></span> <span data-ttu-id="13473-164">Os segmentos têm dois estados possíveis: ativo ou inativo.</span><span class="sxs-lookup"><span data-stu-id="13473-164">Segments have two possible states - active or inactive.</span></span> <span data-ttu-id="13473-165">Esses estados são úteis ao editar um segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-165">These states come in handy when editing a segment.</span></span> <span data-ttu-id="13473-166">Para segmentos inativos, a definição do segmento existe, mas ainda não contém nenhum cliente.</span><span class="sxs-lookup"><span data-stu-id="13473-166">For inactive segments, the segment definition exists but it doesn't contain any customers yet.</span></span> <span data-ttu-id="13473-167">Quando você ativa um segmento, o estado dele muda de "inativo" para "ativo" e ele começa a procurar clientes que correspondam à definição do segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-167">When you activate a segment, its state changes from 'inactive' to 'active" and it starts looking for customers that match the segment definition.</span></span> <span data-ttu-id="13473-168">Se uma [atualização programada](system.md#schedule-tab) estiver configurada, os segmentos inativos terão o **Status** listado como **Ignorado**, indicando que uma atualização nem mesmo foi tentada.</span><span class="sxs-lookup"><span data-stu-id="13473-168">If a [scheduled refresh](system.md#schedule-tab) is configured, inactive segments have the **Status** listed as **Skipped**, indicating that a refresh wasn't even attempted.</span></span> <span data-ttu-id="13473-169">Quando um segmento inativo for ativado, ele será atualizado e incluído nas atualizações agendadas.</span><span class="sxs-lookup"><span data-stu-id="13473-169">When an inactive segment is activated, it will refresh and will be included in scheduled refreshes.</span></span>
  <span data-ttu-id="13473-170">Como alternativa, você pode usar a funcionalidade **Agendar mais tarde** na lista suspensa **Ativar/desativar** para especificar data e hora futuras para a ativação e desativação de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="13473-170">Alternatively, you can use the **Schedule later** functionality in the **Activate/Deactivate** dropdown to specify a future date and time for activation and deactivation of a particular segment.</span></span>
- <span data-ttu-id="13473-171">**Renomeie** o segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-171">**Rename** the segment.</span></span>
- <span data-ttu-id="13473-172">**Baixe** a lista de membros como um arquivo .CSV.</span><span class="sxs-lookup"><span data-stu-id="13473-172">**Download** the list of members as a .CSV file.</span></span>
- <span data-ttu-id="13473-173">A opção **Adicionar a** envia a lista de IDs do cliente no segmento para processamento em outro aplicativo.</span><span class="sxs-lookup"><span data-stu-id="13473-173">**Add to** option sends the list of customer IDs in the segment for processing in another application.</span></span>
- <span data-ttu-id="13473-174">**Exclua** o segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-174">**Delete** the segment.</span></span>

## <a name="refresh-segments"></a><span data-ttu-id="13473-175">Atualizar segmentos</span><span class="sxs-lookup"><span data-stu-id="13473-175">Refresh segments</span></span>

<span data-ttu-id="13473-176">Você pode atualizar todos os segmentos de uma vez, selecionando **Atualizar tudo** na página **Segmentos** ou você pode atualizar um ou vários segmentos ao selecioná-los e escolher **Atualizar** nas opções.</span><span class="sxs-lookup"><span data-stu-id="13473-176">You can refresh all segments at once by selecting **Refresh all** on the **Segments** page or you can refresh one or multiple segments when you select them and choose **Refresh** in from the options.</span></span> <span data-ttu-id="13473-177">Como alternativa, você pode configurar uma atualização recorrente em **Admin** > **Sistema** > **Agendar**.</span><span class="sxs-lookup"><span data-stu-id="13473-177">Alternatively, you can configure a recurring refresh on **Admin** > **System** > **Schedule**.</span></span>

> [!TIP]
> <span data-ttu-id="13473-178">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="13473-178">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="13473-179">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="13473-179">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="13473-180">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="13473-180">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="13473-181">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="13473-181">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="download-and-export-segments"></a><span data-ttu-id="13473-182">Baixar e exportar segmentos</span><span class="sxs-lookup"><span data-stu-id="13473-182">Download and export segments</span></span>

<span data-ttu-id="13473-183">Você pode baixar seus segmentos para um arquivo CSV ou exportá-los para o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="13473-183">You can download your segments to a CSV file or export them to Dynamics 365 Sales.</span></span>

### <a name="download-segments-to-a-csv-file"></a><span data-ttu-id="13473-184">Baixar segmentos para um arquivo CSV</span><span class="sxs-lookup"><span data-stu-id="13473-184">Download segments to a CSV file</span></span>

1. <span data-ttu-id="13473-185">Nas informações de público-alvo, vá para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="13473-185">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="13473-186">Selecione as reticências no bloco de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="13473-186">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="13473-187">Selecione **Baixar como CSV** da lista suspensa de ações.</span><span class="sxs-lookup"><span data-stu-id="13473-187">Select **Download as CSV** from the actions drop-down list.</span></span>

### <a name="export-segments-to-dynamics-365-sales"></a><span data-ttu-id="13473-188">Exportar segmentos para o Dynamics 365 Sales</span><span class="sxs-lookup"><span data-stu-id="13473-188">Export segments to Dynamics 365 Sales</span></span>

<span data-ttu-id="13473-189">Antes de exportar segmentos para o Dynamics 365 Sales, um administrador precisa [criar o destino de exportação](export-destinations.md) para o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="13473-189">Before exporting segments to Dynamics 365 Sales, an admin needs to [create the export destination](export-destinations.md) for Dynamics 365 Sales.</span></span>

1. <span data-ttu-id="13473-190">Nas informações de público-alvo, vá para a página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="13473-190">In audience insights, go to the **Segments** page.</span></span>

2. <span data-ttu-id="13473-191">Selecione as reticências no bloco de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="13473-191">Select the ellipsis in a specific segment's tile.</span></span>

3. <span data-ttu-id="13473-192">Selecione **Adicionar a** na lista suspensa de ações e selecione o destino de exportação para o qual deseja enviar os dados.</span><span class="sxs-lookup"><span data-stu-id="13473-192">Select **Add to** from the actions drop-down list and select the export destination you want to send the data to.</span></span>

## <a name="draft-mode-for-segments"></a><span data-ttu-id="13473-193">Modo de rascunho para segmentos</span><span class="sxs-lookup"><span data-stu-id="13473-193">Draft mode for segments</span></span>

<span data-ttu-id="13473-194">Se nem todos os requisitos para processar um segmento forem atendidos, você poderá salvar o segmento como rascunho e acessá-lo na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="13473-194">If not all requirements to process a segment are met, you can save the segment as a draft and access it from the **Segments** page.</span></span>

<span data-ttu-id="13473-195">Ele será salvo como um segmento inativo e não poderá ser ativado até que seja válido.</span><span class="sxs-lookup"><span data-stu-id="13473-195">It will be saved as an inactive segment, and can't be activated it until it's valid.</span></span>

## <a name="add-more-conditions-to-a-group"></a><span data-ttu-id="13473-196">Adicionar mais condições a um grupo</span><span class="sxs-lookup"><span data-stu-id="13473-196">Add more conditions to a group</span></span>

<span data-ttu-id="13473-197">Para adicionar mais condições a um grupo, você pode usar dois operadores lógicos:</span><span class="sxs-lookup"><span data-stu-id="13473-197">To add more conditions to a group, you can use two logical operators:</span></span>

- <span data-ttu-id="13473-198">Operador **E**: Ambas as condições devem ser atendidas como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="13473-198">**AND** operator: Both conditions must be met as part of the segmentation process.</span></span> <span data-ttu-id="13473-199">Esta opção é mais útil quando você define condições em diferentes entidades.</span><span class="sxs-lookup"><span data-stu-id="13473-199">This option is most useful when you define conditions across different entities.</span></span>

- <span data-ttu-id="13473-200">Operador **OU**: Qualquer uma das condições precisa ser atendida como parte do processo de segmentação.</span><span class="sxs-lookup"><span data-stu-id="13473-200">**OR** operator: Either one of the conditions needs to be met as part of the segmentation process.</span></span> <span data-ttu-id="13473-201">Esta opção é mais útil quando você define várias condições para a mesma entidade.</span><span class="sxs-lookup"><span data-stu-id="13473-201">This option is most useful when you define multiple conditions for the same entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="13473-202">![Operador OU em que uma das condições precisa ser atendida](media/segmentation-either-condition.png "Operador OU em que uma das condições precisa ser atendida")</span><span class="sxs-lookup"><span data-stu-id="13473-202">![OR operator where either condition needs to be met](media/segmentation-either-condition.png "OR operator where either condition needs to be met")</span></span>

<span data-ttu-id="13473-203">Atualmente é possível aninhar um operador **OU** sob um operador **E**, mas não o contrário.</span><span class="sxs-lookup"><span data-stu-id="13473-203">It's currently possible to nest an **OR** operator under an **AND** operator, but not the other way around.</span></span>

## <a name="combine-multiple-groups"></a><span data-ttu-id="13473-204">Combinar vários grupos</span><span class="sxs-lookup"><span data-stu-id="13473-204">Combine multiple groups</span></span>

<span data-ttu-id="13473-205">Cada grupo produz um conjunto específico de clientes.</span><span class="sxs-lookup"><span data-stu-id="13473-205">Each group produces a specific set of customers.</span></span> <span data-ttu-id="13473-206">Você pode combinar esses grupos para incluir os clientes necessários para o seu caso de negócios.</span><span class="sxs-lookup"><span data-stu-id="13473-206">You can combine these groups to include the customers required for your business case.</span></span>

1. <span data-ttu-id="13473-207">Nos insights de público-alvo, vá para a página **Segmentos** e selecione um segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-207">In audience insights, go to the **Segments** page and select a segment.</span></span>

2. <span data-ttu-id="13473-208">Selecione **Adicionar Grupo**.</span><span class="sxs-lookup"><span data-stu-id="13473-208">Select **Add Group**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="13473-209">![Grupo de clientes adicionar grupo](media/customer-group-add-group.png "Grupo de clientes adicionar grupo")</span><span class="sxs-lookup"><span data-stu-id="13473-209">![Customer group add group](media/customer-group-add-group.png "Customer group add group")</span></span>

3. <span data-ttu-id="13473-210">Selecione um dos seguintes operadores definidos: **União**, **Interseção** ou **Exceto**.</span><span class="sxs-lookup"><span data-stu-id="13473-210">Select one of the following set operators: **Union**, **Intersect**, or **Except**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="13473-211">![Grupo de clientes adicionar união](media/customer-group-union.png "Grupo de clientes adicionar união")</span><span class="sxs-lookup"><span data-stu-id="13473-211">![Customer group add union](media/customer-group-union.png "Customer group add union")</span></span>

   <span data-ttu-id="13473-212">Selecione um operador definido para definir um novo grupo.</span><span class="sxs-lookup"><span data-stu-id="13473-212">Select a set operator to define a new group.</span></span> <span data-ttu-id="13473-213">Salve grupos diferentes para determinar quais dados são mantidos:</span><span class="sxs-lookup"><span data-stu-id="13473-213">Save different groups to determine what data gets retained:</span></span>

   - <span data-ttu-id="13473-214">**União** une os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="13473-214">**Union** unites the two groups.</span></span>

   - <span data-ttu-id="13473-215">**Interseção** sobrepõe os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="13473-215">**Intersect** overlaps the two groups.</span></span> <span data-ttu-id="13473-216">Apenas dados que são *comuns* para ambos os grupos é retido no grupo unificado.</span><span class="sxs-lookup"><span data-stu-id="13473-216">Only data that *is common* to both groups is retained in the unified group.</span></span>

   - <span data-ttu-id="13473-217">**Exceto** combina os dois grupos.</span><span class="sxs-lookup"><span data-stu-id="13473-217">**Except** combines the two groups.</span></span> <span data-ttu-id="13473-218">Apenas dados no grupo A que *não são comuns* a dados no grupo B são retidos.</span><span class="sxs-lookup"><span data-stu-id="13473-218">Only data in group A that *is not common* to data in group B is retained.</span></span>

## <a name="view-processing-history-and-segment-members"></a><span data-ttu-id="13473-219">Exibir histórico de processamento e membros do segmento</span><span class="sxs-lookup"><span data-stu-id="13473-219">View processing history and segment members</span></span>

<span data-ttu-id="13473-220">Você pode ver dados consolidados sobre um segmento revisando seus detalhes.</span><span class="sxs-lookup"><span data-stu-id="13473-220">You can see consolidated data about a segment by reviewing its details.</span></span>

<span data-ttu-id="13473-221">Na página **Segmentos**, selecione o segmento que deseja revisar.</span><span class="sxs-lookup"><span data-stu-id="13473-221">On the **Segments** page, select the segment you want to review.</span></span>

<span data-ttu-id="13473-222">A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros.</span><span class="sxs-lookup"><span data-stu-id="13473-222">The upper part of the page includes a trend graph that visualizes changes in member count.</span></span> <span data-ttu-id="13473-223">Passe o mouse sobre os pontos de dados para ver a contagem de membros em uma data específica.</span><span class="sxs-lookup"><span data-stu-id="13473-223">Hover over data points to see the member count on a specific date.</span></span>

<span data-ttu-id="13473-224">Você pode atualizar o período da visualização.</span><span class="sxs-lookup"><span data-stu-id="13473-224">You can update the time frame of the visualization.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="13473-225">![Intervalo de tempo do segmento](media/segment-time-range.png "Intervalo de tempo do segmento")</span><span class="sxs-lookup"><span data-stu-id="13473-225">![Segment time range](media/segment-time-range.png "Segment time range")</span></span>

<span data-ttu-id="13473-226">A parte inferior contém uma lista dos membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-226">The lower part contains a list of the segment members.</span></span>

> [!NOTE]
> <span data-ttu-id="13473-227">Os campos que aparecem nesta lista são baseados nos atributos das entidades do seu segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-227">Fields that appear in this list are based on the attributes of your segment's entities.</span></span>
>
><span data-ttu-id="13473-228">A lista é uma visualização dos membros do segmento correspondentes e mostra os 100 primeiros registros do seu segmento, para que você possa avaliá-lo rapidamente e revisar suas definições, se necessário.</span><span class="sxs-lookup"><span data-stu-id="13473-228">The list is a preview of the matching segment members and shows the first 100 records of your segment so that you can quickly evaluate it and review its definitions if needed.</span></span> <span data-ttu-id="13473-229">Para ver todos os registros correspondentes, você precisa [exportar o segmento](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="13473-229">To see all matching records, you need to [export the segment](export-destinations.md).</span></span>

## <a name="quick-segments"></a><span data-ttu-id="13473-230">Segmentos rápidos</span><span class="sxs-lookup"><span data-stu-id="13473-230">Quick segments</span></span>

<span data-ttu-id="13473-231">Além do construtor de segmento, há outro caminho para a criação de segmentos.</span><span class="sxs-lookup"><span data-stu-id="13473-231">In addition to the segment builder, there's another path for creating segments.</span></span> <span data-ttu-id="13473-232">Os segmentos rápidos permitem criar rapidamente segmentos simples com um único operador e com insights instantâneos.</span><span class="sxs-lookup"><span data-stu-id="13473-232">Quick segments let you build simple segments with a single operator quickly and with instant insights.</span></span>

1. <span data-ttu-id="13473-233">Na página **Segmentos**, selecione **Novo** > **Crie rapidamente a partir de**.</span><span class="sxs-lookup"><span data-stu-id="13473-233">On the **Segments** page, select **New** > **Quickly create from**.</span></span>

   - <span data-ttu-id="13473-234">Selecione a opção **Perfis** para criar um segmento baseado na entidade unificada do Cliente.</span><span class="sxs-lookup"><span data-stu-id="13473-234">Select the **Profiles** option to build a segment that is based on the unified Customer entity.</span></span>
   - <span data-ttu-id="13473-235">Selecione a opção **Medidas** para criar um segmento em cada um dos tipos de medidas de Atributo do Cliente que você criou anteriormente na página **Medidas**.</span><span class="sxs-lookup"><span data-stu-id="13473-235">Select the **Measures** option to build a segment around each of the Customer Attribute type of measures you have previously created on the **Measures** page.</span></span>
   - <span data-ttu-id="13473-236">Selecione a opção **Inteligência** para criar um segmento em torno de uma das entidades de saída que você gerou usando os recursos **Previsões** ou **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="13473-236">Select the **Intelligence** option to build a segment around one of the output entities you generated using either the **Predictions** or **Custom Models** capabilities.</span></span>

2. <span data-ttu-id="13473-237">Na caixa de diálogo **Novo segmento rápido**, selecione um atributo no menu suspenso **Campo**.</span><span class="sxs-lookup"><span data-stu-id="13473-237">In the **New quick segment** dialog box, select an attribute from the **Field** dropdown.</span></span>

3. <span data-ttu-id="13473-238">O sistema fornecerá algumas informações adicionais que ajudarão a criar melhores segmentos de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="13473-238">The system will provide some additional insights that help you create better segments of your customers.</span></span>
   - <span data-ttu-id="13473-239">Para campos categóricos, mostraremos as 10 principais contagens de clientes.</span><span class="sxs-lookup"><span data-stu-id="13473-239">For categorical fields, we'll show 10 top customer counts.</span></span> <span data-ttu-id="13473-240">Escolha um **Valor** e selecione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="13473-240">Choose a **Value** and select **Review**.</span></span>

   - <span data-ttu-id="13473-241">Para um atributo numérico, o sistema mostrará qual valor de atributo se enquadra no percentil de cada cliente.</span><span class="sxs-lookup"><span data-stu-id="13473-241">For a numerical attribute, the system will show what attribute value falls under each customer's percentile.</span></span> <span data-ttu-id="13473-242">Escolha um **Operador** e um **Valor** e selecione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="13473-242">Choose an **Operator** and a **Value**, then select **Review**.</span></span>

4. <span data-ttu-id="13473-243">O sistema fornecerá a você um **Tamanho estimado do segmento**.</span><span class="sxs-lookup"><span data-stu-id="13473-243">The system will provide you with an **Estimated segment size**.</span></span> <span data-ttu-id="13473-244">Você pode optar por gerar o segmento definido ou primeiro revisitá-lo para obter um tamanho de segmento diferente.</span><span class="sxs-lookup"><span data-stu-id="13473-244">You can choose whether to generate the segment you've defined, or first revisit it to get a different segment size.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="13473-245">![Nome e estimativa para um segmento rápido](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")</span><span class="sxs-lookup"><span data-stu-id="13473-245">![Name and estimation for a quick segment](media/quick-segment-name.png "Name and estimation for a quick segment")</span></span>

5. <span data-ttu-id="13473-246">Forneça um **Nome** para seu segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-246">Provide a **Name** for your segment.</span></span> <span data-ttu-id="13473-247">Se preferir, forneça um **Nome para exibição**.</span><span class="sxs-lookup"><span data-stu-id="13473-247">Optionally, provide a **Display name**.</span></span>

6. <span data-ttu-id="13473-248">Selecione **Salvar** para criar seu segmento.</span><span class="sxs-lookup"><span data-stu-id="13473-248">Select **Save** to create your segment.</span></span>

7. <span data-ttu-id="13473-249">Depois que o segmento terminar o processamento, você poderá vê-lo como qualquer outro segmento criado.</span><span class="sxs-lookup"><span data-stu-id="13473-249">After the segment has finished processing, you can view it like any other segment you've created.</span></span>

<span data-ttu-id="13473-250">Para os seguintes cenários, recomendamos o uso do construtor de segmentos, em vez do recursos de segmentos recomendados:</span><span class="sxs-lookup"><span data-stu-id="13473-250">For the following scenarios, we advise using the segment builder rather than the recommended segments capability:</span></span>

- <span data-ttu-id="13473-251">Criando segmentos com filtros em campos categóricos nos quais o operador é diferente do operador **É**</span><span class="sxs-lookup"><span data-stu-id="13473-251">Creating segments with filters on categorical fields where the operator is different than the **Is** operator</span></span>
- <span data-ttu-id="13473-252">Criando segmentos com filtros em campos numéricos em que o operador é diferente dos operadores **Entre**, **Maior que** e **Menor que**</span><span class="sxs-lookup"><span data-stu-id="13473-252">Creating segments with filters on numerical fields where the operator is different than the **Between**, **Greater than**, and **Less than** operators</span></span>
- <span data-ttu-id="13473-253">Criação de segmentos com filtros nos campos de tipo de data</span><span class="sxs-lookup"><span data-stu-id="13473-253">Creating segments with filters on date type fields</span></span>

## <a name="next-steps"></a><span data-ttu-id="13473-254">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="13473-254">Next steps</span></span>

<span data-ttu-id="13473-255">[Exportar um segmento](export-destinations.md) e explorar o [Cartão de Cliente](customer-card-add-in.md) e os [Conectores](export-power-bi.md) para obter insights no nível do cliente.</span><span class="sxs-lookup"><span data-stu-id="13473-255">[Export a segment](export-destinations.md) and explore the [Customer Card](customer-card-add-in.md) and [Connectors](export-power-bi.md) to get insights on the customer level.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]