---
title: Exportar dados do Customer Insights para o Microsoft Advertising
description: Saiba como configurar a conexão e exportar para o Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c2ac92de2718cf7f0622b407bf198a7a7e50a37b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124450"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a><span data-ttu-id="1b0da-103">Exportar segmentos para o Microsoft Advertising (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="1b0da-103">Export segments to Microsoft Advertising (preview)</span></span>

<span data-ttu-id="1b0da-104">Exporte segmentos do Customer Insights para o Microsoft Advertising para criar públicos-alvo de Correspondência de Clientes.</span><span class="sxs-lookup"><span data-stu-id="1b0da-104">Export Customer Insights segments to Microsoft Advertising to create Customer Match audiences.</span></span> <span data-ttu-id="1b0da-105">Use esses públicos-alvo para suas campanhas publicitárias.</span><span class="sxs-lookup"><span data-stu-id="1b0da-105">Use these audiences for your ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1b0da-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="1b0da-106">Prerequisites</span></span>

-   <span data-ttu-id="1b0da-107">Uma [conta do Microsoft Advertising](https://ads.microsoft.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="1b0da-107">An [Microsoft Advertising account](https://ads.microsoft.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="1b0da-108">Você aceitou os termos de uso da Correspondência de Clientes.</span><span class="sxs-lookup"><span data-stu-id="1b0da-108">You've accepted the Customer Match terms of use.</span></span> 
-   <span data-ttu-id="1b0da-109">[Segmentos configurados](segments.md) nos insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="1b0da-109">[Configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="1b0da-110">Os perfis de cliente unificados nos segmentos exportados contêm um campo com um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="1b0da-110">Unified customer profiles in the exported segments contain a field with an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="1b0da-111">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="1b0da-111">Known limitations</span></span>

- <span data-ttu-id="1b0da-112">Você pode exportar até 500.000 perfis por vez para o Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1b0da-112">You can export up to 500 K profiles per export to Microsoft Advertising.</span></span>
- <span data-ttu-id="1b0da-113">A exportação para o Microsoft Advertising está limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="1b0da-113">Exporting to Microsoft Advertising is limited to segments.</span></span>
- <span data-ttu-id="1b0da-114">Exportar até 500.000 perfis para o Microsoft Advertising pode levar até 10 minutos para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="1b0da-114">Exporting up to 500 K profiles to Microsoft Advertising can take up to 10 minutes to complete.</span></span> 


## <a name="set-up-the-connection-to-microsoft-advertising"></a><span data-ttu-id="1b0da-115">Configurar a conexão com o Microsoft Advertising</span><span class="sxs-lookup"><span data-stu-id="1b0da-115">Set up the connection to Microsoft Advertising</span></span>

1. <span data-ttu-id="1b0da-116">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="1b0da-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="1b0da-117">Selecione **Adicionar conexão** e escolha **Microsoft Advertising** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="1b0da-117">Select **Add connection** and choose **Microsoft Advertising** to configure the connection.</span></span>

1. <span data-ttu-id="1b0da-118">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="1b0da-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="1b0da-119">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="1b0da-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="1b0da-120">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="1b0da-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="1b0da-121">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="1b0da-121">Choose who can use this connection.</span></span> <span data-ttu-id="1b0da-122">O padrão é administradores.</span><span class="sxs-lookup"><span data-stu-id="1b0da-122">The default is administrators.</span></span> <span data-ttu-id="1b0da-123">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="1b0da-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="1b0da-124">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="1b0da-124">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="1b0da-125">Selecione **Conectar** para inicializar a conexão ao Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1b0da-125">Select **Connect** to initialize the connection to Microsoft Advertising.</span></span>

1. <span data-ttu-id="1b0da-126">Selecione **Autenticar com Microsoft Advertising** e forneça suas credenciais de administrador do Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1b0da-126">Select **Authenticate with Microsoft Advertising** and provide your admin credentials for Microsoft Advertising.</span></span>

1. <span data-ttu-id="1b0da-127">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="1b0da-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="1b0da-128">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="1b0da-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="1b0da-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="1b0da-129">Configure an export</span></span>

<span data-ttu-id="1b0da-130">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="1b0da-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="1b0da-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="1b0da-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="1b0da-132">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="1b0da-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="1b0da-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="1b0da-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="1b0da-134">No campo **Conexão para exportação**, escolha uma conexão na seção do Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1b0da-134">In the **Connection for export** field, choose a connection from the Microsoft Advertising section.</span></span> <span data-ttu-id="1b0da-135">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="1b0da-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="1b0da-136">Selecione os segmentos a serem exportados.</span><span class="sxs-lookup"><span data-stu-id="1b0da-136">Select the segments to export.</span></span> <span data-ttu-id="1b0da-137">Os públicos-alvo da Correspondência de Clientes no Microsoft Advertising são criados automaticamente com o nome dos segmentos selecionados para exportação.</span><span class="sxs-lookup"><span data-stu-id="1b0da-137">The Customer Match audiences in Microsoft Advertising are automatically created with the name of the segments selected for export.</span></span> <span data-ttu-id="1b0da-138">Cada segmento resultará em um público-alvo separado da Correspondência de Clientes.</span><span class="sxs-lookup"><span data-stu-id="1b0da-138">Each segment will result in a separate Customer Match audience.</span></span> 

1. <span data-ttu-id="1b0da-139">Insira sua **ID do cliente e ID da conta do Microsoft Advertising**.</span><span class="sxs-lookup"><span data-stu-id="1b0da-139">Enter your **Microsoft Advertising Customer ID and Account ID**.</span></span> <span data-ttu-id="1b0da-140">Você pode encontrar a ID do cliente (`cid`) e a ID da conta (`aid`) nos parâmetros da URL quando você estiver conectado ao Microsoft Advertising.</span><span class="sxs-lookup"><span data-stu-id="1b0da-140">You can find the Customer ID (`cid`) and Account ID (`aid`) in the parameters of the URL when you're signed in Microsoft Advertising.</span></span>

1. <span data-ttu-id="1b0da-141">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo em seu perfil de cliente unificado com o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="1b0da-141">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile with a customer's email address.</span></span> <span data-ttu-id="1b0da-142">A exportação de segmentos para o Microsoft Advertising é necessária.</span><span class="sxs-lookup"><span data-stu-id="1b0da-142">It's required to export segments to Microsoft Advertising.</span></span>

1. <span data-ttu-id="1b0da-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="1b0da-143">Select **Save**.</span></span>

<span data-ttu-id="1b0da-144">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="1b0da-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="1b0da-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="1b0da-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="1b0da-146">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="1b0da-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="1b0da-147">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="1b0da-147">Data privacy and compliance</span></span>

<span data-ttu-id="1b0da-148">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Microsoft Advertising, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados que podem ser confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="1b0da-148">When you enable Dynamics 365 Customer Insights to transmit data to Microsoft Advertising, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="1b0da-149">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Microsoft Advertising atenda a todas as obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="1b0da-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Microsoft Advertising meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="1b0da-150">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="1b0da-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="1b0da-151">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="1b0da-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to stop use of this functionality.</span></span>
