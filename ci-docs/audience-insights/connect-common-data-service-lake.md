---
title: Conectar-se a entidades no lake gerenciado pelo Common Data Service
description: Importar dados de um data lake gerenciado pelo Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596945"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a><span data-ttu-id="a5986-103">Conecte-se aos dados em um data lake gerenciado do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a5986-103">Connect to data in a Common Data Service managed data lake</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="a5986-104">Este artigo fornece informações sobre como os clientes existentes do Dynamics 365 podem se conectar rapidamente às suas entidades analíticas no lake gerenciado pelo Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a5986-104">This article provides information on how existing Dynamics 365 customers can quickly connect to their analytical entities in the Common Data Service managed lake.</span></span> <span data-ttu-id="a5986-105">Você deve ser um administrador na organização do Common Data Service para prosseguir e ver a lista de entidades disponíveis no lake gerenciado.</span><span class="sxs-lookup"><span data-stu-id="a5986-105">You must be an admin on the Common Data Service organization to proceed and see the list of entities available in the managed lake.</span></span>

## <a name="important-considerations"></a><span data-ttu-id="a5986-106">Considerações importantes</span><span class="sxs-lookup"><span data-stu-id="a5986-106">Important considerations</span></span>

<span data-ttu-id="a5986-107">Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="a5986-107">Data stored in online services, such as Azure Data Lake Storage, may be stored in a different location than where data is processed or stored in Dynamics 365 Customer Insights.</span></span><span data-ttu-id="a5986-108"> Ao importar ou se conectar a dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span><span class="sxs-lookup"><span data-stu-id="a5986-108"> By importing or connecting to data stored in online services, you agree that data can be transferred to and stored with Dynamics 365 Customer Insights. [Learn more at the Microsoft Trust Center.](https://www.microsoft.com/trust-center)</span></span>

## <a name="connect-to-a-common-data-service-managed-lake"></a><span data-ttu-id="a5986-109">Conectar-se a um data lake gerenciado do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a5986-109">Connect to a Common Data Service managed lake</span></span>

1. <span data-ttu-id="a5986-110">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="a5986-110">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a5986-111">Selecione **Adicionar fonte de dados**.</span><span class="sxs-lookup"><span data-stu-id="a5986-111">Select **Add data source**.</span></span>

3. <span data-ttu-id="a5986-112">Selecione **Conecte-se ao Common Data Service** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5986-112">Select **Connect to Common Data Service** and select **Next**.</span></span>

4. <span data-ttu-id="a5986-113">Insira um **Nome** para a fonte de dados e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a5986-113">Enter a **Name** for the data source and select **Next**.</span></span> <span data-ttu-id="a5986-114">Nomear diretrizes:</span><span class="sxs-lookup"><span data-stu-id="a5986-114">Name guidelines:</span></span> 
   - <span data-ttu-id="a5986-115">Comece com uma letra.</span><span class="sxs-lookup"><span data-stu-id="a5986-115">Start with a letter.</span></span>
   - <span data-ttu-id="a5986-116">Use somente letras e números.</span><span class="sxs-lookup"><span data-stu-id="a5986-116">Use letters and numbers only.</span></span> <span data-ttu-id="a5986-117">Caracteres especiais e espaços não são permitidos.</span><span class="sxs-lookup"><span data-stu-id="a5986-117">Special characters and spaces are not allowed.</span></span>
   - <span data-ttu-id="a5986-118">Use entre 3 e 64 caracteres.</span><span class="sxs-lookup"><span data-stu-id="a5986-118">Use between 3 and 64 characters.</span></span>

5. <span data-ttu-id="a5986-119">Forneça o **Endereço do servidor** para sua organização do Common Data Service e selecione **Conectar-se**.</span><span class="sxs-lookup"><span data-stu-id="a5986-119">Provide the **Server address** for your Common Data Service organization, and select **Sign in**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a5986-120">![Caixa de diálogo para inserir o endereço de servidor do Common Data Service](media/enter-CDS-org-details.png)</span><span class="sxs-lookup"><span data-stu-id="a5986-120">![Dialog box to enter Common Data Service server address](media/enter-CDS-org-details.png)</span></span>

6. <span data-ttu-id="a5986-121">Selecione as entidades que você deseja receber da lista disponível.</span><span class="sxs-lookup"><span data-stu-id="a5986-121">Select the entities you want to ingest from the available list.</span></span>    

   > [!NOTE]
   > <span data-ttu-id="a5986-122">Se algumas entidades já estiverem selecionadas, elas poderão ser usadas por outros aplicativos do Dynamics 365 (como o Dynamics 365 Sales Insights ou o Customer Service Insights).</span><span class="sxs-lookup"><span data-stu-id="a5986-122">If some entities are already selected, they might be used by other Dynamics 365 applications (such as Dynamics 365 Sales Insights or Customer Service Insights).</span></span> <span data-ttu-id="a5986-123">Não é possível alterar a seleção.</span><span class="sxs-lookup"><span data-stu-id="a5986-123">You can't change the selection.</span></span> <span data-ttu-id="a5986-124">Essas entidades estarão disponíveis assim que fonte de dados for criada.</span><span class="sxs-lookup"><span data-stu-id="a5986-124">These entities will be available once the data source is created.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a5986-125">![Caixa de diálogo mostrando uma lista de entidades na organização do Common Data Service](media/select-analytical-entities.png)</span><span class="sxs-lookup"><span data-stu-id="a5986-125">![Dialog box showing a list of entities in the Common Data Service org](media/select-analytical-entities.png)</span></span>

7. <span data-ttu-id="a5986-126">Salve sua seleção para começar a sincronizar as entidades selecionadas com o lake gerenciado do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a5986-126">Save your selection to start syncing the selected entities to the Common Data Service managed lake.</span></span> <span data-ttu-id="a5986-127">Você encontrará a conexão recém-adicionada na página **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="a5986-127">You'll find the newly added connection on the **Data sources** page.</span></span> <span data-ttu-id="a5986-128">Será colocado na fila para atualização e mostrará que as entidades contam como 0 até que todas as entidades sejam sincronizadas.</span><span class="sxs-lookup"><span data-stu-id="a5986-128">It will be queued for refresh and show the entities count as 0 until all the entities are synced.</span></span>

<span data-ttu-id="a5986-129">Apenas uma fonte de dados de um ambiente pode usar simultaneamente o mesmo lake gerenciado pelo Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="a5986-129">Only one data source of an environment can simultaneously use the same Common Data Service managed lake.</span></span>

## <a name="edit-a-common-data-service-managed-lake-data-source"></a><span data-ttu-id="a5986-130">Edite uma fonte de dados de lake gerenciado do Common Data Service</span><span class="sxs-lookup"><span data-stu-id="a5986-130">Edit a Common Data Service managed lake data source</span></span>

<span data-ttu-id="a5986-131">Você só editará a seleção da entidade depois de criar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="a5986-131">You only edit the entity selection after creating the data source.</span></span> <span data-ttu-id="a5986-132">Por exemplo, se entidades adicionais foram adicionadas ao Common Data Service e você quiser importá-las também.</span><span class="sxs-lookup"><span data-stu-id="a5986-132">For example, if additional entities were added to Common Data Service and you want to import them too.</span></span>    
<span data-ttu-id="a5986-133">Para conectar-se a um Common Data Service diferente, [crie uma nova fonte de dados](#connect-to-a-common-data-service-managed-lake).</span><span class="sxs-lookup"><span data-stu-id="a5986-133">To connect to a different Common Data Service, [create a new data source](#connect-to-a-common-data-service-managed-lake).</span></span>

1. <span data-ttu-id="a5986-134">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="a5986-134">In audience insights, go to **Data** > **Data sources**.</span></span>

2. <span data-ttu-id="a5986-135">Ao lado da fonte de dados que você deseja atualizar, selecione as reticências.</span><span class="sxs-lookup"><span data-stu-id="a5986-135">Next to the data source you'd like to update, select the ellipsis.</span></span>

3. <span data-ttu-id="a5986-136">Selecione uma opção **Editar** na lista.</span><span class="sxs-lookup"><span data-stu-id="a5986-136">Select the **Edit** option from the list.</span></span>

4. <span data-ttu-id="a5986-137">Selecione entidades adicionais na lista de entidades disponíveis e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a5986-137">Select additional entities from the available list of entities and select **Save**.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]