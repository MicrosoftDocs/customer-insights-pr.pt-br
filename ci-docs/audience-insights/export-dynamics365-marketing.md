---
title: Exportar dados do Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a conexão e exportar para o Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a13f6f81f5e2570d3302d88c02755f1d86321a01
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759595"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a><span data-ttu-id="0f751-103">Usar segmentos no Dynamics 365 Marketing (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="0f751-103">Use segments in Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="0f751-104">Use [segmentos](segments.md) para gerar campanhas e contatar grupos específicos de clientes com o Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="0f751-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="0f751-105">Para obter mais informações, consulte [Usar segments do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="0f751-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite-for-a-connection"></a><span data-ttu-id="0f751-106">Pré-requisitos para uma conexão</span><span class="sxs-lookup"><span data-stu-id="0f751-106">Prerequisite for a connection</span></span>

- <span data-ttu-id="0f751-107">Os registros de contatos devem estar presentes no Dynamics 365 Marketing antes de exportar um segmento do Customer Insights para o Marketing.</span><span class="sxs-lookup"><span data-stu-id="0f751-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="0f751-108">Leia mais sobre como ingerir contatos no [Dynamics 365 Marketing usando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="0f751-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="0f751-109">Exportar segmentos de insights de público-alvo para o Marketing não criará registros de contatos nas instâncias do Marketing.</span><span class="sxs-lookup"><span data-stu-id="0f751-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="0f751-110">Os registros de contatos do Marketing devem ser ingeridos em insights de público-alvo e usados como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0f751-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="0f751-111">Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="0f751-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="set-up-connection-to-marketing"></a><span data-ttu-id="0f751-112">Configurar conexão com o Marketing</span><span class="sxs-lookup"><span data-stu-id="0f751-112">Set up connection to Marketing</span></span>

1. <span data-ttu-id="0f751-113">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="0f751-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0f751-114">Selecione **Adicionar conexão** e escolha **Dynamics 365 Marketing** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="0f751-114">Select **Add connection** and choose **Dynamics 365 Marketing** to configure the connection.</span></span>

1. <span data-ttu-id="0f751-115">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="0f751-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0f751-116">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="0f751-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0f751-117">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="0f751-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0f751-118">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="0f751-118">Choose who can use this connection.</span></span> <span data-ttu-id="0f751-119">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="0f751-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0f751-120">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0f751-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0f751-121">Digite a URL do Marketing da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="0f751-121">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="0f751-122">Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="0f751-122">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="0f751-123">Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="0f751-123">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="0f751-124">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="0f751-124">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="0f751-125">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="0f751-125">Configure an export</span></span>

<span data-ttu-id="0f751-126">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="0f751-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0f751-127">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0f751-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0f751-128">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="0f751-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0f751-129">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="0f751-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0f751-130">No campo **Conexão para exportação**, escolha uma conexão da seção do Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="0f751-130">In the **Connection for export** field, choose a connection from the Dynamics 365 Marketing section.</span></span> <span data-ttu-id="0f751-131">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="0f751-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0f751-132">Escolha um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="0f751-132">Choose one or more segments.</span></span>

1. <span data-ttu-id="0f751-133">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0f751-133">Select **Save**.</span></span>

<span data-ttu-id="0f751-134">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0f751-134">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0f751-135">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0f751-135">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0f751-136">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0f751-136">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
