---
title: Exportar dados do Customer Insights para Monitor de Campanha
description: Aprenda a configurar a conexão e exportar para o Monitor de Campanha.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 091a3197dc0c19ff78f0419fb4e88868e0f78359
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124167"
---
# <a name="export-segments-to-campaign-monitor-preview"></a><span data-ttu-id="d3248-103">Exportar segmentos para o Monitor de Campanha (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="d3248-103">Export segments to Campaign Monitor (preview)</span></span>

<span data-ttu-id="d3248-104">Exporte segmentos de perfis de clientes unificados para o Monitor de Campanha e use-os para atividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="d3248-104">Export segments of unified customer profiles to Campaign Monitor and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3248-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d3248-105">Prerequisites</span></span>

-   <span data-ttu-id="d3248-106">Você tem uma [conta do Monitor de Campanha](https://www.campaignmonitor.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d3248-106">You have an [Campaign Monitor account](https://www.campaignmonitor.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="d3248-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="d3248-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="d3248-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="d3248-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="d3248-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="d3248-109">Known limitations</span></span>

- <span data-ttu-id="d3248-110">Você pode exportar até 1 milhão de perfis por vez para o Monitor de Campanha.</span><span class="sxs-lookup"><span data-stu-id="d3248-110">You can export up to 1 million profiles per export to Campaign Monitor.</span></span>
- <span data-ttu-id="d3248-111">A exportação para o Monitor de Campanha é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="d3248-111">Exporting to Campaign Monitor is limited to segments.</span></span>
- <span data-ttu-id="d3248-112">Exportar até 1 milhão de perfis para o Monitor de Campanha pode levar até 20 minutos para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="d3248-112">Exporting up to 1 million profiles to Campaign Monitor can take up to 20 minutes to complete.</span></span> 
- <span data-ttu-id="d3248-113">O número de perfis que você pode exportar para o Monitor de Campanha depende e está limitado ao seu contrato com o Monitor de Campanha.</span><span class="sxs-lookup"><span data-stu-id="d3248-113">The number of profiles that you can export to Campaign Monitor is dependent and limited on your contract with Campaign Monitor.</span></span>

## <a name="set-up-connection-to-campaign-monitor"></a><span data-ttu-id="d3248-114">Configurar a conexão com o Monitor de Campanha</span><span class="sxs-lookup"><span data-stu-id="d3248-114">Set up connection to Campaign Monitor</span></span>

1. <span data-ttu-id="d3248-115">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="d3248-115">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d3248-116">Selecione **Adicionar conexão** e escolha **Monitor de Campanha** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="d3248-116">Select **Add connection** and choose **Campaign Monitor** to configure the connection.</span></span>

1. <span data-ttu-id="d3248-117">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="d3248-117">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d3248-118">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="d3248-118">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d3248-119">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="d3248-119">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d3248-120">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="d3248-120">Choose who can use this connection.</span></span> <span data-ttu-id="d3248-121">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="d3248-121">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d3248-122">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="d3248-122">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="d3248-123">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="d3248-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="d3248-124">Selecione **Conectar** para inicializar a conexão com o Monitor de Campanha.</span><span class="sxs-lookup"><span data-stu-id="d3248-124">Select **Connect** to initialize the connection to Campaign Monitor.</span></span>

1. <span data-ttu-id="d3248-125">Selecione **Autenticar com Monitor de Campanha** e forneça suas credenciais de administrador do Monitor de Campanha.</span><span class="sxs-lookup"><span data-stu-id="d3248-125">Select **Authenticate with Campaign Monitor** and provide your admin credentials for Campaign Monitor.</span></span>

1. <span data-ttu-id="d3248-126">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="d3248-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="d3248-127">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="d3248-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="d3248-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="d3248-128">Configure an export</span></span>

<span data-ttu-id="d3248-129">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="d3248-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d3248-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d3248-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d3248-131">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="d3248-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d3248-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="d3248-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="d3248-133">No campo **Conexão para exportação**, escolha uma conexão da seção do Monitor de Campanha.</span><span class="sxs-lookup"><span data-stu-id="d3248-133">In the **Connection for export** field, choose a connection from the Campaign Monitor section.</span></span> <span data-ttu-id="d3248-134">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="d3248-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d3248-135">Insira a [**ID da Lista do Monitor de Campanha**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span><span class="sxs-lookup"><span data-stu-id="d3248-135">Enter your [**Campaign Monitor List ID**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).</span></span>    
   <span data-ttu-id="d3248-136">[Gerar a chave de API](https://www.campaignmonitor.com/api/getting-started/) de **Configurações da Conta** no Monitor de Campanha primeiro para exibir a ID da lista de API.</span><span class="sxs-lookup"><span data-stu-id="d3248-136">[Generate the API key](https://www.campaignmonitor.com/api/getting-started/) from **Account Settings** in Campaign Monitor first to view the API list ID.</span></span>  

3. <span data-ttu-id="d3248-137">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="d3248-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="d3248-138">A exportação de segmentos para o Monitor de Campanha é necessária.</span><span class="sxs-lookup"><span data-stu-id="d3248-138">It's required to export segments to Campaign Monitor.</span></span>

1. <span data-ttu-id="d3248-139">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d3248-139">Select **Save**.</span></span>

<span data-ttu-id="d3248-140">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="d3248-140">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="d3248-141">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="d3248-141">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="d3248-142">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d3248-142">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="d3248-143">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="d3248-143">Data privacy and compliance</span></span>

<span data-ttu-id="d3248-144">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Monitor de Campanha, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="d3248-144">When you enable Dynamics 365 Customer Insights to transmit data to Campaign Monitor, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="d3248-145">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Monitor de Campanha atenda a todas as obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="d3248-145">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Campaign Monitor meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="d3248-146">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="d3248-146">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="d3248-147">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="d3248-147">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
