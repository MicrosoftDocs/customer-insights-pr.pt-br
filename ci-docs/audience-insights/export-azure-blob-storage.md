---
title: Exportar dados do Customer Insights para um Armazenamento de Blobs do Azure
description: Saiba como configurar a conexão com o Armazenamento de Blobs do Azure.
ms.date: 09/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 925b53260e7c633e17d7f172d2dd2d581e982e10
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667125"
---
# <a name="connector-for-azure-blob-storage-preview"></a><span data-ttu-id="57921-103">Conector para Armazenamento de Blobs do Azure (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="57921-103">Connector for Azure Blob storage (preview)</span></span>

<span data-ttu-id="57921-104">Armazene seus dados do Customer Insights em um Armazenamento de Blobs do Azure ou use-o para transferir seus dados para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="57921-104">Store your Customer Insights data in an Azure Blob storage or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-blob-storage"></a><span data-ttu-id="57921-105">Configurar o conector para o Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="57921-105">Configure the connector for Azure Blob storage</span></span>

1. <span data-ttu-id="57921-106">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="57921-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="57921-107">Em **Armazenamento de Blobs do Azure**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="57921-107">Under **Azure Blob Storage**, select **Set up**.</span></span>

1. <span data-ttu-id="57921-108">Insira **Nome da conta**, **Chave da conta** e **Contêiner** para sua conta de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="57921-108">Enter **Account name**, **Account key**, and **Container** for your Azure Blob storage account.</span></span>
    - <span data-ttu-id="57921-109">Para saber mais sobre como encontrar o nome e a chave da conta do Azure Blob Storage, consulte [Gerenciar as configurações da conta de armazenamento no portal do Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="57921-109">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>
    - <span data-ttu-id="57921-110">Para saber como criar um contêiner, consulte [Criar um container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="57921-110">To learn how to create a container, see [Create a container](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="57921-111">Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="57921-111">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="57921-112">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="57921-112">Select **Next**.</span></span>

1. <span data-ttu-id="57921-113">Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.</span><span class="sxs-lookup"><span data-stu-id="57921-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="57921-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="57921-114">Select **Save**.</span></span>

<span data-ttu-id="57921-115">Os dados exportados são armazenados no contêiner do Armazenamento de Blobs do Azure que você configurou.</span><span class="sxs-lookup"><span data-stu-id="57921-115">Exported data is stored in the Azure Blob storage container you configured.</span></span> <span data-ttu-id="57921-116">Os seguintes caminhos de pasta são criados automaticamente no seu contêiner:</span><span class="sxs-lookup"><span data-stu-id="57921-116">The following folder paths are automatically created in your container:</span></span>

- <span data-ttu-id="57921-117">Para entidades de origem e entidades geradas pelo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span><span class="sxs-lookup"><span data-stu-id="57921-117">For source entities and entities generated by the system: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`</span></span>
  - <span data-ttu-id="57921-118">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span><span class="sxs-lookup"><span data-stu-id="57921-118">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`</span></span>
- <span data-ttu-id="57921-119">O model.json das entidades exportadas residirá no nível %ExportDestinationName%</span><span class="sxs-lookup"><span data-stu-id="57921-119">The model.json for the exported entities will reside at the %ExportDestinationName% level</span></span>
  - <span data-ttu-id="57921-120">Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span><span class="sxs-lookup"><span data-stu-id="57921-120">Example: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`</span></span>

## <a name="export-the-data"></a><span data-ttu-id="57921-121">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="57921-121">Export the data</span></span>

<span data-ttu-id="57921-122">Você pode [exportar dados sob demanda](/export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="57921-122">You can [export data on demand](/export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="57921-123">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="57921-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
