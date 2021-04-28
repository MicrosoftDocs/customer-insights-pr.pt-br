---
title: Conector LiveRamp
description: Saiba como configurar a conexão e a exportação para o LiveRamp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 987457966fe1fc034d9e3cd2a1ce33902c7a84f4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760313"
---
# <a name="export-segments-to-liverampreg-preview"></a><span data-ttu-id="b94b9-103">Exportar segmentos para o LiveRamp&reg; (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="b94b9-103">Export segments to LiveRamp&reg; (preview)</span></span>

<span data-ttu-id="b94b9-104">Ative seus dados no LiveRamp para se conectar a mais de 500 plataformas em ecossistemas digitais, sociais e de TV.</span><span class="sxs-lookup"><span data-stu-id="b94b9-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TVs.</span></span> <span data-ttu-id="b94b9-105">Trabalhe com seus dados no LiveRamp para segmentar, suprimir e personalizar campanhas publicitárias.</span><span class="sxs-lookup"><span data-stu-id="b94b9-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites-for-a-connection"></a><span data-ttu-id="b94b9-106">Pré-requisitos para uma conexão</span><span class="sxs-lookup"><span data-stu-id="b94b9-106">Prerequisites for a connection</span></span>

- <span data-ttu-id="b94b9-107">Você precisa de uma assinatura do LiveRamp para usar esse conector.</span><span class="sxs-lookup"><span data-stu-id="b94b9-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="b94b9-108">Para obter uma assinatura, [entre em contato com a LiveRamp](https://liveramp.com/contact/) diretamente.</span><span class="sxs-lookup"><span data-stu-id="b94b9-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="b94b9-109">[Saiba mais sobre o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="b94b9-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="set-up-connection-to-liveramp"></a><span data-ttu-id="b94b9-110">Configurar conexão com o LiveRamp</span><span class="sxs-lookup"><span data-stu-id="b94b9-110">Set up connection to LiveRamp</span></span>

1. <span data-ttu-id="b94b9-111">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="b94b9-111">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="b94b9-112">Selecione **Adicionar conexão** e escolha **LiveRamp** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="b94b9-112">Select **Add connection** and choose **LiveRamp** to configure the connection.</span></span>

1. <span data-ttu-id="b94b9-113">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="b94b9-113">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="b94b9-114">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="b94b9-114">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="b94b9-115">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="b94b9-115">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="b94b9-116">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="b94b9-116">Choose who can use this connection.</span></span> <span data-ttu-id="b94b9-117">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="b94b9-117">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="b94b9-118">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="b94b9-118">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="b94b9-119">Forneça um **Nome do usuário** e uma **Senha** para sua conta do LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="b94b9-119">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="b94b9-120">Essas credenciais podem ser diferentes das credenciais do LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="b94b9-120">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="b94b9-121">Selecione **Verificar** para testar a conexão com o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b94b9-121">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="b94b9-122">Após a verificação bem-sucedida, forneça seu consentimento para **Privacidade e conformidade de dados** marcando a caixa de seleção **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="b94b9-122">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="b94b9-123">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="b94b9-123">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="b94b9-124">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="b94b9-124">Configure an export</span></span>

<span data-ttu-id="b94b9-125">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="b94b9-125">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="b94b9-126">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="b94b9-126">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="b94b9-127">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="b94b9-127">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="b94b9-128">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="b94b9-128">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="b94b9-129">No campo **Conexão para exportação**, escolha uma conexão da seção do LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b94b9-129">In the **Connection for export** field, choose a connection from the LiveRamp section.</span></span> <span data-ttu-id="b94b9-130">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="b94b9-130">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="b94b9-131">No campo **Escolha seu identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar ao LiveRamp para resolução de identidade.</span><span class="sxs-lookup"><span data-stu-id="b94b9-131">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="b94b9-132">![Conector LiveRamp com mapeamento de atributos](media/export-liveramp-segments.png "Conector LiveRamp com mapeamento de atributos")</span><span class="sxs-lookup"><span data-stu-id="b94b9-132">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

1. <span data-ttu-id="b94b9-133">Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="b94b9-133">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="b94b9-134">Selecione **Adicionar atributo** para mapear mais atributos para enviar para o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b94b9-134">Select **Add attribute** to map more attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="b94b9-135">Enviar mais atributos de identificador de chave para o LiveRamp provavelmente resultará em uma taxa de correspondência mais alta.</span><span class="sxs-lookup"><span data-stu-id="b94b9-135">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="b94b9-136">Selecione os segmentos que você deseja exportar para o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="b94b9-136">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="b94b9-137">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b94b9-137">Select **Save**.</span></span>

<span data-ttu-id="b94b9-138">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b94b9-138">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="b94b9-139">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b94b9-139">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="b94b9-140">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="b94b9-140">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 


## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b94b9-141">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="b94b9-141">Data privacy and compliance</span></span>

<span data-ttu-id="b94b9-142">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Liveramp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="b94b9-142">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b94b9-143">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Liveramp cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="b94b9-143">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="b94b9-144">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b94b9-144">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b94b9-145">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="b94b9-145">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
