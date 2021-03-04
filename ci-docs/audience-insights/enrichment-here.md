---
title: Enriquecimento com o enriquecimento de terceiros da HERE Technologies
description: Informações gerais sobre o enriquecimento de terceiros da HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 258e37de9d9685d9ebc30b3c6b8d238d583431b4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269500"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="bcdc2-103">Enriquecimento de perfis de clientes com a HERE Technologies (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="bcdc2-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="bcdc2-104">A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="bcdc2-105">Com os serviços de enriquecimento de dados da HERE Technologies, você pode criar uma compreensão mais precisa da localização de seus clientes com normalização de endereço, extração de latitude e longitude e muito mais.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bcdc2-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bcdc2-106">Prerequisites</span></span>

<span data-ttu-id="bcdc2-107">Para configurar os enriquecimentos da HERE Technologies, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="bcdc2-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="bcdc2-108">Você tem uma assinatura ativa da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="bcdc2-109">Para obter uma assinatura, você pode [se inscrever aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [entre contato com a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-109">To get a subscription, you can [sign-up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="bcdc2-110">Saiba mais sobre o enriquecimento de localização da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="bcdc2-111">Você tem a chave de API da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-111">You have the HERE Technologies API key.</span></span>

- <span data-ttu-id="bcdc2-112">Você tem as permissões de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="bcdc2-112">You have [Administrator](permissions.md#administrator) permissions.</span></span>

## <a name="configuration"></a><span data-ttu-id="bcdc2-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="bcdc2-113">Configuration</span></span>

1. <span data-ttu-id="bcdc2-114">Vá para **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-114">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="bcdc2-115">Selecione **Enriquecer meus dados** no bloco da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-115">Select **Enrich my data** on the HERE Technologies tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcdc2-116">![Bloco da HERE Technologies](media/HERE-tile.png "Bloco da HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="bcdc2-116">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="bcdc2-117">Insira uma **chave de API da HERE Technologies** ativa.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-117">Enter an active **HERE Technologies API key**.</span></span> <span data-ttu-id="bcdc2-118">Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> 

1. <span data-ttu-id="bcdc2-119">Confirme as duas entradas selecionando **Conectar-se à HERE**.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-119">Confirm both inputs by selecting **Connect to HERE**.</span></span>

1.  <span data-ttu-id="bcdc2-120">Selecione **Adicionar dados** e escolha o **Conjunto de dados do cliente** que deseja enriquecer com dados de localização de Tecnologias HERE.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-120">Select **Add data** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="bcdc2-121">Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-121">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. <span data-ttu-id="bcdc2-123">Escolha se deseja mapear os campos para o endereço principal e/ou secundário.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-123">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="bcdc2-124">Você pode especificar um mapeamento de campo para ambos os endereços (por exemplo, um endereço residencial e um comercial) e enriquecer os perfis para ambos os endereços separadamente.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-124">You can specify a field mapping for both addresses (for example, a home and a business address) and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="bcdc2-125">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-125">Select **Next**.</span></span>

1. <span data-ttu-id="bcdc2-126">Defina quais campos de seus perfis unificados devem ser usados para procurar dados de localização correspondentes da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-126">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="bcdc2-127">Os campos **Rua 1** e **CEP** são obrigatórios para o endereço principal e/ou secundário selecionado.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-127">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="bcdc2-128">Para uma maior precisão de correspondência, mais campos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-128">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="bcdc2-129">![Página de configuração de enriquecimento da HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuração de enriquecimento da HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="bcdc2-129">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="bcdc2-130">Selecione **Aplicar** para completar o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-130">Select **Apply** to complete the field mapping.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="bcdc2-131">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="bcdc2-131">Enrichment results</span></span>

<span data-ttu-id="bcdc2-132">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-132">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="bcdc2-133">Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="bcdc2-133">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="bcdc2-134">O tempo de processamento dependerá do tamanho dos dados do cliente e dos tempos de resposta da API da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-134">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="bcdc2-135">Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-135">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="bcdc2-136">Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-136">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="bcdc2-137">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-137">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bcdc2-138">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="bcdc2-138">Next steps</span></span>

<span data-ttu-id="bcdc2-139">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-139">Build on top of your enriched customer data.</span></span> <span data-ttu-id="bcdc2-140">Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-140">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="bcdc2-141">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="bcdc2-141">Data privacy and compliance</span></span>

<span data-ttu-id="bcdc2-142">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-142">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="bcdc2-143">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a HERE Technologies cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="bcdc2-144">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="bcdc2-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="bcdc2-145">Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="bcdc2-145">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]