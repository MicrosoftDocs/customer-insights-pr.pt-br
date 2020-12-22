---
title: Exportar dados do Customer Insights para o Google Ads
description: Saiba como configurar a conexão com o Google Ads.
ms.date: 11/18/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 06aa0b6ff3125d8735adc8c8f9f6dad69087d9f8
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568400"
---
# <a name="connector-for-google-ads-preview"></a><span data-ttu-id="e3618-103">Conector para Google Ads (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="e3618-103">Connector for Google Ads (preview)</span></span>

<span data-ttu-id="e3618-104">Exporte segmentos de perfis de clientes unificados para a lista de públicos-alvo do Google Ads e use-os para anunciar na Pesquisa do Google, no Gmail, no YouTube e na Rede de Display do Google.</span><span class="sxs-lookup"><span data-stu-id="e3618-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="e3618-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="e3618-105">Prerequisites</span></span>

-   <span data-ttu-id="e3618-106">Você deve ter uma [conta do Google Ads](https://ads.google.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="e3618-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="e3618-107">Há públicos-alvo existentes no Google Ads e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="e3618-107">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="e3618-108">Para obter mais informações, consulte [públicos-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="e3618-108">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="e3618-109">Você deve ter [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="e3618-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="e3618-110">Os perfis de clientes unificados nos segmentos exportados contêm campos que representam endereço de email, nome e sobrenome</span><span class="sxs-lookup"><span data-stu-id="e3618-110">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="connect-to-google-ads"></a><span data-ttu-id="e3618-111">Conectar ao Google Ads</span><span class="sxs-lookup"><span data-stu-id="e3618-111">Connect to Google Ads</span></span>

1. <span data-ttu-id="e3618-112">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="e3618-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="e3618-113">Em **Google Ads**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e3618-113">Under **Google Ads**, select **Set up**.</span></span>

1. <span data-ttu-id="e3618-114">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="e3618-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="e3618-115">Insira sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="e3618-115">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="e3618-116">Insira seu **[token de desenvolvedor aprovado do Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="e3618-116">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="e3618-117">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="e3618-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="e3618-118">Insira sua **[ID de público-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e selecione **Conectar** para inicializar a conexão com o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="e3618-118">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="e3618-119">Selecione **Autenticar com o Google Ads** e forneça suas credenciais do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="e3618-119">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="e3618-120">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="e3618-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-segments-googleads.PNG" alt-text="Captura de tela de exportação da conexão com o Google Ads":::

1. <span data-ttu-id="e3618-122">Selecione **Próximo** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="e3618-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="e3618-123">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="e3618-123">Configure the connector</span></span>

1. <span data-ttu-id="e3618-124">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="e3618-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="e3618-125">Repita as mesmas etapas para os campos **Nome** e **Sobrenome**.</span><span class="sxs-lookup"><span data-stu-id="e3618-125">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="e3618-126">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="e3618-126">Select the segments you want to export.</span></span> <span data-ttu-id="e3618-127">Você pode exportar até 1 milhão de perfis de clientes no total para o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="e3618-127">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

1. <span data-ttu-id="e3618-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="e3618-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="e3618-129">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="e3618-129">Export the data</span></span>

<span data-ttu-id="e3618-130">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="e3618-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="e3618-131">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="e3618-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="e3618-132">No Google Ads, agora você pode encontrar seus segmentos em [públicos-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en/).</span><span class="sxs-lookup"><span data-stu-id="e3618-132">In Google Ads, you can now find your segments under [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e3618-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="e3618-133">Known limitations</span></span>

- <span data-ttu-id="e3618-134">Até 1 milhão de perfis por exportação para o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="e3618-134">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="e3618-135">A exportação para o Google Ads é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="e3618-135">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="e3618-136">A exportação de segmentos com um total de 1 milhão de perfis pode levar até 5 minutos devido a limitações do provedor.</span><span class="sxs-lookup"><span data-stu-id="e3618-136">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="e3618-137">A correspondência no Google Ads pode levar até 48 horas.</span><span class="sxs-lookup"><span data-stu-id="e3618-137">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="e3618-138">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="e3618-138">Data privacy and compliance</span></span>

<span data-ttu-id="e3618-139">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Google Ads, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="e3618-139">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="e3618-140">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Google Ads cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="e3618-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="e3618-141">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="e3618-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="e3618-142">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="e3618-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
