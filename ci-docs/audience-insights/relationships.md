---
title: Relacionamentos entre entidades e caminhos de entidade
description: Crie e gerencie relacionamentos entre entidades de várias fontes de dados.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 295c372bb452e7c40aa950506dc494d4a2de1108
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405055"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="edfeb-103">Relacionamentos entre entidades</span><span class="sxs-lookup"><span data-stu-id="edfeb-103">Relationships between entities</span></span>

<span data-ttu-id="edfeb-104">Os relacionamentos ajudam a conectar entidades e gerar um gráfico de seus dados quando as entidades compartilham um identificador comum (chave estrangeira) que pode ser referenciado de uma entidade para outra.</span><span class="sxs-lookup"><span data-stu-id="edfeb-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="edfeb-105">As entidades conectadas permitem definir segmentos e medidas com base em várias fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="edfeb-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="edfeb-106">Há dois tipos de relacionamentos.</span><span class="sxs-lookup"><span data-stu-id="edfeb-106">There are two types of relationships.</span></span> <span data-ttu-id="edfeb-107">Relacionamentos de sistema não editáveis, criados automaticamente, e relacionamentos personalizados, criados e configurados pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="edfeb-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="edfeb-108">Durante os processos de correspondência e mesclagem, os relacionamentos do sistema são criados nos bastidores com base na correspondência inteligente.</span><span class="sxs-lookup"><span data-stu-id="edfeb-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="edfeb-109">Esses relacionamentos ajudam a relacionar os registros do Perfil do Cliente com os registros de outras entidades correspondentes.</span><span class="sxs-lookup"><span data-stu-id="edfeb-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="edfeb-110">O diagrama a seguir ilustra a criação de três relacionamentos do sistema quando a entidade do cliente é correspondida com outras entidades para produzir a entidade final do Perfil do Cliente.</span><span class="sxs-lookup"><span data-stu-id="edfeb-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="edfeb-111">![Criação de relacionamento](media/relationships-entities-merge.png "Criação de relacionamento")</span><span class="sxs-lookup"><span data-stu-id="edfeb-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="edfeb-112">**O Relacionamento *CustomerToContact*** foi criado entre a entidade Cliente e a entidade Contato.</span><span class="sxs-lookup"><span data-stu-id="edfeb-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="edfeb-113">A entidade Cliente obtém o campo-chave **Contact_contactId** para relacionar-se com o campo-chave da entidade de Contato **contactId**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="edfeb-114">**O Relacionamento _CustomerToContact_** foi criado entre a entidade Cliente e a entidade Conta.</span><span class="sxs-lookup"><span data-stu-id="edfeb-114">**_CustomerToAccount_ relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="edfeb-115">A entidade Cliente obtém o campo-chave **Account_accountId** para relacionar-se com o campo-chave da entidade de Conta **accountId**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="edfeb-116">**O Relacionamento _CustomerToWebAccount_** foi criado entre a entidade Cliente e a entidade WebAccount.</span><span class="sxs-lookup"><span data-stu-id="edfeb-116">**_CustomerToWebAccount_ relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="edfeb-117">A entidade Customer obtém o campo-chave **WebAccount_webaccountId** para relacionar-se com o campo-chave da entidade de WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="edfeb-118">Criar um relacionamento</span><span class="sxs-lookup"><span data-stu-id="edfeb-118">Create a relationship</span></span>

<span data-ttu-id="edfeb-119">Defina relacionamentos personalizados na página **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="edfeb-120">Cada relacionamento consiste em uma entidade de Origem (a entidade que detém a chave estrangeira) e uma entidade de Destino (a entidade para a qual a chave estrangeira da entidade de origem aponta).</span><span class="sxs-lookup"><span data-stu-id="edfeb-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="edfeb-121">Nas informações de público-alvo, vá para **Dados** > **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="edfeb-122">Selecione **Novo relacionamento**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="edfeb-123">No painel **Adicionar relacionamento**, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="edfeb-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="edfeb-124">![Digite os detalhes do relacionamento](media/relationships-add.png "Digite os detalhes do relacionamento")</span><span class="sxs-lookup"><span data-stu-id="edfeb-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="edfeb-125">**Nome do relacionamento** : Nome que reflete o objetivo do relacionamento (por exemplo, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="edfeb-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="edfeb-126">**Descrição**: Descrição do relacionamento.</span><span class="sxs-lookup"><span data-stu-id="edfeb-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="edfeb-127">**Entidade de origem**: Selecione a entidade que é usada como fonte no relacionamento (por exemplo, WebLog).</span><span class="sxs-lookup"><span data-stu-id="edfeb-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="edfeb-128">**Cardinalidade**: Selecione a cardinalidade dos registros da entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="edfeb-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="edfeb-129">Por exemplo, "muitos" significa que vários registros do Weblog estão relacionados a uma WebAccount.</span><span class="sxs-lookup"><span data-stu-id="edfeb-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="edfeb-130">**Campo da chave de origem**: Representa o campo de chave estrangeira na entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="edfeb-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="edfeb-131">Por exemplo, o WebLog tem o campo de chave estrangeira **accountId**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="edfeb-132">**Entidade de destino**: Selecione a entidade que é usada como destino no relacionamento (por exemplo, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="edfeb-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="edfeb-133">**Cardinalidade de destino**: Selecione a cardinalidade dos registros da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="edfeb-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="edfeb-134">Por exemplo, "uma" significa que vários registros do Weblog estão relacionados a uma WebAccount.</span><span class="sxs-lookup"><span data-stu-id="edfeb-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="edfeb-135">**Campo-chave de destino**: Este campo representa o campo-chave da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="edfeb-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="edfeb-136">Por exemplo, o WebAccount tem o campo de chave **accountId**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="edfeb-137">Somente relacionamentos muitos para um e um para um são suportados.</span><span class="sxs-lookup"><span data-stu-id="edfeb-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="edfeb-138">Os relacionamentos muitos-para-muitos podem ser criados usando dois relacionamentos muitos-para-um e uma entidade de link (uma entidade usada para conectar a entidade de origem e a entidade de destino).</span><span class="sxs-lookup"><span data-stu-id="edfeb-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="edfeb-139">Excluir um relacionamento</span><span class="sxs-lookup"><span data-stu-id="edfeb-139">Delete a relationship</span></span>

1. <span data-ttu-id="edfeb-140">Nas informações de público-alvo, vá para **Dados** > **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="edfeb-141">Marque as caixas de seleção para os relacionamentos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="edfeb-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="edfeb-142">Selecione **Excluir** na parte superior da tabela **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="edfeb-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="edfeb-143">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="edfeb-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="edfeb-144">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="edfeb-144">Next step</span></span>

<span data-ttu-id="edfeb-145">Os relacionamentos do sistema e personalizados são usados para criar segmentos com base em várias fontes de dados que não são mais isoladas.</span><span class="sxs-lookup"><span data-stu-id="edfeb-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="edfeb-146">Para obter mais informações, consulte [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="edfeb-146">For more information, see [Segments](segments.md).</span></span>
