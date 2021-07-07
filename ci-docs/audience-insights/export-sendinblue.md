---
title: Exportar dados do Customer Insights para o Sendinblue
description: Saiba como configurar a conexão e exportar para o Sendinblue.
ms.date: 06/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58ca0ae5ad4a3a291f4336984d14fefb23a58ab3
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314574"
---
# <a name="export-segments-to-sendinblue-preview"></a><span data-ttu-id="65ad8-103">Exportar segmentos para o Sendinblue (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="65ad8-103">Export segments to Sendinblue (preview)</span></span>

<span data-ttu-id="65ad8-104">Exporte segmentos de perfis de cliente unificados para gerar campanhas, fornecer marketing por email e usar grupos de clientes específicos com o Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="65ad8-104">Export segments of unified customer profiles to generate campaigns, provide email marketing and use specific groups of customers with Sendinblue.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="65ad8-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="65ad8-105">Prerequisites for connection</span></span>

-   <span data-ttu-id="65ad8-106">Você tem uma [conta do Sendinblue](https://www.sendinblue.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="65ad8-106">You have a [Sendinblue account](https://www.sendinblue.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="65ad8-107">Há listas existentes no Sendinblue e os IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="65ad8-107">There are existing lists in Sendinblue and the corresponding IDs.</span></span>
-   <span data-ttu-id="65ad8-108">Você deve ter [segmentos configurados](segments.md).</span><span class="sxs-lookup"><span data-stu-id="65ad8-108">You have [configured segments](segments.md).</span></span>
-   <span data-ttu-id="65ad8-109">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="65ad8-109">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="65ad8-110">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="65ad8-110">Known limitations</span></span>

- <span data-ttu-id="65ad8-111">Até 1 milhão de perfis por exportação para o Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="65ad8-111">Up to 1 million profiles per export to Sendinblue.</span></span>
- <span data-ttu-id="65ad8-112">A exportação para o Sendinblue é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="65ad8-112">Exporting to Sendinblue is limited to segments.</span></span>
- <span data-ttu-id="65ad8-113">A exportação de segmentos com um total de 1 milhão de perfis pode levar até 90 minutos.</span><span class="sxs-lookup"><span data-stu-id="65ad8-113">Exporting segments with a total of 1 million profiles can take up to 90 minutes.</span></span> 
- <span data-ttu-id="65ad8-114">O número de perfis que você pode exportar para a Sendinblue é dependente e limitado pelo seu contrato com a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="65ad8-114">The number of profiles that you can export to Sendinblue is dependent and limited on your contract with Sendinblue.</span></span>

## <a name="set-up-connection-to-sendinblue"></a><span data-ttu-id="65ad8-115">Configurar conexão com a Sendinblue</span><span class="sxs-lookup"><span data-stu-id="65ad8-115">Set up connection to Sendinblue</span></span>

1. <span data-ttu-id="65ad8-116">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="65ad8-116">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="65ad8-117">Selecione **Adicionar conexão** e escolha **Sendinblue** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="65ad8-117">Select **Add connection** and choose **Sendinblue** to configure the connection.</span></span>

1. <span data-ttu-id="65ad8-118">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="65ad8-118">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="65ad8-119">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="65ad8-119">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="65ad8-120">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="65ad8-120">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="65ad8-121">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="65ad8-121">Choose who can use this connection.</span></span> <span data-ttu-id="65ad8-122">Por padrão, são apenas administradores.</span><span class="sxs-lookup"><span data-stu-id="65ad8-122">By default it's only administrators.</span></span> <span data-ttu-id="65ad8-123">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="65ad8-123">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="65ad8-124">Digite sua **[Chave de API da Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span><span class="sxs-lookup"><span data-stu-id="65ad8-124">Enter your **[SendinBlue API key](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.</span></span>

1. <span data-ttu-id="65ad8-125">Selecione **Aceito** para confirmar a **Privacidade dos dados e conformidade** e selecione **Conectar** para inicializar a conexão com a Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="65ad8-125">Select **I agree** to confirm the **Data privacy and compliance** and select **Connect** to initialize the connection to Sendinblue.</span></span>

1. <span data-ttu-id="65ad8-126">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="65ad8-126">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="65ad8-127">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="65ad8-127">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="65ad8-128">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="65ad8-128">Configure an export</span></span>

<span data-ttu-id="65ad8-129">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="65ad8-129">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="65ad8-130">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="65ad8-130">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="65ad8-131">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="65ad8-131">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="65ad8-132">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="65ad8-132">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="65ad8-133">No campo **Conexão para exportação**, escolha uma conexão na seção Sendinblue.</span><span class="sxs-lookup"><span data-stu-id="65ad8-133">In the **Connection for export** field, choose a connection from the Sendinblue section.</span></span> <span data-ttu-id="65ad8-134">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="65ad8-134">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="65ad8-135">Digite seu **ID de lista da Sendinblue**</span><span class="sxs-lookup"><span data-stu-id="65ad8-135">Enter your **Sendinblue list ID**</span></span> 

1. <span data-ttu-id="65ad8-136">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="65ad8-136">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> 

1. <span data-ttu-id="65ad8-137">Como outra opção, você pode exportar o **Nome**, **Sobrenome** e **Telefone** para criar emails mais personalizados.</span><span class="sxs-lookup"><span data-stu-id="65ad8-137">Optionally, you can export **First name**, **Last name**, and **Phone**  to create more personalized emails.</span></span> <span data-ttu-id="65ad8-138">Selecione **Adicionar atributo** para mapear esses campos.</span><span class="sxs-lookup"><span data-stu-id="65ad8-138">Select **Add attribute** to map these fields.</span></span>

1. <span data-ttu-id="65ad8-139">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="65ad8-139">Select the segments you want to export.</span></span> 

1. <span data-ttu-id="65ad8-140">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="65ad8-140">Select **Save**.</span></span>

<span data-ttu-id="65ad8-141">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="65ad8-141">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="65ad8-142">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="65ad8-142">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="65ad8-143">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="65ad8-143">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="65ad8-144">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="65ad8-144">Data privacy and compliance</span></span>

<span data-ttu-id="65ad8-145">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para a Sendinblue, você permite a transferência de dados fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, tais como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="65ad8-145">When you enable Dynamics 365 Customer Insights to transmit data to Sendinblue, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="65ad8-146">A Microsoft transferirá esses dados mediante as suas instruções, mas você é responsável por garantir que a Sendinblue cumpra qualquer obrigação de privacidade ou segurança que você venha a ter.</span><span class="sxs-lookup"><span data-stu-id="65ad8-146">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Sendinblue meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="65ad8-147">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="65ad8-147">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="65ad8-148">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="65ad8-148">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
