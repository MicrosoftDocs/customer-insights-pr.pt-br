---
title: Exportar dados do Customer Insights para o Azure Data Lake Storage Gen2
description: Saiba como configurar a conexão do Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00c3d6178150cbc93fe800779f094809d4dc67b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477165"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="e9527-103">Conector para Azure Data Lake Storage Gen2 (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="e9527-103">Connector for Azure Data Lake Storage Gen2 (preview)</span></span>

<span data-ttu-id="e9527-104">Armazene seus dados do Customer Insights no Azure Data Lake Storage Gen2 ou use-o para transferir seus dados para outros aplicativos.</span><span class="sxs-lookup"><span data-stu-id="e9527-104">Store your Customer Insights data in Azure Data Lake Storage Gen2 or use it to transfer your data to other applications.</span></span>

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a><span data-ttu-id="e9527-105">Configurar o conector do Azure Data Lake Storage Gen2</span><span class="sxs-lookup"><span data-stu-id="e9527-105">Configure the connector for Azure Data Lake Storage Gen2</span></span>

1. <span data-ttu-id="e9527-106">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="e9527-106">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e9527-107">Em **Azure Data Lake Storage Gen2**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e9527-107">Under **Azure Data Lake Storage Gen2**, select **Set up**.</span></span>

1. <span data-ttu-id="e9527-108">Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="e9527-108">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e9527-109">Insira **Nome da conta**, **Chave da conta** e **Contêiner** do Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="e9527-109">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="e9527-110">Para aprender a criar a conta de armazenamento a ser usada com o Azure Data Lake Storage Gen2, consulte [Criar conta de armazenamento](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="e9527-110">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](https://docs.microsoft.com/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="e9527-111">Para saber mais sobre como localizar o nome e a chave da conta de armazenamento do Azure Data Lake Gen2, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="e9527-111">To learn more about how to find the Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](https://docs.microsoft.com/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="e9527-112">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="e9527-112">Select **Next**.</span></span>

1. <span data-ttu-id="e9527-113">Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.</span><span class="sxs-lookup"><span data-stu-id="e9527-113">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="e9527-114">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e9527-114">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e9527-115">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="e9527-115">Export the data</span></span>

<span data-ttu-id="e9527-116">Você pode [exportar dados sob demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="e9527-116">You can [export data on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="e9527-117">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e9527-117">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
