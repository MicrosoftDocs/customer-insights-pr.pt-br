---
title: Exportar dados do Customer Insights para o Constant Contact
description: Saiba como configurar a conexão e exportar para o Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3a9372cc4ffa4fb112a96b1286aee9dc35059a50
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760466"
---
# <a name="export-segment-lists-to-constant-contact-preview"></a><span data-ttu-id="adf3e-103">Exportar listas de segmentos para o Constant Contact (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="adf3e-103">Export segment lists to Constant Contact (preview)</span></span>

<span data-ttu-id="adf3e-104">Exporte segmentos de perfis de clientes unificados para o Constant Contact e use-os para atividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="adf3e-104">Export segments of unified customer profiles to Constant Contact and use them for marketing activities.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="adf3e-105">Pré-requisitos para uma conexão</span><span class="sxs-lookup"><span data-stu-id="adf3e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="adf3e-106">Você deve ter uma [conta do Constant Contact](https://www.constantcontact.com/account-home) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="adf3e-106">You have an [Constant Contact account](https://www.constantcontact.com/account-home) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="adf3e-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="adf3e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="adf3e-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="adf3e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="adf3e-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="adf3e-109">Known limitations</span></span>

- <span data-ttu-id="adf3e-110">Você pode exportar até 1 milhão de perfis por vez para o Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="adf3e-110">You can export up to 1 million profiles per export to Constant Contact.</span></span>
- <span data-ttu-id="adf3e-111">A exportação para o Constant Contact é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="adf3e-111">Exporting to Constant Contact is limited to segments.</span></span>
- <span data-ttu-id="adf3e-112">Exportar até 1 milhão de perfis para o Constant Contact pode levar até 1 hora para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="adf3e-112">Exporting up to 1 million profiles to Constant Contact can take up to 1 hour to complete.</span></span> 
- <span data-ttu-id="adf3e-113">O número de perfis que você pode exportar para o Constant Contact depende e está limitado ao seu contrato com o Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="adf3e-113">The number of profiles that you can export to Constant Contact is dependent and limited on your contract with Constant Contact.</span></span>

## <a name="set-up-connection-to-constant-contact"></a><span data-ttu-id="adf3e-114">Configurar conexão com o Constant Contact</span><span class="sxs-lookup"><span data-stu-id="adf3e-114">Set up connection to Constant Contact</span></span>

1. <span data-ttu-id="adf3e-115">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="adf3e-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="adf3e-116">Selecione **Adicionar conexão** e escolha **Constant Contact** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="adf3e-116">Select **Add connection** and choose **Constant Contact** to configure the connection.</span></span>

1. <span data-ttu-id="adf3e-117">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="adf3e-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="adf3e-118">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="adf3e-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="adf3e-119">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="adf3e-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="adf3e-120">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="adf3e-120">Choose who can use this connection.</span></span> <span data-ttu-id="adf3e-121">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="adf3e-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="adf3e-122">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="adf3e-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="adf3e-123">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="adf3e-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="adf3e-124">Selecione **Conectar** para inicializar a conexão com o Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="adf3e-124">Select **Connect** to initialize the connection to Constant Contact.</span></span>

1. <span data-ttu-id="adf3e-125">Selecione **Autenticar com o AdRoll** e forneça suas credenciais de administrador do Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="adf3e-125">Select **Authenticate with AdRoll** and provide your admin credentials for Constant Contact.</span></span> 

1. <span data-ttu-id="adf3e-126">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="adf3e-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="adf3e-127">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="adf3e-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="adf3e-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="adf3e-128">Configure an export</span></span>

<span data-ttu-id="adf3e-129">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="adf3e-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="adf3e-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="adf3e-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="adf3e-131">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="adf3e-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="adf3e-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="adf3e-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="adf3e-133">No campo **Conexão para exportação**, escolha uma conexão da seção do Constant Contact.</span><span class="sxs-lookup"><span data-stu-id="adf3e-133">In the **Connection for export** field, choose a connection from the Constant Contact section.</span></span> <span data-ttu-id="adf3e-134">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="adf3e-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="adf3e-135">Insira sua [**ID da Lista do Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists).</span><span class="sxs-lookup"><span data-stu-id="adf3e-135">Enter your [**Constant Contact List ID**](https://app.constantcontact.com/pages/contacts/ui#lists).</span></span> <span data-ttu-id="adf3e-136">Abra uma lista no Constant Contact para localizar a ID da lista na URL.</span><span class="sxs-lookup"><span data-stu-id="adf3e-136">Open a list in Constant Contact to find the list ID in the URL.</span></span>

1. <span data-ttu-id="adf3e-137">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="adf3e-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="adf3e-138">A exportação de segmentos para o Constant Contact é necessária.</span><span class="sxs-lookup"><span data-stu-id="adf3e-138">It's required to export segments to Constant Contact.</span></span>

1. <span data-ttu-id="adf3e-139">Opcionalmente, você pode exportar Nome e Sobrenome como campos adicionais para criar emails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="adf3e-139">Optionally, you can export First name and Last name as additional fields to create more personalized emails.</span></span> <span data-ttu-id="adf3e-140">Selecione **Adicionar atributo** para mapear esses campos.</span><span class="sxs-lookup"><span data-stu-id="adf3e-140">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="adf3e-141">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="adf3e-141">Select the segments you want to export.</span></span>

1. <span data-ttu-id="adf3e-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="adf3e-142">Select **Save**.</span></span>

<span data-ttu-id="adf3e-143">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="adf3e-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="adf3e-144">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="adf3e-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="adf3e-145">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="adf3e-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="adf3e-146">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="adf3e-146">Data privacy and compliance</span></span>

<span data-ttu-id="adf3e-147">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Constant Contact, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="adf3e-147">When you enable Dynamics 365 Customer Insights to transmit data to Constant Contact, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="adf3e-148">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Constant Contact atenda a todas as obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="adf3e-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Constant Contact meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="adf3e-149">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="adf3e-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="adf3e-150">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="adf3e-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
