---
title: Atividades do cliente
description: Defina as atividades do cliente e exiba-as na linha do tempo do cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: dcef8f0547009e1488f1abe91423fa0bf5b061de
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267418"
---
# <a name="customer-activities"></a><span data-ttu-id="9a9cc-103">Atividades do cliente</span><span class="sxs-lookup"><span data-stu-id="9a9cc-103">Customer activities</span></span>

<span data-ttu-id="9a9cc-104">Combine as atividades do cliente de [várias fontes de dados](data-sources.md) no Dynamics 365 Customer Insights para criar uma linha do tempo do cliente que lista as atividades em ordem cronológica.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-104">Combine customer activities from [various data sources](data-sources.md) in Dynamics 365 Customer Insights to create a customer timeline that lists the activities in chronological order.</span></span> <span data-ttu-id="9a9cc-105">Você pode incluir a linha do tempo nos aplicativos de interação com os clientes no Dynamics 365 por meio do [Suplemento do Cartão do Cliente](customer-card-add-in.md), ou em um painel de controle do Power BI.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-105">You can include the timeline in customer engagement apps in Dynamics 365 via the [Customer Card add-in](customer-card-add-in.md), or in a Power BI dashboard.</span></span>

## <a name="define-an-activity"></a><span data-ttu-id="9a9cc-106">Definir uma atividade</span><span class="sxs-lookup"><span data-stu-id="9a9cc-106">Define an activity</span></span>

<span data-ttu-id="9a9cc-107">Suas fontes de dados incluem entidades com dados transacionais e de atividades de várias fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-107">Your data sources include entities with transactional and activity data from multiple data sources.</span></span> <span data-ttu-id="9a9cc-108">Identifique essas entidades e selecione as atividades que deseja visualizar na linha do tempo do cliente.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-108">Identify these entities and select the activities you want to view on the customer's timeline.</span></span> <span data-ttu-id="9a9cc-109">Escolha a entidade que inclui sua atividade ou atividades de destino.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-109">Choose the entity that includes your target activity or activities.</span></span>

1. <span data-ttu-id="9a9cc-110">Nos insights de público-alvo, vá para **Dados** > **Atividades**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-110">In audience insights, go to **Data** > **Activities**.</span></span>

1. <span data-ttu-id="9a9cc-111">Selecione **Adicionar atividade**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-111">Select **Add activity**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="9a9cc-112">Uma entidade deve ter pelo menos um atributo do tipo **Data** para ser incluído na linha do tempo do cliente e você não pode adicionar entidades sem os campos de **Data**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-112">An entity must have at least one attribute of type **Date** to be included in a customer timeline and you can't add entities without **Date** fields.</span></span> <span data-ttu-id="9a9cc-113">O controle **Adicionar atividade** é desativado, se nenhuma entidade for encontrada.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-113">The **Add activity** control is disabled if no such entity is found.</span></span>

1. <span data-ttu-id="9a9cc-114">No painel **Adicionar atividade**, defina os valores para os seguintes campos:</span><span class="sxs-lookup"><span data-stu-id="9a9cc-114">In the **Add activity** pane, set the values for the following fields:</span></span>

   - <span data-ttu-id="9a9cc-115">**Entidade**: Selecione uma entidade que inclua dados transacionais ou de atividade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-115">**Entity**: Select an entity that includes transactional or activity data.</span></span>
   - <span data-ttu-id="9a9cc-116">**Chave primária**: Seleciona o campo que identifica exclusivamente um registro.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-116">**Primary key**: Select the field that uniquely identifies a record.</span></span> <span data-ttu-id="9a9cc-117">Não deve conter valores duplicados, valores vazios ou valores ausentes.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-117">It shouldn't contain any duplicate values, empty values, or missing values.</span></span>
   - <span data-ttu-id="9a9cc-118">**Registro de data e hora**: Selecione o campo que representa a hora de início da sua atividade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-118">**Timestamp**: Select the field that represents the start time of your activity.</span></span>
   - <span data-ttu-id="9a9cc-119">**Evento**: Selecione o campo que é o evento para a atividade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-119">**Event**: Select the field that is the event for the activity.</span></span>
   - <span data-ttu-id="9a9cc-120">**Endereço da Web**: Selecione o campo que representa uma URL que fornece informações adicionais sobre esta atividade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-120">**Web address**: Select the field that represents a URL providing additional information about this activity.</span></span> <span data-ttu-id="9a9cc-121">Por exemplo, o sistema transacional que origina essa atividade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-121">For example, the transactional system that sources this activity.</span></span> <span data-ttu-id="9a9cc-122">Esse URL pode ser qualquer campo da fonte de dados ou pode ser construído como um novo campo usando uma transformação do Power Query.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-122">This URL can be any field from the data source, or it can be constructed as a new field using a Power Query transformation.</span></span> <span data-ttu-id="9a9cc-123">Esses dados de URL serão armazenados na entidade da Atividade Unificada, que pode ser consumida posteriormente com as APIs.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-123">This URL data will be stored in the Unified Activity entity, which can be consumed downstream using APIs.</span></span>
   - <span data-ttu-id="9a9cc-124">**Detalhes**: Como opção, selecione o campo que é adicionado para obter detalhes adicionais.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-124">**Details**: Optionally, select the field that is added for additional details.</span></span>
   - <span data-ttu-id="9a9cc-125">**Ícone**: Como opção, selecione o ícone que representa esta atividade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-125">**Icon**: Optionally, select the icon that represents this activity.</span></span>
   - <span data-ttu-id="9a9cc-126">**Tipo de Atividade**: Defina a referência do tipo de atividade para o Common Data Model que melhor descreve a definição semântica da atividade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-126">**Activity Type**: Define the activity type reference to Common Data Model that best describes the semantic definition of the activity.</span></span>

1. <span data-ttu-id="9a9cc-127">Na seção **Definir relacionamento**, configure os detalhes para conectar seus dados de atividade ao cliente correspondente.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-127">In the **Set up relationship** section, configure the details to connect your activity data to its corresponding customer.</span></span>

    - <span data-ttu-id="9a9cc-128">**Campo da entidade de atividade**: selecione o campo na sua entidade de atividade que será usado para estabelecer um relacionamento com outra entidade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-128">**Activity entity field**: Select the field in your activity entity that will be used to establish a relationship with another entity.</span></span>
    - <span data-ttu-id="9a9cc-129">**Entidade do cliente**: selecione a entidade do cliente de origem correspondente com a qual sua entidade de atividade estará em relacionamento.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-129">**Customer entity**: Select the corresponding source customer entity with which your activity entity will be in relationship.</span></span> <span data-ttu-id="9a9cc-130">É possível se relacionar apenas às entidades do cliente de origem que são usadas no processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-130">You can relate to only those source customer entities that are used in the data unification process.</span></span>
    - <span data-ttu-id="9a9cc-131">**Campo da entidade do cliente**: este campo mostra a chave primária da entidade do cliente de origem, conforme selecionada no processo de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-131">**Customer entity field**: This field shows the primary key of the source customer entity as selected in the map process.</span></span> <span data-ttu-id="9a9cc-132">Esse campo de chave primária na entidade do cliente de origem é usado para estabelecer um relacionamento com a entidade da atividade.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-132">This primary key field in the source customer entity is used to establish a relationship with the activity entity.</span></span>
    - <span data-ttu-id="9a9cc-133">**Nome**: se já existir um relacionamento entre esta entidade de atividade e a entidade cliente de origem selecionada, o nome do relacionamento estará no modo somente leitura.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-133">**Name**: If a relationship between this activity entity and the selected source customer entity already exists, the relationship name will be in read-only mode.</span></span> <span data-ttu-id="9a9cc-134">Se não existir esse relacionamento, um novo relacionamento será criado com o nome fornecido aqui.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-134">If there no such relationship exists, a new relationship will be created with the name provided here.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9a9cc-135">![Defina o relacionamento da entidade](media/activities-entities-define.png "Defina o relacionamento da entidade")</span><span class="sxs-lookup"><span data-stu-id="9a9cc-135">![Define the entity relationship](media/activities-entities-define.png "Define the entity relationship")</span></span>

1. <span data-ttu-id="9a9cc-136">Selecione **Salvar** para aplicar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-136">Select **Save** to apply your changes.</span></span>

1. <span data-ttu-id="9a9cc-137">Na página **Atividades**, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-137">On the **Activities** page, select **Run**.</span></span>

> [!TIP]
> <span data-ttu-id="9a9cc-138">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-138">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="9a9cc-139">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="9a9cc-139">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="9a9cc-140">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-140">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="9a9cc-141">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-141">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="edit-an-activity"></a><span data-ttu-id="9a9cc-142">Editar uma atividade</span><span class="sxs-lookup"><span data-stu-id="9a9cc-142">Edit an activity</span></span>

1. <span data-ttu-id="9a9cc-143">Nos insights de público-alvo, vá para **Dados** > **Atividades**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-143">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="9a9cc-144">Selecione a entidade da atividade que você deseja editar e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-144">Select the activity entity you want to edit and select **Edit**.</span></span> <span data-ttu-id="9a9cc-145">Ou você pode passar o mouse sobre a linha da entidade e selecionar o ícone **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-145">Or, you can hover over the entity row and select the **Edit** icon.</span></span>

3. <span data-ttu-id="9a9cc-146">Clique no ícone **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-146">Click on the **Edit** icon.</span></span>

4. <span data-ttu-id="9a9cc-147">No painel **Editar atividade**, atualize os valores e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-147">In the **Edit activity** pane, update the values and select **Save**.</span></span>

5. <span data-ttu-id="9a9cc-148">Na página **Atividades**, selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-148">On the **Activities** page, select **Run**.</span></span>

## <a name="delete-an-activity"></a><span data-ttu-id="9a9cc-149">Excluir uma atividade</span><span class="sxs-lookup"><span data-stu-id="9a9cc-149">Delete an activity</span></span>

1. <span data-ttu-id="9a9cc-150">Nos insights de público-alvo, vá para **Dados** > **Atividades**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-150">In audience insights, go to **Data** > **Activities**.</span></span>

2. <span data-ttu-id="9a9cc-151">Selecione a entidade da atividade que você deseja remover e selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-151">Select the activity entity you want to remove and select **Delete**.</span></span> <span data-ttu-id="9a9cc-152">Ou você pode passar o mouse sobre a linha da entidade e selecionar o ícone **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-152">Or, you can hover over the entity row and select the **Delete** icon.</span></span> <span data-ttu-id="9a9cc-153">Além disso, você pode selecionar várias entidades de atividade a serem excluídas de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-153">Additionally, you can select multiple activity entities to be deleted at once.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="9a9cc-154">![Editar ou excluir o relacionamento da entidade](media/activities-entities-edit-delete.png "Editar ou excluir o relacionamento da entidade")</span><span class="sxs-lookup"><span data-stu-id="9a9cc-154">![Edit or delete the entity relationship](media/activities-entities-edit-delete.png "Edit or delete the entity relationship")</span></span>

3. <span data-ttu-id="9a9cc-155">Selecione no ícone **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-155">Select on the **Delete** icon.</span></span>

4. <span data-ttu-id="9a9cc-156">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="9a9cc-156">Confirm your deletion.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]