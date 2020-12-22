---
title: Exportar dados do Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a conexão com o Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643759"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="34d17-103">Conector para o Dynamics 365 Marketing (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="34d17-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="34d17-104">Use [segmentos](segments.md) para gerar campanhas e contatar grupos específicos de clientes com o Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="34d17-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="34d17-105">Para obter mais informações, consulte [Usar segments do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="34d17-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="34d17-106">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="34d17-106">Prerequisite</span></span>

<span data-ttu-id="34d17-107">Registros de contato [do Dynamics 365 Marketing ingeridos no Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="34d17-107">Contact records [from Dynamics 365 Marketing ingested Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="34d17-108">Configurar o conector para o Marketing</span><span class="sxs-lookup"><span data-stu-id="34d17-108">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="34d17-109">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="34d17-109">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="34d17-110">No **Dynamics 365 Marketing**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="34d17-110">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="34d17-111">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="34d17-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="34d17-112">Digite a URL do Marketing da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="34d17-112">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="34d17-113">Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="34d17-113">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="34d17-114">Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="34d17-114">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="34d17-115">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="34d17-115">Select **Next**.</span></span>

1. <span data-ttu-id="34d17-116">Escolha um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="34d17-116">Choose one or more segments.</span></span>

1. <span data-ttu-id="34d17-117">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="34d17-117">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="34d17-118">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="34d17-118">Export the data</span></span>

<span data-ttu-id="34d17-119">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="34d17-119">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="34d17-120">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="34d17-120">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
