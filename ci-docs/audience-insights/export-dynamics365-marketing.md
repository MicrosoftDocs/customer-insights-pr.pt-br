---
title: Exportar dados do Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a conexão com o Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597589"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a><span data-ttu-id="f7267-103">Conector para o Dynamics 365 Marketing (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="f7267-103">Connector for Dynamics 365 Marketing (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="f7267-104">Use [segmentos](segments.md) para gerar campanhas e contatar grupos específicos de clientes com o Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f7267-104">Use [segments](segments.md) to generate campaigns and contact specific groups of customers with Dynamics 365 Marketing.</span></span> <span data-ttu-id="f7267-105">Para obter mais informações, consulte [Usar segments do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span><span class="sxs-lookup"><span data-stu-id="f7267-105">For more information, see [Use segments from Dynamics 365 Customer Insights with Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)</span></span>

## <a name="prerequisite"></a><span data-ttu-id="f7267-106">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="f7267-106">Prerequisite</span></span>

- <span data-ttu-id="f7267-107">Os registros de contatos devem estar presentes no Dynamics 365 Marketing antes de exportar um segmento do Customer Insights para o Marketing.</span><span class="sxs-lookup"><span data-stu-id="f7267-107">Contact records must be present in Dynamics 365 Marketing before you can export a segment from Customer Insights to Marketing.</span></span> <span data-ttu-id="f7267-108">Leia mais sobre como ingerir contatos no [Dynamics 365 Marketing usando o Common Data Services](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="f7267-108">Read more on how to ingest contacts in [Dynamics 365 Marketing using Common Data Services](connect-power-query.md).</span></span>

  > [!NOTE]
  > <span data-ttu-id="f7267-109">Exportar segmentos de insights de público-alvo para o Marketing não criará registros de contatos nas instâncias do Marketing.</span><span class="sxs-lookup"><span data-stu-id="f7267-109">Exporting segments from audience insights to Marketing will not create new contact records in the Marketing instances.</span></span> <span data-ttu-id="f7267-110">Os registros de contatos do Marketing devem ser ingeridos em insights de público-alvo e usados como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="f7267-110">The contact records from Marketing must be ingested in audience insights and used as a data source.</span></span> <span data-ttu-id="f7267-111">Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.</span><span class="sxs-lookup"><span data-stu-id="f7267-111">They also need to be included in the unified Customer entity to map customer IDs to contact IDs before segments can be exported.</span></span>

## <a name="configure-the-connector-for-marketing"></a><span data-ttu-id="f7267-112">Configurar o conector para o Marketing</span><span class="sxs-lookup"><span data-stu-id="f7267-112">Configure the connector for Marketing</span></span>

1. <span data-ttu-id="f7267-113">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="f7267-113">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f7267-114">No **Dynamics 365 Marketing**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="f7267-114">Under **Dynamics 365 Marketing**, select **Set up**.</span></span>

1. <span data-ttu-id="f7267-115">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="f7267-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f7267-116">Digite a URL do Marketing da sua organização no campo **Endereço do servidor**.</span><span class="sxs-lookup"><span data-stu-id="f7267-116">Enter your organization's Marketing URL in the **Server address** field.</span></span>

1. <span data-ttu-id="f7267-117">Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Marketing.</span><span class="sxs-lookup"><span data-stu-id="f7267-117">In the **Server admin account** section, select **Sign in** and choose a Dynamics 365 Marketing account.</span></span>

1. <span data-ttu-id="f7267-118">Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="f7267-118">Map a customer ID field to the Dynamics 365 Contact ID.</span></span>

1. <span data-ttu-id="f7267-119">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="f7267-119">Select **Next**.</span></span>

1. <span data-ttu-id="f7267-120">Escolha um ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="f7267-120">Choose one or more segments.</span></span>

1. <span data-ttu-id="f7267-121">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f7267-121">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f7267-122">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="f7267-122">Export the data</span></span>

<span data-ttu-id="f7267-123">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="f7267-123">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="f7267-124">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f7267-124">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]