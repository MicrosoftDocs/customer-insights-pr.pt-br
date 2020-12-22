---
title: Procurar e filtrar perfis de cliente
description: Encontre rapidamente informações sobre perfis unificados de clientes e filtre os atributos especificados.
ms.date: 04/16/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1842ad333c23bb155abc89167556163ae79cdd34
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405056"
---
# <a name="customer-profiles-search--filter-index"></a><span data-ttu-id="ca6d5-103">Perfis de clientes: índice de filtro e pesquisa</span><span class="sxs-lookup"><span data-stu-id="ca6d5-103">Customer profiles: Search & filter index</span></span>

<span data-ttu-id="ca6d5-104">O resultado da unificação dos dados do cliente é uma entidade de Perfil do Cliente que fornece uma visão unificada da sua base total de clientes.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-104">The result of unifying your customer data is a Customer Profile entity that provides a unified view into your total customer base.</span></span> <span data-ttu-id="ca6d5-105">Para [encontrar informações rapidamente sobre um cliente ou grupo de clientes específico](customer-profiles.md), você pode configurar o recurso **Pesquisar** e **Filtrar** na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-105">To quickly [find information on a specific customer or group of customers](customer-profiles.md), you can configure the **Search** and **Filter** capabilities on the **Customers** page.</span></span> <span data-ttu-id="ca6d5-106">Leia para saber como os administradores podem editar os atributos na página **Índice de pesquisa e filtro**, que estão disponíveis para os usuários pesquisarem e filtrarem.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-106">Read on to learn how admins can edit the attributes on the **Search & filter index** page, which are available to users for searching and filtering.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="ca6d5-107">![Filtro de pesquisa](media/search-filter.png "Filtro de pesquisa")</span><span class="sxs-lookup"><span data-stu-id="ca6d5-107">![Search filter](media/search-filter.png "Search filter")</span></span>

## <a name="add-fields-and-specify-attributes"></a><span data-ttu-id="ca6d5-108">Adicionar campos e especificar atributos</span><span class="sxs-lookup"><span data-stu-id="ca6d5-108">Add fields and specify attributes</span></span>

<span data-ttu-id="ca6d5-109">Se for a primeira vez que você define atributos pesquisáveis como administrador, você precisará primeiro definir os campos indexados.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-109">If it's the first time you define searchable attributes as an administrator, you need to define indexed fields first.</span></span> <span data-ttu-id="ca6d5-110">Sugerimos que você escolha todos os atributos pelos quais os usuários possam pesquisar e filtrar clientes na página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-110">We suggest you choose all the attributes by which users can search and filter customers on the **Customers** page.</span></span> <span data-ttu-id="ca6d5-111">Você só pode especificar atributos que existem na entidade Perfil do Cliente que você criou durante o processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-111">You can only specify attributes that exist in the Customer Profile entity that you created during the data unification process.</span></span>

1. <span data-ttu-id="ca6d5-112">Abra a página **Clientes** e selecione **Índice de filtro e pesquisa**.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-112">Open the **Customers** page and select **Search & filter index**.</span></span>

> [!NOTE]
> <span data-ttu-id="ca6d5-113">Criamos uma configuração padrão do índice de pesquisa nos atributos disponíveis na entidade Cliente a partir dos seguintes tipos semânticos, conforme definido na página Mapa.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-113">We create a default search index configuration on the available attributes in the Customer entity from the following semantic types as defined on the Map page.</span></span>
> - <span data-ttu-id="ca6d5-114">Nome, Sobrenome, Nome do meio, Nome Completo da Pessoa</span><span class="sxs-lookup"><span data-stu-id="ca6d5-114">Person First name, Last name, Middle name, Full Name</span></span>
> - <span data-ttu-id="ca6d5-115">Nome da Organização</span><span class="sxs-lookup"><span data-stu-id="ca6d5-115">Organization Name</span></span>
> - <span data-ttu-id="ca6d5-116">Endereço de Email</span><span class="sxs-lookup"><span data-stu-id="ca6d5-116">Email address</span></span>
> - <span data-ttu-id="ca6d5-117">Número de telefone</span><span class="sxs-lookup"><span data-stu-id="ca6d5-117">Phone number</span></span>
> - <span data-ttu-id="ca6d5-118">Informações sobre local</span><span class="sxs-lookup"><span data-stu-id="ca6d5-118">Location information</span></span>

2. <span data-ttu-id="ca6d5-119">Selecione **+ Adicionar** para especificar os campos indexados.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-119">Select **+ Add** to specify the indexed fields.</span></span>

3. <span data-ttu-id="ca6d5-120">Selecione os atributos na lista que você deseja adicionar como campos indexados.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-120">Select the attributes in the list you want to add as indexed fields.</span></span> <span data-ttu-id="ca6d5-121">Você sempre pode adicionar mais atributos selecionando **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-121">You can always add more attributes by selecting **Add**.</span></span> <span data-ttu-id="ca6d5-122">Você também pode remover quaisquer atributos selecionados usando o símbolo **Remover**.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-122">You can also remove any selected attributes by selecting the **Remove** symbol.</span></span>

## <a name="explore-the-indexed-customer-fields-table"></a><span data-ttu-id="ca6d5-123">Explore a tabela de campos do cliente Indexado</span><span class="sxs-lookup"><span data-stu-id="ca6d5-123">Explore the Indexed customer fields table</span></span>

<span data-ttu-id="ca6d5-124">As informações a seguir são apresentadas na tabela.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-124">The following information is presented in the table.</span></span>

- <span data-ttu-id="ca6d5-125">**Nome**: Representa o nome do atributo, como aparece na entidade Perfil do Cliente.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-125">**Name**: Represents the attribute's name as it appears in the Customer Profile entity.</span></span>
- <span data-ttu-id="ca6d5-126">**Tipo de dados**: Especifica se o tipo de dados é uma cadeia de caracteres, um número ou uma data.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-126">**Data type**: Specifies whether the data type is a string, a number, or a date.</span></span>
- <span data-ttu-id="ca6d5-127">**Incluído na pesquisa**: Especifica se esse atributo pode ser usado para pesquisar clientes na página **Clientes** usando o campo **Pesquisar**.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-127">**Included in search**: Specifies whether this attribute can be used for searching customers on the **Customers** page using the **Search** field.</span></span>
- <span data-ttu-id="ca6d5-128">**Adicionar Filtro**: Controle para definir como esse atributo pode ser usado para filtrar a página **Clientes**.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-128">**Add Filter**: Control to define how this attribute can be used for filtering on the **Customers** page.</span></span>

## <a name="editing-filtering-options-for-a-given-attribute"></a><span data-ttu-id="ca6d5-129">Editando opções de filtragem para um determinado atributo</span><span class="sxs-lookup"><span data-stu-id="ca6d5-129">Editing filtering options for a given attribute</span></span>

<span data-ttu-id="ca6d5-130">O menu **Filtro** na página **Clientes** pode incluir um número variável de níveis de atributo (por exemplo, diferentes faixas etárias para filtrar os clientes).</span><span class="sxs-lookup"><span data-stu-id="ca6d5-130">The **Filter** menu on the **Customers** page can include a varying number of attribute levels (for example, different age groups to filter customers by).</span></span>

1. <span data-ttu-id="ca6d5-131">Selecione **Adicionar Filtro** para um determinado atributo na página **Índice de pesquisa e filtro**.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-131">Select **Add Filter** for a given attribute on the **Search & filter index** page.</span></span> <span data-ttu-id="ca6d5-132">Você pode definir o número de resultados e a ordem em que eles serão organizados.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-132">You can define the number of results and the order in which they'll be organized.</span></span> <span data-ttu-id="ca6d5-133">Dependendo do tipo de dados do atributo, um dos seguintes painéis será exibido.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-133">Depending on the attribute's data type, one of the following panes appears.</span></span>

- <span data-ttu-id="ca6d5-134">Atributos do tipo de string: Especifique o número de resultados desejados no painel **Opções do filtro da string** e a política de ordem pela qual eles serão organizados.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-134">String-type attributes: Specify the number of desired results on the **String filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="ca6d5-135">Atributos do tipo numérico: Especifique os intervalos incluídos no painel **Opções do filtro de número** e a política de ordem pela qual eles serão organizados.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-135">Numerical-type attributes: Specify the intervals included on the **Number filter options** pane and the order policy by which they'll be organized.</span></span>

- <span data-ttu-id="ca6d5-136">Atributos do tipo de data: Especifique os intervalos incluídos no painel **Opções do filtro de data** e a política de ordem pela qual eles serão organizados.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-136">Date-type attributes:  Specify the intervals included on the **Date filter options** pane and the order policy by which they'll be organized.</span></span>

2. <span data-ttu-id="ca6d5-137">Selecione **Salvar** para aplicar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-137">Select **Save** to apply your changes.</span></span>

3. <span data-ttu-id="ca6d5-138">Selecione **Executar** quando estiver pronto para aplicar suas configurações.</span><span class="sxs-lookup"><span data-stu-id="ca6d5-138">Select **Run** once you're ready to apply your settings.</span></span>
