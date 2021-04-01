---
title: Conector do Power BI
description: Saiba como usar o conector do Dynamics 365 Customer Insights no Power BI.
ms.date: 09/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: e43e2f9dbc84ebfbf2154990a752740f973296cb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596025"
---
# <a name="connector-for-power-bi-preview"></a><span data-ttu-id="08f4e-103">Conector do Power BI (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="08f4e-103">Connector for Power BI (preview)</span></span>

<span data-ttu-id="08f4e-104">Crie visualizações para seus dados com o Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="08f4e-104">Create visualizations for your data with the Power BI Desktop.</span></span> <span data-ttu-id="08f4e-105">Gere insights adicionais e crie relatórios com seus dados de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="08f4e-105">Generate additional insights and build reports with your unified customer data.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="08f4e-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="08f4e-106">Prerequisites</span></span>

- <span data-ttu-id="08f4e-107">Você deve ter perfis de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="08f4e-107">You have unified customer profiles.</span></span>
- <span data-ttu-id="08f4e-108">A versão mais recente do [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalado no seu computador.</span><span class="sxs-lookup"><span data-stu-id="08f4e-108">The latest version of [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) is installed on your computer.</span></span> <span data-ttu-id="08f4e-109">[Saiba mais sobre o Power BI Desktop](/power-bi/desktop-what-is-desktop).</span><span class="sxs-lookup"><span data-stu-id="08f4e-109">[Learn more about Power BI Desktop](/power-bi/desktop-what-is-desktop).</span></span>

## <a name="configure-the-connector-for-power-bi"></a><span data-ttu-id="08f4e-110">Configure o conector do Power BI</span><span class="sxs-lookup"><span data-stu-id="08f4e-110">Configure the connector for Power BI</span></span>

1. <span data-ttu-id="08f4e-111">No Power BI Desktop, selecione **Arquivo** > **Obter Dados**.</span><span class="sxs-lookup"><span data-stu-id="08f4e-111">In Power BI Desktop, select **File** > **Get Data**.</span></span>

1. <span data-ttu-id="08f4e-112">Selecione **Ver mais** e procure **Dynamics 365 Customer Insights**</span><span class="sxs-lookup"><span data-stu-id="08f4e-112">Select **See more** and search for **Dynamics 365 Customer Insights**</span></span>

1. <span data-ttu-id="08f4e-113">Selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="08f4e-113">Select **Connect**.</span></span>

1. <span data-ttu-id="08f4e-114">**Entre** com a mesma conta organizacional usada no Customer Insights e selecione **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="08f4e-114">**Sign in** with the same organizational account you use for Customer Insights and select **Connect**.</span></span>
   > [!NOTE]
   > <span data-ttu-id="08f4e-115">A conta indicada nesta etapa é usada para buscar dados do Customer Insights e não precisa ser a mesma usada para se conectar ao Power BI.</span><span class="sxs-lookup"><span data-stu-id="08f4e-115">The account you indicate in this step is used to fetch data from Customer Insights and doesn't need to be the same you are signed in to Power BI.</span></span> <span data-ttu-id="08f4e-116">Para redefinir a conta que é usada para a busca de dados, abra o Power BI e vá para **Arquivo** > **Opções** > **Configurações** > **Configurações da fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="08f4e-116">To reset the account that is used for data fetching, open Power BI and go to **File** > **Options** > **Settings** > **Data source settings**.</span></span> <span data-ttu-id="08f4e-117">Na lista de fontes de dados, selecione **Fazer logon no Dynamics 365 Customer Insights** e, em seguida, selecione **Limpar permissões**.</span><span class="sxs-lookup"><span data-stu-id="08f4e-117">In the list of data sources, select **Dynamics 365 Customer Insights Login** and select **Clear permissions**.</span></span>  

1. <span data-ttu-id="08f4e-118">Na caixa de diálogo **Navegador**.</span><span class="sxs-lookup"><span data-stu-id="08f4e-118">In the **Navigator** dialog box.</span></span> <span data-ttu-id="08f4e-119">você vê a lista de todos os ambientes aos quais tem acesso.</span><span class="sxs-lookup"><span data-stu-id="08f4e-119">you see the list of all environments you have access to.</span></span> <span data-ttu-id="08f4e-120">Expanda um ambiente e abra qualquer uma das pastas (entidades, medidas, segmentos, enriquecimentos).</span><span class="sxs-lookup"><span data-stu-id="08f4e-120">Expand an environment and open any of the folders (entities, measures, segments, enrichments).</span></span> <span data-ttu-id="08f4e-121">Por exemplo, abra a pasta **Entidades** para ver todas as entidades que você pode importar.</span><span class="sxs-lookup"><span data-stu-id="08f4e-121">For example, open the **Entities** folder, to see all entities you can import.</span></span>

   <span data-ttu-id="08f4e-122">![Navegador de Conector do Power BI](media/power-bi-navigator.png "Navegador de Conector do Power BI")</span><span class="sxs-lookup"><span data-stu-id="08f4e-122">![Power BI Connector Navigator](media/power-bi-navigator.png "Power BI Connector Navigator")</span></span>

1. <span data-ttu-id="08f4e-123">Marque as caixas de seleção ao lado das entidades para incluir e **Carregar**.</span><span class="sxs-lookup"><span data-stu-id="08f4e-123">Select the check boxes next to the entities to include and **Load**.</span></span> <span data-ttu-id="08f4e-124">É possível selecionar várias entidades de vários ambientes.</span><span class="sxs-lookup"><span data-stu-id="08f4e-124">You can select multiple entities from multiple environments.</span></span>

1. <span data-ttu-id="08f4e-125">Você verá uma caixa de diálogo de carregamento enquanto suas entidades são carregadas.</span><span class="sxs-lookup"><span data-stu-id="08f4e-125">You'll see a loading dialog box while your entities are loaded.</span></span> <span data-ttu-id="08f4e-126">Depois que todas as entidades selecionadas forem carregadas, você poderá usar os recursos do Power BI para visualizar os dados.</span><span class="sxs-lookup"><span data-stu-id="08f4e-126">Once all of your selected entities have loaded, you can use the capabilities of Power BI to visualize the data.</span></span>

## <a name="large-data-sets"></a><span data-ttu-id="08f4e-127">Grandes conjuntos de dados</span><span class="sxs-lookup"><span data-stu-id="08f4e-127">Large data sets</span></span>

<span data-ttu-id="08f4e-128">O conector Customer Insights para Power BI foi criado para funcionar com conjuntos de dados que contêm até 1 milhão de perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="08f4e-128">The Customer Insights connector for Power BI is designed to work for data sets that contain up to 1 million customer profiles.</span></span> <span data-ttu-id="08f4e-129">Importar conjuntos de dados maiores pode funcionar, mas é demorado.</span><span class="sxs-lookup"><span data-stu-id="08f4e-129">Importing larger data sets may work, but it takes a long time.</span></span> <span data-ttu-id="08f4e-130">Além disso, o processo pode atingir um tempo limite devido a limitações do Power BI.</span><span class="sxs-lookup"><span data-stu-id="08f4e-130">Additionally, the process could run into a time-out because of Power BI limitations.</span></span> <span data-ttu-id="08f4e-131">Para obter mais informações, consulte [Power BI: recomendações para grandes conjuntos de dados](/power-bi/admin/service-premium-what-is#large-datasets).</span><span class="sxs-lookup"><span data-stu-id="08f4e-131">For more information, see [Power BI: Recommendations for large data sets](/power-bi/admin/service-premium-what-is#large-datasets).</span></span> 

### <a name="work-with-a-subset-of-data"></a><span data-ttu-id="08f4e-132">Trabalhe com um subconjunto de dados</span><span class="sxs-lookup"><span data-stu-id="08f4e-132">Work with a subset of data</span></span>

<span data-ttu-id="08f4e-133">Considere trabalhar com um subconjunto de seus dados.</span><span class="sxs-lookup"><span data-stu-id="08f4e-133">Consider working with a subset of your data.</span></span> <span data-ttu-id="08f4e-134">Por exemplo, você pode criar [segmentos](segments.md) em vez de exportar todos os registros de clientes para o Power BI.</span><span class="sxs-lookup"><span data-stu-id="08f4e-134">For example, you can create [segments](segments.md) instead of exporting all customer records to Power BI.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="08f4e-135">Solução de Problemas</span><span class="sxs-lookup"><span data-stu-id="08f4e-135">Troubleshooting</span></span>

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a><span data-ttu-id="08f4e-136">O ambiente do Customer Insights não é exibido no Power BI</span><span class="sxs-lookup"><span data-stu-id="08f4e-136">Customer Insights environment doesn't show in Power BI</span></span>

<span data-ttu-id="08f4e-137">Os ambientes que têm mais de um [relacionamento](relationships.md) definido entre duas entidades idênticas nos insights de público-alvo não estarão disponíveis no conector do Power BI.</span><span class="sxs-lookup"><span data-stu-id="08f4e-137">Environments that have more than one [relationship](relationships.md) defined between two identical entities in audience insights will not be available in the Power BI connector.</span></span>

<span data-ttu-id="08f4e-138">É possível identificar e remover os relacionamentos duplicados.</span><span class="sxs-lookup"><span data-stu-id="08f4e-138">You can identify and remove the duplicated relationships.</span></span>

1. <span data-ttu-id="08f4e-139">Nos insights de público-alvo, acesse **Dados** > **Relacionamentos** no ambiente ausente no Power BI.</span><span class="sxs-lookup"><span data-stu-id="08f4e-139">In audience insights, go to **Data** > **Relationships** on the environment you're missing in Power BI.</span></span>
2. <span data-ttu-id="08f4e-140">Identifique os relacionamentos duplicados:</span><span class="sxs-lookup"><span data-stu-id="08f4e-140">Identify duplicated relationships:</span></span>
   - <span data-ttu-id="08f4e-141">Verifique se há mais de um relacionamento definido entre as duas entidades iguais.</span><span class="sxs-lookup"><span data-stu-id="08f4e-141">Check if there is more than one relationship defined between the same two entities.</span></span>
   - <span data-ttu-id="08f4e-142">Verifique se há um relacionamento criado entre duas entidades que estão incluídas no processo de unificação.</span><span class="sxs-lookup"><span data-stu-id="08f4e-142">Check if there is a relationship created between two entities that are both included in the unification process.</span></span> <span data-ttu-id="08f4e-143">Existe um relacionamento implícito definido entre todas as entidades incluídas no processo de unificação.</span><span class="sxs-lookup"><span data-stu-id="08f4e-143">There is an implicit relationship defined between all entities included in the unification process.</span></span>
3. <span data-ttu-id="08f4e-144">Remova todos os relacionamentos duplicados identificados.</span><span class="sxs-lookup"><span data-stu-id="08f4e-144">Remove any duplicate relationships identified.</span></span>

<span data-ttu-id="08f4e-145">Após a remoção dos relacionamentos duplicados, tente configurar o conector do Power BI novamente.</span><span class="sxs-lookup"><span data-stu-id="08f4e-145">After removal of the duplicated relationships, try to configure the Power BI connector again.</span></span> <span data-ttu-id="08f4e-146">O ambiente será disponibilizado agora.</span><span class="sxs-lookup"><span data-stu-id="08f4e-146">The environment should be available now.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]