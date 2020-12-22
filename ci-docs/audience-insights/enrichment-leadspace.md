---
title: Enriquecimento de perfis de empresa com a Leadspace de enriquecimento de terceiros
description: Informações gerais sobre o enriquecimento de terceiros da Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1b5c6e46e8e424df83e855d81fc4dd7ecb394e3c
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668709"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="512b6-103">Enriquecimento de perfis de empresa com Leadspace (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="512b6-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="512b6-104">Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="512b6-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="512b6-105">Ela permite que os clientes com perfis de cliente unificados para as empresas possam enriquecer seus dados.</span><span class="sxs-lookup"><span data-stu-id="512b6-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="512b6-106">Os enriquecimentos incluem atributos adicionais, como tamanho da empresa, localização, setor e muito mais.</span><span class="sxs-lookup"><span data-stu-id="512b6-106">Enrichments include additional attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="512b6-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="512b6-107">Prerequisites</span></span>

<span data-ttu-id="512b6-108">Para configurar o Leadspace, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="512b6-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="512b6-109">Você tem uma licença da Leadspace ativa e a “chave perpétua” (referida como **token da Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="512b6-109">You have an active Leadspace license and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="512b6-110">Entre em contato diretamente com [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obter detalhes sobre o produto.</span><span class="sxs-lookup"><span data-stu-id="512b6-110">Contact directly [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) for details about their product.</span></span>
- <span data-ttu-id="512b6-111">Você tem as permissões de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="512b6-111">You have [Administrator](permissions.md#administrator) permissions.</span></span>
- <span data-ttu-id="512b6-112">Você ter [perfis unificados de clientes](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="512b6-112">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>

## <a name="configuration"></a><span data-ttu-id="512b6-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="512b6-113">Configuration</span></span>

1. <span data-ttu-id="512b6-114">Nos insights de público-alvo, vá para **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="512b6-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="512b6-115">Selecione **Enriquecer meus dados** no bloco da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="512b6-115">Select **Enrich my data** on the Leadspace tile.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de tela do bloco da Leadspace.":::

1. <span data-ttu-id="512b6-117">Selecione **Introdução** e digite um **token da Leadspace** ativo (chave perpétua).</span><span class="sxs-lookup"><span data-stu-id="512b6-117">Select **Get Started** and then enter an active **Leadspace token** (perpetual key).</span></span> <span data-ttu-id="512b6-118">Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="512b6-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="512b6-119">Confirme as duas entradas selecionando **Conectar-se à Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="512b6-119">Confirm both inputs by selecting **Connect to Leadspace**.</span></span>

1. <span data-ttu-id="512b6-120">Selecione **Dados do mapa** e defina quais campos de seus perfis unificados devem ser usados para procurar dados da empresa correspondentes na Leadspace.</span><span class="sxs-lookup"><span data-stu-id="512b6-120">Select **Map data** and define which fields from your unified profiles should be used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="512b6-121">O campo **Nome da empresa** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="512b6-121">The **Name of company** field is required.</span></span> <span data-ttu-id="512b6-122">Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Site da empresa** e **Local da empresa**.</span><span class="sxs-lookup"><span data-stu-id="512b6-122">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo da Leadspace.":::
   
1. <span data-ttu-id="512b6-124">Selecione **Aplicar** para completar o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="512b6-124">Select **Apply** to complete the field mapping.</span></span>

1. <span data-ttu-id="512b6-125">Selecione **Executar** para enriquecer os perfis da empresa.</span><span class="sxs-lookup"><span data-stu-id="512b6-125">Select **Run** to enrich the company profiles.</span></span> <span data-ttu-id="512b6-126">O tempo de duração de um enriquecimento depende do número de perfis de clientes unificados.</span><span class="sxs-lookup"><span data-stu-id="512b6-126">How long an enrichment takes depends on the number of unified customer profiles.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="512b6-127">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="512b6-127">Enrichment results</span></span>

<span data-ttu-id="512b6-128">Depois de atualizar o enriquecimento, você pode revisar os dados da empresa recém-enriquecidos em [Meus enriquecimentos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="512b6-128">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="512b6-129">Você pode encontrar o horário da última atualização e o número de perfis aprimorados.</span><span class="sxs-lookup"><span data-stu-id="512b6-129">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="512b6-130">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="512b6-130">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="512b6-131">Para obter mais informações, consulte [APIs da Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="512b6-131">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="512b6-132">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="512b6-132">Next steps</span></span>

<span data-ttu-id="512b6-133">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="512b6-133">Build on top of your enriched customer data.</span></span> <span data-ttu-id="512b6-134">Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="512b6-134">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="512b6-135">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="512b6-135">Data privacy and compliance</span></span>

<span data-ttu-id="512b6-136">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Leadspace, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="512b6-136">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="512b6-137">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Leadspace cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="512b6-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="512b6-138">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="512b6-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="512b6-139">Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="512b6-139">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>