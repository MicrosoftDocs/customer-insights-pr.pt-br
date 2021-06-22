---
title: Exportar dados do Customer Insights para o LinkedIn Ads
description: Saiba como configurar a conexão e exportar para o LinkedIn Ads.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1c7b0c728bc4d4cf6b5aea79396cf0779fbf298d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124452"
---
# <a name="export-segments-to-linkedin-ads-preview"></a><span data-ttu-id="ade0f-103">Exportar segmentos para o LinkedIn Ads (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="ade0f-103">Export segments to LinkedIn Ads (preview)</span></span>

<span data-ttu-id="ade0f-104">Exporte segmentos de perfis de clientes unificados para o LinkedIn Ads para criar públicos-alvo correspondentes.</span><span class="sxs-lookup"><span data-stu-id="ade0f-104">Export segments of unified customer profiles to LinkedIn Ads to create matched audiences.</span></span> <span data-ttu-id="ade0f-105">Use os públicos-alvo correspondentes para a segmentação de empresas e a segmentação de contatos.</span><span class="sxs-lookup"><span data-stu-id="ade0f-105">Use the matched audiences for company targeting and contact targeting.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ade0f-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ade0f-106">Prerequisites</span></span>

-   <span data-ttu-id="ade0f-107">Você deve ter uma [conta do LinkedIn Campaign Manager](https://business.linkedin.com/marketing-solutions/ads) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="ade0f-107">You have an [LinkedIn Campaign Manager account](https://business.linkedin.com/marketing-solutions/ads) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ade0f-108">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="ade0f-108">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ade0f-109">Os perfis de cliente nos segmentos exportados contêm um campo com um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="ade0f-109">Customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ade0f-110">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="ade0f-110">Known limitations</span></span>

- <span data-ttu-id="ade0f-111">Você pode exportar até 100.000 perfis por vez para o LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="ade0f-111">You can export up to 100K profiles per export to LinkedIn Ads.</span></span>
- <span data-ttu-id="ade0f-112">A exportação para o LinkedIn Ads está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="ade0f-112">Exporting to LinkedIn Ads is limited to segments.</span></span>
- <span data-ttu-id="ade0f-113">Exportar até 100.000 perfis para o LinkedIn Ads pode levar até 10 minutos para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="ade0f-113">Exporting up to 100K profiles to LinkedIn Ads can take up to 10 minutes to complete.</span></span> 

## <a name="set-up-the-connection-to-linkedin-ads"></a><span data-ttu-id="ade0f-114">Configurar a conexão ao LinkedIn Ads</span><span class="sxs-lookup"><span data-stu-id="ade0f-114">Set up the connection to LinkedIn Ads</span></span>

1. <span data-ttu-id="ade0f-115">Em insights do público-alvo, acesse **Administrador** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="ade0f-115">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ade0f-116">Selecione **Adicionar conexão** e escolha **LinkedIn Ads** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="ade0f-116">Select **Add connection** and choose **LinkedIn Ads** to configure the connection.</span></span>

1. <span data-ttu-id="ade0f-117">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="ade0f-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ade0f-118">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="ade0f-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ade0f-119">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="ade0f-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ade0f-120">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="ade0f-120">Choose who can use this connection.</span></span> <span data-ttu-id="ade0f-121">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="ade0f-121">If you take no action, the default is administrators.</span></span> <span data-ttu-id="ade0f-122">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ade0f-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ade0f-123">Forneça sua [ID da conta do LinkedIn Campaign Manager](https://www.linkedin.com/help/lms/answer/a424270).</span><span class="sxs-lookup"><span data-stu-id="ade0f-123">Provide your [LinkedIn Campaign Manager Account ID](https://www.linkedin.com/help/lms/answer/a424270).</span></span>

1. <span data-ttu-id="ade0f-124">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="ade0f-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ade0f-125">Selecione **Conectar** para inicializar a conexão com o Monitor de Campanha.</span><span class="sxs-lookup"><span data-stu-id="ade0f-125">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="ade0f-126">Selecione **Autenticar com o LinkedIn** e forneça suas credenciais de administrador do LinkedIn Campaign Manager.</span><span class="sxs-lookup"><span data-stu-id="ade0f-126">Select **Authenticate with LinkedIn** and provide your admin credentials for LinkedIn Campaign Manager.</span></span>

1. <span data-ttu-id="ade0f-127">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ade0f-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ade0f-128">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="ade0f-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ade0f-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="ade0f-129">Configure an export</span></span>

<span data-ttu-id="ade0f-130">Você poderá configurar uma exportação se tiver acesso a uma conexão desse tipo.</span><span class="sxs-lookup"><span data-stu-id="ade0f-130">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="ade0f-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ade0f-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ade0f-132">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ade0f-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ade0f-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="ade0f-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ade0f-134">No campo **Conexão para exportação**, escolha uma conexão da seção do LinkedIn Ads.</span><span class="sxs-lookup"><span data-stu-id="ade0f-134">In the **Connection for export** field, choose a connection from the LinkedIn Ads section.</span></span> <span data-ttu-id="ade0f-135">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="ade0f-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ade0f-136">Escolha se deseja exportar dados para fazer a [segmentação de contatos](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) ou a [segmentação de empresas](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) no LinkedIn.</span><span class="sxs-lookup"><span data-stu-id="ade0f-136">Choose whether you want to export data to do [contact targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) or [company targeting](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting) on LinkedIn.</span></span> 

1. <span data-ttu-id="ade0f-137">Na seção **Correspondência de dados**, selecione o campo em seu perfil de cliente unificado que represente o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="ade0f-137">In the **Data matching** section, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ade0f-138">A exportação de segmentos para o LinkedIn Ads é necessária.</span><span class="sxs-lookup"><span data-stu-id="ade0f-138">It's required to export segments to LinkedIn Ads.</span></span>

1. <span data-ttu-id="ade0f-139">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="ade0f-139">Select the segments you want to export.</span></span> <span data-ttu-id="ade0f-140">Os públicos-alvo correspondentes no LinkedIn Campaign Manager serão criados automaticamente com o nome dos segmentos que você selecionou para exportação.</span><span class="sxs-lookup"><span data-stu-id="ade0f-140">The matched audiences in LinkedIn Campaign Manager will automatically be created with the name of the segments that you selected to export.</span></span> <span data-ttu-id="ade0f-141">Cada segmento resultará em um público-alvo correspondente separado.</span><span class="sxs-lookup"><span data-stu-id="ade0f-141">Each segment will result in a separate matched audience.</span></span> 

1. <span data-ttu-id="ade0f-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ade0f-142">Select **Save**.</span></span>

<span data-ttu-id="ade0f-143">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="ade0f-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ade0f-144">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ade0f-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ade0f-145">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ade0f-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ade0f-146">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="ade0f-146">Data privacy and compliance</span></span>

<span data-ttu-id="ade0f-147">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o LinkedIn Ads, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados que podem ser confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="ade0f-147">When you enable Dynamics 365 Customer Insights to transmit data to LinkedIn Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ade0f-148">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o LinkedIn Ads atenda a todas as obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="ade0f-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that LinkedIn Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="ade0f-149">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ade0f-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ade0f-150">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ade0f-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop the use of this functionality.</span></span>
