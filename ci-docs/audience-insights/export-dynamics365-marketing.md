---
title: Exportar dados do Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a conexão com o Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a06920b8ff25d7102ccd14ae68cf42fe91fa1ee6
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269040"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="96488-103">Conector para o Dynamics 365 Marketing (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="96488-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="96488-104">Use [segmentos](segments.md) para gerar campanhas e contatar grupos específicos de clientes com o Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="96488-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="96488-105">Para obter mais informações, consulte [Usar segments do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="96488-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="96488-106">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="96488-106">Prerequisite</span></span>

- <span data-ttu-id="96488-107">Os registros de contatos devem estar presentes no Dynamics 365 Marketing antes de exportar um segmento do Customer Insights para o Marketing.</span><span class="sxs-lookup"><span data-stu-id="96488-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="96488-108">Leia mais sobre como ingerir contatos no [Dynamics 365 Marketing usando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="96488-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="96488-109">Exportar segmentos de insights de público-alvo para o Marketing não criará registros de contatos nas instâncias do Marketing.</span><span class="sxs-lookup"><span data-stu-id="96488-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="96488-110">Os registros de contatos do Marketing devem ser ingeridos em insights de público-alvo e usados como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="96488-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="96488-111">Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="96488-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="96488-112">Configurar o conector para o Marketing</span><span class="sxs-lookup"><span data-stu-id="96488-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="96488-113">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="96488-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="96488-114">No **Dynamics 365 Marketing**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="96488-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="96488-115">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="96488-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="96488-116">Digite a URL do Marketing da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="96488-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="96488-117">Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="96488-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="96488-118">Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="96488-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="96488-119">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="96488-119">Select **Next**.</span></span>

1. <span data-ttu-id="96488-120">Escolha um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="96488-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="96488-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="96488-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="96488-122">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="96488-122">Export the data</span></span>

<span data-ttu-id="96488-123">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="96488-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="96488-124">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="96488-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]