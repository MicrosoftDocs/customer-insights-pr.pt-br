---
title: Exportar dados do Customer Insights para o Gerenciador de Anúncios do Facebook
description: Aprenda a configurar a conexão com o Gerenciador de Anúncios do Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269960"
---
# <a name="connector-for-facebook-ads-manager-preview"></a><span data-ttu-id="db343-103">Conector para Gerenciador de Anúncios do Facebook (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="db343-103">Connector for Facebook Ads Manager (preview)</span></span>

<span data-ttu-id="db343-104">Exporte segmentos de perfis unificados de clientes para o Gerenciador de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.</span><span class="sxs-lookup"><span data-stu-id="db343-104">Export segments of unified customer profiles to Facebook Ads Manager to create campaigns on Facebook and Instagram.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db343-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="db343-105">Prerequisites</span></span>

- <span data-ttu-id="db343-106">Você deve ter uma [**Conta de Anúncios do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclui uma [**Conta de Negócios do Facebook**](https://business.facebook.com/).</span><span class="sxs-lookup"><span data-stu-id="db343-106">You need to have a [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) which includes a [**Facebook Business Account**](https://business.facebook.com/).</span></span>
- <span data-ttu-id="db343-107">Você deve ser um administrador na [**Conta de Anúncios do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span><span class="sxs-lookup"><span data-stu-id="db343-107">You need to be an administrator on the [**Facebook Ad Account**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).</span></span>

## <a name="connect-to-facebook-ads-manager"></a><span data-ttu-id="db343-108">Conecte-se ao Gerenciador de Anúncios do Facebook</span><span class="sxs-lookup"><span data-stu-id="db343-108">Connect to Facebook Ads Manager</span></span>

1. <span data-ttu-id="db343-109">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="db343-109">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="db343-110">Em Gerenciador de Anúncios do **Facebook**, selecione **Configuração**.</span><span class="sxs-lookup"><span data-stu-id="db343-110">Under **Facebook Ads Manager**, select **Set up**.</span></span>

1. <span data-ttu-id="db343-111">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="db343-111">Give your export destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="db343-112">Selecione **Continue com Facebook** para fazer login na sua Conta de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="db343-112">Select **Continue with Facebook** to sign in to your Facebook Ad Account.</span></span>

1. <span data-ttu-id="db343-113">Conceda permissão a **ads_management** depois de autenticar com o Facebook.</span><span class="sxs-lookup"><span data-stu-id="db343-113">Allow the **ads_management** permission after authenticating with Facebook.</span></span>

1. <span data-ttu-id="db343-114">Selecione a Conta de Anúncios do **Facebook** na qual você deseja trabalhar.</span><span class="sxs-lookup"><span data-stu-id="db343-114">Select the **Facebook Ads Account** that you want to work with.</span></span>

1. <span data-ttu-id="db343-115">Selecione um **Público-alvo personalizado existente** na lista suspensa ou crie um **Novo público-alvo personalizado**.</span><span class="sxs-lookup"><span data-stu-id="db343-115">Select an **Existing custom audience** from the drop-down list or create a **New custom audience**.</span></span> <span data-ttu-id="db343-116">Para obter mais informações, consulte [**Público no Gerenciador de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span><span class="sxs-lookup"><span data-stu-id="db343-116">For more information, see [**Audiences in Facebook Ads Manager**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).</span></span>

1. <span data-ttu-id="db343-117">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="db343-117">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="db343-118">Selecione **Próximo** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="db343-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="db343-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="db343-119">Configure the connector</span></span>

1. <span data-ttu-id="db343-120">No campo **Escolher identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar para o Gerenciador de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="db343-120">In the **Choose your key identifier field**, select **Email**, **Name and address**, or **Phone** to send to Facebook Ads Manager.</span></span>

1. <span data-ttu-id="db343-121">Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="db343-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>
   > <span data-ttu-id="db343-122">[DICA] As melhores chances de correspondência ocorrem se você selecionar **E-mail** como o identificador.</span><span class="sxs-lookup"><span data-stu-id="db343-122">[TIP] The best chances for a match occur if you select **Email** as key identifier.</span></span> <span data-ttu-id="db343-123">Adicionar identificadores adicionais pode melhorar a correspondência.</span><span class="sxs-lookup"><span data-stu-id="db343-123">Adding additional identifiers may improve the matching.</span></span>

1. <span data-ttu-id="db343-124">Selecione **Adicionar atributo** para mapear os atributos adicionais para enviar ao Gerenciador de Anúncios do Facebook.</span><span class="sxs-lookup"><span data-stu-id="db343-124">Select **Add attribute** to map additional attributes to send to Facebook Ads Manager.</span></span> <span data-ttu-id="db343-125">Os atributos do Gerenciador de Anúncios do Facebook estão sendo mapeados para os seguintes nomes de usuários amigáveis: **FN** = **Nome**, **LN** = **Sobrenome**, **FI** = **Primeira Inicial**, **PHONE** = **Telefone**, **GEN** = **Gênero**, **DOB** = **Data de Nascimento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal/CEP**, **COUNTRY** = **País/Região**</span><span class="sxs-lookup"><span data-stu-id="db343-125">Attributes from Facebook Ads Manager are mapping to the following user friendly names: **FN** = **First Name**, **LN** = **Last Name**, **FI** = **First Initial**, **PHONE** = **Phone**, **GEN** = **Gender**, **DOB** = **Date of birth**, **ST** = **State**, **CT** = **City**, **ZIP** = **Postal code / Zip code**, **COUNTRY** = **Country / Region**</span></span>

1. <span data-ttu-id="db343-126">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="db343-126">Select the segments you want to export.</span></span>

1. <span data-ttu-id="db343-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="db343-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="db343-128">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="db343-128">Export the data</span></span>

<span data-ttu-id="db343-129">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="db343-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="db343-130">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="db343-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="db343-131">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="db343-131">Known limitations</span></span>

- <span data-ttu-id="db343-132">Até 10 milhões de perfis de cliente por exportação para o Gerenciador de Anúncios do Facebook</span><span class="sxs-lookup"><span data-stu-id="db343-132">Up to 10 million customer profile per export to Facebook Ads Manager</span></span> 
- <span data-ttu-id="db343-133">A exportação para o Gerenciador de Anúncios do Facebook é limitada a segmentos</span><span class="sxs-lookup"><span data-stu-id="db343-133">Export to Facebook Ads Manager is limited to segments</span></span>
- <span data-ttu-id="db343-134">A exportação de segmentos com um total de 10 milhão de perfis pode levar até 90 minutos para ser concluída</span><span class="sxs-lookup"><span data-stu-id="db343-134">Exporting segments with a total of 10 million profiles can take up to 90 minutes to complete</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="db343-135">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="db343-135">Data privacy and compliance</span></span>

<span data-ttu-id="db343-136">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Gerenciador de Anúncios do Facebook, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="db343-136">When you enable Dynamics 365 Customer Insights to transmit data to Facebook Ads Manager, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="db343-137">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Gerenciador de Anúncios do Facebook cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="db343-137">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Facebook Ads meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="db343-138">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="db343-138">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="db343-139">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="db343-139">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]