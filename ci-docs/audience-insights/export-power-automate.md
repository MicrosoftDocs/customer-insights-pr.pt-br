---
title: Conector do Power Automate | Microsoft Docs
description: Criar fluxos no Microsoft Power Automate a partir do Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e973bb11b31c9e70b695ebec8aa2700fdaa5e44f
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597911"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="c0e83-103">Conector do Power Automate (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="c0e83-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="c0e83-104">Dispare eventos específicos para ocorrerem automaticamente quando os dados forem alterados e gerencie fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="c0e83-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="c0e83-105">Gatilhos do Power Automate</span><span class="sxs-lookup"><span data-stu-id="c0e83-105">Power Automate triggers</span></span>

<span data-ttu-id="c0e83-106">Use gatilhos para criar fluxos da nuvem e automatizar tarefas repetitivas, como notificações ou ações mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="c0e83-106">Use triggers to create cloud flows and automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="c0e83-107">Gatilho quando uma atualização fonte de dados falhar.</span><span class="sxs-lookup"><span data-stu-id="c0e83-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="c0e83-108">Gatilho quando uma atualização fonte de dados for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="c0e83-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="c0e83-109">Gatilho quando um limite for ultrapassado em um segmento.</span><span class="sxs-lookup"><span data-stu-id="c0e83-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="c0e83-110">O gatilho é limitado ao cruzamento acima do limite.</span><span class="sxs-lookup"><span data-stu-id="c0e83-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="c0e83-111">Gatilho quando um limite for ultrapassado em uma medida de negócios.</span><span class="sxs-lookup"><span data-stu-id="c0e83-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="c0e83-112">O gatilho é limitado ao cruzamento acima do limite.</span><span class="sxs-lookup"><span data-stu-id="c0e83-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="c0e83-113">Dispare quando uma atualização completa (de fontes de dados, segmentos, medidas,...) for concluída.</span><span class="sxs-lookup"><span data-stu-id="c0e83-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="c0e83-114">Dispare quando uma atualização do processo de unificação (mapear, corresponder, mesclar) for concluída.</span><span class="sxs-lookup"><span data-stu-id="c0e83-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="c0e83-115">[Configure seus gatilhos no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="c0e83-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="c0e83-116">Ações do Power Automate</span><span class="sxs-lookup"><span data-stu-id="c0e83-116">Power Automate actions</span></span>
<span data-ttu-id="c0e83-117">O conector do Power Automate fornece outras ações além dos gatilhos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c0e83-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="c0e83-118">Para obter mais informações, consulte [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="c0e83-118">For more information, see the [Dynamics 365 Customer Insights Connector](/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow"></a><span data-ttu-id="c0e83-119">Criar um fluxo do Power Automate</span><span class="sxs-lookup"><span data-stu-id="c0e83-119">Create a Power Automate flow</span></span>

1. <span data-ttu-id="c0e83-120">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="c0e83-120">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="c0e83-121">No bloco do **Power Automate**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="c0e83-121">On the **Power Automate** tile, select **Set up**.</span></span>

1. <span data-ttu-id="c0e83-122">O Conector do Customer Insights (versão preliminar) no Power Automate é exibido.</span><span class="sxs-lookup"><span data-stu-id="c0e83-122">The Customer Insights Connector (preview) in Power Automate opens.</span></span> <span data-ttu-id="c0e83-123">**Entre** no Power Automate.</span><span class="sxs-lookup"><span data-stu-id="c0e83-123">**Sign in** to Power Automate.</span></span>

1. <span data-ttu-id="c0e83-124">Escolha um dos gatilhos disponíveis e adicione mais etapas ao novo fluxo.</span><span class="sxs-lookup"><span data-stu-id="c0e83-124">Choose one of the available triggers and add more steps to your new flow.</span></span> <span data-ttu-id="c0e83-125">Para obter mais informações, consulte [Criar um fluxo da nuvem no Power Automate](/power-automate/get-started-logic-flow).</span><span class="sxs-lookup"><span data-stu-id="c0e83-125">For more information, see [Create a cloud flow in Power Automate](/power-automate/get-started-logic-flow).</span></span>

<span data-ttu-id="c0e83-126">Exemplos de como usar fluxos:</span><span class="sxs-lookup"><span data-stu-id="c0e83-126">Examples how to use flows:</span></span> 
- <span data-ttu-id="c0e83-127">Publique uma mensagem em um canal do Microsoft Teams se houver falha na atualização da fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c0e83-127">Post a message to a Microsoft Teams channel if a data source refresh fails.</span></span> 
- <span data-ttu-id="c0e83-128">Envie um email para os proprietários dos dados quando um limite em um segmento for excedido.</span><span class="sxs-lookup"><span data-stu-id="c0e83-128">Send an email to the data owners when a threshold on a segment is crossed.</span></span>



[!INCLUDE[footer-include](../includes/footer-banner.md)]