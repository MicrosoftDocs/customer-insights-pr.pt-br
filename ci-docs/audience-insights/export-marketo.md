---
title: Exportar dados do Customer Insights para o Marketo
description: Saiba como configurar a conexão com o Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570389"
---
# <a name="connector-for-marketo-preview"></a><span data-ttu-id="2a463-103">Conector para Marketo (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="2a463-103">Connector for Marketo (preview)</span></span>

<span data-ttu-id="2a463-104">Exporte segmentos de perfis de clientes unificados para gerar campanhas, fornecer marketing por email e usar grupos específicos de clientes com o Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a463-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2a463-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="2a463-105">Prerequisites</span></span>

-   <span data-ttu-id="2a463-106">Você deve ter uma [conta do Marketo](https://login.marketo.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="2a463-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2a463-107">Há listas existentes no Marketo e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="2a463-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="2a463-108">Para obter mais informações, consulte [listas do Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="2a463-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="2a463-109">Você deve ter [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="2a463-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="2a463-110">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="2a463-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-marketo"></a><span data-ttu-id="2a463-111">Conectar-se ao Marketo</span><span class="sxs-lookup"><span data-stu-id="2a463-111">Connect to Marketo</span></span>

1. <span data-ttu-id="2a463-112">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="2a463-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="2a463-113">Em **Marketo**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="2a463-113">Under **Marketo**, select **Set up**.</span></span>

1. <span data-ttu-id="2a463-114">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="2a463-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="2a463-115">Insira **[ID de cliente do Marketo, Segredo do cliente e Nome de Host do Ponto de Extremidade REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="2a463-115">Enter your **[Marketo client ID, Client secret and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="2a463-116">Insira sua **[ID de lista do Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="2a463-116">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="2a463-117">Selecione **Aceito** para confirmar a **Conformidade e privacidade dos dados** e selecione **Conectar** para inicializar a conexão com o Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a463-117">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="2a463-118">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2a463-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Captura de tela de exportação da conexão com o Marketo":::

1. <span data-ttu-id="2a463-120">Selecione **Próximo** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="2a463-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="2a463-121">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="2a463-121">Configure the connector</span></span>

1. <span data-ttu-id="2a463-122">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="2a463-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="2a463-123">Opcionalmente, você pode exportar **Nome**, **Sobrenome**, **Cidade**, **Estado** e **País/Região** como campos adicionais para criar emails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="2a463-123">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  as additional fields to create more personalized emails.</span></span> <span data-ttu-id="2a463-124">Selecione **Adicionar atributo** para mapear esses campos.</span><span class="sxs-lookup"><span data-stu-id="2a463-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="2a463-125">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="2a463-125">Select the segments you want to export.</span></span> <span data-ttu-id="2a463-126">Você pode exportar até 1 milhão de perfis de clientes no total para o Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a463-126">You can export up to 1 million customer profiles in total to Marketo.</span></span>

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Selecionar campos e segmentos para exportar para o Marketo":::

1. <span data-ttu-id="2a463-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2a463-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="2a463-129">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="2a463-129">Export the data</span></span>

<span data-ttu-id="2a463-130">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="2a463-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="2a463-131">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2a463-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2a463-132">No Marketo, agora você pode encontrar seus segmentos em [listas do Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="2a463-132">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2a463-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="2a463-133">Known limitations</span></span>

- <span data-ttu-id="2a463-134">Até 1 milhão de perfis por exportação para o Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a463-134">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="2a463-135">A exportação para o Marketo é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="2a463-135">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="2a463-136">A exportação de segmentos com um total de 1 milhão de perfis pode levar até 3 horas.</span><span class="sxs-lookup"><span data-stu-id="2a463-136">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="2a463-137">O número de perfis que você pode exportar para o Marketo depende e está limitado ao seu contrato com o Marketo.</span><span class="sxs-lookup"><span data-stu-id="2a463-137">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2a463-138">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="2a463-138">Data privacy and compliance</span></span>

<span data-ttu-id="2a463-139">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Marketo, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="2a463-139">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2a463-140">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Marketo cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="2a463-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2a463-141">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2a463-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="2a463-142">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2a463-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
