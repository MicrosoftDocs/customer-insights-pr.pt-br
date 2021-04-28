---
title: Exportar dados do Customer Insights para o Autopilot
description: Aprenda a configurar a conexão e exportar para o Autopilot.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e320a48d5b7c35b530e3a38567b226b804879e4e
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760083"
---
# <a name="export-segments-to-autopilot-preview"></a><span data-ttu-id="4b713-103">Exportar segmentos para o Autopilot (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="4b713-103">Export segments to Autopilot (preview)</span></span>

<span data-ttu-id="4b713-104">Exporte segmentos de perfis de clientes unificados para o Autopilot e use-os para marketing por email no Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4b713-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="4b713-105">Pré-requisitos para uma conexão</span><span class="sxs-lookup"><span data-stu-id="4b713-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="4b713-106">Você deve ter uma [conta do Autopilot](https://www.autopilothq.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="4b713-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="4b713-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="4b713-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="4b713-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="4b713-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="4b713-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="4b713-109">Known limitations</span></span>

- <span data-ttu-id="4b713-110">Você pode exportar até 100.000 perfis de clientes no total para o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4b713-110">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="4b713-111">A exportação para o Autopilot é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="4b713-111">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="4b713-112">A exportação de até 100.000 perfis para o Autopilot pode levar até algumas horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="4b713-112">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="4b713-113">O número de perfis que você pode exportar para o Autopilot depende e está limitado ao seu contrato com o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4b713-113">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="set-up-connection-to-autopilot"></a><span data-ttu-id="4b713-114">Configurar conexão com o Autopilot</span><span class="sxs-lookup"><span data-stu-id="4b713-114">Set up connection to Autopilot</span></span>

1. <span data-ttu-id="4b713-115">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="4b713-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="4b713-116">Selecione **Adicionar conexão** e escolha **Autopilot** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="4b713-116">Select **Add connection** and choose **Autopilot** to configure the connection.</span></span>

1. <span data-ttu-id="4b713-117">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="4b713-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="4b713-118">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="4b713-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="4b713-119">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="4b713-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="4b713-120">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="4b713-120">Choose who can use this connection.</span></span> <span data-ttu-id="4b713-121">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="4b713-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="4b713-122">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="4b713-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

3. <span data-ttu-id="4b713-123">Insira sua [chave de API do Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="4b713-123">Enter your [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="4b713-124">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="4b713-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="4b713-125">Selecione **Conectar** para inicializar a conexão com o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4b713-125">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="4b713-126">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="4b713-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="4b713-127">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="4b713-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="4b713-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="4b713-128">Configure an export</span></span>

<span data-ttu-id="4b713-129">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="4b713-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="4b713-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="4b713-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="4b713-131">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="4b713-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="4b713-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="4b713-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="4b713-133">No campo **Conexão para exportação**, escolha uma conexão da seção do Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4b713-133">In the **Connection for export** field, choose a connection from the Autopilot section.</span></span> <span data-ttu-id="4b713-134">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="4b713-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

3. <span data-ttu-id="4b713-135">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="4b713-135">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="4b713-136">Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**.</span><span class="sxs-lookup"><span data-stu-id="4b713-136">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="4b713-137">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="4b713-137">Select the segments you want to export.</span></span> <span data-ttu-id="4b713-138">É altamente **recomendável não exportar mais de 100.000 perfis de clientes no total** para o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="4b713-138">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="4b713-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="4b713-139">Select **Save**.</span></span>

<span data-ttu-id="4b713-140">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="4b713-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="4b713-141">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="4b713-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="4b713-142">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="4b713-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="4b713-143">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="4b713-143">Data privacy and compliance</span></span>

<span data-ttu-id="4b713-144">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Autopilot, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="4b713-144">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="4b713-145">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Autopilot cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="4b713-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="4b713-146">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="4b713-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="4b713-147">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="4b713-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
