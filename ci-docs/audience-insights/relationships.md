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
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269853"
---
# <a name="relationships-between-entities"></a><span data-ttu-id="5118c-103">Relacionamentos entre entidades</span><span class="sxs-lookup"><span data-stu-id="5118c-103">Relationships between entities</span></span>

<span data-ttu-id="5118c-104">Os relacionamentos ajudam a conectar entidades e gerar um gráfico de seus dados quando as entidades compartilham um identificador comum (chave estrangeira) que pode ser referenciado de uma entidade para outra.</span><span class="sxs-lookup"><span data-stu-id="5118c-104">Relationships help you connect entities and generate a graph of your data when entities share a common identifier (foreign key) that can be referenced from one entity to another.</span></span> <span data-ttu-id="5118c-105">As entidades conectadas permitem definir segmentos e medidas com base em várias fontes de dados.</span><span class="sxs-lookup"><span data-stu-id="5118c-105">Connected entities enable you to define segments and measures based on multiple data sources.</span></span>

<span data-ttu-id="5118c-106">Há dois tipos de relacionamentos.</span><span class="sxs-lookup"><span data-stu-id="5118c-106">There are two types of relationships.</span></span> <span data-ttu-id="5118c-107">Relacionamentos de sistema não editáveis, criados automaticamente, e relacionamentos personalizados, criados e configurados pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="5118c-107">Non-editable system relationships, which are created automatically, and custom relationships created and configured by users.</span></span>

<span data-ttu-id="5118c-108">Durante os processos de correspondência e mesclagem, os relacionamentos do sistema são criados nos bastidores com base na correspondência inteligente.</span><span class="sxs-lookup"><span data-stu-id="5118c-108">During the match and merge processes, system relationships are created behind the scenes based on intelligent matching.</span></span> <span data-ttu-id="5118c-109">Esses relacionamentos ajudam a relacionar os registros do Perfil do Cliente com os registros de outras entidades correspondentes.</span><span class="sxs-lookup"><span data-stu-id="5118c-109">These relationships help relate the Customer Profile records with other corresponding entities' records.</span></span> <span data-ttu-id="5118c-110">O diagrama a seguir ilustra a criação de três relacionamentos do sistema quando a entidade do cliente é correspondida com outras entidades para produzir a entidade final do Perfil do Cliente.</span><span class="sxs-lookup"><span data-stu-id="5118c-110">The following diagram illustrates the creation of three system relationships when the customer entity is matched with additional entities to produce the final Customer Profile entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5118c-111">![Criação de relacionamento](media/relationships-entities-merge.png "Criação de relacionamento")</span><span class="sxs-lookup"><span data-stu-id="5118c-111">![Relationship creation](media/relationships-entities-merge.png "Relationship creation")</span></span>

- <span data-ttu-id="5118c-112">**O Relacionamento *CustomerToContact*** foi criado entre a entidade Cliente e a entidade Contato.</span><span class="sxs-lookup"><span data-stu-id="5118c-112">***CustomerToContact* relationship** was created between the Customer entity and the Contact entity.</span></span> <span data-ttu-id="5118c-113">A entidade Cliente obtém o campo-chave **Contact_contactId** para relacionar-se com o campo-chave da entidade de Contato **contactId**.</span><span class="sxs-lookup"><span data-stu-id="5118c-113">The Customer entity gets the key field **Contact_contactId** to relate to the Contact entity key field **contactId**.</span></span>
- <span data-ttu-id="5118c-114">**O Relacionamento *CustomerToContact*** foi criado entre a entidade Cliente e a entidade Conta.</span><span class="sxs-lookup"><span data-stu-id="5118c-114">***CustomerToAccount* relationship** was created between the Customer entity and the Account entity.</span></span> <span data-ttu-id="5118c-115">A entidade Cliente obtém o campo-chave **Account_accountId** para relacionar-se com o campo-chave da entidade de Conta **accountId**.</span><span class="sxs-lookup"><span data-stu-id="5118c-115">The Customer entity gets the key field **Account_accountId** to relate to the Account entity key field **accountId**.</span></span>
- <span data-ttu-id="5118c-116">**O Relacionamento *CustomerToWebAccount*** foi criado entre a entidade Cliente e a entidade WebAccount.</span><span class="sxs-lookup"><span data-stu-id="5118c-116">***CustomerToWebAccount* relationship** was created between the Customer entity and the WebAccount entity.</span></span> <span data-ttu-id="5118c-117">A entidade Customer obtém o campo-chave **WebAccount_webaccountId** para relacionar-se com o campo-chave da entidade de WebAccount **webaccountId**.</span><span class="sxs-lookup"><span data-stu-id="5118c-117">The Customer entity gets the key field **WebAccount_webaccountId** to relate to the WebAccount entity key field **webaccountId**.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="5118c-118">Criar um relacionamento</span><span class="sxs-lookup"><span data-stu-id="5118c-118">Create a relationship</span></span>

<span data-ttu-id="5118c-119">Defina relacionamentos personalizados na página **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="5118c-119">Define custom relationships on the **Relationships** page.</span></span> <span data-ttu-id="5118c-120">Cada relacionamento consiste em uma entidade de Origem (a entidade que detém a chave estrangeira) e uma entidade de Destino (a entidade para a qual a chave estrangeira da entidade de origem aponta).</span><span class="sxs-lookup"><span data-stu-id="5118c-120">Each relationship consists of a Source entity (the entity that holds the foreign key) and a Target entity (the entity that the source entity's foreign key points to).</span></span>

1. <span data-ttu-id="5118c-121">Nas informações de público-alvo, vá para **Dados** > **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="5118c-121">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="5118c-122">Selecione **Novo relacionamento**.</span><span class="sxs-lookup"><span data-stu-id="5118c-122">Select **New relationship**.</span></span>

3. <span data-ttu-id="5118c-123">No painel **Adicionar relacionamento**, forneça as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="5118c-123">In the **Add relationship** pane, provide the following information:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="5118c-124">![Digite os detalhes do relacionamento](media/relationships-add.png "Digite os detalhes do relacionamento")</span><span class="sxs-lookup"><span data-stu-id="5118c-124">![Enter relationship details](media/relationships-add.png "Enter relationship details")</span></span>

   - <span data-ttu-id="5118c-125">**Nome do relacionamento** : Nome que reflete o objetivo do relacionamento (por exemplo, **AccountWebLogs**).</span><span class="sxs-lookup"><span data-stu-id="5118c-125">**Relationship name**: Name that reflects the purpose of the relationship (for example, **AccountWebLogs**).</span></span>
   - <span data-ttu-id="5118c-126">**Descrição**: Descrição do relacionamento.</span><span class="sxs-lookup"><span data-stu-id="5118c-126">**Description**: Description of the relationship.</span></span>
   - <span data-ttu-id="5118c-127">**Entidade de origem**: Selecione a entidade que é usada como fonte no relacionamento (por exemplo, WebLog).</span><span class="sxs-lookup"><span data-stu-id="5118c-127">**Source entity**: Select the entity that is used as a source in the relationship (for example, WebLog).</span></span>
   - <span data-ttu-id="5118c-128">**Cardinalidade**: Selecione a cardinalidade dos registros da entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="5118c-128">**Cardinality**: Select the cardinality of the source entity records.</span></span> <span data-ttu-id="5118c-129">Por exemplo, "muitos" significa que vários registros do Weblog estão relacionados a uma WebAccount.</span><span class="sxs-lookup"><span data-stu-id="5118c-129">For example, "many" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="5118c-130">**Campo da chave de origem**: Representa o campo de chave estrangeira na entidade de origem.</span><span class="sxs-lookup"><span data-stu-id="5118c-130">**Source key field**: This represents the foreign key field in the source entity.</span></span> <span data-ttu-id="5118c-131">Por exemplo, o WebLog tem o campo de chave estrangeira **accountId**.</span><span class="sxs-lookup"><span data-stu-id="5118c-131">For example, WebLog has the **accountId** foreign key field.</span></span>
   - <span data-ttu-id="5118c-132">**Entidade de destino**: Selecione a entidade que é usada como destino no relacionamento (por exemplo, WebAccount).</span><span class="sxs-lookup"><span data-stu-id="5118c-132">**Target entity**: Select the entity that is used as a target in the relationship (for example, WebAccount).</span></span>
   - <span data-ttu-id="5118c-133">**Cardinalidade de destino**: Selecione a cardinalidade dos registros da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="5118c-133">**Target cardinality**: Select the cardinality of the target entity records.</span></span> <span data-ttu-id="5118c-134">Por exemplo, "uma" significa que vários registros do Weblog estão relacionados a uma WebAccount.</span><span class="sxs-lookup"><span data-stu-id="5118c-134">For example, "one" means that multiple Weblog records are related to one WebAccount.</span></span>
   - <span data-ttu-id="5118c-135">**Campo-chave de destino**: Este campo representa o campo-chave da entidade de destino.</span><span class="sxs-lookup"><span data-stu-id="5118c-135">**Target key field**: This field represents the key field of target entity.</span></span> <span data-ttu-id="5118c-136">Por exemplo, o WebAccount tem o campo de chave **accountId**.</span><span class="sxs-lookup"><span data-stu-id="5118c-136">For example, WebAccount has the **accountId** key field.</span></span>

> [!NOTE]
> <span data-ttu-id="5118c-137">Somente relacionamentos muitos para um e um para um são suportados.</span><span class="sxs-lookup"><span data-stu-id="5118c-137">Only many-to-one and one-to-one relationships are supported.</span></span> <span data-ttu-id="5118c-138">Os relacionamentos muitos-para-muitos podem ser criados usando dois relacionamentos muitos-para-um e uma entidade de link (uma entidade usada para conectar a entidade de origem e a entidade de destino).</span><span class="sxs-lookup"><span data-stu-id="5118c-138">Many-to-many relationships can be created using two many-to-one relationships and a link entity (an entity that is used to connect the source entity and the target entity).</span></span>

## <a name="delete-a-relationship"></a><span data-ttu-id="5118c-139">Excluir um relacionamento</span><span class="sxs-lookup"><span data-stu-id="5118c-139">Delete a relationship</span></span>

1. <span data-ttu-id="5118c-140">Nas informações de público-alvo, vá para **Dados** > **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="5118c-140">In audience insights, go to **Data** > **Relationships**.</span></span>

2. <span data-ttu-id="5118c-141">Marque as caixas de seleção para os relacionamentos que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="5118c-141">Select check boxes for the relationships you want to delete.</span></span>

3. <span data-ttu-id="5118c-142">Selecione **Excluir** na parte superior da tabela **Relacionamentos**.</span><span class="sxs-lookup"><span data-stu-id="5118c-142">Select **Delete** at the top of the **Relationships** table.</span></span>

4. <span data-ttu-id="5118c-143">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="5118c-143">Confirm your deletion.</span></span>

## <a name="next-step"></a><span data-ttu-id="5118c-144">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5118c-144">Next step</span></span>

<span data-ttu-id="5118c-145">Os relacionamentos do sistema e personalizados são usados para criar segmentos com base em várias fontes de dados que não são mais isoladas.</span><span class="sxs-lookup"><span data-stu-id="5118c-145">System and custom relationships are used to create segments based on multiple data sources that are no longer siloed.</span></span> <span data-ttu-id="5118c-146">Para obter mais informações, consulte [Segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="5118c-146">For more information, see [Segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]