---
title: Exportar dados do Customer Insights para o Dynamics 365 Sales
description: Saiba como configurar a conexão com o Dynamics 365 Sales.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 0013c4e6a96401d6cdbea55ed38f85f5e10dcc56
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268994"
---
# <a name="connector-for-dynamics-365-sales-preview"></a><span data-ttu-id="6665d-103">Conector para Dynamics 365 Sales (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="6665d-103">Connector for Dynamics 365 Sales (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="6665d-104">Use seus dados de cliente para criar listas de marketing, fluxos de trabalho de acompanhamento e enviar promoções com o Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="6665d-104">Use your customer data to create marketing lists, follow up workflows, and send out promotions with Dynamics 365 Sales.</span></span>

## <a name="prerequisite"></a><span data-ttu-id="6665d-105">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="6665d-105">Prerequisite</span></span>

1. <span data-ttu-id="6665d-106">Os registros de contatos devem estar presentes no Dynamics 365 Sales antes de exportar um segmento do Customer Insights para o Sales.</span><span class="sxs-lookup"><span data-stu-id="6665d-106">Contact records must be present in Dynamics 365 Sales before you can export a segment from Customer Insights to Sales.</span></span> <span data-ttu-id="6665d-107">Leia mais sobre como ingerir contatos no [Dynamics 365 Sales usando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="6665d-107">Read more on how to ingest contacts in [Dynamics 365 Sales using Common Data Services](connect-power-query.md).</span></span>

   > [!NOTE]
   > <span data-ttu-id="6665d-108">Exportar segmentos de insights de público-alvo para o Sales não criará registros de contatos nas instâncias do Sales.</span><span class="sxs-lookup"><span data-stu-id="6665d-108">Exporting segments from audience insights to Sales will not create new contact records in the Sales instances.</span></span> <span data-ttu-id="6665d-109">Os registros de contatos do Sales devem ser ingeridos em insights de público-alvo e usados como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="6665d-109">The contact records from Sales must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="6665d-110">Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="6665d-110">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-sales"></a><span data-ttu-id="6665d-111">Configurar o conector para o Sales</span><span class="sxs-lookup"><span data-stu-id="6665d-111">Configure the connector for Sales</span></span>

1. <span data-ttu-id="6665d-112">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="6665d-112">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="6665d-113">No **Dynamics 365 Sales**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="6665d-113">Under **Dynamics 365 Sales**, select **Set up**.</span></span>

1. <span data-ttu-id="6665d-114">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="6665d-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="6665d-115">Digite a URL do Sales da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="6665d-115">Enter your organization's Sales URL in the **Server address** field.</span></span>

1. <span data-ttu-id="6665d-116">Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Sales.</span><span class="sxs-lookup"><span data-stu-id="6665d-116">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Sales account.</span></span>

1. <span data-ttu-id="6665d-117">Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="6665d-117">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="6665d-118">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="6665d-118">Select **Next**.</span></span>

1. <span data-ttu-id="6665d-119">Escolha um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="6665d-119">Choose one or more segments.</span></span>

1. <span data-ttu-id="6665d-120">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6665d-120">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="6665d-121">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="6665d-121">Export the data</span></span>

<span data-ttu-id="6665d-122">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="6665d-122">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="6665d-123">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6665d-123">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]