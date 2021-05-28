---
title: Exportar dados do Customer Insights para um Armazenamento de Blobs do Azure
description: Aprenda a configurar a conexão e exportar para o Armazenamento de blobs.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976120"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a><span data-ttu-id="da422-103">Exportar a lista de segmentos e outros dados para o Armazenamento de Blobs do Azure (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="da422-103">Export segment list and other data to Azure Blob Storage (preview)</span></span>

<span data-ttu-id="da422-104">Armazene seus dados do Customer Insights em um Armazenamento de blobs ou use-o para transferir seus dados para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="da422-104">Store your Customer Insights data in a Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="set-up-the-connection-to-blob-storage"></a><span data-ttu-id="da422-105">Configurar a conexão com o Armazenamento de blobs</span><span class="sxs-lookup"><span data-stu-id="da422-105">Set up the connection to Blob storage</span></span>

1. <span data-ttu-id="da422-106">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="da422-106">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="da422-107">Selecione **Adicionar conexão** e escolha **Armazenamento de Blobs do Azure** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="da422-107">Select **Add connection** and choose **Azure Blob Storage** to configure the connection.</span></span>

1. <span data-ttu-id="da422-108">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="da422-108">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="da422-109">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="da422-109">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="da422-110">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="da422-110">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="da422-111">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="da422-111">Choose who can use this connection.</span></span> <span data-ttu-id="da422-112">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="da422-112">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="da422-113">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="da422-113">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="da422-114">Insira **Nome da conta**, **Chave de conta** e **Contêiner** para a Conta de armazenamento de blobs.</span><span class="sxs-lookup"><span data-stu-id="da422-114">Enter **Account name**, **Account key**, and **Container** for your Blob storage account.</span></span>
    - <span data-ttu-id="da422-115">Para saber mais sobre como encontrar o nome da Conta de armazenamento de blobs e a chave de conta, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="da422-115">To learn more about how to find the Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="da422-116">Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="da422-116">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="da422-117">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="da422-117">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="da422-118">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="da422-118">Configure an export</span></span>

<span data-ttu-id="da422-119">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="da422-119">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="da422-120">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="da422-120">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="da422-121">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="da422-121">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="da422-122">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="da422-122">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="da422-123">No campo **Conexão para exportação**, escolha uma conexão da seção do Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="da422-123">In the **Connection for export** field, choose a connection from the Azure Blob Storage section.</span></span> <span data-ttu-id="da422-124">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="da422-124">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="da422-125">Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.</span><span class="sxs-lookup"><span data-stu-id="da422-125">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="da422-126">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="da422-126">Select **Save**.</span></span>

<span data-ttu-id="da422-127">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="da422-127">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="da422-128">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="da422-128">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span>     
<span data-ttu-id="da422-129">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="da422-129">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="da422-130">Os dados exportados são armazenados no contêiner de Armazenamento de blobs configurado.</span><span class="sxs-lookup"><span data-stu-id="da422-130">Exported data is stored in the Blob storage container you configured.</span></span> <span data-ttu-id="da422-131">Os seguintes caminhos de pasta são criados automaticamente no seu contêiner:</span><span class="sxs-lookup"><span data-stu-id="da422-131">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="da422-132">Para entidades de origem e entidades geradas pelo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="da422-132">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="da422-133">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="da422-133">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="da422-134">O model.json das entidades exportadas estará no nível %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="da422-134">The model.json for the exported entities will be at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="da422-135">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="da422-135">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
