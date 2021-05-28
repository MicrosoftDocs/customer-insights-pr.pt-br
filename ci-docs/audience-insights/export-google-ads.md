---
title: Exportar dados do Customer Insights para o Google Ads
description: Saiba como configurar a conexão e exportar para o Google Ads.
ms.date: 03/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 73f3257a3ae6e8423f45410546535df5e3b400ce
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976304"
---
# <a name="export-segments-to-google-ads-preview"></a><span data-ttu-id="f81e6-103">Exportar segmentos para o Google Ads (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="f81e6-103">Export segments to Google Ads (preview)</span></span>

<span data-ttu-id="f81e6-104">Exporte segmentos de perfis de clientes unificados para a lista de públicos-alvo do Google Ads e use-os para anunciar na Pesquisa do Google, no Gmail, no YouTube e na Rede de Display do Google.</span><span class="sxs-lookup"><span data-stu-id="f81e6-104">Export segments of unified customer profiles to Google Ads audience list and use them to advertise on Google Search, Gmail, YouTube, and Google Display Network.</span></span> 

## <a name="prerequisites-for-connection"></a><span data-ttu-id="f81e6-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="f81e6-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="f81e6-106">Você deve ter uma [conta do Google Ads](https://ads.google.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="f81e6-106">You have a [Google Ads account](https://ads.google.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="f81e6-107">Você deve ter um [token de Desenvolvedor do Google Ads aprovado](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span><span class="sxs-lookup"><span data-stu-id="f81e6-107">You have an [approved Google Ads Developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)</span></span> 
-   <span data-ttu-id="f81e6-108">Você deve atender aos requisitos da [Política de Correspondência de Clientes](https://support.google.com/adspolicy/answer/6299717)</span><span class="sxs-lookup"><span data-stu-id="f81e6-108">You fulfill the requirements of the [Customer Match Policy](https://support.google.com/adspolicy/answer/6299717)</span></span>
-   <span data-ttu-id="f81e6-109">Você deve atender aos requisitos dos [tamanhos de listas de remarketing](https://support.google.com/google-ads/answer/7558048)</span><span class="sxs-lookup"><span data-stu-id="f81e6-109">You fulfill the requirements of the [remarketing list sizes](https://support.google.com/google-ads/answer/7558048)</span></span> 

-   <span data-ttu-id="f81e6-110">Há públicos-alvo existentes no Google Ads e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="f81e6-110">There are existing audiences in Google Ads and the corresponding IDs.</span></span> <span data-ttu-id="f81e6-111">Para obter mais informações, consulte [públicos-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span><span class="sxs-lookup"><span data-stu-id="f81e6-111">For more information, see [Google Ads audiences](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.).</span></span>
-   <span data-ttu-id="f81e6-112">Você deve ter [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="f81e6-112">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="f81e6-113">Os perfis de clientes unificados nos segmentos exportados contêm campos que representam endereço de email, nome e sobrenome</span><span class="sxs-lookup"><span data-stu-id="f81e6-113">Unified customer profiles in the exported segments contain fields representing an email address, first name, and last name</span></span>

## <a name="known-limitations"></a><span data-ttu-id="f81e6-114">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="f81e6-114">Known limitations</span></span>

- <span data-ttu-id="f81e6-115">Até 1 milhão de perfis por exportação para o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f81e6-115">Up to 1 million profiles per export to Google Ads.</span></span>
- <span data-ttu-id="f81e6-116">A exportação para o Google Ads é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="f81e6-116">Exporting to Google Ads is limited to segments.</span></span>
- <span data-ttu-id="f81e6-117">A exportação de segmentos com um total de 1 milhão de perfis pode levar até 5 minutos devido a limitações do provedor.</span><span class="sxs-lookup"><span data-stu-id="f81e6-117">Exporting segments with a total of 1 million profiles can take up to 5 minutes because of limitations on the provider side.</span></span> 
- <span data-ttu-id="f81e6-118">A correspondência no Google Ads pode levar até 48 horas.</span><span class="sxs-lookup"><span data-stu-id="f81e6-118">The matching in Google Ads can take up to 48 hours.</span></span>

## <a name="set-up-connection-to-google-ads"></a><span data-ttu-id="f81e6-119">Configurar conexão com o Google Ads</span><span class="sxs-lookup"><span data-stu-id="f81e6-119">Set up connection to Google Ads</span></span>

1. <span data-ttu-id="f81e6-120">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="f81e6-120">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="f81e6-121">Selecione **Adicionar conexão** e escolha **Google Ads** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="f81e6-121">Select **Add connection** and choose **Google Ads** to configure the connection.</span></span>

1. <span data-ttu-id="f81e6-122">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="f81e6-122">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="f81e6-123">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="f81e6-123">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="f81e6-124">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="f81e6-124">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="f81e6-125">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="f81e6-125">Choose who can use this connection.</span></span> <span data-ttu-id="f81e6-126">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="f81e6-126">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="f81e6-127">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="f81e6-127">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="f81e6-128">Insira sua **[ID de cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)**.</span><span class="sxs-lookup"><span data-stu-id="f81e6-128">Enter your **[Google Ads customer ID](https://support.google.com/google-ads/answer/1704344)**.</span></span>

1. <span data-ttu-id="f81e6-129">Insira seu **[token de desenvolvedor aprovado do Google Ads](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span><span class="sxs-lookup"><span data-stu-id="f81e6-129">Enter your **[Google Ads approved developer token](https://developers.google.com/google-ads/api/docs/first-call/dev-token)**.</span></span>

1. <span data-ttu-id="f81e6-130">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="f81e6-130">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="f81e6-131">Selecione **Autenticar com o Google Ads** e forneça suas credenciais do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f81e6-131">Select **Authenticate with Google Ads** and provide your Google Ads credentials.</span></span>

1. <span data-ttu-id="f81e6-132">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="f81e6-132">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="f81e6-133">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="f81e6-133">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="f81e6-134">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="f81e6-134">Configure an export</span></span>

<span data-ttu-id="f81e6-135">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="f81e6-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="f81e6-136">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="f81e6-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="f81e6-137">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="f81e6-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="f81e6-138">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="f81e6-138">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="f81e6-139">No campo **Conexão para exportação**, escolha uma conexão da seção do Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f81e6-139">In the **Connection for export** field, choose a connection from the Google Ads section.</span></span> <span data-ttu-id="f81e6-140">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="f81e6-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="f81e6-141">Insira sua **[ID de público-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** e selecione **Conectar** para inicializar a conexão com o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f81e6-141">Enter your **[Google Ads audience ID](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns.)** and select **Connect** to initialize the connection to Google Ads.</span></span>

1. <span data-ttu-id="f81e6-142">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="f81e6-142">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="f81e6-143">Repita as mesmas etapas para os campos **Nome** e **Sobrenome**.</span><span class="sxs-lookup"><span data-stu-id="f81e6-143">Repeat the same steps for \*\*First name" and **Last name** fields.</span></span>

1. <span data-ttu-id="f81e6-144">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="f81e6-144">Select the segments you want to export.</span></span> <span data-ttu-id="f81e6-145">Você pode exportar até 1 milhão de perfis de clientes no total para o Google Ads.</span><span class="sxs-lookup"><span data-stu-id="f81e6-145">You can export up to 1 million customer profiles in total to Google Ads.</span></span>

<span data-ttu-id="f81e6-146">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="f81e6-146">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="f81e6-147">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f81e6-147">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="f81e6-148">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="f81e6-148">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f81e6-149">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="f81e6-149">Data privacy and compliance</span></span>

<span data-ttu-id="f81e6-150">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Google Ads, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="f81e6-150">When you enable Dynamics 365 Customer Insights to transmit data to Google Ads, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f81e6-151">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Google Ads cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="f81e6-151">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Google Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="f81e6-152">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f81e6-152">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f81e6-153">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f81e6-153">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
