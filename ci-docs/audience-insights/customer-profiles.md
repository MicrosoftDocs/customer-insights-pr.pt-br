---
title: Exibir perfis de cliente
description: Obtenha uma exibição combinada de seus dados de cliente unificados.
ms.date: 12/01/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a5d928ae518f3cb1afbf8e2b197e51b27665f6e0
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269730"
---
# <a name="customer-profiles"></a><span data-ttu-id="64635-103">Perfis do cliente</span><span class="sxs-lookup"><span data-stu-id="64635-103">Customer profiles</span></span>

<span data-ttu-id="64635-104">A página **Clientes** mostra uma exibição combinada de seus clientes, com base nos dados de perfil coletados usando [todas as fontes de dados](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="64635-104">The **Customers** page shows a combined view of your customers, based on profile data gathered from [all data sources](data-sources.md).</span></span> <span data-ttu-id="64635-105">Os perfis de clientes ficam disponíveis depois que você [cria a entidade do Cliente unificada](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="64635-105">Customer profiles are available once you [create the unified Customer entity](data-unification.md).</span></span> <span data-ttu-id="64635-106">Certifique-se de concluir o processo de unificação de dados para obter visões mais amplas de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="64635-106">Make sure you complete the data unification process to get richer views of your customers.</span></span> <span data-ttu-id="64635-107">A página também permite que você procure clientes.</span><span class="sxs-lookup"><span data-stu-id="64635-107">The page also lets you search for customers.</span></span>

<span data-ttu-id="64635-108">Os clientes podem ser indivíduos ou organizações (visualização).</span><span class="sxs-lookup"><span data-stu-id="64635-108">Customers can be individuals or organizations (preview).</span></span> <span data-ttu-id="64635-109">Cada perfil de cliente ou organização é representado por um bloco.</span><span class="sxs-lookup"><span data-stu-id="64635-109">Each customer or organization profile is represented by a tile.</span></span> <span data-ttu-id="64635-110">Selecione um bloco para ver informações adicionais sobre esse cliente ou organização específica.</span><span class="sxs-lookup"><span data-stu-id="64635-110">Select a tile to see additional information on that specific customer or organization.</span></span> <span data-ttu-id="64635-111">Use os controles de paginação na parte inferior da página para ver registros adicionais.</span><span class="sxs-lookup"><span data-stu-id="64635-111">Use the pagination controls at the bottom of the page to see additional records.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="64635-112">![Perfis do cliente B2C](media/profiles-customers.png "Perfis do cliente B2C")</span><span class="sxs-lookup"><span data-stu-id="64635-112">![B2C customer profiles](media/profiles-customers.png "B2C customer profiles")</span></span>

<span data-ttu-id="64635-113">Organizações (Versão Prévia)</span><span class="sxs-lookup"><span data-stu-id="64635-113">Organizations (Preview)</span></span>
> [!div class="mx-imgBorder"] 
> <span data-ttu-id="64635-114">![Perfis do cliente B2B](media/profile-customers-b2b.png "Perfis do cliente B2B")</span><span class="sxs-lookup"><span data-stu-id="64635-114">![B2B customer profiles](media/profile-customers-b2b.png "B2B customer profiles")</span></span>

> [!NOTE]
> <span data-ttu-id="64635-115">Se você não conseguir ver os blocos ao selecionar **Clientes** na navegação, seu administrador precisará [definir pelo menos um atributo pesquisável](search-filter-index.md) no **Índice de filtro e pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="64635-115">If you can't see the tiles when you select **Customers** in navigation, your administrator needs to [define at least one searchable attribute](search-filter-index.md) on the **Search & filter index**.</span></span>

## <a name="search-for-customers"></a><span data-ttu-id="64635-116">Procurar clientes</span><span class="sxs-lookup"><span data-stu-id="64635-116">Search for customers</span></span>

<span data-ttu-id="64635-117">Procure clientes inserindo um nome ou algum outro atributo na caixa de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="64635-117">Search for customers by entering a name or some other attribute in the search box.</span></span> <span data-ttu-id="64635-118">A pesquisa só funciona dentro da entidade Perfil do Cliente criada durante o processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="64635-118">The search only works within the Customer Profile entity created during the data unification process.</span></span>

<span data-ttu-id="64635-119">Como administrador, você pode configurar os atributos pesquisáveis usando a página **Índice de filtro e pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="64635-119">As an admin, you can configure the searchable attributes using the **Search & filter index** page.</span></span> <span data-ttu-id="64635-120">Para obter mais informações, consulte [Gerenciar Índice de filtro e pesquisa](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="64635-120">For more information, see [Manage search & filter index](search-filter-index.md).</span></span>

## <a name="filter-customers"></a><span data-ttu-id="64635-121">Filtrar clientes</span><span class="sxs-lookup"><span data-stu-id="64635-121">Filter customers</span></span>

<span data-ttu-id="64635-122">Você pode filtrar os clientes pelos campos da entidade Perfil do Cliente.</span><span class="sxs-lookup"><span data-stu-id="64635-122">You can filter customers by the Customer Profile entity fields.</span></span> <span data-ttu-id="64635-123">Semelhante à pesquisa, seu admin precisará primeiro definir os campos como filtráveis usando a página **Índice de filtro e pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="64635-123">Similar to search, your admin will first need to define the fields as filterable using the **Search & filter index** page.</span></span>

1. <span data-ttu-id="64635-124">Selecione **Filtro** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="64635-124">Select **Filter** on the **Customers** page.</span></span>

2. <span data-ttu-id="64635-125">Marque as caixas próximas aos atributos pelos quais você deseja filtrar os clientes.</span><span class="sxs-lookup"><span data-stu-id="64635-125">Check the boxes next to the attributes you want to filter customers by.</span></span>

   > [!div class="mx-imgBorder"] 
   > <span data-ttu-id="64635-126">![Perfis do cliente](media/profiles-customers3.png "Perfis do cliente")</span><span class="sxs-lookup"><span data-stu-id="64635-126">![Customer profiles](media/profiles-customers3.png "Customer profiles")</span></span>

3. <span data-ttu-id="64635-127">Remova seus filtros selecionando **Limpar filtros** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="64635-127">Remove your filters by selecting **Clear filters** on the **Customers** page.</span></span>

##  <a name="customer-details-page"></a><span data-ttu-id="64635-128">Página Detalhes do cliente</span><span class="sxs-lookup"><span data-stu-id="64635-128">Customer details page</span></span>

<span data-ttu-id="64635-129">Selecione qualquer um dos blocos do cliente para abrir a **página Detalhes do cliente**.</span><span class="sxs-lookup"><span data-stu-id="64635-129">Select any of the customer tiles to open the **Customer details page**.</span></span> <span data-ttu-id="64635-130">Essa exibição contém informações unificadas para o cliente selecionado.</span><span class="sxs-lookup"><span data-stu-id="64635-130">This view contains unified information for the selected customer.</span></span>

<span data-ttu-id="64635-131">Os detalhes do cliente incluem:</span><span class="sxs-lookup"><span data-stu-id="64635-131">Customer details include:</span></span>

-   <span data-ttu-id="64635-132">**Bloco do perfil do cliente:** este bloco mostra os diferentes valores da entidade unificada do perfil do cliente.</span><span class="sxs-lookup"><span data-stu-id="64635-132">**Customer profile tile:** This tile shows the different values from the unified customer profile entity.</span></span> <span data-ttu-id="64635-133">Esses detalhes podem incluir endereço de email, nome, cidade e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="64635-133">These details can include email address, name, city, and so on.</span></span> 

-   <span data-ttu-id="64635-134">**Interesses potenciais, marcas potenciais:** mostra se você configurou um enriquecimento primário.</span><span class="sxs-lookup"><span data-stu-id="64635-134">**Potential interests, potential brands:** Shows if you configured a first-party enrichment.</span></span> <span data-ttu-id="64635-135">Representa interesses e afinidades potenciais para marcas que um cliente com um perfil semelhante a este possa ter.</span><span class="sxs-lookup"><span data-stu-id="64635-135">It represents potential interests and affinities for brands a customer with a profile similar to this customer might have.</span></span> <span data-ttu-id="64635-136">Para obter mais informações, consulte [Enriquecer os perfis de clientes com afinidades de marca e de interesse](enrichment-microsoft-graph.md).</span><span class="sxs-lookup"><span data-stu-id="64635-136">For more information, see [Enrich customer profiles with brand and interest affinities](enrichment-microsoft-graph.md).</span></span>

-   <span data-ttu-id="64635-137">**Medidas:** mostra se você configurou uma ou mais medidas de um tipo específico: medidas de atributo do cliente.</span><span class="sxs-lookup"><span data-stu-id="64635-137">**Measures:** Shows if you configured one or more measures of a specific type: customer attribute measures.</span></span> <span data-ttu-id="64635-138">Elas incluem KPIs calculados em torno de seus clientes no nível do cliente individual.</span><span class="sxs-lookup"><span data-stu-id="64635-138">They include calculated KPIs around your customers on the individual customer level.</span></span> <span data-ttu-id="64635-139">Para obter mais informações, consulte [Definir e gerenciar medidas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="64635-139">For more information, see [Define and manage measures](measures.md).</span></span>

-   <span data-ttu-id="64635-140">**Linha do tempo da atividade:** mostra se você configurou atividades.</span><span class="sxs-lookup"><span data-stu-id="64635-140">**Activity timeline:** Shows if you have configured activities.</span></span> <span data-ttu-id="64635-141">A exibição da linha do tempo contém atividades classificadas cronologicamente desse cliente, começando com a atividade mais recente.</span><span class="sxs-lookup"><span data-stu-id="64635-141">The timeline view contains chronologically sorted activities of this customer, starting with the most recent activity.</span></span> <span data-ttu-id="64635-142">Para obter mais informações, consulte [Atividades do cliente](activities.md).</span><span class="sxs-lookup"><span data-stu-id="64635-142">For more information, see [Customer activities](activities.md).</span></span>

<span data-ttu-id="64635-143">Selecione **Voltar aos Clientes** para retornar à página de pesquisa do cliente.</span><span class="sxs-lookup"><span data-stu-id="64635-143">Select **Back to Customers** to return to the customer search page.</span></span>

## <a name="next-steps"></a><span data-ttu-id="64635-144">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="64635-144">Next steps</span></span>

<span data-ttu-id="64635-145">[Adicione mais fontes de dados](data-sources.md) ou [crie segmentos de clientes](segments.md).</span><span class="sxs-lookup"><span data-stu-id="64635-145">[Add more data sources](data-sources.md) or [create customer segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]