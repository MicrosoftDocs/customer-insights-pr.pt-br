---
title: Ingerir dados por meio de um conector do Power Query
description: Conectores para fontes de dados com base no Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 8a170cc5b64b4b383501021232c83948e838a0e2
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405033"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="09aeb-103">Conectar-se à fonte de dados do Power Query</span><span class="sxs-lookup"><span data-stu-id="09aeb-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="09aeb-104">O Power Query oferece um amplo conjunto de conectores para ingerir dados.</span><span class="sxs-lookup"><span data-stu-id="09aeb-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="09aeb-105">A maioria desses conectores são suportados por Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="09aeb-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="09aeb-106">Adicionar fontes de dados com base em conectores do Power Query geralmente segue as etapas descritas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="09aeb-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="09aeb-107">No entanto, dependendo do conector que você usa, são necessárias informações diferentes.</span><span class="sxs-lookup"><span data-stu-id="09aeb-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="09aeb-108">Para obter mais informações, consulte a documentação sobre conectores individuais na [referência do conector do Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="09aeb-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="09aeb-109">Criar uma nova fonte de dados</span><span class="sxs-lookup"><span data-stu-id="09aeb-109">Create a new data source</span></span>

1. <span data-ttu-id="09aeb-110">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="09aeb-111">Selecione **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="09aeb-112">Escolha o método **Importar dados** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="09aeb-113">Forneça um **Nome** para a fonte de dados e selecione **Avançar** para criar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="09aeb-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span>

1. <span data-ttu-id="09aeb-114">Escolha um dos [conectores disponíveis](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="09aeb-114">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="09aeb-115">Para este exemplo, selecionamos o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-115">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="09aeb-116">Insira os detalhes necessários nas **Configurações de conexão** para o conector selecionado e selecione **Avançar** para ver uma prévia dos dados.</span><span class="sxs-lookup"><span data-stu-id="09aeb-116">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="09aeb-117">Selecione **Transformar dados**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-117">Select **Transform data**.</span></span> <span data-ttu-id="09aeb-118">Nesta etapa, você adicionará entidades à sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="09aeb-118">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="09aeb-119">Entidades são conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="09aeb-119">Entities are datasets.</span></span> <span data-ttu-id="09aeb-120">Se você possui um banco de dados que inclui vários conjuntos de dados, cada conjunto de dados é sua própria entidade.</span><span class="sxs-lookup"><span data-stu-id="09aeb-120">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="09aeb-121">A caixa de diálogo **Power Query - Editar consultas** permite revisar e refinar os dados.</span><span class="sxs-lookup"><span data-stu-id="09aeb-121">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="09aeb-122">As entidades que os sistemas identificaram na sua fonte de dados selecionada aparecem no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="09aeb-122">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="09aeb-123">![Caixa de diálogo Editar consultas](media/data-manager-configure-edit-queries.png "Caixa de diálogo Editar consultas")</span><span class="sxs-lookup"><span data-stu-id="09aeb-123">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="09aeb-124">Você também poderá transformar seus dados.</span><span class="sxs-lookup"><span data-stu-id="09aeb-124">You can also transform your data.</span></span> <span data-ttu-id="09aeb-125">Selecione uma entidade para editar ou transformar.</span><span class="sxs-lookup"><span data-stu-id="09aeb-125">Select an entity to edit or transform.</span></span> <span data-ttu-id="09aeb-126">Use as opções na janela do Power Query para aplicar as transformações.</span><span class="sxs-lookup"><span data-stu-id="09aeb-126">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="09aeb-127">Cada transformação é listada em **Etapas aplicadas**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-127">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="09aeb-128">O Power Query fornece várias opções de transformação pré-criadas.</span><span class="sxs-lookup"><span data-stu-id="09aeb-128">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="09aeb-129">Para obter mais informações, consulte [Transformações do Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="09aeb-129">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="09aeb-130">Você pode adicionar entidades adicionais à sua fonte de dados, selecionando **Obter dados** na caixa de diálogo **Editar consultas**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-130">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="09aeb-131">Essas transformações são altamente recomendadas:</span><span class="sxs-lookup"><span data-stu-id="09aeb-131">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="09aeb-132">Se você estiver ingerindo dados de um arquivo CSV, a primeira linha geralmente contém cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="09aeb-132">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="09aeb-133">Vá para **Transformar tabela** e selecione **Usar cabeçalhos como primeira linha**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-133">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="09aeb-134">Certifique-se de que o tipo de dados esteja definido de forma adequada.</span><span class="sxs-lookup"><span data-stu-id="09aeb-134">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="09aeb-135">Selecione **Salvar** no canto inferior direito da janela do Power Query para salvar as transformações.</span><span class="sxs-lookup"><span data-stu-id="09aeb-135">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="09aeb-136">Depois de salvar, você encontrará sua fonte de dados em **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-136">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="09aeb-137">Na página **Fontes de dados**, você observará que a nova fonte de dados está no status **Atualizando**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-137">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="09aeb-138">Fontes de dados do Power Query disponíveis</span><span class="sxs-lookup"><span data-stu-id="09aeb-138">Available Power Query data sources</span></span>

<span data-ttu-id="09aeb-139">Consulte a [referência do conector do Power Query](https://docs.microsoft.com/power-query/connectors/) para obter uma lista atualizada de conectores que você pode selecionar para importar os dados para o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="09aeb-139">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="09aeb-140">Conectores com uma marca de seleção na coluna **Customer Insights (Dataflows)** estão disponíveis para criar novas fontes de dados com base no Power Query.</span><span class="sxs-lookup"><span data-stu-id="09aeb-140">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="09aeb-141">Revise a documentação de um conector específico para saber mais sobre seus pré-requisitos, limitações e outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="09aeb-141">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="09aeb-142">Editar fontes de dados do Power Query</span><span class="sxs-lookup"><span data-stu-id="09aeb-142">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="09aeb-143">Talvez não seja possível fazer alterações nas fontes de dados que estão sendo usadas no momento em um dos processos do aplicativo (*segmentação*, *corresponder* ou *mesclar*, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="09aeb-143">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="09aeb-144">Usando a página **Configurações** você pode rastrear o andamento de cada um dos processos ativos.</span><span class="sxs-lookup"><span data-stu-id="09aeb-144">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="09aeb-145">Quando um processo é concluído, você pode retornar à página **Fontes de Dados** e fazer suas alterações.</span><span class="sxs-lookup"><span data-stu-id="09aeb-145">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="09aeb-146">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="09aeb-146">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="09aeb-147">Selecione as reticências verticais ao lado da fonte de dados que você deseja alterar e selecione **Editar** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="09aeb-147">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="09aeb-148">![Editar opção](media/edit-option-data-sources.png "Editar opção")</span><span class="sxs-lookup"><span data-stu-id="09aeb-148">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="09aeb-149">Aplique suas mudanças e transformações na caixa de diálogo **Power Query - Editar consultas**, conforme descrito na seção [Criar uma nova fonte de dados](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="09aeb-149">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="09aeb-150">Selecione **Salvar** no Power Query após concluir suas edições para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="09aeb-150">Select **Save** in Power Query after completing your edits to save your changes.</span></span>
