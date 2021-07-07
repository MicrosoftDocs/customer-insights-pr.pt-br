---
title: Exportar dados do Customer Insights para a ActiveCampaign
description: Saiba como configurar a conexão e exportar para a ActiveCampaign.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d85fa9836618e27f7f3da6ce17c07b4bc89e187
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314575"
---
# <a name="export-segments-to-activecampaign-preview"></a><span data-ttu-id="d91cf-103">Exportar segmentos para a ActiveCampaign (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="d91cf-103">Export segments to ActiveCampaign (preview)</span></span>

<span data-ttu-id="d91cf-104">Exporte segmentos de perfis unificados de clientes para a ActiveCampaign e use-os para atividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="d91cf-104">Export segments of unified customer profiles to ActiveCampaign and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d91cf-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d91cf-105">Prerequisites</span></span>

-   <span data-ttu-id="d91cf-106">Você ter uma [conta da ActiveCampaign](https://www.activecampaign.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d91cf-106">You have an [ActiveCampaign account](https://www.activecampaign.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d91cf-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="d91cf-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d91cf-108">Os perfis de cliente unificados nos segmentos exportados contêm um campo com um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="d91cf-108">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d91cf-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="d91cf-109">Known limitations</span></span>

- <span data-ttu-id="d91cf-110">Você pode exportar até 1 milhão de perfis por exportação para a ActiveCampaign e isso pode levar até 90 minutos para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="d91cf-110">You can export up to 1 million profiles per export to ActiveCampaign and it can take up to 90 minutes to complete.</span></span>
- <span data-ttu-id="d91cf-111">A exportação para a ActiveCampaign é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="d91cf-111">Exporting to ActiveCampaign is limited to segments.</span></span>
- <span data-ttu-id="d91cf-112">O número de perfis que você pode exportar para a ActiveCampaign depende de seu contrato com a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="d91cf-112">The number of profiles that you can export to ActiveCampaign depends on your contract with ActiveCampaign.</span></span>

## <a name="set-up-connection-to-activecampaign"></a><span data-ttu-id="d91cf-113">Configurar conexão para a ActiveCampaign</span><span class="sxs-lookup"><span data-stu-id="d91cf-113">Set up connection to ActiveCampaign</span></span>

1. <span data-ttu-id="d91cf-114">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="d91cf-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d91cf-115">Selecione **Adicionar conexão** e escolha **ActiveCampaign** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d91cf-115">Select **Add connection** and choose **ActiveCampaign** to configure the connection.</span></span>

1. <span data-ttu-id="d91cf-116">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="d91cf-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d91cf-117">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="d91cf-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d91cf-118">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="d91cf-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d91cf-119">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="d91cf-119">Choose who can use this connection.</span></span> <span data-ttu-id="d91cf-120">Por padrão, são somente os administradores.</span><span class="sxs-lookup"><span data-stu-id="d91cf-120">By default, it's only administrators.</span></span> <span data-ttu-id="d91cf-121">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d91cf-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d91cf-122">Insira sua [Chave de API da ActiveCampaign e Nome do Host do Ponto de Extremidade REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span><span class="sxs-lookup"><span data-stu-id="d91cf-122">Enter your [ActiveCampaign API Key and REST Endpoint Hostname](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key).</span></span> <span data-ttu-id="d91cf-123">O Nome do host do ponto de extremidade REST é somente o nome do host, sem https://.</span><span class="sxs-lookup"><span data-stu-id="d91cf-123">The REST Endpoint Hostname is the hostname only, without https://.</span></span> 

1. <span data-ttu-id="d91cf-124">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="d91cf-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d91cf-125">Selecione **Conectar** para inicializar conexão à ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="d91cf-125">Select **Connect** to initialize the connection to ActiveCampaign.</span></span>

1. <span data-ttu-id="d91cf-126">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d91cf-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d91cf-127">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="d91cf-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d91cf-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="d91cf-128">Configure an export</span></span>

<span data-ttu-id="d91cf-129">Você poderá configurar uma exportação se tiver acesso a uma conexão desse tipo.</span><span class="sxs-lookup"><span data-stu-id="d91cf-129">You can configure an export if you have access to a connection of this type.</span></span> <span data-ttu-id="d91cf-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d91cf-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d91cf-131">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="d91cf-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d91cf-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="d91cf-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d91cf-133">No campo **Conexão para exportação**, escolha uma conexão na seção da ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="d91cf-133">In the **Connection for export** field, choose a connection from the ActiveCampaign section.</span></span> <span data-ttu-id="d91cf-134">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="d91cf-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d91cf-135">Insira sua [**ID da Lista da ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span><span class="sxs-lookup"><span data-stu-id="d91cf-135">Enter your [**ActiveCampaign List ID**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).</span></span>    

3. <span data-ttu-id="d91cf-136">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="d91cf-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d91cf-137">É necessário exportar segmentos para a ActiveCampaign.</span><span class="sxs-lookup"><span data-stu-id="d91cf-137">It's required to export segments to ActiveCampaign.</span></span> <span data-ttu-id="d91cf-138">Opcionalmente, você pode exportar Nome, Sobrenome, e Telefone para criar emails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="d91cf-138">Optionally, you can export First name, Last name, and Phone to create more personalized emails.</span></span> <span data-ttu-id="d91cf-139">Selecione Adicionar atributo para mapear esses campos.</span><span class="sxs-lookup"><span data-stu-id="d91cf-139">Select Add attribute to map these fields.</span></span>

1. <span data-ttu-id="d91cf-140">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d91cf-140">Select **Save**.</span></span>

<span data-ttu-id="d91cf-141">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="d91cf-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d91cf-142">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d91cf-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d91cf-143">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d91cf-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d91cf-144">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="d91cf-144">Data privacy and compliance</span></span>

<span data-ttu-id="d91cf-145">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para a ActiveCampaign, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="d91cf-145">When you enable Dynamics 365 Customer Insights to transmit data to ActiveCampaign, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d91cf-146">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que a ActiveCampaign cumpra quaisquer obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="d91cf-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that ActiveCampaign meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d91cf-147">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d91cf-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d91cf-148">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d91cf-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
