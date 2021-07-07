---
title: Enriquecimento com o enriquecimento de terceiros da HERE Technologies
description: Informações gerais sobre o enriquecimento de terceiros da HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b3c1da0f541efb85b2ca9d87a2e3b97bbfb6ca7f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305280"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a><span data-ttu-id="ad9d6-103">Enriquecimento de perfis de clientes com a HERE Technologies (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="ad9d6-103">Enrichment of customer profiles with HERE Technologies (preview)</span></span>

<span data-ttu-id="ad9d6-104">A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-104">HERE Technologies is a location platform company that provides location-centric data and services.</span></span> <span data-ttu-id="ad9d6-105">Com os serviços de enriquecimento de dados da HERE Technologies, você pode criar uma compreensão mais precisa da localização de seus clientes com normalização de endereço, extração de latitude e longitude e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-105">With HERE Technologies' data enrichment services, you can build a more precise location understanding of your customers with address normalization, latitude and longitude extraction, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ad9d6-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ad9d6-106">Prerequisites</span></span>

<span data-ttu-id="ad9d6-107">Para configurar os enriquecimentos da HERE Technologies, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="ad9d6-107">To configure HERE Technologies enrichments, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ad9d6-108">Você tem uma assinatura ativa da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-108">You have an active HERE Technologies subscription.</span></span> <span data-ttu-id="ad9d6-109">Para obter uma assinatura, você pode [inscrever-se aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [entre contato com a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-109">To get a subscription, you can [sign up here](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) or [contact HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) directly.</span></span> [<span data-ttu-id="ad9d6-110">Saiba mais sobre o enriquecimento de localização da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-110">Learn more about HERE Technologies Location Enrichment.</span></span>](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- <span data-ttu-id="ad9d6-111">Uma [conexão](connections.md) da HERE está disponível *ou* você tem permissões de [administrador](permissions.md#administrator) e a chave de API da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-111">A HERE [connection](connections.md) is available *or* you have [administrator](permissions.md#administrator) permissions and the HERE Technologies API key.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="ad9d6-112">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="ad9d6-112">Configure the enrichment</span></span>

1. <span data-ttu-id="ad9d6-113">Vá para **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-113">Go to **Data** > **Enrichment**.</span></span> 

1. <span data-ttu-id="ad9d6-114">Selecione **Enriquecer meus dados** no bloco da HERE Technologies e selecione **Começar agora**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-114">Select **Enrich my data** on the HERE Technologies tile and select **Get started**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ad9d6-115">![Bloco da HERE Technologies](media/HERE-tile.png "Bloco da HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ad9d6-115">![HERE Technologies tile](media/HERE-tile.png "HERE Technologies tile")</span></span>

1. <span data-ttu-id="ad9d6-116">Selecione uma [conexão](connections.md) na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-116">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="ad9d6-117">Contate um administrador se nenhuma conexão estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-117">Contact  an administrator if no connection is available.</span></span> <span data-ttu-id="ad9d6-118">Se for administrador, você poderá criar uma conexão selecionando **Adicionar conexão**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-118">If you are an administrator, you can create a connection by selecting **Add connection**.</span></span> <span data-ttu-id="ad9d6-119">Escolha **HERE Technologies** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-119">Choose **HERE Technologies** from the dropdown list.</span></span> 

1. <span data-ttu-id="ad9d6-120">Selecione **Conectar-se à HERE Technologies** para confirmar a seleção da conexão.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-120">Select **Connect to HERE Technologies** to confirm the selection.</span></span>

1.  <span data-ttu-id="ad9d6-121">Selecione **Avançar** e escolha o **Conjunto de dados do cliente** que você deseja enriquecer com os dados de localização da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-121">Select **Next** and choose the **Customer data set** you want to enrich with location data from HERE Technologies.</span></span> <span data-ttu-id="ad9d6-122">Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. <span data-ttu-id="ad9d6-124">Escolha se deseja mapear os campos para o endereço principal e/ou secundário.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-124">Choose if you want to map fields to the primary and/or secondary address.</span></span> <span data-ttu-id="ad9d6-125">Você pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis para ambos os endereços separadamente.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-125">You can specify a field mapping for both addresses and enrich the profiles for both addresses separately.</span></span> <span data-ttu-id="ad9d6-126">Por exemplo, se houver um endereço residencial e comercial.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-126">For example, if there's a home and a business address.</span></span> <span data-ttu-id="ad9d6-127">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-127">Select **Next**.</span></span>

1. <span data-ttu-id="ad9d6-128">Defina quais campos de seus perfis unificados devem ser usados para procurar dados de localização correspondentes da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-128">Define which fields from your unified profiles should be used to look for matching location data from HERE Technologies.</span></span> <span data-ttu-id="ad9d6-129">Os campos **Rua 1** e **CEP** são obrigatórios para o endereço principal e/ou secundário selecionado.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-129">The **Street 1** and **Zip/Postal Code** fields are required for the selected primary and/or secondary address.</span></span> <span data-ttu-id="ad9d6-130">Para uma maior precisão de correspondência, mais campos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-130">For a higher match accuracy, more fields can be added.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ad9d6-131">![Página de configuração de enriquecimento da HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuração de enriquecimento da HERE Technologies")</span><span class="sxs-lookup"><span data-stu-id="ad9d6-131">![HERE Technologies enrichment configuration page](media/enrichment-HERE-configuration.png "HERE Technologies enrichment configuration page")</span></span>

1. <span data-ttu-id="ad9d6-132">Selecione **Avançar** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-132">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="ad9d6-133">Forneça um nome para o enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-133">Provide a name for the enrichment.</span></span> 

1. <span data-ttu-id="ad9d6-134">Selecione **Salvar enriquecimento** depois de revisar suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-134">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-here-technologies"></a><span data-ttu-id="ad9d6-135">Configurar a conexão para a HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="ad9d6-135">Configure the connection for HERE Technologies</span></span> 

<span data-ttu-id="ad9d6-136">Você deve ser um administrador para configurar as conexões.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-136">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="ad9d6-137">Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da HERE technologies.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-137">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the HERE Technologies tile.</span></span>

1. <span data-ttu-id="ad9d6-138">Insira um nome para a conexão na caixa **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="ad9d6-139">Forneça uma chave de API da HERE Technologies válida.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-139">Provide a valid HERE Technologies API key.</span></span>

1. <span data-ttu-id="ad9d6-140">Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** selecionando **Eu concordo**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-140">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="ad9d6-141">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="ad9d6-142">Depois de concluir a verificação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-142">After completing the verification, select **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ad9d6-143">![Página de configuração de conexão da HERE technologies](media/enrichment-HERE-connection.png "Página de configuração de conexão da HERE technologies")</span><span class="sxs-lookup"><span data-stu-id="ad9d6-143">![HERE Technologies connection configuration page](media/enrichment-HERE-connection.png "HERE Technologies connection configuration page")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ad9d6-144">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="ad9d6-144">Enrichment results</span></span>

<span data-ttu-id="ad9d6-145">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ad9d6-146">Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ad9d6-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ad9d6-147">O tempo de processamento dependerá do tamanho dos dados do cliente e dos tempos de resposta da API da HERE Technologies.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-147">The processing time will depend on the size of your customer data and the API response times from HERE Technologies.</span></span>

<span data-ttu-id="ad9d6-148">Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ad9d6-149">Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ad9d6-150">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ad9d6-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ad9d6-151">Next steps</span></span>

<span data-ttu-id="ad9d6-152">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ad9d6-153">Crie [segmentos](segments.md) e [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-153">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ad9d6-154">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="ad9d6-154">Data privacy and compliance</span></span>

<span data-ttu-id="ad9d6-155">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-155">When you enable Dynamics 365 Customer Insights to transmit data to HERE Technologies, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ad9d6-156">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a HERE Technologies cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that HERE Technologies meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ad9d6-157">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ad9d6-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ad9d6-158">Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ad9d6-158">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
