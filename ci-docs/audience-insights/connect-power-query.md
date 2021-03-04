---
title: Ingerir dados por meio de um conector do Power Query
description: Conectores para fontes de dados com base no Power Query.
ms.date: 09/29/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d51a7efa5fd9f7336d1662500eb804a674738493
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267754"
---
# <a name="connect-to-a-power-query-data-source"></a><span data-ttu-id="dfeed-103">Conectar-se à fonte de dados do Power Query</span><span class="sxs-lookup"><span data-stu-id="dfeed-103">Connect to a Power Query data source</span></span>

<span data-ttu-id="dfeed-104">O Power Query oferece um amplo conjunto de conectores para ingerir dados.</span><span class="sxs-lookup"><span data-stu-id="dfeed-104">Power Query offers a broad set of connectors to ingest data.</span></span> <span data-ttu-id="dfeed-105">A maioria desses conectores são suportados por Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dfeed-105">Most of these connectors are supported by Dynamics 365 Customer Insights.</span></span> <span data-ttu-id="dfeed-106">Adicionar fontes de dados com base em conectores do Power Query geralmente segue as etapas descritas na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="dfeed-106">Adding data sources based on Power Query connectors generally follows the steps outlined in the next section.</span></span> <span data-ttu-id="dfeed-107">No entanto, dependendo do conector que você usa, são necessárias informações diferentes.</span><span class="sxs-lookup"><span data-stu-id="dfeed-107">However, depending on the connector you use, different information is required.</span></span> <span data-ttu-id="dfeed-108">Para obter mais informações, consulte a documentação sobre conectores individuais na [referência do conector do Power Query](https://docs.microsoft.com/power-query/connectors/).</span><span class="sxs-lookup"><span data-stu-id="dfeed-108">For more information, see the documentation about individual connectors in the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/).</span></span>

## <a name="create-a-new-data-source"></a><span data-ttu-id="dfeed-109">Criar uma nova fonte de dados</span><span class="sxs-lookup"><span data-stu-id="dfeed-109">Create a new data source</span></span>

1. <span data-ttu-id="dfeed-110">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-110">In audience insights, go to **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="dfeed-111">Selecione **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-111">Select **Add data source**.</span></span>

1. <span data-ttu-id="dfeed-112">Escolha o método **Importar dados** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-112">Choose the **Import data** method and select **Next**.</span></span>

1. <span data-ttu-id="dfeed-113">Forneça um **Nome** para a fonte de dados e selecione **Avançar** para criar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="dfeed-113">Provide a **Name** for the data source, and select **Next** to create the data source.</span></span> <span data-ttu-id="dfeed-114">Nomear diretrizes:</span><span class="sxs-lookup"><span data-stu-id="dfeed-114">Name guidelines:</span></span> 
   - <span data-ttu-id="dfeed-115">Comece com uma letra.</span><span class="sxs-lookup"><span data-stu-id="dfeed-115">Start with a letter.</span></span>
   - <span data-ttu-id="dfeed-116">Use somente letras e números.</span><span class="sxs-lookup"><span data-stu-id="dfeed-116">Use letters and numbers only.</span></span> <span data-ttu-id="dfeed-117">Caracteres especiais e espaços não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="dfeed-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="dfeed-118">Use entre 3 e 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="dfeed-118">Use between 3 and 64 characters.</span></span>

1. <span data-ttu-id="dfeed-119">Escolha um dos [conectores disponíveis](#available-power-query-data-sources).</span><span class="sxs-lookup"><span data-stu-id="dfeed-119">Choose one of the [available connectors](#available-power-query-data-sources).</span></span> <span data-ttu-id="dfeed-120">Para este exemplo, selecionamos o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-120">For this example, we select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="dfeed-121">Insira os detalhes necessários nas **Configurações de conexão** para o conector selecionado e selecione **Avançar** para ver uma prévia dos dados.</span><span class="sxs-lookup"><span data-stu-id="dfeed-121">Enter the required details in the **Connection settings** for the selected connector and select **Next** to see a preview of the data.</span></span>

1. <span data-ttu-id="dfeed-122">Selecione **Transformar dados**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-122">Select **Transform data**.</span></span> <span data-ttu-id="dfeed-123">Nesta etapa, você adicionará entidades à sua fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="dfeed-123">In this step, you'll add entities to your data source.</span></span> <span data-ttu-id="dfeed-124">Entidades são conjuntos de dados.</span><span class="sxs-lookup"><span data-stu-id="dfeed-124">Entities are datasets.</span></span> <span data-ttu-id="dfeed-125">Se você possui um banco de dados que inclui vários conjuntos de dados, cada conjunto de dados é sua própria entidade.</span><span class="sxs-lookup"><span data-stu-id="dfeed-125">If you have a database that includes multiple datasets, each dataset is its own entity.</span></span>

1. <span data-ttu-id="dfeed-126">A caixa de diálogo **Power Query - Editar consultas** permite revisar e refinar os dados.</span><span class="sxs-lookup"><span data-stu-id="dfeed-126">The **Power Query - Edit queries** dialog lets you review and refine the data.</span></span> <span data-ttu-id="dfeed-127">As entidades que os sistemas identificaram na sua fonte de dados selecionada aparecem no painel esquerdo.</span><span class="sxs-lookup"><span data-stu-id="dfeed-127">The entities that the systems identified in your selected data source appear in the left pane.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dfeed-128">![Caixa de diálogo Editar consultas](media/data-manager-configure-edit-queries.png "Caixa de diálogo Editar consultas")</span><span class="sxs-lookup"><span data-stu-id="dfeed-128">![Edit queries dialog](media/data-manager-configure-edit-queries.png "Edit queries dialog")</span></span>

1. <span data-ttu-id="dfeed-129">Você também poderá transformar seus dados.</span><span class="sxs-lookup"><span data-stu-id="dfeed-129">You can also transform your data.</span></span> <span data-ttu-id="dfeed-130">Selecione uma entidade para editar ou transformar.</span><span class="sxs-lookup"><span data-stu-id="dfeed-130">Select an entity to edit or transform.</span></span> <span data-ttu-id="dfeed-131">Use as opções na janela do Power Query para aplicar as transformações.</span><span class="sxs-lookup"><span data-stu-id="dfeed-131">Use the options in the Power Query window to apply transformations.</span></span> <span data-ttu-id="dfeed-132">Cada transformação é listada em **Etapas aplicadas**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-132">Each transformation gets listed under **Applied steps**.</span></span> <span data-ttu-id="dfeed-133">O Power Query fornece várias opções de transformação pré-criadas.</span><span class="sxs-lookup"><span data-stu-id="dfeed-133">Power Query provides numerous pre-built transformation options.</span></span> <span data-ttu-id="dfeed-134">Para obter mais informações, consulte [Transformações do Power Query](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span><span class="sxs-lookup"><span data-stu-id="dfeed-134">For more information, see [Power Query Transformations](https://docs.microsoft.com/power-query/power-query-what-is-power-query#transformations).</span></span>

1. <span data-ttu-id="dfeed-135">Você pode adicionar entidades adicionais à sua fonte de dados, selecionando **Obter dados** na caixa de diálogo **Editar consultas**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-135">You can add additional entities to your data source by selecting **Get data** in the **Edit queries** dialog.</span></span>

   <span data-ttu-id="dfeed-136">Essas transformações são altamente recomendadas:</span><span class="sxs-lookup"><span data-stu-id="dfeed-136">These transformations are highly recommended:</span></span>

   - <span data-ttu-id="dfeed-137">Se você estiver ingerindo dados de um arquivo CSV, a primeira linha geralmente contém cabeçalhos.</span><span class="sxs-lookup"><span data-stu-id="dfeed-137">If you're ingesting data from a CSV file, the first row often contains headers.</span></span> <span data-ttu-id="dfeed-138">Vá para **Transformar tabela** e selecione **Usar cabeçalhos como primeira linha**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-138">Go to **Transform table** and select **Use headers as first row**.</span></span>
   - <span data-ttu-id="dfeed-139">Certifique-se de que o tipo de dados esteja definido de forma adequada.</span><span class="sxs-lookup"><span data-stu-id="dfeed-139">Ensure the data type is set appropriately.</span></span>

1. <span data-ttu-id="dfeed-140">Selecione **Salvar** no canto inferior direito da janela do Power Query para salvar as transformações.</span><span class="sxs-lookup"><span data-stu-id="dfeed-140">Select **Save** at the bottom of the Power Query window to save the transformations.</span></span> <span data-ttu-id="dfeed-141">Depois de salvar, você encontrará sua fonte de dados em **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-141">After saving, you'll find your data source on **Data** > **Data sources**.</span></span>

1. <span data-ttu-id="dfeed-142">Na página **Fontes de dados**, você observará que a nova fonte de dados está no status **Atualizando**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-142">On the **Data sources** page, you'll notice the new data source is in **Refreshing** status.</span></span>

## <a name="available-power-query-data-sources"></a><span data-ttu-id="dfeed-143">Fontes de dados do Power Query disponíveis</span><span class="sxs-lookup"><span data-stu-id="dfeed-143">Available Power Query data sources</span></span>

<span data-ttu-id="dfeed-144">Consulte a [referência do conector do Power Query](https://docs.microsoft.com/power-query/connectors/) para obter uma lista atualizada de conectores que você pode selecionar para importar os dados para o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dfeed-144">See the [Power Query connector reference](https://docs.microsoft.com/power-query/connectors/) for an up-to-date list of connectors that you can select to import data to Customer Insights.</span></span> 

<span data-ttu-id="dfeed-145">Conectores com uma marca de seleção na coluna **Customer Insights (Dataflows)** estão disponíveis para criar novas fontes de dados com base no Power Query.</span><span class="sxs-lookup"><span data-stu-id="dfeed-145">Connectors with a checkmark in the **Customer Insights (Dataflows)** column are available to create new data sources based on Power Query.</span></span> <span data-ttu-id="dfeed-146">Revise a documentação de um conector específico para saber mais sobre seus pré-requisitos, limitações e outros detalhes.</span><span class="sxs-lookup"><span data-stu-id="dfeed-146">Review the documentation of a specific connector to learn more about its prerequisites, limitations, and other details.</span></span>

## <a name="edit-power-query-data-sources"></a><span data-ttu-id="dfeed-147">Editar fontes de dados do Power Query</span><span class="sxs-lookup"><span data-stu-id="dfeed-147">Edit Power Query data sources</span></span>

> [!NOTE]
> <span data-ttu-id="dfeed-148">Talvez não seja possível fazer alterações nas fontes de dados que estão sendo usadas no momento em um dos processos do aplicativo (*segmentação*, *corresponder* ou *mesclar*, por exemplo).</span><span class="sxs-lookup"><span data-stu-id="dfeed-148">It might not be possible to make changes to data sources that are currently being used in one of the app's processes (*segmentation*, *match*, or *merge*, for example).</span></span> 
>
> <span data-ttu-id="dfeed-149">Usando a página **Configurações** você pode rastrear o andamento de cada um dos processos ativos.</span><span class="sxs-lookup"><span data-stu-id="dfeed-149">Using the **Settings** page, you can track the progress of each of the active processes.</span></span> <span data-ttu-id="dfeed-150">Quando um processo é concluído, você pode retornar à página **Fontes de Dados** e fazer suas alterações.</span><span class="sxs-lookup"><span data-stu-id="dfeed-150">When a process completes, you can return to the **Data Sources** page and make your changes.</span></span>

1. <span data-ttu-id="dfeed-151">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="dfeed-151">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="dfeed-152">Selecione as reticências verticais ao lado da fonte de dados que você deseja alterar e selecione **Editar** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="dfeed-152">Select the vertical ellipsis next to the data source you want to change and select **Edit** from the drop-down menu.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dfeed-153">![Editar opção](media/edit-option-data-sources.png "Editar opção")</span><span class="sxs-lookup"><span data-stu-id="dfeed-153">![Edit option](media/edit-option-data-sources.png "Edit option")</span></span>

3. <span data-ttu-id="dfeed-154">Aplique suas mudanças e transformações na caixa de diálogo **Power Query - Editar consultas**, conforme descrito na seção [Criar uma nova fonte de dados](#create-a-new-data-source).</span><span class="sxs-lookup"><span data-stu-id="dfeed-154">Apply your changes and transformations in the **Power Query - Edit queries** dialog as described in the [Create a new data source](#create-a-new-data-source) section.</span></span>

4. <span data-ttu-id="dfeed-155">Selecione **Salvar** no Power Query após concluir suas edições para salvar suas alterações.</span><span class="sxs-lookup"><span data-stu-id="dfeed-155">Select **Save** in Power Query after completing your edits to save your changes.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]