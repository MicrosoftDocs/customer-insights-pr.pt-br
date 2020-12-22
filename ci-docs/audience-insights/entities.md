---
title: Entidades e conjuntos de dados
description: Exiba os dados na página Entidades.
ms.date: 04/16/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: e3f41c0424b2cd756d72ae6af9d5225ebba92628
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405020"
---
# <a name="entities-in-audience-insights"></a><span data-ttu-id="da6fa-103">Entidades em insights de público-alvo</span><span class="sxs-lookup"><span data-stu-id="da6fa-103">Entities in audience insights</span></span>

<span data-ttu-id="da6fa-104">Após [configurar suas fontes de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="da6fa-104">After [configuring your data sources](data-sources.md), go to the **Entities** page to evaluate the quality of the ingested data.</span></span> <span data-ttu-id="da6fa-105">As entidades são consideradas conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="da6fa-105">Entities are considered datasets.</span></span> <span data-ttu-id="da6fa-106">Vários recursos do Dynamics 365 Customer Insights são criados com base nessas entidades.</span><span class="sxs-lookup"><span data-stu-id="da6fa-106">Multiple capabilities of Dynamics 365 Customer Insights are built around these entities.</span></span> <span data-ttu-id="da6fa-107">Analisá-los de perto pode ajudá-lo a validar a saída desses recursos.</span><span class="sxs-lookup"><span data-stu-id="da6fa-107">Reviewing them closely can help you validate the output of those capabilities.</span></span>

<span data-ttu-id="da6fa-108">A página **Entidades** lista as entidades e tem várias colunas:</span><span class="sxs-lookup"><span data-stu-id="da6fa-108">The **Entities** page lists entities and includes several columns:</span></span>

- <span data-ttu-id="da6fa-109">**Nome** : O nome da sua entidade de dados.</span><span class="sxs-lookup"><span data-stu-id="da6fa-109">**Name**: The name of your data entity.</span></span> <span data-ttu-id="da6fa-110">Se você vir um símbolo de aviso próximo ao nome de uma entidade, significa que os dados dessa entidade não foram carregados com êxito.</span><span class="sxs-lookup"><span data-stu-id="da6fa-110">If you see a warning symbol next to an entity name, it means that the data for that entity didn't load successfully.</span></span>
- <span data-ttu-id="da6fa-111">**Fonte**: O tipo de fontes de dados que ingeriu a entidade</span><span class="sxs-lookup"><span data-stu-id="da6fa-111">**Source**: The type of data source that ingested the entity</span></span>
- <span data-ttu-id="da6fa-112">**Criada por**: Nome da pessoa que criou a entidade</span><span class="sxs-lookup"><span data-stu-id="da6fa-112">**Created by**: Name of the person who created the entity</span></span>
- <span data-ttu-id="da6fa-113">**Criada**: Data e hora de criação da entidade</span><span class="sxs-lookup"><span data-stu-id="da6fa-113">**Created**: Date and time of the entity creation</span></span>
- <span data-ttu-id="da6fa-114">**Atualizada por**: Nome da pessoa que atualizou a entidade</span><span class="sxs-lookup"><span data-stu-id="da6fa-114">**Updated by**: Name of the person who updated the entity</span></span>
- <span data-ttu-id="da6fa-115">**Ultima atualização**: Data e hora da última atualização da entidade</span><span class="sxs-lookup"><span data-stu-id="da6fa-115">**Last updated**: Date and time of the last update of the entity</span></span>
- <span data-ttu-id="da6fa-116">**Última atualização**: Data e hora da última atualização de dados</span><span class="sxs-lookup"><span data-stu-id="da6fa-116">**Last refresh**: Date and time of the last data refresh</span></span>

## <a name="exploring-a-specific-entitys-data"></a><span data-ttu-id="da6fa-117">Explorando dados de uma entidade específica</span><span class="sxs-lookup"><span data-stu-id="da6fa-117">Exploring a specific entity's data</span></span>

<span data-ttu-id="da6fa-118">Selecione uma entidade para explorar os diferentes campos e registros incluídos nessa entidade.</span><span class="sxs-lookup"><span data-stu-id="da6fa-118">Select an entity to explore the different fields and records included within that entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="da6fa-119">![Selecionar uma entidade](media/data-manager-entities-data.png "Selecionar uma entidade")</span><span class="sxs-lookup"><span data-stu-id="da6fa-119">![Select an entity](media/data-manager-entities-data.png "Select an entity")</span></span>

- <span data-ttu-id="da6fa-120">A guia **Dados** é selecionada por padrão e mostra uma tabela que lista detalhes sobre os registros individuais da entidade.</span><span class="sxs-lookup"><span data-stu-id="da6fa-120">The **Data** tab is selected by default and shows a table listing details about individual records of the entity.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="da6fa-121">![Tabela de campos](media/data-manager-entities-fields.PNG "Tabela de campos")</span><span class="sxs-lookup"><span data-stu-id="da6fa-121">![Fields table](media/data-manager-entities-fields.PNG "Fields table")</span></span>

- <span data-ttu-id="da6fa-122">A guia **Campos** mostra uma tabela para revisar detalhes da entidade selecionada, como nomes de campos, tipos de dados e tipos.</span><span class="sxs-lookup"><span data-stu-id="da6fa-122">The **Fields** tab shows a table to review details for the selected entity, such as field names, data types, and types.</span></span> <span data-ttu-id="da6fa-123">A coluna **Tipo** mostra os tipos associados de Common Data Model que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos usuários.</span><span class="sxs-lookup"><span data-stu-id="da6fa-123">The **Type** column shows Common Data Model associated types, which are either auto-identified by the system or [manually mapped](map-entities.md) by users.</span></span> <span data-ttu-id="da6fa-124">Esses são tipos semânticos que podem diferir dos tipos de dados dos atributos - por exemplo, o campo *Email* abaixo tem um tipo de dados *Texto*, mas seu tipo de Common Data Model (semântico) pode ser *Email* ou *Endereço de E-mail*.</span><span class="sxs-lookup"><span data-stu-id="da6fa-124">These are semantic types that can differ from the attributes' data types—for example, the field *Email* below has a data type *Text* but its (semantic) Common Data Model type might be *Email* or *EmailAddress*.</span></span>

> [!NOTE]
> <span data-ttu-id="da6fa-125">Ambas as tabelas mostram apenas uma amostra dos dados da sua entidade.</span><span class="sxs-lookup"><span data-stu-id="da6fa-125">Both tables show only a sample of your entity's data.</span></span> <span data-ttu-id="da6fa-126">Para visualizar o conjunto completo de dados, vá para a página **Fontes de dados**, selecione uma entidade, selecione **Editar** e, em seguida, visualize os dados dessa entidade com o editor Power Query, conforme explicado em [Fontes de dados](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="da6fa-126">To view the full data set, go to the **Data sources** page, select an entity, select **Edit**, and then view this entity's data with the Power Query editor as explained in [Data sources](data-sources.md).</span></span>

<span data-ttu-id="da6fa-127">Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características importantes dos dados, como nulos, valores ausentes, valores exclusivos, contagens e distribuições, conforme aplicável a seus dados.</span><span class="sxs-lookup"><span data-stu-id="da6fa-127">To learn more about the data ingested in the entity, the **Summary** column provides you with some important characteristics of the data, such as nulls, missing values, unique values, counts, and distributions, as applicable to your data.</span></span>

<span data-ttu-id="da6fa-128">Selecione o ícone do gráfico para ver o resumo dos dados.</span><span class="sxs-lookup"><span data-stu-id="da6fa-128">Select the chart icon to see the summary of the data.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="da6fa-129">![Símbolo de resumo](media/data-manager-entities-summary.png "Tabela de resumo de dados")</span><span class="sxs-lookup"><span data-stu-id="da6fa-129">![Summary symbol](media/data-manager-entities-summary.png "Data summary table")</span></span>

### <a name="next-step"></a><span data-ttu-id="da6fa-130">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="da6fa-130">Next step</span></span>

<span data-ttu-id="da6fa-131">Veja o tópico [Unificar](data-unification.md) para saber como *mapear*, *corresponder* e *mesclar* os dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="da6fa-131">See the [Unify](data-unification.md) topic to learn how to *map*, *match*, and *merge* the ingested data.</span></span>
