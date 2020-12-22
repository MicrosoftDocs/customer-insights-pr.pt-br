---
title: Mesclar entidades na unificação de dados
description: Mescle entidades para criar perfis de clientes unificados.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 045fd8d8f65161b91caabed2ac52494dc4fb3910
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405049"
---
# <a name="merge-entities"></a><span data-ttu-id="8d2a2-103">Mesclar entidades</span><span class="sxs-lookup"><span data-stu-id="8d2a2-103">Merge entities</span></span>

<span data-ttu-id="8d2a2-104">A fase de mesclagem na última fase no processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-104">The merge phase is the last phase in the data unification process.</span></span> <span data-ttu-id="8d2a2-105">Seu objetivo é reconciliar dados conflitantes.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-105">Its purpose is reconciling conflicting data.</span></span> <span data-ttu-id="8d2a2-106">Exemplos de dados conflitantes podem incluir um nome de cliente encontrado em dois de seus conjuntos de dados, mas que mostra um pouco diferente em cada um ("Grant Marshall" versus "Grant Marshal") ou um número de telefone que difere no formato (617-803-091X versus 617803091X).</span><span class="sxs-lookup"><span data-stu-id="8d2a2-106">Examples of conflicting data could include a customer name found in two of your datasets but that shows up a little differently in each ("Grant Marshall" versus "Grant Marshal"), or a phone number that differs in format (617-803-091X versus 617803091X).</span></span> <span data-ttu-id="8d2a2-107">A mesclagem desses pontos de dados conflitantes é feita atributo a atributo.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-107">Merging those conflicting data points is done on an attribute-by-attribute basis.</span></span>

<span data-ttu-id="8d2a2-108">Depois de concluir a [fase de correspondência](match-entities.md), você inicia a fase de mesclagem selecionando o bloco **Mesclar** na página **Unificar**.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-108">After completing the [match phase](match-entities.md), you start the merge phase by selecting the **Merge** tile on the **Unify** page.</span></span>

## <a name="review-system-recommendations"></a><span data-ttu-id="8d2a2-109">Revisar recomendações do sistema</span><span class="sxs-lookup"><span data-stu-id="8d2a2-109">Review system recommendations</span></span>

<span data-ttu-id="8d2a2-110">Na página **Mesclar**, você pode escolher e excluir atributos para mesclar a sua entidade de perfil de cliente unificado (o resultado do processo de configuração).</span><span class="sxs-lookup"><span data-stu-id="8d2a2-110">On the **Merge** page, you choose and exclude attributes to merge within your unified customer profile entity (the result of the configuration process).</span></span> <span data-ttu-id="8d2a2-111">Alguns atributos são mesclados automaticamente pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-111">Some attributes are automatically merged by the system.</span></span>

### <a name="view-merged-attributes"></a><span data-ttu-id="8d2a2-112">Exibir atributos mesclados</span><span class="sxs-lookup"><span data-stu-id="8d2a2-112">View merged attributes</span></span>

<span data-ttu-id="8d2a2-113">Para exibir os atributos incluídos em um dos atributos mesclados automaticamente, selecione esse atributo mesclado.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-113">To view the attributes that are included in one of your automatically merged attributes, select that merged attribute.</span></span> <span data-ttu-id="8d2a2-114">Os dois atributos que compõem esse atributo mesclado são exibidos em duas novas linhas abaixo do atributo mesclado.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-114">The two attributes that compose that merged attribute display in two new rows beneath the merged attribute.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d2a2-115">![Selecionar atributo mesclado](media/configure-data-merge-profile-attributes.png "Selecionar atributo mesclado")</span><span class="sxs-lookup"><span data-stu-id="8d2a2-115">![Select merged attribute](media/configure-data-merge-profile-attributes.png "Select merged attribute")</span></span>

### <a name="separate-merged-attributes"></a><span data-ttu-id="8d2a2-116">Separar atributos mesclados</span><span class="sxs-lookup"><span data-stu-id="8d2a2-116">Separate merged attributes</span></span>

<span data-ttu-id="8d2a2-117">Para separar ou desmembrar qualquer um dos atributos mesclados automaticamente, localize o atributo na tabela **Atributos do perfil**.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-117">To separate or unmerge any of the automatically merged attributes, find the attribute in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="8d2a2-118">Selecione o botão de reticências (...).</span><span class="sxs-lookup"><span data-stu-id="8d2a2-118">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="8d2a2-119">Na lista suspensa, selecione **Campos separados**.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-119">In the dropdown list, select **Separate fields**.</span></span>

### <a name="remove-merged-attributes"></a><span data-ttu-id="8d2a2-120">Remova os atributos mesclados</span><span class="sxs-lookup"><span data-stu-id="8d2a2-120">Remove merged attributes</span></span>

<span data-ttu-id="8d2a2-121">Para excluir um atributo da entidade do perfil do cliente final, localize-o na tabela **Atributos do perfil**.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-121">To exclude an attribute from the final customer profile entity, find it in the **Profile attributes** table.</span></span>

1. <span data-ttu-id="8d2a2-122">Selecione o botão de reticências (...).</span><span class="sxs-lookup"><span data-stu-id="8d2a2-122">Select the ellipsis (...) button.</span></span>
  
2. <span data-ttu-id="8d2a2-123">Na lista suspensa, selecione **Não mesclar**.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-123">In the dropdown list, select **Don't merge**.</span></span>

   <span data-ttu-id="8d2a2-124">O atributo é movido para a seção **Removido do registro do cliente**.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-124">The attribute is moved to the **Removed from customer record** section.</span></span>

## <a name="manually-add-a-merged-attribute"></a><span data-ttu-id="8d2a2-125">Adicionar manualmente um atributo mesclado</span><span class="sxs-lookup"><span data-stu-id="8d2a2-125">Manually add a merged attribute</span></span>

<span data-ttu-id="8d2a2-126">Para adicionar um atributo mesclado, vá para a página **Mesclar**.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-126">To add a merged attribute, go to the **Merge** page.</span></span>

1. <span data-ttu-id="8d2a2-127">Selecione **Adicionar atributo mesclado**.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-127">Select **Add merged attribute**.</span></span>

2. <span data-ttu-id="8d2a2-128">Forneça um **Nome** para identificá-lo na página **Mesclar** posteriormente.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-128">Provide a **Name** to identify it on the **Merge** page later.</span></span>

3. <span data-ttu-id="8d2a2-129">Se preferir, forneça um **Nome para exibição** para aparecer na entidade unificada do Perfil do Cliente.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-129">Optionally, provide a **Display name** to appear in the unified Customer Profile entity.</span></span>

4. <span data-ttu-id="8d2a2-130">Configure **Selecionar atributos duplicados** para selecionar os atributos que você deseja mesclar nas entidades correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-130">Configure **Select duplicate attributes** to select the attributes that you want to merge from the matched entities.</span></span> <span data-ttu-id="8d2a2-131">Você também pode procurar por atributos.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-131">You can also search for attributes.</span></span>

5. <span data-ttu-id="8d2a2-132">Defina **Classificar por importância** para priorizar um atributo acima dos outros.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-132">Set the **Rank by importance** to prioritize one attribute above the others.</span></span> <span data-ttu-id="8d2a2-133">Por exemplo, se a entidade *WebAccountCSV* tiver os dados mais precisos sobre o atributo *Nomes Completos*, você pode priorizar essa entidade em vez de *ContactCSV*, selecionando *WebAccountCSV*.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-133">For example, if the *WebAccountCSV* entity includes the most accurate data about the *Full Names* attribute, you could prioritize this entity over *ContactCSV* by selecting *WebAccountCSV*.</span></span> <span data-ttu-id="8d2a2-134">Como um resultado, *WebAccountCSV* passa para a primeira prioridade, enquanto *ContactCSV* passa para a segunda prioridade ao extrair valores para o atributo *Nome Completo*.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-134">As a result, *WebAccountCSV* moves to first priority, while *ContactCSV* moves to second priority when pulling values for the *Full Name* attribute.</span></span>

## <a name="run-your-merge"></a><span data-ttu-id="8d2a2-135">Execute sua mesclagem</span><span class="sxs-lookup"><span data-stu-id="8d2a2-135">Run your merge</span></span>

<span data-ttu-id="8d2a2-136">Quer você mescle atributos manualmente ou permita que o sistema os mescle, sempre é possível executar sua mesclagem.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-136">Whether you manually merge attributes or let the system merge them, you can always run your merge.</span></span> <span data-ttu-id="8d2a2-137">Selecione **Executar** na página **Mesclar** para iniciar o processo.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-137">Select **Run** on the **Merge** page to start the process.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="8d2a2-138">![Mesclagem de dados Salvar e Executar](media/configure-data-merge-save-run.png "Mesclagem de dados Salvar e Executar")</span><span class="sxs-lookup"><span data-stu-id="8d2a2-138">![Data merge Save and Run](media/configure-data-merge-save-run.png "Data merge Save and Run")</span></span>

<span data-ttu-id="8d2a2-139">Para fazer alterações adicionais e executar novamente a etapa, você pode cancelar uma mesclagem em andamento.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-139">To make additional changes and rerun the step, you can cancel an in-progress merge.</span></span> <span data-ttu-id="8d2a2-140">Selecione **Atualizando...** e selecione **Cancelar o trabalho** no painel lateral exibido.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-140">Select **Refreshing ...** and select **Cancel job**  in the side pane that appears.</span></span>

<span data-ttu-id="8d2a2-141">Após o texto **Atualizando...** mudar para **Bem-sucedido**, a mesclagem concluiu e resolveu as contradições nos seus dados de acordo com as políticas que você definiu.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-141">After the **Refreshing ...** text changes to **Successful**, merge has completed and resolved contradictions in your data according to the policies you defined.</span></span> <span data-ttu-id="8d2a2-142">Atributos mesclados e não mesclados são incluídos na entidade de perfil unificado.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-142">Merged and unmerged attributes are included in the unified profile entity.</span></span> <span data-ttu-id="8d2a2-143">Atributos excluídos não estão incluídos na entidade de perfil unificado.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-143">Excluded attributes aren't included in the unified profile entity.</span></span>

<span data-ttu-id="8d2a2-144">Se não foi a primeira vez que você executou uma mesclagem com êxito, todos os processos posteriores, incluindo enriquecimento, segmentação e medidas, serão executados novamente de forma automática.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-144">If it wasn't the first time you ran a merge successfully, all downstream processes, including enrichment, segmentation, and measures will rerun automatically.</span></span> <span data-ttu-id="8d2a2-145">Depois que todos os processos posteriores foram executados novamente, os perfis dos clientes refletem todas as alterações feitas.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-145">After all downstream processes have been rerun, the customer profiles reflect any changes you made.</span></span>

> [!TIP]
> <span data-ttu-id="8d2a2-146">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-146">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="8d2a2-147">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="8d2a2-147">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="8d2a2-148">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-148">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="8d2a2-149">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-149">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="next-step"></a><span data-ttu-id="8d2a2-150">Próxima Etapa</span><span class="sxs-lookup"><span data-stu-id="8d2a2-150">Next Step</span></span>

<span data-ttu-id="8d2a2-151">Configurar [atividades](activities.md), [enriquecimento](enrichment-microsoft-graph.md) ou [relacionamentos](relationships.md) para obter mais informações sobre seus clientes.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-151">Configure [activities](activities.md), [enrichment](enrichment-microsoft-graph.md), or [relationships](relationships.md) to gain more insights about your customers.</span></span>

<span data-ttu-id="8d2a2-152">Se você já configurou atividades, enriquecimento ou relacionamentos, ou se definiu segmentos, eles serão processados automaticamente para usar os dados mais recentes do cliente.</span><span class="sxs-lookup"><span data-stu-id="8d2a2-152">If you already configured activities, enrichment, or relationships, or if you defined segments, they'll be processed automatically to use the latest customer data.</span></span>


