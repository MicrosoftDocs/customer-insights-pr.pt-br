---
title: Exportar dados do Customer Insights para o SendGrid
description: Saiba como configurar a conexão e exportar para o SendGrid.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a4c64cf77c682e07f3d0759c43355336b5806fc8
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759751"
---
# <a name="export-segments-to-sendgrid-preview"></a><span data-ttu-id="d8595-103">Exportar segmentos para o SendGrid (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="d8595-103">Export segments to SendGrid (preview)</span></span>

<span data-ttu-id="d8595-104">Exporte segmentos de perfis de clientes unificados para as listas de contato do SendGrid e use-os para campanhas e marketing por email no SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d8595-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="d8595-105">Pré-requisitos para uma conexão</span><span class="sxs-lookup"><span data-stu-id="d8595-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="d8595-106">Você deve ter uma [conta do SendGrid](https://sendgrid.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d8595-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d8595-107">Há listas de contato existentes no SendGrid e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d8595-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="d8595-108">Para obter mais informações, consulte [SendGrid – Gerenciar contatos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="d8595-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="d8595-109">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="d8595-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d8595-110">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="d8595-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d8595-111">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="d8595-111">Known limitations</span></span>

- <span data-ttu-id="d8595-112">Até 100.000 perfis no total para o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d8595-112">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="d8595-113">A exportação para o SendGrid é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="d8595-113">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="d8595-114">A exportação de até 100.000 perfis para o SendGrid pode levar até algumas horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="d8595-114">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="d8595-115">O número de perfis que você pode exportar para o SendGrid depende e está limitado ao seu contrato com o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d8595-115">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="set-up-connection-to-sendgrid"></a><span data-ttu-id="d8595-116">Configurar conexão com o SendGrid</span><span class="sxs-lookup"><span data-stu-id="d8595-116">Set up connection to SendGrid</span></span>

1. <span data-ttu-id="d8595-117">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="d8595-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d8595-118">Selecione **Adicionar conexão** e escolha **SendGrid** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d8595-118">Select **Add connection** and choose **SendGrid** to configure the connection.</span></span>

1. <span data-ttu-id="d8595-119">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="d8595-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d8595-120">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="d8595-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d8595-121">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="d8595-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d8595-122">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="d8595-122">Choose who can use this connection.</span></span> <span data-ttu-id="d8595-123">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="d8595-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d8595-124">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d8595-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d8595-125">Insira a **Chave de API do SendGrid** [Chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="d8595-125">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="d8595-126">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="d8595-126">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d8595-127">Selecione **Conectar** para inicializar a conexão com o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d8595-127">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="d8595-128">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d8595-128">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d8595-129">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="d8595-129">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d8595-130">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="d8595-130">Configure an export</span></span>

<span data-ttu-id="d8595-131">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="d8595-131">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d8595-132">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d8595-132">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d8595-133">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="d8595-133">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d8595-134">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="d8595-134">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d8595-135">No campo **Conexão para exportação**, escolha uma conexão da seção do SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d8595-135">In the **Connection for export** field, choose a connection from the SendGrid section.</span></span> <span data-ttu-id="d8595-136">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="d8595-136">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d8595-137">Insira a **[ID de lista do SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="d8595-137">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="d8595-138">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="d8595-138">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d8595-139">Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**, **País/Região**, **Estado**, **Cidade** e **CEP**.</span><span class="sxs-lookup"><span data-stu-id="d8595-139">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="d8595-140">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="d8595-140">Select the segments you want to export.</span></span> <span data-ttu-id="d8595-141">É altamente **recomendável não exportar mais de 100.000 perfis de clientes no total** para o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="d8595-141">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="d8595-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d8595-142">Select **Save**.</span></span>

<span data-ttu-id="d8595-143">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="d8595-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d8595-144">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d8595-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d8595-145">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d8595-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d8595-146">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="d8595-146">Data privacy and compliance</span></span>

<span data-ttu-id="d8595-147">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao SendGrid, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="d8595-147">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d8595-148">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o SendGrid cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="d8595-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="d8595-149">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d8595-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="d8595-150">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d8595-150">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]