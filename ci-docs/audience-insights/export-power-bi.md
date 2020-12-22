---
title: Conector do Power BI
description: Saiba como usar o conector do Dynamics 365 Customer Insights no Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405014"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="908d4-103">Conector do Power BI (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="908d4-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="908d4-104">Crie visualizações para seus dados com o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="908d4-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="908d4-105">Gere insights adicionais e crie relatórios com seus dados de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="908d4-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="908d4-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="908d4-106">Prerequisites</span></span>

- <span data-ttu-id="908d4-107">Você deve ter perfis de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="908d4-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="908d4-108">A versão mais recente do [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) foi instalada no seu computador.</span><span class="sxs-lookup"><span data-stu-id="908d4-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="908d4-109">[Saiba mais sobre o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="908d4-109">[Learn more about Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="908d4-110">Configure o conector do Power BI</span><span class="sxs-lookup"><span data-stu-id="908d4-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="908d4-111">No Power BI Desktop, selecione **Arquivo** > **Obter Dados**.</span><span class="sxs-lookup"><span data-stu-id="908d4-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="908d4-112">Selecione **Ver mais** e procure **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="908d4-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="908d4-113">Selecione o resultado e selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="908d4-113">Select the result and select **Connect**.</span></span>

1. <span data-ttu-id="908d4-114">**Entre** com a mesma conta organizacional usada no Customer Insights e selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="908d4-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="908d4-115">A conta indicada nesta etapa é usada para buscar dados do Customer Insights e não precisa ser a mesma usada para se conectar ao Power BI.</span><span class="sxs-lookup"><span data-stu-id="908d4-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="908d4-116">Para redefinir a conta que é usada para a busca de dados, abra o Power BI e vá para **Arquivo** > **Opções** > **Configurações** > **Configurações da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="908d4-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="908d4-117">Na lista de fontes de dados, selecione **Fazer logon no Dynamics 365 Customer Insights** e, em seguida, selecione **Limpar permissões**.</span><span class="sxs-lookup"><span data-stu-id="908d4-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="908d4-118">Na caixa de diálogo **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="908d4-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="908d4-119">você vê a lista de todos os ambientes aos quais tem acesso.</span><span class="sxs-lookup"><span data-stu-id="908d4-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="908d4-120">Expanda um ambiente e abra qualquer uma das pastas (entidades, medidas, segmentos, enriquecimentos).</span><span class="sxs-lookup"><span data-stu-id="908d4-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="908d4-121">Por exemplo, abra a pasta **Entidades** para ver todas as entidades que você pode importar.</span><span class="sxs-lookup"><span data-stu-id="908d4-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="908d4-122">![Navegador de Conector do Power BI](media/power-bi-navigator.png "Navegador de Conector do Power BI")</span><span class="sxs-lookup"><span data-stu-id="908d4-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="908d4-123">Marque as caixas de seleção ao lado das entidades para incluir e **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="908d4-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="908d4-124">É possível selecionar várias entidades de vários ambientes.</span><span class="sxs-lookup"><span data-stu-id="908d4-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="908d4-125">Você verá uma caixa de diálogo de carregamento enquanto suas entidades são carregadas.</span><span class="sxs-lookup"><span data-stu-id="908d4-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="908d4-126">Depois que todas as entidades selecionadas forem carregadas, você poderá usar os recursos do Power BI para visualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="908d4-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="908d4-127">Grandes conjuntos de dados</span><span class="sxs-lookup"><span data-stu-id="908d4-127">Large data sets</span></span>

<span data-ttu-id="908d4-128">O conector Customer Insights para Power BI foi criado para funcionar com conjuntos de dados que contêm até 1 milhão de perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="908d4-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="908d4-129">Importar conjuntos de dados maiores pode funcionar, mas é demorado.</span><span class="sxs-lookup"><span data-stu-id="908d4-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="908d4-130">Além disso, o processo pode atingir um tempo limite devido a limitações do Power BI.</span><span class="sxs-lookup"><span data-stu-id="908d4-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="908d4-131">Para obter mais informações, consulte [Power BI: recomendações para grandes conjuntos de dados](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="908d4-131">For more information, see [Power BI: Recommendations for large data sets](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="908d4-132">Trabalhe com um subconjunto de dados</span><span class="sxs-lookup"><span data-stu-id="908d4-132">Work with a subset of data</span></span>

<span data-ttu-id="908d4-133">Considere trabalhar com um subconjunto de seus dados.</span><span class="sxs-lookup"><span data-stu-id="908d4-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="908d4-134">Por exemplo, você pode criar [segmentos](segments.md) em vez de exportar todos os registros de clientes para o Power BI.</span><span class="sxs-lookup"><span data-stu-id="908d4-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>
