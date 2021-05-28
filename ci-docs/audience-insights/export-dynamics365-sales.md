---
title: Exportar dados do Customer Insights para o Dynamics 365 Sales
description: Saiba como configurar a conexão e exportar para o Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 328bb2f26ebcea234fb645e5225930ab12f82a8b
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976212"
---
# <a name="use-segments-in-dynamics-365-sales-preview"></a><span data-ttu-id="b11ba-103">Usar segmentos no Dynamics 365 Sales (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="b11ba-103">Use segments in Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="b11ba-104">Use seus dados de cliente para criar listas de marketing, fluxos de trabalho de acompanhamento e enviar promoções com o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b11ba-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite-for-connection"></a><span data-ttu-id="b11ba-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="b11ba-105">Prerequisite for connection</span></span>

1. <span data-ttu-id="b11ba-106">Os registros de contatos devem estar presentes no Dynamics 365 Sales antes de exportar um segmento do Customer Insights para o Sales.</span><span class="sxs-lookup"><span data-stu-id="b11ba-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="b11ba-107">Leia mais sobre como ingerir contatos no [Dynamics 365 Sales usando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="b11ba-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="b11ba-108">Exportar segmentos de insights de público-alvo para o Sales não criará registros de contatos nas instâncias do Sales.</span><span class="sxs-lookup"><span data-stu-id="b11ba-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="b11ba-109">Os registros de contatos do Sales devem ser ingeridos em insights de público-alvo e usados como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="b11ba-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="b11ba-110">Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="b11ba-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-the-connection-to-sales"></a><span data-ttu-id="b11ba-111">Configurar a conexão com o Sales</span><span class="sxs-lookup"><span data-stu-id="b11ba-111">Set up the connection to Sales</span></span>

1. <span data-ttu-id="b11ba-112">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="b11ba-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b11ba-113">Selecione **Adicionar conexão** e escolha **Dynamics 365 Sales** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="b11ba-113">Select **Add connection** and choose **Dynamics 365 Sales** to configure the connection.</span></span>

1. <span data-ttu-id="b11ba-114">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="b11ba-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b11ba-115">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="b11ba-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b11ba-116">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="b11ba-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b11ba-117">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="b11ba-117">Choose who can use this connection.</span></span> <span data-ttu-id="b11ba-118">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="b11ba-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b11ba-119">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b11ba-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b11ba-120">Digite a URL do Sales da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="b11ba-120">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="b11ba-121">Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b11ba-121">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="b11ba-122">Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="b11ba-122">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="b11ba-123">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="b11ba-123">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="b11ba-124">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="b11ba-124">Configure an export</span></span>

<span data-ttu-id="b11ba-125">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="b11ba-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b11ba-126">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b11ba-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b11ba-127">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="b11ba-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b11ba-128">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="b11ba-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b11ba-129">No campo **Conexão para exportação**, escolha uma conexão da seção do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="b11ba-129">In the **Connection for export** field, choose a connection from the Dynamics 365 Sales section.</span></span> <span data-ttu-id="b11ba-130">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="b11ba-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b11ba-131">Escolha um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="b11ba-131">Choose one or more segments.</span></span>

1. <span data-ttu-id="b11ba-132">Selecione **Salvar**</span><span class="sxs-lookup"><span data-stu-id="b11ba-132">Select **Save**</span></span>

<span data-ttu-id="b11ba-133">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b11ba-133">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b11ba-134">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b11ba-134">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b11ba-135">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b11ba-135">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
