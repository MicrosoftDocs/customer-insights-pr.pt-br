---
title: Procurar e filtrar perfis de cliente
description: Encontre rapidamente informações sobre perfis unificados de clientes e filtre os atributos especificados.
ms.date: 01/19/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d675738c43cbdb5f9b478d53d6124db38ba3004d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270052"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="cf213-103">Perfis de clientes: índice de filtro e pesquisa</span><span class="sxs-lookup"><span data-stu-id="cf213-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="cf213-104">O resultado da unificação dos dados do cliente é uma entidade de Perfil do Cliente que fornece uma visão unificada da sua base total de clientes.</span><span class="sxs-lookup"><span data-stu-id="cf213-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="cf213-105">Para [encontrar informações rapidamente sobre um cliente ou grupo de clientes específico](customer-profiles.md), você pode configurar o recurso **Pesquisar** e **Filtrar** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="cf213-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="cf213-106">Leia para saber como os administradores podem editar os atributos na página **Índice de pesquisa e filtro**, que estão disponíveis para os usuários pesquisarem e filtrarem.</span><span class="sxs-lookup"><span data-stu-id="cf213-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="cf213-107">![Filtro de pesquisa](media/search-filter.png "Filtro de pesquisa")</span><span class="sxs-lookup"><span data-stu-id="cf213-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="cf213-108">Adicionar campos e especificar atributos</span><span class="sxs-lookup"><span data-stu-id="cf213-108">Add fields and specify attributes</span></span>

<span data-ttu-id="cf213-109">Se for a primeira vez que você define atributos pesquisáveis como administrador, você precisará primeiro definir os campos indexados.</span><span class="sxs-lookup"><span data-stu-id="cf213-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="cf213-110">Sugerimos que você escolha todos os atributos pelos quais os usuários possam pesquisar e filtrar clientes na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="cf213-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="cf213-111">Você só pode especificar atributos que existem na entidade Perfil do Cliente que você criou durante o processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="cf213-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="cf213-112">Abra a página **Clientes** e selecione **Índice de filtro e pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="cf213-112">Open the **Customers** page and select **Search & filter index**.</span></span>

2. <span data-ttu-id="cf213-113">Selecione **+ Adicionar** para especificar os campos indexados.</span><span class="sxs-lookup"><span data-stu-id="cf213-113">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="cf213-114">Selecione os atributos na lista que você deseja adicionar como campos indexados.</span><span class="sxs-lookup"><span data-stu-id="cf213-114">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="cf213-115">Você sempre pode adicionar mais atributos selecionando **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cf213-115">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="cf213-116">Você também pode remover quaisquer atributos selecionados usando o símbolo **Remover**.</span><span class="sxs-lookup"><span data-stu-id="cf213-116">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="cf213-117">Explore a tabela de campos do cliente Indexado</span><span class="sxs-lookup"><span data-stu-id="cf213-117">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="cf213-118">As informações a seguir são apresentadas na tabela.</span><span class="sxs-lookup"><span data-stu-id="cf213-118">The following information is presented in the table.</span></span>

- <span data-ttu-id="cf213-119">**Nome**: Representa o nome do atributo, como aparece na entidade Perfil do Cliente.</span><span class="sxs-lookup"><span data-stu-id="cf213-119">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="cf213-120">**Tipo de dados**: Especifica se o tipo de dados é uma cadeia de caracteres, um número ou uma data.</span><span class="sxs-lookup"><span data-stu-id="cf213-120">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="cf213-121">**Incluído na pesquisa**: Especifica se esse atributo pode ser usado para pesquisar clientes na página **Clientes** usando o campo **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="cf213-121">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="cf213-122">**Adicionar Filtro**: Controle para definir como esse atributo pode ser usado para filtrar a página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="cf213-122">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="cf213-123">Editando opções de filtragem para um determinado atributo</span><span class="sxs-lookup"><span data-stu-id="cf213-123">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="cf213-124">O menu **Filtro** na página **Clientes** pode incluir um número variável de níveis de atributo (por exemplo, diferentes faixas etárias para filtrar os clientes).</span><span class="sxs-lookup"><span data-stu-id="cf213-124">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="cf213-125">Selecione **Adicionar Filtro** para um determinado atributo na página **Índice de pesquisa e filtro**.</span><span class="sxs-lookup"><span data-stu-id="cf213-125">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="cf213-126">Você pode definir o número de resultados e a ordem em que eles serão organizados.</span><span class="sxs-lookup"><span data-stu-id="cf213-126">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="cf213-127">Dependendo do tipo de dados do atributo, um dos seguintes painéis será exibido.</span><span class="sxs-lookup"><span data-stu-id="cf213-127">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="cf213-128">Atributos do tipo de string: Especifique o número de resultados desejados no painel **Opções do filtro da string** e a política de ordem pela qual eles serão organizados.</span><span class="sxs-lookup"><span data-stu-id="cf213-128">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="cf213-129">Atributos do tipo numérico: Especifique os intervalos incluídos no painel **Opções do filtro de número** e a política de ordem pela qual eles serão organizados.</span><span class="sxs-lookup"><span data-stu-id="cf213-129">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="cf213-130">Atributos do tipo de data: Especifique os intervalos incluídos no painel **Opções do filtro de data** e a política de ordem pela qual eles serão organizados.</span><span class="sxs-lookup"><span data-stu-id="cf213-130">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="cf213-131">Selecione **Salvar** para aplicar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="cf213-131">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="cf213-132">Selecione **Executar** quando estiver pronto para aplicar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="cf213-132">Select **Run** once you're ready to apply your settings.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cf213-133">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="cf213-133">Next steps</span></span>

<span data-ttu-id="cf213-134">Vá até a página **Clientes** para pesquisar perfis de clientes ou usar os campos indexados para ver um subconjunto de todos os perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="cf213-134">Go to the **Customers** page to search for customer profiles or use the indexed fields to see a subset of all customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]