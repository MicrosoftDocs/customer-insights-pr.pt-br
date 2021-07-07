---
title: Mesclar entidades na unificação de dados
description: Mescle entidades para criar perfis de clientes unificados.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 86ab3cefa70e5fab4bdb27cde363adee26efee4c
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305608"
---
# <a name="merge-entities"></a><span data-ttu-id="57635-103">Mesclar entidades</span><span class="sxs-lookup"><span data-stu-id="57635-103">Merge entities</span></span>

<span data-ttu-id="57635-104">A fase de mesclagem na última fase no processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="57635-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="57635-105">Seu objetivo é reconciliar dados conflitantes.</span><span class="sxs-lookup"><span data-stu-id="57635-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="57635-106">Exemplos de dados conflitantes podem incluir um nome de cliente encontrado em dois de seus conjuntos de dados, mas que mostra um pouco diferente em cada um ("Grant Marshall" versus "Grant Marshal") ou um número de telefone que difere no formato (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="57635-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="57635-107">A mesclagem desses pontos de dados conflitantes é feita atributo a atributo.</span><span class="sxs-lookup"><span data-stu-id="57635-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

:::image type="content" source="media/merge-fields-page.png" alt-text="Página da mesclagem no processo de unificação de dados mostrando a tabela com campos mesclados que definem o perfil unificado do cliente.":::

<span data-ttu-id="57635-109">Depois de concluir a [fase de correspondência](match-entities.md), você inicia a fase de mesclagem selecionando o bloco **Mesclar** na página **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="57635-109">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="57635-110">Revisar recomendações do sistema</span><span class="sxs-lookup"><span data-stu-id="57635-110">Review system recommendations</span></span>

<span data-ttu-id="57635-111">Em **Dados** > **Unificar** > **Mesclar**, você escolhe e exclui atributos para mesclar dentro de sua entidade de perfil unificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="57635-111">On **Data** > **Unify** > **Merge**, you choose and exclude attributes to merge within your unified customer profile entity.</span></span> <span data-ttu-id="57635-112">O perfil unificado do cliente é o resultado do processo de unificação dos dados.</span><span class="sxs-lookup"><span data-stu-id="57635-112">The unified customer profile is the result of the data unification process.</span></span> <span data-ttu-id="57635-113">Alguns atributos são mesclados automaticamente pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="57635-113">Some attributes are automatically merged by the system.</span></span>

<span data-ttu-id="57635-114">Para ver os atributos incluídos em um de seus atributos mesclados automaticamente, selecione esse atributo mesclado na guia **Campos do cliente** da tabela.</span><span class="sxs-lookup"><span data-stu-id="57635-114">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute in the **Customer fields** tab of the table.</span></span> <span data-ttu-id="57635-115">Os atributos que compõem esse atributo mesclado aparecem em duas novas linhas abaixo do atributo mesclado.</span><span class="sxs-lookup"><span data-stu-id="57635-115">The attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

## <a name="separate-rename-exclude-and-edit-merged-fields"></a><span data-ttu-id="57635-116">Separar, renomear, excluir e editar campos mesclados</span><span class="sxs-lookup"><span data-stu-id="57635-116">Separate, rename, exclude, and edit merged fields</span></span>

<span data-ttu-id="57635-117">Você pode mudar a forma como o sistema processa atributos mesclados para gerar o perfil unificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="57635-117">You can change how the system processes merged attributes to generate the unified customer profile.</span></span> <span data-ttu-id="57635-118">Selecione **Mostrar mais** e escolha o que você quer alterar.</span><span class="sxs-lookup"><span data-stu-id="57635-118">Select **Show more** and choose what you want to change.</span></span>

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opções no menu suspenso Mostrar mais para gerenciar atributos mesclados.":::

<span data-ttu-id="57635-120">Para obter mais informações, consulte as seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="57635-120">For more information, see the following sections.</span></span>

## <a name="separate-merged-fields"></a><span data-ttu-id="57635-121">Separar campos mesclados</span><span class="sxs-lookup"><span data-stu-id="57635-121">Separate merged fields</span></span>

<span data-ttu-id="57635-122">Para separar os campos mesclados, localize o atributo na tabela.</span><span class="sxs-lookup"><span data-stu-id="57635-122">To separate merged fields, find the attribute in the table.</span></span> <span data-ttu-id="57635-123">Os campos separados aparecem como pontos de dados individuais no perfil unificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="57635-123">Separated fields show as individual data points on the unified customer profile.</span></span> 

1. <span data-ttu-id="57635-124">Selecione o campo mesclado.</span><span class="sxs-lookup"><span data-stu-id="57635-124">Select the merged field.</span></span>
  
1. <span data-ttu-id="57635-125">Selecione **Mostrar mais** e escolha **Campos separados**.</span><span class="sxs-lookup"><span data-stu-id="57635-125">Select **Show more** and choose **Separate fields**.</span></span>
 
1. <span data-ttu-id="57635-126">Confirme a separação.</span><span class="sxs-lookup"><span data-stu-id="57635-126">Confirm the separation.</span></span>

1. <span data-ttu-id="57635-127">Selecione **Salvar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="57635-127">Select **Save** and **Run** to process the changes.</span></span>

## <a name="rename-merged-fields"></a><span data-ttu-id="57635-128">Renomear campos mesclados</span><span class="sxs-lookup"><span data-stu-id="57635-128">Rename merged fields</span></span>

<span data-ttu-id="57635-129">Altere o nome de exibição dos atributos mesclados.</span><span class="sxs-lookup"><span data-stu-id="57635-129">Change the display name of merged attributes.</span></span> <span data-ttu-id="57635-130">Não é possível alterar o nome da entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="57635-130">You can't change the name of the output entity.</span></span>

1. <span data-ttu-id="57635-131">Selecione o campo mesclado.</span><span class="sxs-lookup"><span data-stu-id="57635-131">Select the merged field.</span></span>
  
1. <span data-ttu-id="57635-132">Selecione **Mostrar mais** e escolha **Renomear**.</span><span class="sxs-lookup"><span data-stu-id="57635-132">Select **Show more** and choose **Rename**.</span></span>

1. <span data-ttu-id="57635-133">Confirme o nome de exibição alterado.</span><span class="sxs-lookup"><span data-stu-id="57635-133">Confirm the changed display name.</span></span> 

1. <span data-ttu-id="57635-134">Selecione **Salvar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="57635-134">Select **Save** and **Run** to process the changes.</span></span>

## <a name="exclude-merged-fields"></a><span data-ttu-id="57635-135">Excluir campos mesclados</span><span class="sxs-lookup"><span data-stu-id="57635-135">Exclude merged fields</span></span>

<span data-ttu-id="57635-136">Exclua um atributo do perfil unificado do cliente.</span><span class="sxs-lookup"><span data-stu-id="57635-136">Exclude an attribute from the unified customer profile.</span></span> <span data-ttu-id="57635-137">Se o campo for usado em outros processos, por exemplo, em um segmento, remova-o desses processos antes de excluí-lo do perfil do cliente.</span><span class="sxs-lookup"><span data-stu-id="57635-137">If the field is used in other processes, for example in a segment, remove it from these processes before excluding it from the customer profile.</span></span> 

1. <span data-ttu-id="57635-138">Selecione o campo mesclado.</span><span class="sxs-lookup"><span data-stu-id="57635-138">Select the merged field.</span></span>
  
1. <span data-ttu-id="57635-139">Selecione **Mostrar mais** e escolha **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="57635-139">Select **Show more** and choose **Exclude**.</span></span>

1. <span data-ttu-id="57635-140">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="57635-140">Confirm the exclusion.</span></span>

1. <span data-ttu-id="57635-141">Selecione **Salvar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="57635-141">Select **Save** and **Run** to process the changes.</span></span> 

<span data-ttu-id="57635-142">Na página **Meslar**, selecione **Campos excluídos** para ver a lista de todos os campos excluídos.</span><span class="sxs-lookup"><span data-stu-id="57635-142">On the **Merge** page, select **Excluded fields** to see the list of all excluded fields.</span></span> <span data-ttu-id="57635-143">Este painel lhe permite adicionar novamente campos excluídos.</span><span class="sxs-lookup"><span data-stu-id="57635-143">This pane lets you add excluded fields back.</span></span>

## <a name="manually-combine-fields"></a><span data-ttu-id="57635-144">Combinar campos manualmente</span><span class="sxs-lookup"><span data-stu-id="57635-144">Manually combine fields</span></span>

<span data-ttu-id="57635-145">Especifique um atributo mesclado manualmente.</span><span class="sxs-lookup"><span data-stu-id="57635-145">Specify a merged attribute manually.</span></span> 

1. <span data-ttu-id="57635-146">Na página **Mesclar**, selecione **Combinar campos**.</span><span class="sxs-lookup"><span data-stu-id="57635-146">On the **Merge** page, select **Combine fields**.</span></span>

1. <span data-ttu-id="57635-147">Forneça um **Nome** e um **Nome do campo de saída**.</span><span class="sxs-lookup"><span data-stu-id="57635-147">Provide a **Name** and an **Output field name**.</span></span>

1. <span data-ttu-id="57635-148">Escolha um campo para adicionar.</span><span class="sxs-lookup"><span data-stu-id="57635-148">Choose a field to add.</span></span> <span data-ttu-id="57635-149">Selecione **Adicionar campos** para combinar outros campos.</span><span class="sxs-lookup"><span data-stu-id="57635-149">Select **Add fields** to combine more fields.</span></span>

1. <span data-ttu-id="57635-150">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="57635-150">Confirm the exclusion.</span></span>

1. <span data-ttu-id="57635-151">Selecione **Salvar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="57635-151">Select **Save** and **Run** to process the changes.</span></span> 

## <a name="change-the-order-of-fields"></a><span data-ttu-id="57635-152">Alterar a ordem dos campos</span><span class="sxs-lookup"><span data-stu-id="57635-152">Change the order of fields</span></span>

<span data-ttu-id="57635-153">Algumas entidades contêm mais detalhes que outras.</span><span class="sxs-lookup"><span data-stu-id="57635-153">Some entities contain more details than others.</span></span> <span data-ttu-id="57635-154">Se uma entidade tiver os dados mais recentes sobre um campo, você pode priorizá-los sobre outras entidades ao mesclar valores.</span><span class="sxs-lookup"><span data-stu-id="57635-154">If an entity includes the latest data about a field, you can prioritize it over other entities when merging values.</span></span>

1. <span data-ttu-id="57635-155">Selecione o campo mesclado.</span><span class="sxs-lookup"><span data-stu-id="57635-155">Select the merged field.</span></span>
  
1. <span data-ttu-id="57635-156">Selecione **Mostrar mais** e escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="57635-156">Select **Show more** and choose **Edit**.</span></span>

1. <span data-ttu-id="57635-157">No painel **Combinar campos**, selecione **Mover para cima/para baixo** para definir a ordem ou arraste e solte-os na posição desejada.</span><span class="sxs-lookup"><span data-stu-id="57635-157">In the **Combine fields** pane, select **Move up/down** to set the order or drag and drop them in the desired position.</span></span>

1. <span data-ttu-id="57635-158">Confirme a alteração.</span><span class="sxs-lookup"><span data-stu-id="57635-158">Confirm the change.</span></span>

1. <span data-ttu-id="57635-159">Selecione **Salvar** e **Executar** para processar as alterações.</span><span class="sxs-lookup"><span data-stu-id="57635-159">Select **Save** and **Run** to process the changes.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="57635-160">Execute sua mesclagem</span><span class="sxs-lookup"><span data-stu-id="57635-160">Run your merge</span></span>

<span data-ttu-id="57635-161">Quer você mescle atributos manualmente ou permita que o sistema os mescle, sempre é possível executar sua mesclagem.</span><span class="sxs-lookup"><span data-stu-id="57635-161">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="57635-162">Selecione **Executar** na página **Mesclar** para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="57635-162">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="57635-163">![Mesclagem de dados Salvar e Executar](media/configure-data-merge-save-run.png "Mesclagem de dados Salvar e Executar")</span><span class="sxs-lookup"><span data-stu-id="57635-163">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="57635-164">Escolha **Executar somente Mesclagem** se você só quiser ver a saída refletida na entidade unificada do cliente.</span><span class="sxs-lookup"><span data-stu-id="57635-164">Choose **Run only Merge** if you only want to see the output reflected in the unified customer entity.</span></span> <span data-ttu-id="57635-165">Os processos posteriores serão atualizados conforme [definida agenda de atualização](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57635-165">Downstream processes will be refreshed as [defined in the refresh schedule](system.md#schedule-tab).</span></span>

<span data-ttu-id="57635-166">Escolha **Executar processos de mesclagem e posteriores** para atualizar o sistema com suas alterações.</span><span class="sxs-lookup"><span data-stu-id="57635-166">Choose **Run Merge and downstream processes** to refresh the system with your changes.</span></span> <span data-ttu-id="57635-167">Todos os processos, incluindo enriquecimento, segmentos e medidas, serão executados novamente automaticamente.</span><span class="sxs-lookup"><span data-stu-id="57635-167">All processes, including enrichment, segments, and measures will rerun automatically.</span></span> <span data-ttu-id="57635-168">Após o término de todos os processos posteriores, os perfis do cliente refletirão as alterações.</span><span class="sxs-lookup"><span data-stu-id="57635-168">After all downstream processes have completed, the customer profiles reflect any changes you made.</span></span>

<span data-ttu-id="57635-169">Para fazer mais alterações e executar a etapa novamente, cancele uma mesclagem em andamento.</span><span class="sxs-lookup"><span data-stu-id="57635-169">To make more changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="57635-170">Selecione **Atualizando...** e selecione **Cancelar o trabalho** no painel lateral exibido.</span><span class="sxs-lookup"><span data-stu-id="57635-170">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

> [!TIP]
> <span data-ttu-id="57635-171">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="57635-171">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="57635-172">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="57635-172">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="57635-173">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="57635-173">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="57635-174">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="57635-174">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="57635-175">Próxima Etapa</span><span class="sxs-lookup"><span data-stu-id="57635-175">Next Step</span></span>

<span data-ttu-id="57635-176">Configurar [atividades](activities.md), [enriquecimento](enrichment-hub.md) ou [relacionamentos](relationships.md) para obter mais informações sobre seus clientes.</span><span class="sxs-lookup"><span data-stu-id="57635-176">Configure [activities](activities.md), [enrichment](enrichment-hub.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="57635-177">Se você já tiver configurado atividades, enriquecimento ou segmentos, eles serão processados automaticamente para usar os dados mais recentes do cliente.</span><span class="sxs-lookup"><span data-stu-id="57635-177">If you already configured activities, enrichment, or segments, they'll be processed automatically to use the latest customer data.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
