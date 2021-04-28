---
title: Exportar dados do Customer Insights para o RollWorks
description: Saiba como configurar a conexão e exportar para o RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 4979f0147dea2270f11342c1bb6b0693f3c24aea
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760468"
---
# <a name="export-segment-lists-to-rollworks-preview"></a><span data-ttu-id="ac950-103">Exportar listas de segmentos para o RollWorks (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="ac950-103">Export segment lists to RollWorks (preview)</span></span>

<span data-ttu-id="ac950-104">Exporte segmentos de perfis de clientes unificados para o RollWorks e use-os para publicidade.</span><span class="sxs-lookup"><span data-stu-id="ac950-104">Export segments of unified customer profiles to RollWorks and use them for advertising.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="ac950-105">Pré-requisitos para uma conexão</span><span class="sxs-lookup"><span data-stu-id="ac950-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="ac950-106">Você deve ter uma [conta do RollWorks](https://www.rollworks.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="ac950-106">You have an [RollWorks account](https://www.rollworks.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="ac950-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="ac950-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="ac950-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="ac950-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="ac950-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="ac950-109">Known limitations</span></span>

- <span data-ttu-id="ac950-110">Você pode exportar até 250.000 perfis por vez para o RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ac950-110">You can export up to 250'000 profiles in per export to RollWorks.</span></span>
- <span data-ttu-id="ac950-111">Você não pode exportar segmentos com menos de 100 perfis para o RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ac950-111">You can't export segments with fewer than 100 profiles to RollWorks.</span></span> 
- <span data-ttu-id="ac950-112">A exportação para o RollWorks é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="ac950-112">Exporting to RollWorks is limited to segments.</span></span>
- <span data-ttu-id="ac950-113">Exportar até 250.000 perfis para o RollWorks pode levar até 10 minutos para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="ac950-113">Exporting up to 250'000 profiles to RollWorks can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="ac950-114">O número de perfis que você pode exportar para o RollWorks depende e está limitado ao seu contrato com o RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ac950-114">The number of profiles that you can export to RollWorks is dependent and limited on your contract with RollWorks.</span></span>

## <a name="set-up-connection-to-rollworks"></a><span data-ttu-id="ac950-115">Configurar conexão com o RollWorks</span><span class="sxs-lookup"><span data-stu-id="ac950-115">Set up connection to RollWorks</span></span>

1. <span data-ttu-id="ac950-116">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="ac950-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="ac950-117">Selecione **Adicionar conexão** e escolha **RollWorks** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="ac950-117">Select **Add connection** and choose **RollWorks** to configure the connection.</span></span>

1. <span data-ttu-id="ac950-118">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="ac950-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="ac950-119">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="ac950-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="ac950-120">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="ac950-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="ac950-121">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="ac950-121">Choose who can use this connection.</span></span> <span data-ttu-id="ac950-122">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="ac950-122">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="ac950-123">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="ac950-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="ac950-124">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="ac950-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="ac950-125">Selecione **Conectar** para inicializar a conexão com o RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ac950-125">Select **Connect** to initialize the connection to RollWorks.</span></span>

1. <span data-ttu-id="ac950-126">Selecione **Autenticar com o RollWorks** e forneça suas credenciais de administrador do RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ac950-126">Select **Authenticate with RollWorks** and provide your admin credentials for RollWorks.</span></span>

1. <span data-ttu-id="ac950-127">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="ac950-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="ac950-128">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="ac950-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="ac950-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="ac950-129">Configure an export</span></span>

<span data-ttu-id="ac950-130">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="ac950-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="ac950-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="ac950-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="ac950-132">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="ac950-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="ac950-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="ac950-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="ac950-134">No campo **Conexão para exportação**, escolha uma conexão da seção do RollWorks.</span><span class="sxs-lookup"><span data-stu-id="ac950-134">In the **Connection for export** field, choose a connection from the RollWorks section.</span></span> <span data-ttu-id="ac950-135">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="ac950-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="ac950-136">Insira sua **ID de Anunciante do RollWorks** [RollWorks Anunciável](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="ac950-136">Enter your **RollWorks Advertiser ID** [RollWorks Advertisable](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).</span></span>

3. <span data-ttu-id="ac950-137">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="ac950-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="ac950-138">A exportação de segmentos para o RollWorks é necessária.</span><span class="sxs-lookup"><span data-stu-id="ac950-138">It's required to export segments to RollWorks.</span></span>

1. <span data-ttu-id="ac950-139">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="ac950-139">Select the segments you want to export.</span></span> <span data-ttu-id="ac950-140">Selecione um segmento com pelo menos 100 membros.</span><span class="sxs-lookup"><span data-stu-id="ac950-140">Select a segment with a least 100 members.</span></span> <span data-ttu-id="ac950-141">Você não poderá exportar segmentos menores.</span><span class="sxs-lookup"><span data-stu-id="ac950-141">You can't export smaller segments.</span></span> <span data-ttu-id="ac950-142">Além disso, o tamanho máximo de um segmento para exportação é de 250.000 membros por exportação.</span><span class="sxs-lookup"><span data-stu-id="ac950-142">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="ac950-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="ac950-143">Select **Save**.</span></span>

<span data-ttu-id="ac950-144">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="ac950-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="ac950-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ac950-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ac950-146">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="ac950-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ac950-147">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="ac950-147">Data privacy and compliance</span></span>

<span data-ttu-id="ac950-148">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o RollWorks, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="ac950-148">When you enable Dynamics 365 Customer Insights to transmit data to RollWorks, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ac950-149">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o RollWorks atenda a todas as obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="ac950-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that RollWorks meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ac950-150">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ac950-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="ac950-151">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ac950-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
