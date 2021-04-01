---
title: Mapear entidades para unificação de dados
description: Mapeie dados para criar perfis de clientes unificados.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 36b7f7b2fac9497245cf6759506c53753972f173
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595979"
---
# <a name="map-entities-and-attributes"></a><span data-ttu-id="3cc98-103">Mapear entidades e atributos</span><span class="sxs-lookup"><span data-stu-id="3cc98-103">Map entities and attributes</span></span>

<span data-ttu-id="3cc98-104">**Mapear** é o primeiro estágio do processo de unificação de dados de insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="3cc98-104">**Map** is the first stage in the data unification process of audience insights.</span></span> <span data-ttu-id="3cc98-105">O mapeamento consiste em três fases:</span><span class="sxs-lookup"><span data-stu-id="3cc98-105">Mapping consists of three phases:</span></span>

- <span data-ttu-id="3cc98-106">*Seleção de entidade* : Identifique as entidades combináveis que levam a um conjunto de dados com informações mais completas sobre seus clientes.</span><span class="sxs-lookup"><span data-stu-id="3cc98-106">*Entity selection*: Identify the combinable entities that lead to a dataset with more complete information about your customers.</span></span>
- <span data-ttu-id="3cc98-107">*Seleção de atributo*: Para cada entidade, identifique as colunas que você deseja combinar e reconcilie nas fases *corresponder* e *mesclar*.</span><span class="sxs-lookup"><span data-stu-id="3cc98-107">*Attribute selection*: For each entity, identify the columns you want to combine and reconcile in the *match* and *merge* phases.</span></span> <span data-ttu-id="3cc98-108">Essas colunas são chamadas *Atributos*.</span><span class="sxs-lookup"><span data-stu-id="3cc98-108">These columns are called *Attributes*.</span></span>
- <span data-ttu-id="3cc98-109">*Seleção de chave primária e tipo semântico*: Para cada entidade, identifique um atributo que deseja definir como a chave primária dessa entidade e, para cada atributo, identifique um tipo semântico que melhor descreve esse atributo.</span><span class="sxs-lookup"><span data-stu-id="3cc98-109">*Primary key and semantic type selection*: For each entity, identify an attribute you want to define as the primary key for that entity, and for each attribute, identify a semantic type that best describes that attribute.</span></span>

<span data-ttu-id="3cc98-110">Para obter mais informações sobre o fluxo geral de unificação de dados, consulte [Unificar](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="3cc98-110">For more information about the general flow of data unification, see [Unify](data-unification.md).</span></span>

## <a name="select-the-first-entities"></a><span data-ttu-id="3cc98-111">Selecione as primeiras entidades</span><span class="sxs-lookup"><span data-stu-id="3cc98-111">Select the first entities</span></span>

1. <span data-ttu-id="3cc98-112">Nos insights de público-alvo, vá para **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-112">In audience insights, go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="3cc98-113">Inicie a fase de mapeamento escolhendo **Selecionar entidades**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-113">Start the map phase by selecting **Select entities**.</span></span>

3. <span data-ttu-id="3cc98-114">Selecione as entidades e atributos que deseja usar nas fases de *correspondência* e *mesclagem*.</span><span class="sxs-lookup"><span data-stu-id="3cc98-114">Select the entities and attributes you want to use in the *match* and *merge* phases.</span></span> <span data-ttu-id="3cc98-115">Você pode selecionar os atributos necessários individualmente de uma entidade ou incluir todos os atributos de uma entidade marcando a caixa de seleção **Incluir todos os campos** no nível da entidade.</span><span class="sxs-lookup"><span data-stu-id="3cc98-115">You can select the required attributes individually from an entity or include all attributes from an entity by selecting the **Include all fields** checkbox on the entity level.</span></span> <span data-ttu-id="3cc98-116">Recomendamos selecionar pelo menos duas entidades para se beneficiar do processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="3cc98-116">We recommend selecting at least two entities to benefit from the data unification process.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cc98-117">![Adicionar exemplo de entidades](media/data-manager-configure-map-add-entities-example.png "Adicionar exemplo de entidades")</span><span class="sxs-lookup"><span data-stu-id="3cc98-117">![Add entities example](media/data-manager-configure-map-add-entities-example.png "Add entities example")</span></span>

   <span data-ttu-id="3cc98-118">Neste exemplo, estamos adicionando as entidades **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-118">In this example, we're adding the **eCommerceContacts** and **loyCustomers** entities.</span></span> <span data-ttu-id="3cc98-119">Ao escolher essas entidades, você pode obter insights nos quais clientes de negócios online são membros do programa de fidelidade.</span><span class="sxs-lookup"><span data-stu-id="3cc98-119">By choosing these entities, you can derive insights on which of the online business customers are loyalty program members.</span></span>
   
   <span data-ttu-id="3cc98-120">Você pode pesquisar palavras-chave em todos os atributos e entidades para selecionar os atributos necessários que deseja mapear.</span><span class="sxs-lookup"><span data-stu-id="3cc98-120">You can search on keywords across all attributes and entities to select the required attributes you want to map.</span></span>
   
     > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cc98-121">![Exemplo de campos de pesquisa](media/data-manager-configure-map-search-fields-example.png "Exemplo de campos de pesquisa")</span><span class="sxs-lookup"><span data-stu-id="3cc98-121">![Search fields example](media/data-manager-configure-map-search-fields-example.png "Search fields example")</span></span>

4. <span data-ttu-id="3cc98-122">Selecione **Aplicar** para confirmar suas seleções.</span><span class="sxs-lookup"><span data-stu-id="3cc98-122">Select **Apply** to confirm your selections.</span></span>

## <a name="select-primary-key-and-semantic-type-for-attributes"></a><span data-ttu-id="3cc98-123">Selecione a chave primária e o tipo semântico dos atributos</span><span class="sxs-lookup"><span data-stu-id="3cc98-123">Select primary key and semantic type for attributes</span></span>

<span data-ttu-id="3cc98-124">Depois de selecionar suas entidades, a página **Mapa** lista as entidades selecionadas para sua revisão.</span><span class="sxs-lookup"><span data-stu-id="3cc98-124">After selecting your entities, the **Map** page lists the selected entities for your review.</span></span> <span data-ttu-id="3cc98-125">Defina a chave primária para uma entidade e identifique o tipo semântico de um atributo na entidade.</span><span class="sxs-lookup"><span data-stu-id="3cc98-125">Define the primary key for an entity and identify the semantic type for an attribute in the entity.</span></span>

- <span data-ttu-id="3cc98-126">**Chave primária**: Selecione um atributo como chave primária para cada uma de suas entidades.</span><span class="sxs-lookup"><span data-stu-id="3cc98-126">**Primary key**: Select one attribute as a primary key for each of your entities.</span></span> <span data-ttu-id="3cc98-127">Para um atributo ser uma chave primária válida, ele não deve ter valores duplicados, valores ausentes ou valores nulos.</span><span class="sxs-lookup"><span data-stu-id="3cc98-127">For an attribute to be a valid primary key, it shouldn't include duplicate values, missing values, or null values.</span></span> <span data-ttu-id="3cc98-128">Os atributos de tipo de dados cadeia de caracteres, inteiro e GUID têm suporte como chaves primárias e serão exibidos em um campo para você selecionar.</span><span class="sxs-lookup"><span data-stu-id="3cc98-128">String, integer, and GUID data type attributes are supported as primary keys and will be displayed in a field for you to select from.</span></span>

- <span data-ttu-id="3cc98-129">**Tipo de semântico de atributo**: Categorias de seus atributos, como endereço de email ou nome.</span><span class="sxs-lookup"><span data-stu-id="3cc98-129">**Attribute semantic type**: Categories of your attributes, such as email address or name.</span></span> <span data-ttu-id="3cc98-130">Para usar modelos de IA para previsão inteligente de semântica, economizar tempo e melhorar a precisão, defina **Mapeamento inteligente** como **ATIVADO**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-130">To use AI models for smart prediction of semantics, save time and improve accuracy, set **Intelligent mapping** to **ON**.</span></span> <span data-ttu-id="3cc98-131">O mapeamento inteligente destaca a recomendação de semântica baseada em IA no campo **Tipo**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-131">Intelligent mapping highlights AI-based semantics recommendation in the **Type** field.</span></span> <span data-ttu-id="3cc98-132">Se defini-lo como **DESATIVADO**, você verá nossas recomendações de mapeamento regulares.</span><span class="sxs-lookup"><span data-stu-id="3cc98-132">If you set it to **OFF**, you will see our regular mapping recommendations.</span></span> <span data-ttu-id="3cc98-133">Você pode selecionar qualquer tipo semântico da lista de opções disponível e substituir a seleção sugerida.</span><span class="sxs-lookup"><span data-stu-id="3cc98-133">You can select any semantic type from the available list of options and override the suggested selection.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3cc98-134">![Tipo de atributo e previsão semântica](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo de atributo e previsão semântica")</span><span class="sxs-lookup"><span data-stu-id="3cc98-134">![Attribute type and semantic prediction](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Attribute type and semantic prediction")</span></span>

<span data-ttu-id="3cc98-135">Também é possível adicionar um tipo semântico personalizado.</span><span class="sxs-lookup"><span data-stu-id="3cc98-135">Adding a custom semantic type is also possible.</span></span> <span data-ttu-id="3cc98-136">Selecione o campo de tipo para um atributo e digite seu nome de tipo semântico personalizado.</span><span class="sxs-lookup"><span data-stu-id="3cc98-136">Select the type field for an attribute, and type your custom semantic type name.</span></span> <span data-ttu-id="3cc98-137">Dessa forma, você também pode alterar os tipos de atributos que foram identificados pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="3cc98-137">This way, you can also change the attribute types that were identified by the system.</span></span>

<span data-ttu-id="3cc98-138">Todos os atributos para os quais um tipo semântico é automaticamente identificado são agrupados na seção **Rever campos mapeados**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-138">All attributes for which a semantic type is automatically identified are grouped in the **Review mapped fields** section.</span></span> <span data-ttu-id="3cc98-139">Revise esses atributos e seus tipos semânticos, pois eles serão usados para combinar suas entidades na etapa de mesclagem da unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="3cc98-139">Review these attributes and their semantic types because they'll be used to combine your entities in the merge step of data unification.</span></span>

<span data-ttu-id="3cc98-140">Atributos que não são mapeados automaticamente para um tipo semântico são agrupados na seção **Definir os dados nos campos não mapeados**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-140">Attributes that aren't automatically mapped to a semantic type are grouped in the **Define the data in the unmapped fields** section.</span></span> <span data-ttu-id="3cc98-141">Selecione o campo de tipo semântico para os atributos não mapeados ou insira seu nome de tipo de atributo personalizado.</span><span class="sxs-lookup"><span data-stu-id="3cc98-141">Select the semantic type field for the unmapped attributes, or enter your custom attribute-type name.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3cc98-142">![Chave primária e tipo de atributo](media/data-manager-configure-map-add-attributes.png "Chave primária e tipo de atributo")</span><span class="sxs-lookup"><span data-stu-id="3cc98-142">![Primary key and attribute type](media/data-manager-configure-map-add-attributes.png "Primary key and attribute type")</span></span>

> [!NOTE]
> <span data-ttu-id="3cc98-143">Um campo deve ser mapeado para o tipo semântico Person.FullName para preencher o nome do cliente no cartão do cliente.</span><span class="sxs-lookup"><span data-stu-id="3cc98-143">One field should map to the semantic type Person.FullName to populate the customer name in customer card.</span></span> <span data-ttu-id="3cc98-144">Caso contrário, os cartões do cliente aparecerão sem nome.</span><span class="sxs-lookup"><span data-stu-id="3cc98-144">Otherwise, the customer cards will appear nameless.</span></span> 

## <a name="add-and-remove-attributes-and-entities"></a><span data-ttu-id="3cc98-145">Adicionar e remover atributos e entidades</span><span class="sxs-lookup"><span data-stu-id="3cc98-145">Add and remove attributes and entities</span></span>

1. <span data-ttu-id="3cc98-146">Em **Unificar** > **Mapa**, selecione **Editar campos**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-146">On **Unify** > **Map**, select **Edit fields**.</span></span>

2. <span data-ttu-id="3cc98-147">No painel **Editar campos**, adicione ou remova atributos e entidades.</span><span class="sxs-lookup"><span data-stu-id="3cc98-147">In the **Edit fields** pane, add or remove attributes and entities.</span></span> <span data-ttu-id="3cc98-148">Use a pesquisa ou role para localizar e selecionar seus atributos e entidades de interesse.</span><span class="sxs-lookup"><span data-stu-id="3cc98-148">Use the search or scroll to find and select your attributes and entities of interest.</span></span> <span data-ttu-id="3cc98-149">Você não pode remover um atributo ou uma entidade se eles já foram correspondidos.</span><span class="sxs-lookup"><span data-stu-id="3cc98-149">You can't remove an attribute or an entity if they've already been matched.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="3cc98-150">![Adicionar ou remover atributos](media/configure-data-map-edit.png "Adicionar ou remover atributos")</span><span class="sxs-lookup"><span data-stu-id="3cc98-150">![Add or remove attributes](media/configure-data-map-edit.png "Add or remove attributes")</span></span>

3. <span data-ttu-id="3cc98-151">Selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-151">Select **Apply**.</span></span>

## <a name="add-images-to-profiles"></a><span data-ttu-id="3cc98-152">Adicionar imagens aos perfis</span><span class="sxs-lookup"><span data-stu-id="3cc98-152">Add images to profiles</span></span>

<span data-ttu-id="3cc98-153">Se uma entidade contiver URLs para imagens ou logotipos de perfil disponíveis publicamente, você poderá adicioná-los ao perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="3cc98-153">If an entity contains URLs to publicly available profile images or logos, you can add them to the unified customer profile.</span></span>

<span data-ttu-id="3cc98-154">Selecione a entidade e encontre o campo que contém a URL para a imagem do perfil.</span><span class="sxs-lookup"><span data-stu-id="3cc98-154">Select the entity and find the field that contains the URL to the profile image.</span></span> <span data-ttu-id="3cc98-155">No campo de entrada **Tipo**, insira manualmente o seguinte valor:</span><span class="sxs-lookup"><span data-stu-id="3cc98-155">In the **Type** input field, manually enter the following value:</span></span> 
- <span data-ttu-id="3cc98-156">Para uma pessoa: Person.ProfileImage</span><span class="sxs-lookup"><span data-stu-id="3cc98-156">For a person: Person.ProfileImage</span></span>
- <span data-ttu-id="3cc98-157">Para uma organização: Organization.LogoImage</span><span class="sxs-lookup"><span data-stu-id="3cc98-157">For an organization: Organization.LogoImage</span></span>

<span data-ttu-id="3cc98-158">Continue com as etapas de unificação e certifique-se de que o atributo que contém a URL da imagem também seja adicionada à etapa [Mesclar](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="3cc98-158">Continue with the unification steps and ensure the attribute that contains the image URL is also added in the [Merge](merge-entities.md) step.</span></span>

## <a name="set-attributes-for-organizations"></a><span data-ttu-id="3cc98-159">Definir atributos para organizações</span><span class="sxs-lookup"><span data-stu-id="3cc98-159">Set attributes for organizations</span></span>

<span data-ttu-id="3cc98-160">Para organizações (Visualização), o tipo de atributo deve ser mapeado para "Organization.Name"</span><span class="sxs-lookup"><span data-stu-id="3cc98-160">For organizations (Preview), the attribute type should be mapped to "Organization.Name"</span></span>
> [!div class="mx-imgBorder"]
> <span data-ttu-id="3cc98-161">![Chave primária e tipo de atributo B2B](media/configure-data-map-edit-b2b.png "Chave primária e tipo de atributo B2B")</span><span class="sxs-lookup"><span data-stu-id="3cc98-161">![Primary key and attribute type B2B](media/configure-data-map-edit-b2b.png "Primary key and attribute type B2B")</span></span>

## <a name="next-step"></a><span data-ttu-id="3cc98-162">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="3cc98-162">Next step</span></span>

<span data-ttu-id="3cc98-163">Como parte do processo de unificação de dados, vá para a página **Corresponder**.</span><span class="sxs-lookup"><span data-stu-id="3cc98-163">As part of the data unification process, go to the **Match** page.</span></span> <span data-ttu-id="3cc98-164">Visite [**Corresponder**](match-entities.md) para aprender sobre esta fase.</span><span class="sxs-lookup"><span data-stu-id="3cc98-164">Visit [**Match**](match-entities.md) to learn about this phase.</span></span>

> [!TIP]
> <span data-ttu-id="3cc98-165">Confira o seguinte vídeo: [Introdução: Criando um Perfil de Cliente Unificado](https://youtu.be/oBfGEhucAxs).</span><span class="sxs-lookup"><span data-stu-id="3cc98-165">Check out the following video: [Getting Started: Creating a Unified Customer Profile](https://youtu.be/oBfGEhucAxs).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]