---
title: Conector do Power Automate | Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ce2477d957a1792e0436a0dfc15a33621b1c89a9
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976074"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="6779e-103">Conector do Power Automate (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="6779e-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="6779e-104">Dispare eventos específicos para ocorrerem automaticamente quando os dados forem alterados e gerencie fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="6779e-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="6779e-105">Gatilhos do Power Automate</span><span class="sxs-lookup"><span data-stu-id="6779e-105">Power Automate triggers</span></span>

<span data-ttu-id="6779e-106">Use gatilhos para criar fluxos da nuvem e automatizar tarefas repetitivas, como notificações ou ações mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="6779e-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="6779e-107">Gatilho quando uma atualização fonte de dados falhar.</span><span class="sxs-lookup"><span data-stu-id="6779e-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="6779e-108">Gatilho quando uma atualização fonte de dados for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="6779e-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="6779e-109">Gatilho quando um limite for ultrapassado em um segmento.</span><span class="sxs-lookup"><span data-stu-id="6779e-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="6779e-110">O gatilho é limitado ao cruzamento acima do limite.</span><span class="sxs-lookup"><span data-stu-id="6779e-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="6779e-111">Gatilho quando um limite for ultrapassado em uma medida de negócios.</span><span class="sxs-lookup"><span data-stu-id="6779e-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="6779e-112">Somente medidas de negócios sem uma dimensão contam com suporte.</span><span class="sxs-lookup"><span data-stu-id="6779e-112">Only business measures without a dimension are supported.</span></span> <span data-ttu-id="6779e-113">O gatilho é limitado ao cruzamento acima do limite.</span><span class="sxs-lookup"><span data-stu-id="6779e-113">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="6779e-114">Dispare quando uma atualização completa (de fontes de dados, segmentos, medidas,...) for concluída.</span><span class="sxs-lookup"><span data-stu-id="6779e-114">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="6779e-115">Dispare quando uma atualização do processo de unificação (mapear, corresponder, mesclar) for concluída.</span><span class="sxs-lookup"><span data-stu-id="6779e-115">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="6779e-116">[Configure seus gatilhos no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="6779e-116">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="6779e-117">Ações do Power Automate</span><span class="sxs-lookup"><span data-stu-id="6779e-117">Power Automate actions</span></span>
<span data-ttu-id="6779e-118">O conector do Power Automate fornece outras ações além dos gatilhos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="6779e-118">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="6779e-119">Para obter mais informações, consulte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="6779e-119">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="6779e-120">Criar um fluxo do Power Automate</span><span class="sxs-lookup"><span data-stu-id="6779e-120">Create a Power Automate flow</span></span>

1. <span data-ttu-id="6779e-121">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="6779e-121">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6779e-122">No bloco do **Power Automate**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6779e-122">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="6779e-123">O Conector do Customer Insights (versão preliminar) no Power Automate é exibido.</span><span class="sxs-lookup"><span data-stu-id="6779e-123">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="6779e-124">**Entre** no Power Automate.</span><span class="sxs-lookup"><span data-stu-id="6779e-124">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="6779e-125">Escolha um dos gatilhos disponíveis e adicione mais etapas ao novo fluxo.</span><span class="sxs-lookup"><span data-stu-id="6779e-125">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="6779e-126">Para obter mais informações, consulte [Criar um fluxo da nuvem no Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="6779e-126">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="6779e-127">Exemplos de como usar fluxos:</span><span class="sxs-lookup"><span data-stu-id="6779e-127">Examples how to use flows:</span></span> 
- <span data-ttu-id="6779e-128">Publique uma mensagem em um canal do Microsoft Teams se houver falha na atualização da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6779e-128">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="6779e-129">Envie um email para os proprietários dos dados quando um limite em um segmento for excedido.</span><span class="sxs-lookup"><span data-stu-id="6779e-129">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]
