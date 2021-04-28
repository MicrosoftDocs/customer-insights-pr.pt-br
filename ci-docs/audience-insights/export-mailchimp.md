---
title: Exportar dados do Customer Insights para o Mailchimp
description: Saiba como configurar a conexão e exportar para o Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b94a8e8b6bb867ca04a64007d592b22fbd700618
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759864"
---
# <a name="export-segment-lists-to-mailchimp-preview"></a><span data-ttu-id="0a17c-103">Exportar listas de segmentos para o Mailchimp (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="0a17c-103">Export segment lists to Mailchimp (preview)</span></span>

<span data-ttu-id="0a17c-104">Exporte segmentos de perfis de clientes unificados para o Mailchimp a fim de criar boletins informativos e campanhas por email.</span><span class="sxs-lookup"><span data-stu-id="0a17c-104">Export segments of unified customer profiles to Mailchimp to create newsletters and email campaigns.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0a17c-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="0a17c-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0a17c-106">Você deve ter uma [conta do Mailchimp](https://mailchimp.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="0a17c-106">You have a [Mailchimp account](https://mailchimp.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0a17c-107">Há públicos-alvo existentes no Mailchimp e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="0a17c-107">There are existing audiences in Mailchimp and the corresponding IDs.</span></span> <span data-ttu-id="0a17c-108">Para obter mais informações, consulte [públicos-alvo do Mailchimp](https://mailchimp.com/help/create-audience/).</span><span class="sxs-lookup"><span data-stu-id="0a17c-108">For more information, see [Mailchimp audiences](https://mailchimp.com/help/create-audience/).</span></span>
-   <span data-ttu-id="0a17c-109">Você deve ter [segmentos configurados](segments.md)</span><span class="sxs-lookup"><span data-stu-id="0a17c-109">You have [configured segments](segments.md)</span></span>
-   <span data-ttu-id="0a17c-110">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="0a17c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0a17c-111">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="0a17c-111">Known limitations</span></span>

- <span data-ttu-id="0a17c-112">Até 1 milhão de perfis por exportação para o Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0a17c-112">Up to 1 million profiles per export to Mailchimp.</span></span>
- <span data-ttu-id="0a17c-113">A exportação para o Mailchimp é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="0a17c-113">Exporting to Mailchimp is limited to segments.</span></span>
- <span data-ttu-id="0a17c-114">Exportar segmentos com 1 milhão de perfis pode levar até três horas.</span><span class="sxs-lookup"><span data-stu-id="0a17c-114">Exporting segments with 1 million profiles can take up to three hours.</span></span> 
- <span data-ttu-id="0a17c-115">O número de perfis que você pode exportar para o Mailchimp depende e está limitado ao seu contrato com o Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0a17c-115">The number of profiles that you can export to Mailchimp is dependent and limited on your contract with Mailchimp.</span></span>

## <a name="set-up-connection-to-mailchimp"></a><span data-ttu-id="0a17c-116">Configurar conexão com o Mailchimp</span><span class="sxs-lookup"><span data-stu-id="0a17c-116">Set up connection to Mailchimp</span></span>

1. <span data-ttu-id="0a17c-117">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="0a17c-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0a17c-118">Selecione **Adicionar conexão** e escolha **Autopilot** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="0a17c-118">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="0a17c-119">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="0a17c-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0a17c-120">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="0a17c-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0a17c-121">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="0a17c-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0a17c-122">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="0a17c-122">Choose who can use this connection.</span></span> <span data-ttu-id="0a17c-123">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="0a17c-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0a17c-124">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0a17c-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0a17c-125">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="0a17c-125">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="0a17c-126">Selecione **Conectar** para inicializar a conexão com o Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0a17c-126">Select **Connect** to initialize the connection to Mailchimp.</span></span>

1. <span data-ttu-id="0a17c-127">Selecione **Autenticar com o Mailchimp** e forneça suas credenciais do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0a17c-127">Select **Authenticate with Mailchimp** and provide your Mailchimp credentials.</span></span>

1. <span data-ttu-id="0a17c-128">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0a17c-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0a17c-129">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="0a17c-129">Select **Save** to complete the connection.</span></span> 

## <a name="configure-the-connector"></a><span data-ttu-id="0a17c-130">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="0a17c-130">Configure the connector</span></span>

<span data-ttu-id="0a17c-131">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="0a17c-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0a17c-132">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0a17c-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0a17c-133">Vá para **Dados**> **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="0a17c-133">Go to **Data**> **Exports**.</span></span>

1. <span data-ttu-id="0a17c-134">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="0a17c-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0a17c-135">No campo **Conexão para exportação**, escolha uma conexão da seção do Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0a17c-135">In the **Connection for export** field, choose a connection from the Mailchimp section.</span></span> <span data-ttu-id="0a17c-136">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="0a17c-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0a17c-137">Insira sua **[ID do público-alvo do Mailchimp](https://mailchimp.com/help/find-audience-id/)**</span><span class="sxs-lookup"><span data-stu-id="0a17c-137">Enter your **[Mailchimp audience ID](https://mailchimp.com/help/find-audience-id/)**</span></span>

3. <span data-ttu-id="0a17c-138">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="0a17c-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0a17c-139">Opcionalmente, você pode exportar **Nome** e **Sobrenome** para criar emails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="0a17c-139">Optionally, you can export **First name** and **Last name** to create more personalized emails.</span></span> <span data-ttu-id="0a17c-140">Selecione **Adicionar atributo** para mapear esses campos.</span><span class="sxs-lookup"><span data-stu-id="0a17c-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0a17c-141">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="0a17c-141">Select the segments you want to export.</span></span> <span data-ttu-id="0a17c-142">Você pode exportar até 1 milhão de perfis de clientes no total para o Mailchimp.</span><span class="sxs-lookup"><span data-stu-id="0a17c-142">You can export up to 1 million customer profiles in total to Mailchimp.</span></span>

1. <span data-ttu-id="0a17c-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0a17c-143">Select **Save**.</span></span>

<span data-ttu-id="0a17c-144">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0a17c-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0a17c-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0a17c-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0a17c-146">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0a17c-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0a17c-147">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="0a17c-147">Data privacy and compliance</span></span>

<span data-ttu-id="0a17c-148">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Mailchimp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="0a17c-148">When you enable Dynamics 365 Customer Insights to transmit data to Mailchimp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0a17c-149">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Mailchimp cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="0a17c-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Mailchimp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0a17c-150">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0a17c-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0a17c-151">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="0a17c-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
