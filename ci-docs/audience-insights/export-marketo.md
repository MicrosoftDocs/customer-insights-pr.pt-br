---
title: Exportar dados do Customer Insights para o Marketo
description: Saiba como configurar a conexão e exportar para o Marketo.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 01290d5fae7af1737b73373d75e334ae1ed67d37
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5759807"
---
# <a name="export-segments-to-marketo-preview"></a><span data-ttu-id="0903c-103">Exportar segmentos para o Marketo (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="0903c-103">Export segments to Marketo (preview)</span></span>

<span data-ttu-id="0903c-104">Exporte segmentos de perfis de clientes unificados para gerar campanhas, fornecer marketing por email e usar grupos específicos de clientes com o Marketo.</span><span class="sxs-lookup"><span data-stu-id="0903c-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Marketo.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="0903c-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="0903c-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="0903c-106">Você deve ter uma [conta do Marketo](https://login.marketo.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="0903c-106">You have a [Marketo account](https://login.marketo.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="0903c-107">Há listas existentes no Marketo e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="0903c-107">There are existing lists in Marketo and the corresponding IDs.</span></span> <span data-ttu-id="0903c-108">Para obter mais informações, consulte [listas do Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0903c-108">For more information, see [Marketo lists](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>
-   <span data-ttu-id="0903c-109">Você deve ter [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="0903c-109">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="0903c-110">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="0903c-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="0903c-111">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="0903c-111">Known limitations</span></span>

- <span data-ttu-id="0903c-112">Até 1 milhão de perfis por exportação para o Marketo.</span><span class="sxs-lookup"><span data-stu-id="0903c-112">Up to 1 million profiles per export to Marketo.</span></span>
- <span data-ttu-id="0903c-113">A exportação para o Marketo é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="0903c-113">Exporting to Marketo is limited to segments.</span></span>
- <span data-ttu-id="0903c-114">A exportação de segmentos com um total de 1 milhão de perfis pode levar até 3 horas.</span><span class="sxs-lookup"><span data-stu-id="0903c-114">Exporting segments with a total of 1 million profiles can take up to 3 hours.</span></span> 
- <span data-ttu-id="0903c-115">O número de perfis que você pode exportar para o Marketo depende e está limitado ao seu contrato com o Marketo.</span><span class="sxs-lookup"><span data-stu-id="0903c-115">The number of profiles that you can export to Marketo is dependent and limited on your contract with Marketo.</span></span>

## <a name="set-up-connection-to-marketo"></a><span data-ttu-id="0903c-116">Configurar conexão com o Marketo</span><span class="sxs-lookup"><span data-stu-id="0903c-116">Set up connection to Marketo</span></span>

1. <span data-ttu-id="0903c-117">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="0903c-117">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="0903c-118">Selecione **Adicionar conexão** e escolha **Marketo** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="0903c-118">Select **Add connection** and choose **Marketo** to configure the connection.</span></span>

1. <span data-ttu-id="0903c-119">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="0903c-119">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="0903c-120">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="0903c-120">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="0903c-121">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="0903c-121">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="0903c-122">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="0903c-122">Choose who can use this connection.</span></span> <span data-ttu-id="0903c-123">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="0903c-123">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="0903c-124">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="0903c-124">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="0903c-125">Insira **[ID de cliente do Marketo, Segredo do cliente e Nome de Host do Ponto de Extremidade REST](https://developers.marketo.com/rest-api/authentication/)**.</span><span class="sxs-lookup"><span data-stu-id="0903c-125">Enter your **[Marketo client ID, Client secret, and REST Endpoint Hostname](https://developers.marketo.com/rest-api/authentication/)**.</span></span>

1. <span data-ttu-id="0903c-126">Selecione **Aceito** para confirmar a **Conformidade e privacidade dos dados** e selecione **Conectar** para inicializar a conexão com o Marketo.</span><span class="sxs-lookup"><span data-stu-id="0903c-126">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Marketo.</span></span>

1. <span data-ttu-id="0903c-127">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="0903c-127">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="0903c-128">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="0903c-128">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="0903c-129">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="0903c-129">Configure an export</span></span>

<span data-ttu-id="0903c-130">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="0903c-130">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="0903c-131">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="0903c-131">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="0903c-132">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="0903c-132">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="0903c-133">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="0903c-133">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="0903c-134">No campo **Conexão para exportação**, escolha uma conexão da seção do Marketo.</span><span class="sxs-lookup"><span data-stu-id="0903c-134">In the **Connection for export** field, choose a connection from the Marketo section.</span></span> <span data-ttu-id="0903c-135">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="0903c-135">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="0903c-136">Insira sua **[ID de lista do Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span><span class="sxs-lookup"><span data-stu-id="0903c-136">Enter your **[Marketo list ID](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)**</span></span> 

1. <span data-ttu-id="0903c-137">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="0903c-137">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="0903c-138">Opcionalmente, você pode exportar **Nome**, **Sobrenome**, **Cidade**, **Estado** e **País/Região** para criar emails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="0903c-138">Optionally, you can export **First name**, **Last name**, **City**, **State**, and **Country/Region**  to create more personalized emails.</span></span> <span data-ttu-id="0903c-139">Selecione **Adicionar atributo** para mapear esses campos.</span><span class="sxs-lookup"><span data-stu-id="0903c-139">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="0903c-140">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="0903c-140">Select the segments you want to export.</span></span> <span data-ttu-id="0903c-141">Você pode exportar até 1 milhão de perfis de clientes no total para o Marketo.</span><span class="sxs-lookup"><span data-stu-id="0903c-141">You can export up to 1 million customer profiles in total to Marketo.</span></span>

1. <span data-ttu-id="0903c-142">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0903c-142">Select **Save**.</span></span>

<span data-ttu-id="0903c-143">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="0903c-143">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="0903c-144">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="0903c-144">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="0903c-145">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="0903c-145">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="0903c-146">No Marketo, agora você pode encontrar seus segmentos em [listas do Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span><span class="sxs-lookup"><span data-stu-id="0903c-146">In Marketo, you can now find your segments under [Marketo lists](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).</span></span>


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="0903c-147">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="0903c-147">Data privacy and compliance</span></span>

<span data-ttu-id="0903c-148">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Marketo, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="0903c-148">When you enable Dynamics 365 Customer Insights to transmit data to Marketo, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="0903c-149">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Marketo cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="0903c-149">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Marketo meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="0903c-150">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="0903c-150">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="0903c-151">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="0903c-151">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]