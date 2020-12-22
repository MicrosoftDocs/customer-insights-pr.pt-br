---
title: Conector do Power Automate | Microsoft Docs
description: Crie fluxos no Microsoft Power Automate desde o Dynamics 365 Customer Insights.
ms.date: 08/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: philk
manager: shellyha
ms.openlocfilehash: ffe92414365b0b777691a4a2d585100e4fbea591
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405009"
---
# <a name="power-automate-connector-preview"></a><span data-ttu-id="761a3-103">Conector do Power Automate (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="761a3-103">Power Automate connector (preview)</span></span>

<span data-ttu-id="761a3-104">Dispare eventos específicos para ocorrerem automaticamente quando os dados forem alterados e gerencie fluxos mais complexos diretamente no [Power Automate](https://flow.microsoft.com/).</span><span class="sxs-lookup"><span data-stu-id="761a3-104">Trigger specific events to occur automatically when your data changes and manage more complex flows directly in [Power Automate](https://flow.microsoft.com/).</span></span>

## <a name="power-automate-triggers"></a><span data-ttu-id="761a3-105">Gatilhos do Power Automate</span><span class="sxs-lookup"><span data-stu-id="761a3-105">Power Automate triggers</span></span>

<span data-ttu-id="761a3-106">Você pode usar uma variedade de gatilhos que permitem criar fluxos para automatizar tarefas repetitivas, como notificações ou ações mais avançadas.</span><span class="sxs-lookup"><span data-stu-id="761a3-106">You can use a variety of triggers that allow you to create flows to automate repetitive tasks, such as notifications or more advanced actions.</span></span> 

- <span data-ttu-id="761a3-107">Gatilho quando uma atualização fonte de dados falhar.</span><span class="sxs-lookup"><span data-stu-id="761a3-107">Trigger when a data source refresh fails.</span></span> 
- <span data-ttu-id="761a3-108">Gatilho quando uma atualização fonte de dados for bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="761a3-108">Trigger when a data source refresh succeeds.</span></span>
- <span data-ttu-id="761a3-109">Gatilho quando um limite for ultrapassado em um segmento.</span><span class="sxs-lookup"><span data-stu-id="761a3-109">Trigger when a threshold is crossed on a segment.</span></span> <span data-ttu-id="761a3-110">O gatilho é limitado ao cruzamento acima do limite.</span><span class="sxs-lookup"><span data-stu-id="761a3-110">The trigger is limited to crossing above the threshold.</span></span>
- <span data-ttu-id="761a3-111">Gatilho quando um limite for ultrapassado em uma medida de negócios.</span><span class="sxs-lookup"><span data-stu-id="761a3-111">Trigger when a threshold is crossed on a business measure.</span></span> <span data-ttu-id="761a3-112">O gatilho é limitado ao cruzamento acima do limite.</span><span class="sxs-lookup"><span data-stu-id="761a3-112">The trigger is limited crossing above the threshold.</span></span>
- <span data-ttu-id="761a3-113">Dispare quando uma atualização completa (de fontes de dados, segmentos, medidas,...) for concluída.</span><span class="sxs-lookup"><span data-stu-id="761a3-113">Trigger when a full refresh of (data sources, segments, measures,...) is completed.</span></span>
- <span data-ttu-id="761a3-114">Dispare quando uma atualização do processo de unificação (mapear, corresponder, mesclar) for concluída.</span><span class="sxs-lookup"><span data-stu-id="761a3-114">Trigger when a refresh of the unification process (map, match, merge) is completed.</span></span>

<span data-ttu-id="761a3-115">[Configure seus gatilhos no Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span><span class="sxs-lookup"><span data-stu-id="761a3-115">[Configure your triggers in Power Automate](https://flow.microsoft.com/connectors/shared_customerinsights/dynamics-365-customer-insights-connector/).</span></span>

## <a name="power-automate-actions"></a><span data-ttu-id="761a3-116">Ações do Power Automate</span><span class="sxs-lookup"><span data-stu-id="761a3-116">Power Automate actions</span></span>
<span data-ttu-id="761a3-117">O conector do Power Automate fornece outras ações além dos gatilhos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="761a3-117">The Power Automate connector provides other actions than the available triggers.</span></span> <span data-ttu-id="761a3-118">Para obter mais informações, consulte [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span><span class="sxs-lookup"><span data-stu-id="761a3-118">For more information, see the [Dynamics 365 Customer Insights Connector](https://docs.microsoft.com/connectors/customerinsights/).</span></span>

## <a name="create-a-power-automate-flow-in-audience-insights"></a><span data-ttu-id="761a3-119">Criar um fluxo do Power Automate nos insights de público-alvo</span><span class="sxs-lookup"><span data-stu-id="761a3-119">Create a Power Automate flow in audience insights</span></span>

1. <span data-ttu-id="761a3-120">Nos insights de público-alvo, vá para **Administrador** > **Sistema**.</span><span class="sxs-lookup"><span data-stu-id="761a3-120">In audience insights, go to **Admin** > **System**.</span></span>

1. <span data-ttu-id="761a3-121">Na página **Sistema**, selecione a guia **Status**.</span><span class="sxs-lookup"><span data-stu-id="761a3-121">On the **System** page, select the **Status** tab.</span></span>

1. <span data-ttu-id="761a3-122">Na seção **Fontes de Dados**, selecione **Fluxos** e selecione **Criar um fluxo** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="761a3-122">In the **Data Sources** section, select **Flows** and select **Create a flow** from the dropdown list.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="761a3-123">![Conector do Power Automate mostrando a ação Criar um Fluxo](media/power-automate-connector-create-flow.png "Conector do Power Automate mostrando a ação Criar um Fluxo")</span><span class="sxs-lookup"><span data-stu-id="761a3-123">![Power Automate connector showing Create a Flow action](media/power-automate-connector-create-flow.png "Power Automate connector showing Create a Flow action")</span></span>

1. <span data-ttu-id="761a3-124">No Power Automate, selecione um dos gatilhos disponíveis para criar seu fluxo preferido.</span><span class="sxs-lookup"><span data-stu-id="761a3-124">In Power Automate, select one of the available triggers to create your preferred flow.</span></span> <span data-ttu-id="761a3-125">Se estiver criando seu primeiro fluxo, você precisará se autenticar com o conector do Power Automate primeiro.</span><span class="sxs-lookup"><span data-stu-id="761a3-125">If you're creating your first flow, you'll need to authenticate with the Power Automate connector first.</span></span>
