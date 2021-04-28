---
title: Exportar dados do Customer Insights para o Azure Data Lake Storage Gen2
description: Saiba como configurar a conexão do Azure Data Lake Storage Gen2.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f431b707e1d65ffe47f8b3aa1c52abaa964e871a
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760037"
---
# <a name="set-up-the-connection-to-azure-data-lake-storage-gen2-preview"></a><span data-ttu-id="bec13-103">Configurar a conexão com o Azure Data Lake Storage Gen2 (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="bec13-103">Set up the connection to Azure Data Lake Storage Gen2 (preview)</span></span>

1. <span data-ttu-id="bec13-104">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="bec13-104">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="bec13-105">Selecione **Adicionar conexão** e escolha **Azure Data Lake Gen 2** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="bec13-105">Select **Add connection** and choose **Azure Data Lake Gen 2** to configure the connection.</span></span>

1. <span data-ttu-id="bec13-106">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="bec13-106">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="bec13-107">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="bec13-107">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="bec13-108">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="bec13-108">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="bec13-109">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="bec13-109">Choose who can use this connection.</span></span> <span data-ttu-id="bec13-110">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="bec13-110">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="bec13-111">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="bec13-111">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="bec13-112">Insira **Nome da conta**, **Chave da conta** e **Contêiner** do Azure Data Lake Storage Gen2.</span><span class="sxs-lookup"><span data-stu-id="bec13-112">Enter **Account name**, **Account key**, and **Container** for your Azure Data Lake Storage Gen2.</span></span>
    - <span data-ttu-id="bec13-113">Para aprender a criar a conta de armazenamento a ser usada com o Azure Data Lake Storage Gen2, consulte [Criar conta de armazenamento](/azure/storage/blobs/create-data-lake-storage-account).</span><span class="sxs-lookup"><span data-stu-id="bec13-113">To learn how to create a storage account to use with Azure Data Lake Storage Gen2, see [Create storage account](/azure/storage/blobs/create-data-lake-storage-account).</span></span> 
    - <span data-ttu-id="bec13-114">Para saber mais sobre como encontrar o nome do Azure Data Lake Gen2 e a chave de conta, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bec13-114">To learn more about Azure Data Lake Gen2 storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

1. <span data-ttu-id="bec13-115">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="bec13-115">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="bec13-116">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="bec13-116">Configure an export</span></span>

<span data-ttu-id="bec13-117">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="bec13-117">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="bec13-118">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="bec13-118">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="bec13-119">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="bec13-119">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="bec13-120">Para criar uma exportação, selecione **Adicionar exportação**.</span><span class="sxs-lookup"><span data-stu-id="bec13-120">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="bec13-121">No campo **Conexão para exportação**, escolha uma conexão da seção do **Azure Data Lake**.</span><span class="sxs-lookup"><span data-stu-id="bec13-121">In the **Connection for export** field, choose a connection from the **Azure Data Lake** section.</span></span> <span data-ttu-id="bec13-122">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="bec13-122">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="bec13-123">Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.</span><span class="sxs-lookup"><span data-stu-id="bec13-123">Select the box next to each of the entities you want to export to this destination.</span></span>

1. <span data-ttu-id="bec13-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bec13-124">Select **Save**.</span></span>

<span data-ttu-id="bec13-125">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="bec13-125">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="bec13-126">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bec13-126">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bec13-127">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bec13-127">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

<span data-ttu-id="bec13-128">Os dados exportados são armazenados no Azure Data Lake Gen 2 configurado.</span><span class="sxs-lookup"><span data-stu-id="bec13-128">Exported data is stored in the Azure Data Lake Gen 2 storage container you configured.</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
