---
title: Exportar dados do Customer Insights para o Omnisend
description: Saiba como configurar a conexão e exportar para o Omnisend.
ms.date: 05/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8bd692819fa8451ded5e74191ee717f81f87425d
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124451"
---
# <a name="export-segments-to-omnisend-preview"></a><span data-ttu-id="afcc0-103">Exportar segmentos para o Omnisend (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="afcc0-103">Export segments to Omnisend (preview)</span></span>

<span data-ttu-id="afcc0-104">Exporte segmentos de perfis de clientes unificados para o Omnisend e use-os para atividades de marketing.</span><span class="sxs-lookup"><span data-stu-id="afcc0-104">Export segments of unified customer profiles to Omnisend and use them for marketing activities.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="afcc0-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="afcc0-105">Prerequisites</span></span>

-   <span data-ttu-id="afcc0-106">Você deve ter uma [conta do Omnisend](https://www.omnisend.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="afcc0-106">You have an [Omnisend account](https://www.omnisend.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="afcc0-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="afcc0-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="afcc0-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="afcc0-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="afcc0-109">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="afcc0-109">Known limitations</span></span>

- <span data-ttu-id="afcc0-110">Você pode exportar até 1 milhão de perfis por exportação para Omnisend e pode isso levar até 4 horas para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="afcc0-110">You can export up to 1 million profiles per export to Omnisend and it can take up to 4 hours to complete.</span></span>
- <span data-ttu-id="afcc0-111">A exportação para o Omnisend é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="afcc0-111">Exporting to Omnisend is limited to segments.</span></span>
- <span data-ttu-id="afcc0-112">O número de perfis que você pode exportar para o Omnisend depende do seu contrato com o Omnisend.</span><span class="sxs-lookup"><span data-stu-id="afcc0-112">The number of profiles that you can export to Omnisend depends on your contract with Omnisend.</span></span>

## <a name="set-up-connection-to-omnisend"></a><span data-ttu-id="afcc0-113">Configurar conexão com o Omnisend</span><span class="sxs-lookup"><span data-stu-id="afcc0-113">Set up connection to Omnisend</span></span>

1. <span data-ttu-id="afcc0-114">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="afcc0-114">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="afcc0-115">Selecione **Adicionar conexão** e escolha **Omnisend** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="afcc0-115">Select **Add connection** and choose **Omnisend** to configure the connection.</span></span>

1. <span data-ttu-id="afcc0-116">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="afcc0-116">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="afcc0-117">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="afcc0-117">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="afcc0-118">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="afcc0-118">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="afcc0-119">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="afcc0-119">Choose who can use this connection.</span></span> <span data-ttu-id="afcc0-120">Por padrão, são apenas administradores.</span><span class="sxs-lookup"><span data-stu-id="afcc0-120">By default it's only administrators.</span></span> <span data-ttu-id="afcc0-121">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="afcc0-121">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="afcc0-122">Insira sua [chave de API do Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span><span class="sxs-lookup"><span data-stu-id="afcc0-122">Enter your [Omnisend API key](https://support.omnisend.com/en/articles/1061890-generating-api-key).</span></span>

1. <span data-ttu-id="afcc0-123">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="afcc0-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="afcc0-124">Selecione **Conectar** para inicializar a conexão com o Omnisend.</span><span class="sxs-lookup"><span data-stu-id="afcc0-124">Select **Connect** to initialize the connection to Omnisend.</span></span>

1. <span data-ttu-id="afcc0-125">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="afcc0-125">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="afcc0-126">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="afcc0-126">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="afcc0-127">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="afcc0-127">Configure an export</span></span>

<span data-ttu-id="afcc0-128">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="afcc0-128">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="afcc0-129">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="afcc0-129">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="afcc0-130">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="afcc0-130">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="afcc0-131">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="afcc0-131">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="afcc0-132">No campo **Conexão para exportação**, escolha uma conexão da seção do Omnisend.</span><span class="sxs-lookup"><span data-stu-id="afcc0-132">In the **Connection for export** field, choose a connection from the Omnisend section.</span></span> <span data-ttu-id="afcc0-133">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="afcc0-133">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="afcc0-134">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="afcc0-134">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="afcc0-135">A exportação de segmentos para o Omnisend é necessária.</span><span class="sxs-lookup"><span data-stu-id="afcc0-135">It's required to export segments to Omnisend.</span></span> <span data-ttu-id="afcc0-136">Opcionalmente, você pode exportar Nome, Sobrenome, Endereço, País/Região, Estado, Cidade e CEP para criar emails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="afcc0-136">Optionally, you can export First name, Last name, Address, Country/Region, State, City, and Post Code to create more personalized emails.</span></span> <span data-ttu-id="afcc0-137">Selecione **Adicionar atributo** para mapear esses campos.</span><span class="sxs-lookup"><span data-stu-id="afcc0-137">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="afcc0-138">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="afcc0-138">Select **Save**.</span></span>

<span data-ttu-id="afcc0-139">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="afcc0-139">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="afcc0-140">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="afcc0-140">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="afcc0-141">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="afcc0-141">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="afcc0-142">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="afcc0-142">Data privacy and compliance</span></span>

<span data-ttu-id="afcc0-143">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Ommisend, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="afcc0-143">When you enable Dynamics 365 Customer Insights to transmit data to Ommisend, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="afcc0-144">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Ommisend atenda a todas as obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="afcc0-144">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Omnisend meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="afcc0-145">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="afcc0-145">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="afcc0-146">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="afcc0-146">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
