---
title: Atualização incremental de fontes de dados baseadas no Power Query
description: Atualize dados novos e atualizados de grandes fontes de dados baseadas no Power Query.
ms.date: 09/28/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d4b01be75d25fa0e120904924a193171eefec579
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268534"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a><span data-ttu-id="2d539-103">Atualização incremental de fontes de dados baseadas no Power Query</span><span class="sxs-lookup"><span data-stu-id="2d539-103">Incremental refresh for data sources based on Power Query</span></span>

<span data-ttu-id="2d539-104">A atualização incremental de fontes de dados oferece as seguintes vantagens:</span><span class="sxs-lookup"><span data-stu-id="2d539-104">Incremental refresh for data sources provides the following advantages:</span></span>

- <span data-ttu-id="2d539-105">**Atualizações mais rápidas** - Apenas os dados que foram alterados são atualizados.</span><span class="sxs-lookup"><span data-stu-id="2d539-105">**Faster refreshes** - Only data that has changed gets refreshed.</span></span> <span data-ttu-id="2d539-106">Por exemplo, você pode atualizar apenas os últimos cinco dias de um conjunto de dados histórico.</span><span class="sxs-lookup"><span data-stu-id="2d539-106">For example, you might refresh only the past five days of a historical dataset.</span></span>
- <span data-ttu-id="2d539-107">**Maior confiabilidade** - Com atualizações menores, você não precisa manter conexões com sistemas de fontes voláteis por tanto tempo, reduzindo o risco de problemas de conexão.</span><span class="sxs-lookup"><span data-stu-id="2d539-107">**Increased reliability** - With smaller refreshes, you don't need to maintain connections to volatile source systems for as long, reducing the risk of connection issues.</span></span>
- <span data-ttu-id="2d539-108">**Consumo reduzido de recursos** - Atualizar apenas um subconjunto dos dados totais leva a um uso mais eficiente dos recursos de computação e diminui o volume ambiental.</span><span class="sxs-lookup"><span data-stu-id="2d539-108">**Reduced resource consumption** - Refreshing only a subset of your total data leads to more efficient use of computing resources and decreases the environmental footprint.</span></span>

## <a name="configure-incremental-refresh"></a><span data-ttu-id="2d539-109">Configurar atualização incremental</span><span class="sxs-lookup"><span data-stu-id="2d539-109">Configure incremental refresh</span></span>

<span data-ttu-id="2d539-110">Os insights de público-alvo permitem a atualização incremental de fontes de dados importadas por meio do Power Query que oferecem suporte à ingestão incremental.</span><span class="sxs-lookup"><span data-stu-id="2d539-110">Audience insights allows incremental refresh for data sources imported through Power Query that support incremental ingestion.</span></span> <span data-ttu-id="2d539-111">Por exemplo, bancos de dados SQL do Azure com campos de data e hora, que indicam quando os registros de dados foram atualizados pela última vez.</span><span class="sxs-lookup"><span data-stu-id="2d539-111">For example, Azure SQL databases with date and time fields, which indicate when data records were last updated.</span></span>

1. <span data-ttu-id="2d539-112">[Criar uma nova fonte de dados baseada no Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="2d539-112">[Create a new data source based on Power Query](connect-power-query.md).</span></span>

1. <span data-ttu-id="2d539-113">Forneça um nome para a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="2d539-113">Provide a name for the data source.</span></span>

1. <span data-ttu-id="2d539-114">Selecione uma fonte de dados que ofereça suporte à atualização incremental, como o banco de dados SQL do Azure.</span><span class="sxs-lookup"><span data-stu-id="2d539-114">Select a data source that supports incremental refresh, such as Azure SQL database.</span></span>

1. <span data-ttu-id="2d539-115">Selecione as entidades ou tabelas a serem ingeridas.</span><span class="sxs-lookup"><span data-stu-id="2d539-115">Select the entities or tables to ingest.</span></span>

1. <span data-ttu-id="2d539-116">Conclua as etapas de transformação e selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="2d539-116">Complete the transformation steps and select **Next**.</span></span>

1. <span data-ttu-id="2d539-117">Na caixa de diálogo **Configurar atualização incremental**, selecione **Configurar** para abrir as **Configurações de atualização incremental**.</span><span class="sxs-lookup"><span data-stu-id="2d539-117">In the **Set up incremental refresh** dialog box, select **Set up** to open the **Incremental refresh settings**.</span></span> <span data-ttu-id="2d539-118">Se você selecionar **Pular**, a fonte de dados atualizará todo o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="2d539-118">If you select **Skip**, the data source will refresh the entire data set.</span></span>
   > [!TIP]
   > <span data-ttu-id="2d539-119">Você também pode aplicar a atualização incremental posteriormente editando uma fonte de dados existente.</span><span class="sxs-lookup"><span data-stu-id="2d539-119">You can also apply incremental refresh later by editing an existing data source.</span></span>

1. <span data-ttu-id="2d539-120">Em **Configurações de atualização incremental**, você configurará a atualização incremental para todas as entidades selecionadas ao criar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="2d539-120">On **Incremental refresh settings**, you'll configure the incremental refresh for all entities that you selected when creating the data source.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="2d539-121">![Configurar entidades em uma fonte de dados para atualização incremental](media/incremental-refresh-settings.png "Configurar entidades em uma fonte de dados para atualização incremental")</span><span class="sxs-lookup"><span data-stu-id="2d539-121">![Configure entities in a data source for incremental refresh](media/incremental-refresh-settings.png "Configure entities in a data source for incremental refresh")</span></span>

1. <span data-ttu-id="2d539-122">Selecione uma entidade e forneça os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="2d539-122">Select an entity, and provide the following details:</span></span>

   - <span data-ttu-id="2d539-123">**Definir a chave primária** : Selecione uma chave primária para a entidade ou tabela.</span><span class="sxs-lookup"><span data-stu-id="2d539-123">**Define the primary key**: Select a primary key for the entity or table.</span></span>
   - <span data-ttu-id="2d539-124">**Defina o campo "última atualização"** : Este campo exibirá apenas atributos do tipo de data ou hora.</span><span class="sxs-lookup"><span data-stu-id="2d539-124">**Define the "last updated" field**: This field will only display attributes of type date or time.</span></span> <span data-ttu-id="2d539-125">Selecione um atributo que indica quando os registros foram atualizados pela última vez.</span><span class="sxs-lookup"><span data-stu-id="2d539-125">Select an attribute that indicates when the records were last updated.</span></span> <span data-ttu-id="2d539-126">Ele será usado para identificar os registros que se enquadram no período de atualização incremental.</span><span class="sxs-lookup"><span data-stu-id="2d539-126">It will be used to identify the records that fall within the incremental refresh time frame.</span></span>
   - <span data-ttu-id="2d539-127">**Verificar se há atualizações a cada** : Especifique quanto tempo você deseja que dure o período de atualização incremental.</span><span class="sxs-lookup"><span data-stu-id="2d539-127">**Check for updates every**: Specify how long you want the incremental refresh time frame to be.</span></span>

1. <span data-ttu-id="2d539-128">Selecione **Salvar** para concluir a criação da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="2d539-128">Select **Save** to complete the creation of the data source.</span></span> <span data-ttu-id="2d539-129">A atualização inicial dos dados será uma atualização completa.</span><span class="sxs-lookup"><span data-stu-id="2d539-129">The initial data refresh will be a full refresh.</span></span> <span data-ttu-id="2d539-130">Posteriormente, a atualização incremental de dados acontece conforme configurado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="2d539-130">Afterwards, the incremental data refresh happens as configured in the previous step.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]