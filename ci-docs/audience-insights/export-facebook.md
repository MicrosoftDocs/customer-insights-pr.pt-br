---
title: Exportar dados do Customer Insights para o Gerenciador de Anúncios do Facebook
description: Saiba como configurar a conexão e exportar para o Gerenciador de Anúncios do Facebook.
ms.date: 04/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ca32906a98bc734639fb369d6f5a92e8888fd850
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906796"
---
# <a name="export-segments-list-to-facebook-ads-manager-preview"></a><span data-ttu-id="0c8c0-103">Exportar lista de segmentos para o Gerenciador de Anúncios do Facebook (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="0c8c0-103">Export segments list to Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="0c8c0-104">Exporte segmentos de perfis unificados de clientes para o Gerenciador de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0c8c0-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="0c8c0-105">Prerequisites for connection</span></span>

- <span data-ttu-id="0c8c0-106">Você deve ter uma [**Conta de Anúncios do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclua uma [**Conta de Negócios do Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="0c8c0-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) that includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="0c8c0-107">Você deve ser um administrador na [**Conta de Anúncios do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="0c8c0-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0c8c0-108">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="0c8c0-108">Known limitations</span></span>

- <span data-ttu-id="0c8c0-109">Até 10 milhões de perfis de clientes por exportação para o Gerenciador de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-109">Up to 10 million customer profile per export to Facebook Ads Manager.</span></span>
- <span data-ttu-id="0c8c0-110">A exportação para o Gerenciador de Anúncios do Facebook é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-110">Export to Facebook Ads Manager is limited to segments.</span></span>
- <span data-ttu-id="0c8c0-111">Crie ou atualize públicos personalizados no Facebook do tipo *lista de clientes* apenas.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-111">Create or update custom audiences in Facebook of type *customer list* only.</span></span>
- <span data-ttu-id="0c8c0-112">A exportação de segmentos com um total de 10 milhões de perfis pode levar até 90 minutos para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-112">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete.</span></span>

## <a name="set-up-connection-to-facebook-ads-manager"></a><span data-ttu-id="0c8c0-113">Configurar conexão com o Gerenciador de Anúncios do Facebook</span><span class="sxs-lookup"><span data-stu-id="0c8c0-113">Set up connection to Facebook Ads Manager</span></span>

<span data-ttu-id="0c8c0-114">Para que os usuários possam criar uma exportação, um administrador deve configurar a conexão com o serviço e permitir que os colaboradores usem essa conexão.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-114">Before users can create an export, an administrator must configure the connection to the service and allow contributors to use the connection.</span></span>

1. <span data-ttu-id="0c8c0-115">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0c8c0-116">Selecione **Adicionar conexão** e escolha **Gerenciador de Anúncios do Facebook** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-116">Select **Add connection** and choose **Facebook Ads Manager** to configure the connection.</span></span>

1. <span data-ttu-id="0c8c0-117">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0c8c0-118">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0c8c0-119">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0c8c0-120">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-120">Choose who can use this connection.</span></span> <span data-ttu-id="0c8c0-121">Se você não fizer nada, o padrão será **Administradores**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-121">If you take no action, the default will be **Administrators**.</span></span> <span data-ttu-id="0c8c0-122">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0c8c0-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0c8c0-123">Autenticar com Anúncios do Facebook:</span><span class="sxs-lookup"><span data-stu-id="0c8c0-123">Authenticate with Facebook Ads:</span></span> 

   1. <span data-ttu-id="0c8c0-124">Selecione **Continue com Facebook** para fazer login na sua Conta de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-124">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

   1. <span data-ttu-id="0c8c0-125">Conceda permissão a **ads_management** depois de autenticar com o Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-125">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

   1. <span data-ttu-id="0c8c0-126">Selecione a Conta de Anúncios do **Facebook** na qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-126">Select the **Facebook Ads Account** that you want to work with.</span></span>

   1. <span data-ttu-id="0c8c0-127">Selecione um **Público-alvo personalizado existente** na lista suspensa ou crie um **Novo público-alvo personalizado**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-127">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="0c8c0-128">Para obter mais informações, consulte [**Público no Gerenciador de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="0c8c0-128">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>
      > [!NOTE]
      > <span data-ttu-id="0c8c0-129">Você só pode criar ou atualizar públicos personalizados no Facebook do tipo *lista de clientes* com esta exportação.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-129">You can only create or update custom audiences on Facebook of the type *customer list* with this export.</span></span> <span data-ttu-id="0c8c0-130">Em alguns casos, você vê públicos personalizados de diferentes tipos na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-130">In some cases, you see custom audiences of different types in the drop-down list.</span></span> <span data-ttu-id="0c8c0-131">A seleção de um tipo diferente de *lista de clientes* resultará em uma exportação com falha.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-131">Selecting a different type than *customer list* will result in a failing export.</span></span> 

1. <span data-ttu-id="0c8c0-132">Examine a **Conformidade e privacidade dos dados** e selecione **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-132">Review the **Data privacy and compliance** and select **I agree**.</span></span>

1. <span data-ttu-id="0c8c0-133">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-133">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0c8c0-134">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="0c8c0-134">Configure an export</span></span>

<span data-ttu-id="0c8c0-135">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-135">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0c8c0-136">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0c8c0-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0c8c0-137">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-137">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0c8c0-138">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-138">To create a new export, select **Add destination**.</span></span> 

1. <span data-ttu-id="0c8c0-139">Em **Conexão para exportação**, escolha uma conexão da seção do **Gerenciador de Anúncios do Facebook**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-139">In **Connection for export** choose a connection from the **Facebook Ads Manager** section.</span></span> <span data-ttu-id="0c8c0-140">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-140">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0c8c0-141">No campo **Escolher identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar para o Gerenciador de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-141">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span> 

1. <span data-ttu-id="0c8c0-142">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-142">Give your connection a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="0c8c0-143">Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-143">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="0c8c0-144">[DICA] As melhores chances de correspondência ocorrem se você selecionar **E-mail** como o identificador.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-144">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="0c8c0-145">Adicionar identificadores adicionais pode melhorar a correspondência.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-145">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="0c8c0-146">Selecione **Adicionar atributo** para mapear mais atributos para enviar para o Gerenciador de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-146">Select **Add attribute** to map more attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="0c8c0-147">Os atributos do Gerenciador de Anúncios do Facebook estão sendo mapeados para os seguintes nomes fáceis de usar: **FN** = **Nome**, **LN** = **Sobrenome**, **FI** = **Primeira Inicial**, **PHONE** = **Telefone**, **GEN** = **Gênero**, **DOB** = **Data de Nascimento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal/CEP**, **COUNTRY** = **País/Região**</span><span class="sxs-lookup"><span data-stu-id="0c8c0-147">Attributes from Facebook Ads Manager are mapping to the following user-friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="0c8c0-148">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-148">Select the segments you want to export.</span></span>

1. <span data-ttu-id="0c8c0-149">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-149">Select **Save**.</span></span>

<span data-ttu-id="0c8c0-150">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-150">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0c8c0-151">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0c8c0-151">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0c8c0-152">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0c8c0-152">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0c8c0-153">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="0c8c0-153">Data privacy and compliance</span></span>

<span data-ttu-id="0c8c0-154">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Gerenciador de Anúncios do Facebook, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-154">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0c8c0-155">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Gerenciador de Anúncios do Facebook cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-155">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="0c8c0-156">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0c8c0-156">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0c8c0-157">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="0c8c0-157">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
