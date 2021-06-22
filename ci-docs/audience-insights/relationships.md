---
title: Relacionamentos entre entidades e caminhos de entidade
description: Crie e gerencie relacionamentos entre entidades de várias fontes de dados.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171150"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="7baff-103">Relacionamentos entre entidades</span><span class="sxs-lookup"><span data-stu-id="7baff-103">Relationships between entities</span></span>

<span data-ttu-id="7baff-104">Relacionamentos conectam entidades e definem um gráfico de seus dados quando as entidades compartilham um identificador comum, uma chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="7baff-104">Relationships connect entities and define a graph of your data when entities share a common identifier, a foreign key.</span></span> <span data-ttu-id="7baff-105">Essa chave estrangeira pode ser referenciada de uma entidade para outra.</span><span class="sxs-lookup"><span data-stu-id="7baff-105">This foreign key can be referenced from one entity to another.</span></span> <span data-ttu-id="7baff-106">As entidades conectadas permitem a definição de segmentos e medidas com base em várias fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="7baff-106">Connected entities enable the definition of segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="7baff-107">Existem três tipos de relacionamento:</span><span class="sxs-lookup"><span data-stu-id="7baff-107">There are three types of relationships:</span></span> 
- <span data-ttu-id="7baff-108">Relacionamentos de sistema não editáveis, criados pelo sistema como parte do processo de unificação de dados</span><span class="sxs-lookup"><span data-stu-id="7baff-108">Non-editable system relationships, created by the system as part of the data unification process</span></span>
- <span data-ttu-id="7baff-109">Relacionamentos herdados não editáveis, que são criados automaticamente por meio da ingestão de fontes de dados</span><span class="sxs-lookup"><span data-stu-id="7baff-109">Non-editable inherited relationships, which are created automatically from ingesting data sources</span></span> 
- <span data-ttu-id="7baff-110">Relacionamentos personalizados editáveis, criados e configurados por usuários</span><span class="sxs-lookup"><span data-stu-id="7baff-110">Editable custom relationships, created and configured by users</span></span>

## <a name="non-editable-system-relationships"></a><span data-ttu-id="7baff-111">Relações de sistema não editáveis</span><span class="sxs-lookup"><span data-stu-id="7baff-111">Non-editable system relationships</span></span>

<span data-ttu-id="7baff-112">Durante a unificação de dados, os relacionamentos do sistema são criados automaticamente com base na correspondência inteligente.</span><span class="sxs-lookup"><span data-stu-id="7baff-112">During data unification, system relationships are created automatically based on intelligent matching.</span></span> <span data-ttu-id="7baff-113">Esses relacionamentos ajudam a relacionar os registros do perfil do cliente com os registros correspondentes.</span><span class="sxs-lookup"><span data-stu-id="7baff-113">These relationships help relate the customer profile records with corresponding records.</span></span> <span data-ttu-id="7baff-114">O diagrama a seguir ilustra a criação de três relacionamentos baseados no sistema.</span><span class="sxs-lookup"><span data-stu-id="7baff-114">The following diagram illustrates the creation of three system-based relationships.</span></span> <span data-ttu-id="7baff-115">A entidade do cliente é combinada com outras entidades para produzir a entidade unificada *Cliente*.</span><span class="sxs-lookup"><span data-stu-id="7baff-115">The customer entity is matched with other entities to produce the unified *Customer* entity.</span></span>

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama com caminhos de relacionamento para a entidade do cliente com três relacionamentos 1:N.":::

- <span data-ttu-id="7baff-117">O **Relacionamento *CustomerToContact*** foi criado entre a entidade *Cliente* e a entidade *Contato*.</span><span class="sxs-lookup"><span data-stu-id="7baff-117">***CustomerToContact* relationship** was created between the *Customer* entity and the *Contact* entity.</span></span> <span data-ttu-id="7baff-118">A entidade *Cliente* obtém o campo-chave **Contact_contactID** para relacionar-se com o campo-chave da entidade de *Contato* **contactID**.</span><span class="sxs-lookup"><span data-stu-id="7baff-118">The *Customer* entity gets the key field **Contact_contactID** to relate to the *Contact* entity key field **contactID**.</span></span>
- <span data-ttu-id="7baff-119">O **Relacionamento *CustomerToContact*** foi criado entre a entidade *Cliente* e a entidade *Conta*.</span><span class="sxs-lookup"><span data-stu-id="7baff-119">***CustomerToAccount* relationship** was created between the *Customer* entity and the *Account* entity.</span></span> <span data-ttu-id="7baff-120">A entidade *Cliente* obtém o campo-chave **Account_accountID** para relacionar-se com o campo-chave da entidade de *Conta* **accountID**.</span><span class="sxs-lookup"><span data-stu-id="7baff-120">The *Customer* entity gets the key field **Account_accountID** to relate to the *Account* entity key field **accountID**.</span></span>
- <span data-ttu-id="7baff-121">O **Relacionamento *CustomerToWebAccount*** foi criado entre a entidade *Cliente* e a entidade *WebAccount*.</span><span class="sxs-lookup"><span data-stu-id="7baff-121">***CustomerToWebAccount* relationship** was created between the *Customer* entity and the *WebAccount* entity.</span></span> <span data-ttu-id="7baff-122">A entidade *Customer* obtém o campo-chave **WebAccount_webaccountID** para relacionar-se com o campo-chave da entidade de *WebAccount* **webaccountID**.</span><span class="sxs-lookup"><span data-stu-id="7baff-122">The *Customer* entity gets the key field **WebAccount_webaccountID** to relate to the *WebAccount* entity key field **webaccountID**.</span></span>

## <a name="non-editable-inherited-relationships"></a><span data-ttu-id="7baff-123">Relações herdadas não editáveis</span><span class="sxs-lookup"><span data-stu-id="7baff-123">Non-editable inherited relationships</span></span>

<span data-ttu-id="7baff-124">Durante o processo de ingestão de dados, o sistema verifica as fontes de dados para relacionamentos existentes.</span><span class="sxs-lookup"><span data-stu-id="7baff-124">During the data ingestion process, the system checks data sources for existing relationships.</span></span> <span data-ttu-id="7baff-125">Se não houver relacionamentos, o sistema os criará automaticamente.</span><span class="sxs-lookup"><span data-stu-id="7baff-125">If no relationship exists, the system automatically creates them.</span></span> <span data-ttu-id="7baff-126">Esses relacionamentos também são usados em processos downstream.</span><span class="sxs-lookup"><span data-stu-id="7baff-126">These relationships are also used in downstream processes.</span></span>

## <a name="create-a-custom-relationship"></a><span data-ttu-id="7baff-127">Criar um relacionamento personalizado</span><span class="sxs-lookup"><span data-stu-id="7baff-127">Create a custom relationship</span></span>

<span data-ttu-id="7baff-128">O relacionamento consiste em uma *entidade de origem* contendo a chave estrangeira e uma *entidade de destino* para a qual a chave estrangeira da entidade de origem aponta.</span><span class="sxs-lookup"><span data-stu-id="7baff-128">Relationship consists of a *source entity* containing the foreign key and a *target entity* that the source entity's foreign key points to.</span></span> 

1. <span data-ttu-id="7baff-129">Nas informações de público-alvo, vá para **Dados** > **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="7baff-129">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="7baff-130">Selecione **Novo relacionamento**.</span><span class="sxs-lookup"><span data-stu-id="7baff-130">Select **New relationship**.</span></span>

3. <span data-ttu-id="7baff-131">No painel **Novo relacionamento**, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="7baff-131">In the **New relationship** pane, provide the following information:</span></span>

   :::image type="content" source="media/relationship-add.png" alt-text="Novo painel lateral de relacionamento com campos de entrada vazios.":::

   - <span data-ttu-id="7baff-133">**Nome do relacionamento**: nome que reflete o propósito do relacionamento.</span><span class="sxs-lookup"><span data-stu-id="7baff-133">**Relationship name**: Name that reflects the purpose of the relationship.</span></span> <span data-ttu-id="7baff-134">Exemplo: CustomerToSupportCase.</span><span class="sxs-lookup"><span data-stu-id="7baff-134">Example: CustomerToSupportCase.</span></span>
   - <span data-ttu-id="7baff-135">**Descrição**: Descrição do relacionamento.</span><span class="sxs-lookup"><span data-stu-id="7baff-135">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="7baff-136">**Entidade de origem**: entidade que é usada como fonte no relacionamento.</span><span class="sxs-lookup"><span data-stu-id="7baff-136">**Source entity**: Entity that is used as a source in the relationship.</span></span> <span data-ttu-id="7baff-137">Exemplo: SupportCase.</span><span class="sxs-lookup"><span data-stu-id="7baff-137">Example: SupportCase.</span></span>
   - <span data-ttu-id="7baff-138">**Entidade de destino**: entidade que é usada como destino no relacionamento.</span><span class="sxs-lookup"><span data-stu-id="7baff-138">**Target entity**: Entity that is used as a target in the relationship.</span></span> <span data-ttu-id="7baff-139">Exemplo: cliente.</span><span class="sxs-lookup"><span data-stu-id="7baff-139">Example: Customer.</span></span>
   - <span data-ttu-id="7baff-140">**Cardinalidade de origem**: especifique a cardinalidade da entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="7baff-140">**Source cardinality**: Specify the cardinality of the source entity.</span></span> <span data-ttu-id="7baff-141">A cardinalidade descreve o número de elementos possíveis em um conjunto.</span><span class="sxs-lookup"><span data-stu-id="7baff-141">Cardinality describes the number of possible elements in a set.</span></span> <span data-ttu-id="7baff-142">Sempre está relacionado à cardinalidade de destino.</span><span class="sxs-lookup"><span data-stu-id="7baff-142">It always relates to the target cardinality.</span></span> <span data-ttu-id="7baff-143">Você pode escolher entre **Um** e **Muitos**.</span><span class="sxs-lookup"><span data-stu-id="7baff-143">You can choose between **One** and **Many**.</span></span> <span data-ttu-id="7baff-144">Somente relacionamentos muitos para um e um para um são suportados.</span><span class="sxs-lookup"><span data-stu-id="7baff-144">Only many-to-one and one-to-one relationships are supported.</span></span>  
     - <span data-ttu-id="7baff-145">Muitos para um: vários registros de origem podem se relacionar a um registro de destino.</span><span class="sxs-lookup"><span data-stu-id="7baff-145">Many-to-one: Multiple source records can relate to one target record.</span></span> <span data-ttu-id="7baff-146">Exemplo: vários casos de suporte de um único cliente.</span><span class="sxs-lookup"><span data-stu-id="7baff-146">Example: Multiple support cases from a single customer.</span></span>
     - <span data-ttu-id="7baff-147">Um para um: um único registro de origem se relaciona a um registro de destino.</span><span class="sxs-lookup"><span data-stu-id="7baff-147">One-to-one: A single source record relates to a one target record.</span></span> <span data-ttu-id="7baff-148">Exemplo: uma ID de fidelidade para um único cliente.</span><span class="sxs-lookup"><span data-stu-id="7baff-148">Example: One loyalty ID for a single customer.</span></span>

     > [!NOTE]
     > <span data-ttu-id="7baff-149">Os relacionamentos muitos para muitos podem ser criados por meio de dois relacionamentos muitos para um e uma entidade de vinculação, que conecta a entidade de origem e a entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="7baff-149">Many-to-many relationships can be created using two many-to-one relationships and a linking entity, which connects the source entity and the target entity.</span></span>

   - <span data-ttu-id="7baff-150">**Cardinalidade de destino**: Selecione a cardinalidade dos registros da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="7baff-150">**Target cardinality**: Select the cardinality of the target entity records.</span></span> 
   - <span data-ttu-id="7baff-151">**Campo-chave de fonte**: o campo de chave estrangeira na entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="7baff-151">**Source key field**: The foreign key field in the source entity.</span></span> <span data-ttu-id="7baff-152">Exemplo: o SupportCase pode usar CaseID como um campo de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="7baff-152">Example: SupportCase could use CaseID as a foreign key field.</span></span>
   - <span data-ttu-id="7baff-153">**Campo-chave de destino**: o campo-chave da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="7baff-153">**Target key field**: The key field of the target entity.</span></span> <span data-ttu-id="7baff-154">Exemplo: o cliente pode usar o campo-chave **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="7baff-154">Example Customer could use the **CustomerID** key field.</span></span>

4. <span data-ttu-id="7baff-155">Selecione **Salvar** para criar o relacionamento personalizado.</span><span class="sxs-lookup"><span data-stu-id="7baff-155">Select **Save** to create the custom relationship.</span></span>

## <a name="view-relationships"></a><span data-ttu-id="7baff-156">Exibir relacionamentos</span><span class="sxs-lookup"><span data-stu-id="7baff-156">View relationships</span></span>

<span data-ttu-id="7baff-157">A página Relacionamentos lista todos os relacionamentos que foram criados.</span><span class="sxs-lookup"><span data-stu-id="7baff-157">The Relationships page lists all the relationships that have been created.</span></span> <span data-ttu-id="7baff-158">Cada linha representa um relacionamento, que também inclui detalhes sobre a entidade de origem, a entidade de destino e a cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="7baff-158">Each row represents a relationship, which also includes details about the source entity, the target entity, and the cardinality.</span></span> 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de relacionamentos e opções na barra de ação da página Relacionamentos.":::

<span data-ttu-id="7baff-160">Esta página oferece um conjunto de opções para relacionamentos novos e existentes:</span><span class="sxs-lookup"><span data-stu-id="7baff-160">This page offers a set of options for existing and new relationships:</span></span> 
- <span data-ttu-id="7baff-161">**Novo relacionamento**: [Criar um relacionamento personalizado](#create-a-custom-relationship).</span><span class="sxs-lookup"><span data-stu-id="7baff-161">**New Relationship**: [Create a custom relationship](#create-a-custom-relationship).</span></span>
- <span data-ttu-id="7baff-162">**Visualizador**: [explore o visualizador de relacionamento](#explore-the-relationship-visualizer) para ver um diagrama de rede dos relacionamentos existentes e sua cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="7baff-162">**Visualizer**: [Explore the relationship visualizer](#explore-the-relationship-visualizer) to see a network diagram of the existing relationships and their cardinality.</span></span>
- <span data-ttu-id="7baff-163">**Filtrar por**: escolha o tipo de relacionamento a ser mostrado na lista.</span><span class="sxs-lookup"><span data-stu-id="7baff-163">**Filter by**: Choose the type of relationships to show in the list.</span></span>
- <span data-ttu-id="7baff-164">**Pesquisar relacionamentos**: use uma pesquisa baseada em texto nas propriedades dos relacionamentos.</span><span class="sxs-lookup"><span data-stu-id="7baff-164">**Search relationships**: Use a text-based search on properties of the relationships.</span></span>

### <a name="explore-the-relationship-visualizer"></a><span data-ttu-id="7baff-165">Explorar o visualizador de relacionamento</span><span class="sxs-lookup"><span data-stu-id="7baff-165">Explore the relationship visualizer</span></span>

<span data-ttu-id="7baff-166">O visualizador de relacionamento mostra um diagrama de rede dos relacionamentos existentes entre entidades conectadas e sua cardinalidade.</span><span class="sxs-lookup"><span data-stu-id="7baff-166">The relationship visualizer shows a network diagram of the existing relationships between connected entities and their cardinality.</span></span>

<span data-ttu-id="7baff-167">Para personalizar a exibição, você pode alterar a posição das caixas arrastando-as na tela.</span><span class="sxs-lookup"><span data-stu-id="7baff-167">To customize the view, you can change the position of the boxes by dragging them on the canvas.</span></span>

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de tela do diagrama de rede do visualizador de relacionamento com conexões entre entidades relacionadas.":::

<span data-ttu-id="7baff-169">Opções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="7baff-169">Available options:</span></span> 
- <span data-ttu-id="7baff-170">**Exportar como imagem**: salve a exibição atual como um arquivo de imagem.</span><span class="sxs-lookup"><span data-stu-id="7baff-170">**Export as image**: Save the current view as an image file.</span></span>
- <span data-ttu-id="7baff-171">**Alterar para layout horizontal/vertical**: altere o alinhamento das entidades e relacionamentos.</span><span class="sxs-lookup"><span data-stu-id="7baff-171">**Change to horizontal/vertical layout**: Change the alignment of the entities and relationships.</span></span>
- <span data-ttu-id="7baff-172">**Editar**: atualize as propriedades de relacionamentos personalizados no painel de edição e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="7baff-172">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>

## <a name="manage-existing-relationships"></a><span data-ttu-id="7baff-173">Gerenciar relacionamentos existentes</span><span class="sxs-lookup"><span data-stu-id="7baff-173">Manage existing relationships</span></span> 

<span data-ttu-id="7baff-174">Na página Relacionamentos, cada relacionamento é representado por uma linha.</span><span class="sxs-lookup"><span data-stu-id="7baff-174">On the Relationships page, each relationship is represented by a row.</span></span> 

<span data-ttu-id="7baff-175">Selecione um parentesco e escolha uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="7baff-175">Select a relationship and choose one of the following options:</span></span> 
 
- <span data-ttu-id="7baff-176">**Editar**: atualize as propriedades de relacionamentos personalizados no painel de edição e salve as alterações.</span><span class="sxs-lookup"><span data-stu-id="7baff-176">**Edit**: Update properties of custom relationships in the edit pane and save changes.</span></span>
- <span data-ttu-id="7baff-177">**Excluir**: exclua relacionamentos personalizados.</span><span class="sxs-lookup"><span data-stu-id="7baff-177">**Delete**: Delete custom relationships.</span></span>
- <span data-ttu-id="7baff-178">**Exibir**: exiba relacionamentos criados pelo sistema e herdados.</span><span class="sxs-lookup"><span data-stu-id="7baff-178">**View**: View system-created and inherited relationships.</span></span> 

## <a name="next-step"></a><span data-ttu-id="7baff-179">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="7baff-179">Next step</span></span>

<span data-ttu-id="7baff-180">Os relacionamentos do sistema e personalizados são usados para [criar segmentos](segments.md) com base em várias fontes de dados que não são mais isoladas.</span><span class="sxs-lookup"><span data-stu-id="7baff-180">System and custom relationships are used to [create segments](segments.md) based on multiple data sources that are no longer siloed.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
