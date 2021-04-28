---
title: Enriquecimento de perfis de empresa com a Leadspace de enriquecimento de terceiros
description: Informações gerais sobre o enriquecimento de terceiros da Leadspace.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ccf4f661ecffb281556a4545b1f26ee809c697cd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895899"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a><span data-ttu-id="4042e-103">Enriquecimento de perfis de empresa com a Leadspace (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="4042e-103">Enrichment of company profiles with Leadspace (preview)</span></span>

<span data-ttu-id="4042e-104">Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B.</span><span class="sxs-lookup"><span data-stu-id="4042e-104">Leadspace is a data science company that provides a B2B Customer Data Platform.</span></span> <span data-ttu-id="4042e-105">Ela permite que os clientes com perfis de cliente unificados para as empresas possam enriquecer seus dados.</span><span class="sxs-lookup"><span data-stu-id="4042e-105">It enables customers with unified customer profiles for companies to enrich their data.</span></span> <span data-ttu-id="4042e-106">Os enriquecimentos incluem mais atributos, como tamanho da empresa, local, setor e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4042e-106">Enrichments include more attributes such as company size, location, industry, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="4042e-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="4042e-107">Prerequisites</span></span>

<span data-ttu-id="4042e-108">Para configurar a Leadspace, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="4042e-108">To configure Leadspace, the following prerequisites must be met:</span></span>

- <span data-ttu-id="4042e-109">Você ter uma licença da Leadspace ativa.</span><span class="sxs-lookup"><span data-stu-id="4042e-109">You have an active Leadspace license.</span></span>
- <span data-ttu-id="4042e-110">Você ter [perfis unificados de clientes](customer-profiles.md) para empresas.</span><span class="sxs-lookup"><span data-stu-id="4042e-110">You have [unified customer profiles](customer-profiles.md) for companies.</span></span>
- <span data-ttu-id="4042e-111">Uma conexão da Leadspace já ter sido configurada por um administrador ou você ter permissões de [administrador](permissions.md#administrator) e a "chave perpétua" (chamada de **token da Leadspace**).</span><span class="sxs-lookup"><span data-stu-id="4042e-111">A Leadspace connection has already been configured by an administrator or you have [administrator](permissions.md#administrator) permissions and the “perpetual key” (referred to as **Leadspace token**).</span></span> <span data-ttu-id="4042e-112">Contate a [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) diretamente para obter detalhes sobre seu produto.</span><span class="sxs-lookup"><span data-stu-id="4042e-112">Contact [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) directly for details about their product.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="4042e-113">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="4042e-113">Configure the enrichment</span></span>

1. <span data-ttu-id="4042e-114">Nos insights de público-alvo, vá para **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="4042e-114">In audience insights, go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="4042e-115">Selecione **Enriquecer meus dados** no bloco da Leadspace e selecione **Começar agora**.</span><span class="sxs-lookup"><span data-stu-id="4042e-115">Select **Enrich my data** on the Leadspace tile and select **Get started**.</span></span>

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de tela do bloco da Leadspace.":::

1. <span data-ttu-id="4042e-117">Selecione uma [conexão](connections.md) na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="4042e-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="4042e-118">Contate um administrador se nenhuma conexão estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="4042e-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="4042e-119">Se for administrador, você poderá criar uma conexão selecionando **Adicionar conexão** e escolhendo **Leadspace**.</span><span class="sxs-lookup"><span data-stu-id="4042e-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **Leadspace**.</span></span> 

1. <span data-ttu-id="4042e-120">Selecione **Conectar-se à Leadspace** para confirmar a conexão.</span><span class="sxs-lookup"><span data-stu-id="4042e-120">Select **Connect to Leadspace** to confirm the connection.</span></span>

1. <span data-ttu-id="4042e-121">Selecione **Avançar** e escolha o **Conjunto de dados do cliente** que você deseja enriquecer com os dados de empresas da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="4042e-121">Select **Next** and choose the **Customer data set** you want to enrich with company data from Leadspace.</span></span> <span data-ttu-id="4042e-122">Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="4042e-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. <span data-ttu-id="4042e-124">Selecione **Avançar** e defina quais tipos de campos de seus perfis unificados serão usados para procurar dados de empresas correspondentes da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="4042e-124">Select **Next** and define which fields from your unified profiles are used to look for matching company data from Leadspace.</span></span> <span data-ttu-id="4042e-125">O campo **Nome da empresa** é obrigatório.</span><span class="sxs-lookup"><span data-stu-id="4042e-125">The **Name of company** field is required.</span></span> <span data-ttu-id="4042e-126">Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Site da empresa** e **Local da empresa**.</span><span class="sxs-lookup"><span data-stu-id="4042e-126">For a higher match accuracy, up to two other fields, **Company website** and **Company location**, can be added.</span></span>

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo da Leadspace.":::

1. <span data-ttu-id="4042e-128">Selecione **Avançar** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="4042e-128">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="4042e-129">Forneça um nome para o enriquecimento e selecione **Salvar enriquecimento** depois de revisar suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="4042e-129">Provide a name for the enrichment and select **Save enrichment** after reviewing your choices.</span></span>


## <a name="configure-the-connection-for-leadspace"></a><span data-ttu-id="4042e-130">Configurar a conexão para a Leadspace</span><span class="sxs-lookup"><span data-stu-id="4042e-130">Configure the connection for Leadspace</span></span> 

<span data-ttu-id="4042e-131">Você deve ser um administrador para configurar as conexões.</span><span class="sxs-lookup"><span data-stu-id="4042e-131">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="4042e-132">Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da Leadspace.</span><span class="sxs-lookup"><span data-stu-id="4042e-132">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Leadspace tile.</span></span>

1. <span data-ttu-id="4042e-133">Selecione **Começar**</span><span class="sxs-lookup"><span data-stu-id="4042e-133">Select **Get Started**</span></span> 

1. <span data-ttu-id="4042e-134">Insira um nome para a conexão na caixa **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="4042e-134">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="4042e-135">Forneça um token da Leadspace válido.</span><span class="sxs-lookup"><span data-stu-id="4042e-135">Provide a valid Leadspace token.</span></span>

1. <span data-ttu-id="4042e-136">Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**</span><span class="sxs-lookup"><span data-stu-id="4042e-136">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="4042e-137">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="4042e-137">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="4042e-138">Depois de concluir a verificação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4042e-138">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuração de conexão da Leadspace.":::

## <a name="enrichment-results"></a><span data-ttu-id="4042e-140">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="4042e-140">Enrichment results</span></span>

<span data-ttu-id="4042e-141">Depois de atualizar o enriquecimento, você pode revisar os dados da empresa recém-enriquecidos em [Meus enriquecimentos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="4042e-141">After refreshing the enrichment, you can review the newly enriched company data under [My enrichments](enrichment-hub.md).</span></span> <span data-ttu-id="4042e-142">Você pode encontrar o horário da última atualização e o número de perfis aprimorados.</span><span class="sxs-lookup"><span data-stu-id="4042e-142">You can find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="4042e-143">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="4042e-143">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

<span data-ttu-id="4042e-144">Para obter mais informações, consulte [APIs da Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span><span class="sxs-lookup"><span data-stu-id="4042e-144">For more information, see [Leadspace APIs](https://support.leadspace.com/hc/en-us/sections/201997649-API).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4042e-145">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="4042e-145">Next steps</span></span>

<span data-ttu-id="4042e-146">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="4042e-146">Build on top of your enriched customer data.</span></span> <span data-ttu-id="4042e-147">Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="4042e-147">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4042e-148">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="4042e-148">Data privacy and compliance</span></span>

<span data-ttu-id="4042e-149">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Leadspace, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="4042e-149">When you enable Dynamics 365 Customer Insights to transmit data to Leadspace, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4042e-150">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Leadspace cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="4042e-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Leadspace meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="4042e-151">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4042e-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4042e-152">Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="4042e-152">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
