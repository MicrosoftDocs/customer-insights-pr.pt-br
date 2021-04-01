---
title: Exportar dados do Customer Insights para o Autopilot
description: Saiba como configurar a conexão com o Autopilot.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6d039c4afd84eaad942d214d4e6fb8ef7b1ec72a
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596110"
---
# <a name="connector-for-autopilot-preview"></a><span data-ttu-id="b931a-103">Conector para Autopilot (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="b931a-103">Connector for Autopilot (preview)</span></span>

<span data-ttu-id="b931a-104">Exporte segmentos de perfis de clientes unificados para o Autopilot e use-os para marketing por email no Autopilot.</span><span class="sxs-lookup"><span data-stu-id="b931a-104">Export segments of unified customer profiles to Autopilot and use them for email marketing in Autopilot.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b931a-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b931a-105">Prerequisites</span></span>

-   <span data-ttu-id="b931a-106">Você deve ter uma [conta do Autopilot](https://www.autopilothq.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="b931a-106">You have an [Autopilot account](https://www.autopilothq.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b931a-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="b931a-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b931a-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="b931a-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-autopilot"></a><span data-ttu-id="b931a-109">Conectar ao Autopilot</span><span class="sxs-lookup"><span data-stu-id="b931a-109">Connect to Autopilot</span></span>

1. <span data-ttu-id="b931a-110">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="b931a-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b931a-111">Em **Autopilot**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b931a-111">Under **Autopilot**, select **Set up**.</span></span>

1. <span data-ttu-id="b931a-112">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="b931a-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-autopilot.PNG" alt-text="Painel de configuração para conexão do Autopilot.":::

1. <span data-ttu-id="b931a-114">Insira a **Chave de API do Autopilot** [Chave de API do Autopilot](https://autopilot.docs.apiary.io/#).</span><span class="sxs-lookup"><span data-stu-id="b931a-114">Enter your **Autopilot API key** [Autopilot API key](https://autopilot.docs.apiary.io/#).</span></span>

1. <span data-ttu-id="b931a-115">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="b931a-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b931a-116">Selecione **Conectar** para inicializar a conexão com o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="b931a-116">Select **Connect** to initialize the connection to Autopilot.</span></span>

1. <span data-ttu-id="b931a-117">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b931a-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b931a-118">Selecione **Próximo** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="b931a-118">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b931a-119">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="b931a-119">Configure the connector</span></span>

1. <span data-ttu-id="b931a-120">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="b931a-120">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b931a-121">Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**.</span><span class="sxs-lookup"><span data-stu-id="b931a-121">Repeat the same steps for other optional fields such as **First name**, **Last name**.</span></span>

1. <span data-ttu-id="b931a-122">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="b931a-122">Select the segments you want to export.</span></span> <span data-ttu-id="b931a-123">É altamente **recomendável não exportar mais de 100.000 perfis de clientes no total** para o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="b931a-123">We strongly **recommend to not export more than 100'000 customer profiles in total** to Autopilot.</span></span> 

1. <span data-ttu-id="b931a-124">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b931a-124">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b931a-125">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="b931a-125">Export the data</span></span>

<span data-ttu-id="b931a-126">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b931a-126">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b931a-127">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b931a-127">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b931a-128">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="b931a-128">Known limitations</span></span>

- <span data-ttu-id="b931a-129">Você pode exportar até 100.000 perfis de clientes no total para o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="b931a-129">You can export up to 100'000 profiles in total to Autopilot.</span></span>
- <span data-ttu-id="b931a-130">A exportação para o Autopilot é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="b931a-130">Exporting to Autopilot is limited to segments.</span></span>
- <span data-ttu-id="b931a-131">A exportação de até 100.000 perfis para o Autopilot pode levar até algumas horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="b931a-131">Exporting up to 100'000 profiles to Autopilot can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="b931a-132">O número de perfis que você pode exportar para o Autopilot depende e está limitado ao seu contrato com o Autopilot.</span><span class="sxs-lookup"><span data-stu-id="b931a-132">The number of profiles that you can export to Autopilot is dependent and limited on your contract with Autopilot.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b931a-133">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="b931a-133">Data privacy and compliance</span></span>

<span data-ttu-id="b931a-134">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Autopilot, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="b931a-134">When you enable Dynamics 365 Customer Insights to transmit data to Autopilot, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b931a-135">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Autopilot cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="b931a-135">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Autopilot meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b931a-136">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b931a-136">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b931a-137">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="b931a-137">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]