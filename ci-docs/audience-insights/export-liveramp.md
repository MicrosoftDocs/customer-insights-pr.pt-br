---
title: Conector LiveRamp
description: Saiba como exportar dados para o LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 86aa8c66a47ee61741082c95f05d2e5ce3f06f35
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667170"
---
# <a name="liverampreg-connector-preview"></a><span data-ttu-id="f6a91-103">Conector do LiveRamp&reg; (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="f6a91-103">LiveRamp&reg; connector (preview)</span></span>

<span data-ttu-id="f6a91-104">Ative seus dados no LiveRamp para conectar-se a mais de 500 plataformas nos ecossistemas digital, social e de TV.</span><span class="sxs-lookup"><span data-stu-id="f6a91-104">Activate your data in LiveRamp to connect with over 500 platforms across digital, social, and TV ecosystems.</span></span> <span data-ttu-id="f6a91-105">Trabalhe com seus dados no LiveRamp para segmentar, suprimir e personalizar campanhas publicitárias.</span><span class="sxs-lookup"><span data-stu-id="f6a91-105">Work with your data in LiveRamp to target, suppress, and personalize ad campaigns.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f6a91-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f6a91-106">Prerequisites</span></span>

- <span data-ttu-id="f6a91-107">Você precisa de uma assinatura do LiveRamp para usar esse conector.</span><span class="sxs-lookup"><span data-stu-id="f6a91-107">You need a LiveRamp subscription to use this connector.</span></span>
- <span data-ttu-id="f6a91-108">Para obter uma assinatura, [entre em contato com a LiveRamp](https://liveramp.com/contact/) diretamente.</span><span class="sxs-lookup"><span data-stu-id="f6a91-108">To get a subscription, [contact LiveRamp](https://liveramp.com/contact/) directly.</span></span> <span data-ttu-id="f6a91-109">[Saiba mais sobre o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span><span class="sxs-lookup"><span data-stu-id="f6a91-109">[Learn more about LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).</span></span>

## <a name="connect-to-liveramp"></a><span data-ttu-id="f6a91-110">Conectar-se ao LiveRamp</span><span class="sxs-lookup"><span data-stu-id="f6a91-110">Connect to LiveRamp</span></span>

1. <span data-ttu-id="f6a91-111">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="f6a91-111">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="f6a91-112">No bloco **LiveRamp**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="f6a91-112">In the **LiveRamp** tile, select **Set up**.</span></span>

1. <span data-ttu-id="f6a91-113">Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="f6a91-113">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="f6a91-114">Forneça um **Nome do usuário** e uma **Senha** para sua conta do LiveRamp Secure FTP (SFTP).</span><span class="sxs-lookup"><span data-stu-id="f6a91-114">Provide a **Username** and **Password** for your LiveRamp Secure FTP (SFTP) account.</span></span>
<span data-ttu-id="f6a91-115">Essas credenciais podem ser diferentes das credenciais do LiveRamp Onboarding.</span><span class="sxs-lookup"><span data-stu-id="f6a91-115">These credentials may be different from your LiveRamp Onboarding credentials.</span></span>

1. <span data-ttu-id="f6a91-116">Selecione **Verificar** para testar a conexão com o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6a91-116">Select **Verify** to test the connection to LiveRamp.</span></span>

1. <span data-ttu-id="f6a91-117">Após a verificação bem-sucedida, forneça seu consentimento para **Privacidade e conformidade de dados** marcando a caixa de seleção **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="f6a91-117">After successful verification, provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="f6a91-118">Selecione **Avançar** para configurar o conector LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6a91-118">Select **Next** to set up the LiveRamp connector.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="f6a91-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="f6a91-119">Configure the connector</span></span>

1. <span data-ttu-id="f6a91-120">No campo **Escolha seu identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar ao LiveRamp para resolução de identidade.</span><span class="sxs-lookup"><span data-stu-id="f6a91-120">In the **Choose your key identifier** field, select **Email**,  **Name and address**, or **Phone** to send to LiveRamp for identity resolution.</span></span>

1. <span data-ttu-id="f6a91-121">Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.</span><span class="sxs-lookup"><span data-stu-id="f6a91-121">Map the corresponding attributes from your unified customer entity for the selected key identifier.</span></span>

1. <span data-ttu-id="f6a91-122">Selecione **Adicionar atributo** para mapear atributos adicionais para enviar ao LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6a91-122">Select **Add attribute** to map additional attributes to send to LiveRamp.</span></span>

   > [!TIP]
   > <span data-ttu-id="f6a91-123">Enviar mais atributos de identificador de chave para o LiveRamp provavelmente resultará em uma taxa de correspondência mais alta.</span><span class="sxs-lookup"><span data-stu-id="f6a91-123">Sending more key identifier attributes to LiveRamp is likely to get you a higher match rate.</span></span>

1. <span data-ttu-id="f6a91-124">Selecione os segmentos que você deseja exportar para o LiveRamp.</span><span class="sxs-lookup"><span data-stu-id="f6a91-124">Select the segments you want to export to LiveRamp.</span></span>

1. <span data-ttu-id="f6a91-125">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f6a91-125">Select **Save**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f6a91-126">![Conector LiveRamp com mapeamento de atributos](media/export-liveramp-segments.png "Conector LiveRamp com mapeamento de atributos")</span><span class="sxs-lookup"><span data-stu-id="f6a91-126">![LiveRamp connector with attribute mapping](media/export-liveramp-segments.png "LiveRamp connector with attribute mapping")</span></span>

## <a name="export-the-data"></a><span data-ttu-id="f6a91-127">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="f6a91-127">Export the data</span></span>

<span data-ttu-id="f6a91-128">A exportação começará em breve se todos os pré-requisitos para exportação tiverem sido concluídos.</span><span class="sxs-lookup"><span data-stu-id="f6a91-128">The export will start shortly if all prerequisites for export have been completed.</span></span> <span data-ttu-id="f6a91-129">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="f6a91-129">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>
<span data-ttu-id="f6a91-130">Depois que a exportação for concluída com êxito, você poderá entrar no LiveRamp Onboarding para ativar e distribuir seus dados.</span><span class="sxs-lookup"><span data-stu-id="f6a91-130">Once the export is successfully completed, you can sign in to LiveRamp Onboarding to activate and distribute your data.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="f6a91-131">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="f6a91-131">Data privacy and compliance</span></span>

<span data-ttu-id="f6a91-132">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Liveramp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="f6a91-132">When you enable Dynamics 365 Customer Insights to transmit data to Liveramp, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="f6a91-133">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Liveramp cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="f6a91-133">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Liveramp meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="f6a91-134">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="f6a91-134">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="f6a91-135">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="f6a91-135">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>