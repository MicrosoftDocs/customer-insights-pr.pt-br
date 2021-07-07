---
title: Exportar dados do Customer Insights para o Gerenciador de Anúncios do Facebook
description: Saiba como configurar a conexão e exportar para o Gerenciador de Anúncios do Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e20c7b7fd3989d7621cb7765f38b85c8ab4adfcb
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305096"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="b2673-103">Exportar lista de segmentos para o Gerenciador de Anúncios do Facebook (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="b2673-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="b2673-104">Exporte segmentos de perfis unificados de clientes para o Gerenciador de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.</span><span class="sxs-lookup"><span data-stu-id="b2673-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="b2673-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="b2673-105">Prerequisites for connection</span></span>

- <span data-ttu-id="b2673-106">Você precisa ter uma [**Conta do Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclua uma [**Conta de negócios do Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="b2673-106">You need to have a [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="b2673-107">Você precisa ser um administrador na [**Conta do Facebook Ads**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="b2673-107">You need to be an administrator on the [**Facebook Ads Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b2673-108">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="b2673-108">Known limitations</span></span>

- <span data-ttu-id="b2673-109">Até 10 milhão de perfis de cliente por exportação para o Facebook Ads Manager.</span><span class="sxs-lookup"><span data-stu-id="b2673-109">Up to 10 million customer profiles per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="b2673-110">A exportação para o Gerenciador de Anúncios do Facebook é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="b2673-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="b2673-111">Crie ou atualize públicos personalizados no Facebook do tipo *lista de clientes* apenas.</span><span class="sxs-lookup"><span data-stu-id="b2673-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="b2673-112">A exportação de segmentos com um total de 10 milhões de perfis pode levar até 90 minutos para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="b2673-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="b2673-113">Configurar conexão com o Gerenciador de Anúncios do Facebook</span><span class="sxs-lookup"><span data-stu-id="b2673-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="b2673-114">Para que os usuários possam criar uma exportação, um administrador deve configurar a conexão com o serviço e permitir que os colaboradores usem essa conexão.</span><span class="sxs-lookup"><span data-stu-id="b2673-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="b2673-115">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="b2673-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b2673-116">Selecione **Adicionar conexão** e escolha **Gerenciador de Anúncios do Facebook** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="b2673-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="b2673-117">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="b2673-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b2673-118">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="b2673-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b2673-119">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="b2673-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b2673-120">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="b2673-120">Choose who can use this connection.</span></span> <span data-ttu-id="b2673-121">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="b2673-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b2673-122">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b2673-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b2673-123">Autenticar com Anúncios do Facebook:</span><span class="sxs-lookup"><span data-stu-id="b2673-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="b2673-124">Selecione **Continuar com o Facebook** para entrar com sua conta do Facebook Ads.</span><span class="sxs-lookup"><span data-stu-id="b2673-124">Select **Continue with Facebook** to sign in to your Facebook Ads account.</span></span>

   1. <span data-ttu-id="b2673-125">Conceda permissão a **ads_management** depois de autenticar com o Facebook.</span><span class="sxs-lookup"><span data-stu-id="b2673-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="b2673-126">Selecione a Conta de Anúncios do **Facebook** na qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="b2673-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="b2673-127">Selecione um **Público-alvo personalizado existente** na lista suspensa ou crie um **Novo público-alvo personalizado**.</span><span class="sxs-lookup"><span data-stu-id="b2673-127">Select an **Existing custom audience** from the dropdown list or create a **New custom audience**.</span></span> <span data-ttu-id="b2673-128">Para obter mais informações, consulte [**Público no Gerenciador de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="b2673-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="b2673-129">Você só pode criar ou atualizar públicos personalizados no Facebook do tipo *lista de clientes* com esta exportação.</span><span class="sxs-lookup"><span data-stu-id="b2673-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="b2673-130">Em alguns casos, você vê públicos-alvo de diferentes tipos na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b2673-130">In some cases, you see custom audiences of different types in the dropdown list.</span></span> <span data-ttu-id="b2673-131">A seleção de um tipo diferente de *lista de clientes* resultará em uma exportação com falha.</span><span class="sxs-lookup"><span data-stu-id="b2673-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="b2673-132">Examine a **Conformidade e privacidade dos dados** e selecione **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="b2673-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="b2673-133">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="b2673-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b2673-134">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="b2673-134">Configure an export</span></span>

<span data-ttu-id="b2673-135">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="b2673-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b2673-136">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b2673-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b2673-137">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="b2673-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b2673-138">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="b2673-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="b2673-139">Em **Conexão para exportação**, escolha uma conexão da seção do **Gerenciador de Anúncios do Facebook**.</span><span class="sxs-lookup"><span data-stu-id="b2673-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="b2673-140">Se você não vir este nome de seção, significa que não há conexões desse tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="b2673-140">If you don't see this section name, then no connections of this type are available to you.</span></span>

1. <span data-ttu-id="b2673-141">No campo **Escolher identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar para o Gerenciador de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="b2673-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="b2673-142">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="b2673-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="b2673-143">Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="b2673-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > [!TIP]
   > <span data-ttu-id="b2673-144">É mais provável obter uma correspondência se você selecionar **Email** como identificador principal.</span><span class="sxs-lookup"><span data-stu-id="b2673-144">The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="b2673-145">Adicionar identificadores adicionais pode melhorar a correspondência.</span><span class="sxs-lookup"><span data-stu-id="b2673-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="b2673-146">Selecione **Adicionar atributo** para mapear mais atributos para enviar para o Gerenciador de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="b2673-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="b2673-147">Os atributos do Facebook Ads Manager são mapeados para os seguintes nomes amigáveis: **FN** = **Nome**, **LN** = **Sobrenome**, **FI** = **Primeira inicial**, **PHONE** = **Telefone**, **GEN** = **Gênero**, **DOB** = **Data de nascimento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal / CEP**, **COUNTRY** = **País / Região**</span><span class="sxs-lookup"><span data-stu-id="b2673-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / ZIP Code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="b2673-148">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="b2673-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="b2673-149">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b2673-149">Select **Save**.</span></span>

<span data-ttu-id="b2673-150">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b2673-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b2673-151">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b2673-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> 

<span data-ttu-id="b2673-152">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b2673-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b2673-153">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="b2673-153">Data privacy and compliance</span></span>

<span data-ttu-id="b2673-154">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Gerenciador de Anúncios do Facebook, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="b2673-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b2673-155">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Gerenciador de Anúncios do Facebook cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="b2673-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b2673-156">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b2673-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b2673-157">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="b2673-157">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
