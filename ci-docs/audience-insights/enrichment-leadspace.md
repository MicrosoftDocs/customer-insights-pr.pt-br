---
title: Enriquecimento de perfis de empresa com a Leadspace de enriquecimento de terceiros
description: Informações gerais sobre o enriquecimento de terceiros da Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269408"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="35b06-103">Enriquecimento de perfis de empresa com Leadspace (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="35b06-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="35b06-104">Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="35b06-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="35b06-105">Ela permite que os clientes com perfis de cliente unificados para as empresas possam enriquecer seus dados.</span><span class="sxs-lookup"><span data-stu-id="35b06-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="35b06-106">Os enriquecimentos incluem atributos adicionais, como tamanho da empresa, localização, setor e muito mais.</span><span class="sxs-lookup"><span data-stu-id="35b06-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="35b06-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="35b06-107">Prerequisites</span></span>

<span data-ttu-id="35b06-108">Para configurar o Leadspace, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="35b06-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="35b06-109">Você tem uma licença da Leadspace ativa e a “chave perpétua” (referida como **token da Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="35b06-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="35b06-110">Entre em contato diretamente com [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obter detalhes sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="35b06-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="35b06-111">Você tem as permissões de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="35b06-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="35b06-112">Você ter [perfis unificados de clientes](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="35b06-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="35b06-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="35b06-113">Configuration</span></span>

1. <span data-ttu-id="35b06-114">Nos insights de público-alvo, vá para **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="35b06-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="35b06-115">Selecione **Enriquecer meus dados** no bloco da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="35b06-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de tela do bloco da Leadspace.":::

1. <span data-ttu-id="35b06-117">Selecione **Introdução** e digite um **token da Leadspace** ativo (chave perpétua).</span><span class="sxs-lookup"><span data-stu-id="35b06-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="35b06-118">Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="35b06-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="35b06-119">Confirme as duas entradas selecionando **Conectar-se à Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="35b06-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="35b06-120">Selecione **Mapear dados** e escolha o conjunto de dados que deseja enriquecer com dados da empresa do Leadspace.</span><span class="sxs-lookup"><span data-stu-id="35b06-120">Select **Map data** and choose the data set you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="35b06-121">Você pode selecionar a entidade *Cliente* para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="35b06-121">You can select the *Customer* entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Escolha entre enriquecimento do segmento e do perfil do cliente.":::

1. <span data-ttu-id="35b06-123">Clique em **Próximo** e defina quais campos de seus perfis unificados devem ser usados para procurar dados da empresa correspondentes na Leadspace.</span><span class="sxs-lookup"><span data-stu-id="35b06-123">Click **Next** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="35b06-124">O campo **Nome da empresa** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="35b06-124">The **Name of company** field is required.</span></span> <span data-ttu-id="35b06-125">Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Site da empresa** e **Local da empresa**.</span><span class="sxs-lookup"><span data-stu-id="35b06-125">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo da Leadspace.":::
   
1. <span data-ttu-id="35b06-127">Selecione **Aplicar** para completar o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="35b06-127">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="35b06-128">Selecione **Executar** para enriquecer os perfis da empresa.</span><span class="sxs-lookup"><span data-stu-id="35b06-128">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="35b06-129">O tempo de duração de um enriquecimento depende do número de perfis de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="35b06-129">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="35b06-130">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="35b06-130">Enrichment results</span></span>

<span data-ttu-id="35b06-131">Depois de atualizar o enriquecimento, você pode revisar os dados da empresa recém-enriquecidos em [Meus enriquecimentos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="35b06-131">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="35b06-132">Você pode encontrar o horário da última atualização e o número de perfis aprimorados.</span><span class="sxs-lookup"><span data-stu-id="35b06-132">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="35b06-133">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="35b06-133">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="35b06-134">Para obter mais informações, consulte [APIs da Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="35b06-134">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="35b06-135">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="35b06-135">Next steps</span></span>

<span data-ttu-id="35b06-136">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="35b06-136">Build on top of your enriched customer data.</span></span> <span data-ttu-id="35b06-137">Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="35b06-137">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="35b06-138">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="35b06-138">Data privacy and compliance</span></span>

<span data-ttu-id="35b06-139">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Leadspace, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="35b06-139">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="35b06-140">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Leadspace cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="35b06-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="35b06-141">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="35b06-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="35b06-142">Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="35b06-142">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]