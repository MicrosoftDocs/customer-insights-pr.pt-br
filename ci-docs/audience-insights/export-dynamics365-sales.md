---
title: Exportar dados do Customer Insights para o Dynamics 365 Sales
description: Saiba como configurar a conexão com o Dynamics 365 Sales.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: af0824e69dfdf620a0ac756e32a9bd3dd85e5151
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643804"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="32df8-103">Conector para Dynamics 365 Sales (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="32df8-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="32df8-104">Use seus dados de cliente para criar listas de marketing, fluxos de trabalho de acompanhamento e enviar promoções com o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="32df8-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="32df8-105">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="32df8-105">Prerequisite</span></span>

<span data-ttu-id="32df8-106">Registros de contato [do Dynamics 365 Sales ingeridos usando o Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="32df8-106">Contact records [from Dynamics 365 Sales ingested using Common Data Service](connect-power-query.md).</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="32df8-107">Configurar o conector para o Sales</span><span class="sxs-lookup"><span data-stu-id="32df8-107">Configure the connector for Sales</span></span>

1. <span data-ttu-id="32df8-108">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="32df8-108">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="32df8-109">No **Dynamics 365 Sales**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="32df8-109">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="32df8-110">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="32df8-110">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="32df8-111">Digite a URL do Sales da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="32df8-111">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="32df8-112">Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="32df8-112">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="32df8-113">Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="32df8-113">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="32df8-114">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="32df8-114">Select **Next**.</span></span>

1. <span data-ttu-id="32df8-115">Escolha um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="32df8-115">Choose one or more segments.</span></span>

1. <span data-ttu-id="32df8-116">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="32df8-116">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="32df8-117">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="32df8-117">Export the data</span></span>

<span data-ttu-id="32df8-118">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="32df8-118">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="32df8-119">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="32df8-119">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
