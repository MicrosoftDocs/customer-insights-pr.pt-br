---
title: Exportar dados do Customer Insights para o DotDigital
description: Saiba como configurar a conexão e exportar para o DotDigital.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8b0bda638c9bc7bb9cb2fdb01be11489b44f28a5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124397"
---
# <a name="export-segments-to-dotdigital-preview"></a><span data-ttu-id="6ccc3-103">Exportar segmentos para o DotDigital (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="6ccc3-103">Export segments to DotDigital (preview)</span></span>

<span data-ttu-id="6ccc3-104">Exporte segmentos de perfis de clientes unificados para catálogos de endereços do DotDigital e use-os para campanhas, marketing por email e para criar segmentos de clientes com o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="6ccc3-105">Pré-requisitos para uma conexão</span><span class="sxs-lookup"><span data-stu-id="6ccc3-105">Prerequisites for a connection</span></span>

-   <span data-ttu-id="6ccc3-106">Você deve ter uma [conta do DotDigital](https://dotdigital.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="6ccc3-107">Há catálogos de endereços existentes no DotDigital e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="6ccc3-108">A ID pode ser encontrada na URL ao selecionar e abrir um catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="6ccc3-109">Para obter mais informações, consulte [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="6ccc3-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="6ccc3-110">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="6ccc3-111">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="6ccc3-112">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="6ccc3-112">Known limitations</span></span>

- <span data-ttu-id="6ccc3-113">Até 1 milhão de perfis por exportação para o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-113">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="6ccc3-114">A exportação para o DotDigital é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-114">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="6ccc3-115">A exportação de segmentos com um total de 1 milhão de perfis pode levar até 3 horas devido a limitações do provedor.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-115">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="6ccc3-116">O número de perfis que você pode exportar para o DotDigital depende e está limitado ao seu contrato com o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-116">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="set-up-connection-to-dotdigital"></a><span data-ttu-id="6ccc3-117">Configurar conexão com o DotDigital</span><span class="sxs-lookup"><span data-stu-id="6ccc3-117">Set up connection to DotDigital</span></span>

1. <span data-ttu-id="6ccc3-118">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-118">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="6ccc3-119">Selecione **Adicionar conexão** e escolha **DotDigital** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-119">Select **Add connection** and choose **DotDigital** to configure the connection.</span></span>

1. <span data-ttu-id="6ccc3-120">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-120">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="6ccc3-121">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-121">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="6ccc3-122">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-122">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="6ccc3-123">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-123">Choose who can use this connection.</span></span> <span data-ttu-id="6ccc3-124">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-124">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="6ccc3-125">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="6ccc3-125">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="6ccc3-126">Insira seu **nome de usuário e senha do DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-126">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="6ccc3-127">Insira sua **[ID do catálogo de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-127">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="6ccc3-128">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-128">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="6ccc3-129">Selecione **Conectar** para inicializar a conexão com o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-129">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="6ccc3-130">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-130">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="6ccc3-131">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-131">Select **Save** to complete the connection.</span></span> 

## <a name="configure-an-export"></a><span data-ttu-id="6ccc3-132">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="6ccc3-132">Configure an export</span></span>

<span data-ttu-id="6ccc3-133">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-133">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="6ccc3-134">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="6ccc3-134">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="6ccc3-135">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-135">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="6ccc3-136">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-136">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="6ccc3-137">No campo **Conexão para exportação**, escolha uma conexão da seção do DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-137">In the **Connection for export** field, choose a connection from the DotDigital section.</span></span> <span data-ttu-id="6ccc3-138">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-138">If you don't see this section name, there are no connections of this type available to you.</span></span>


1. <span data-ttu-id="6ccc3-139">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-139">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="6ccc3-140">Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**, **Nome completo**, **Gênero** e **Código postal**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-140">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="6ccc3-141">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-141">Select the segments you want to export.</span></span> <span data-ttu-id="6ccc3-142">Você pode exportar até 1 milhão de perfis de clientes no total para o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-142">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="6ccc3-143">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-143">Select **Save**.</span></span>

<span data-ttu-id="6ccc3-144">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-144">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="6ccc3-145">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="6ccc3-145">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="6ccc3-146">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="6ccc3-146">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 
 
<span data-ttu-id="6ccc3-147">No DotDigital, agora você pode encontrar seus segmentos nos [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="6ccc3-147">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="6ccc3-148">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="6ccc3-148">Data privacy and compliance</span></span>

<span data-ttu-id="6ccc3-149">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao DotDigital, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-149">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="6ccc3-150">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o DotDigital cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-150">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="6ccc3-151">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="6ccc3-151">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="6ccc3-152">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="6ccc3-152">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
