---
title: Exportar dados do Customer Insights para o Snapchat
description: Saiba como configurar a conexão e exportar para o Snapchat.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d3dae7f0fef1fc3792c90c8ac0d3b037f5c0923d
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760465"
---
# <a name="export-segment-lists-to-snapchat-preview"></a><span data-ttu-id="2be3e-103">Exportar listas de segmentos para o Snapchat (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="2be3e-103">Export segment lists to Snapchat (preview)</span></span>

<span data-ttu-id="2be3e-104">Exporte segmentos de perfis de clientes unificados para o Snapchat e use-os para publicidade.</span><span class="sxs-lookup"><span data-stu-id="2be3e-104">Export segments of unified customer profiles to Snapchat and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="2be3e-105">Pré-requisitos para uma conexão</span><span class="sxs-lookup"><span data-stu-id="2be3e-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="2be3e-106">Você deve ter uma [Conta de Negócios do Snapchat](https://business.snapchat.com/), uma [Conta de Anúncios do Snapchat](https://ads.snapchat.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="2be3e-106">You have a [Snapchat Business account](https://business.snapchat.com/), a [Snapchat Ads account](https://ads.snapchat.com/), and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="2be3e-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="2be3e-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="2be3e-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="2be3e-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="2be3e-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="2be3e-109">Known limitations</span></span>

- <span data-ttu-id="2be3e-110">A exportação para o Snapchat é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="2be3e-110">Exporting to Snapchat is limited to segments.</span></span>
- <span data-ttu-id="2be3e-111">Exportar até 1 milhão de perfis para o Snapchat pode levar até 15 minutos para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="2be3e-111">Exporting up to 1 million profiles to Snapchat can take up to 15 minutes to complete.</span></span> 

## <a name="set-up-connection-to-snapchat"></a><span data-ttu-id="2be3e-112">Configurar conexão com o Snapchat</span><span class="sxs-lookup"><span data-stu-id="2be3e-112">Set up connection to Snapchat</span></span>

1. <span data-ttu-id="2be3e-113">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="2be3e-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="2be3e-114">Selecione **Adicionar conexão** e escolha **Snapchat** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="2be3e-114">Select **Add connection** and choose **Snapchat** to configure the connection.</span></span>

1. <span data-ttu-id="2be3e-115">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="2be3e-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="2be3e-116">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="2be3e-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="2be3e-117">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="2be3e-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="2be3e-118">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="2be3e-118">Choose who can use this connection.</span></span> <span data-ttu-id="2be3e-119">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="2be3e-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="2be3e-120">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="2be3e-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="2be3e-121">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="2be3e-121">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="2be3e-122">Selecione **Conectar** para inicializar a conexão com o Snapchat.</span><span class="sxs-lookup"><span data-stu-id="2be3e-122">Select **Connect** to initialize the connection to Snapchat.</span></span>

1. <span data-ttu-id="2be3e-123">Selecione **Autenticar com o Snapchat** e forneça suas credenciais de administrador do Snapchat.</span><span class="sxs-lookup"><span data-stu-id="2be3e-123">Select **Authenticate with Snapchat** and provide your admin credentials for Snapchat.</span></span> 

1. <span data-ttu-id="2be3e-124">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="2be3e-124">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="2be3e-125">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="2be3e-125">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="2be3e-126">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="2be3e-126">Configure an export</span></span>

<span data-ttu-id="2be3e-127">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="2be3e-127">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="2be3e-128">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="2be3e-128">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="2be3e-129">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="2be3e-129">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="2be3e-130">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="2be3e-130">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="2be3e-131">No campo **Conexão para exportação**, escolha uma conexão da seção do Snapchat.</span><span class="sxs-lookup"><span data-stu-id="2be3e-131">In the **Connection for export** field, choose a connection from the Snapchat section.</span></span> <span data-ttu-id="2be3e-132">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="2be3e-132">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="2be3e-133">Insira a [**ID do Público-Alvo do Snapchat**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span><span class="sxs-lookup"><span data-stu-id="2be3e-133">Enter the [**Snapchat Audience ID**](https://businesshelp.snapchat.com/s/article/custom-audiences).</span></span>

1. <span data-ttu-id="2be3e-134">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="2be3e-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="2be3e-135">A exportação de segmentos para o Snapchat é necessária.</span><span class="sxs-lookup"><span data-stu-id="2be3e-135">It's required to export segments to Snapchat.</span></span>

1. <span data-ttu-id="2be3e-136">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="2be3e-136">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="2be3e-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2be3e-137">Select **Save**.</span></span>

<span data-ttu-id="2be3e-138">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="2be3e-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="2be3e-139">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="2be3e-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="2be3e-140">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="2be3e-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="2be3e-141">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="2be3e-141">Data privacy and compliance</span></span>

<span data-ttu-id="2be3e-142">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Snapchat, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="2be3e-142">When you enable Dynamics 365 Customer Insights to transmit data to Snapchat, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="2be3e-143">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Snapchat atenda a todas as obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="2be3e-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Snapchat meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="2be3e-144">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="2be3e-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="2be3e-145">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2be3e-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
