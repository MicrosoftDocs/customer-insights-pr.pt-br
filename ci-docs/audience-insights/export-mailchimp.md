---
title: Exportar dados do Customer Insights para o Mailchimp
description: Saiba como configurar a conexão com o Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 2b465b32fa956e3f45a23f471dc3a3183def16ef
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267159"
---
# <a name="connector-for-mailchimp-preview"></a><span data-ttu-id="8d2a1-103">Conector para Mailchimp (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="8d2a1-103">Connector for Mailchimp (preview)</span></span>

<span data-ttu-id="8d2a1-104">Exporte segmentos de perfis de clientes unificados para o Mailchimp a fim de criar boletins informativos e campanhas por email.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="8d2a1-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="8d2a1-105">Prerequisites</span></span>

-   <span data-ttu-id="8d2a1-106">Você deve ter uma [conta do Mailchimp](https://mailchimp.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="8d2a1-107">Há públicos-alvo existentes no Mailchimp e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="8d2a1-108">Para obter mais informações, consulte [públicos-alvo do Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="8d2a1-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="8d2a1-109">Você deve ter [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="8d2a1-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="8d2a1-110">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-mailchimp"></a><span data-ttu-id="8d2a1-111">Conectar ao Mailchimp</span><span class="sxs-lookup"><span data-stu-id="8d2a1-111">Connect to Mailchimp</span></span>

1. <span data-ttu-id="8d2a1-112">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="8d2a1-113">Em **Mailchimp**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-113">Under **Mailchimp**, select **Set up**.</span></span>

1. <span data-ttu-id="8d2a1-114">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="8d2a1-115">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="8d2a1-116">Insira sua **[ID de público-alvo do Mailchimp](https://mailchimp.com/help/find-audience-id/)** e selecione **Conectar** para inicializar a conexão com o Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-116">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)** and select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="8d2a1-117">Selecione **Autenticar com o Mailchimp** e forneça suas credenciais do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-117">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="8d2a1-118">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-118">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Captura de tela de exportação da conexão com o Mailchimp":::

1. <span data-ttu-id="8d2a1-120">Selecione **Próximo** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-120">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="8d2a1-121">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="8d2a1-121">Configure the connector</span></span>

1. <span data-ttu-id="8d2a1-122">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-122">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="8d2a1-123">Opcionalmente, você pode exportar **Nome** e **Sobrenome** como campos adicionais para criar emails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-123">Optionally, you can export **First name** and **Last name** as additional fields to create more personalized emails.</span></span> <span data-ttu-id="8d2a1-124">Selecione **Adicionar atributo** para mapear esses campos.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-124">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="8d2a1-125">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-125">Select the segments you want to export.</span></span> <span data-ttu-id="8d2a1-126">Você pode exportar até 1 milhão de perfis de clientes no total para o Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-126">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selecionar campos e segmentos para exportar para o Mailchimp":::

1. <span data-ttu-id="8d2a1-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="8d2a1-129">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="8d2a1-129">Export the data</span></span>

<span data-ttu-id="8d2a1-130">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="8d2a1-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="8d2a1-131">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="8d2a1-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="8d2a1-132">No Mailchimp, agora você pode encontrar seus segmentos em [públicos-alvo do Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="8d2a1-132">In Mailchimp, you can now find your segments under [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="8d2a1-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="8d2a1-133">Known limitations</span></span>

- <span data-ttu-id="8d2a1-134">Até 1 milhão de perfis por exportação para o Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-134">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="8d2a1-135">A exportação para o Mailchimp é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-135">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="8d2a1-136">A exportação de segmentos com um total de 1 milhão de perfis pode levar até três horas devido a limitações do provedor.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-136">Exporting segments with a total of 1 million profiles can take up to three hours due to limitations on the provider side.</span></span> 
- <span data-ttu-id="8d2a1-137">O número de perfis que você pode exportar para o Mailchimp depende e está limitado ao seu contrato com o Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-137">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="8d2a1-138">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="8d2a1-138">Data privacy and compliance</span></span>

<span data-ttu-id="8d2a1-139">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Mailchimp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-139">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="8d2a1-140">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Mailchimp cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="8d2a1-141">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="8d2a1-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="8d2a1-142">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="8d2a1-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]