---
title: Exportar dados do Customer Insights para o SendGrid
description: Saiba como configurar a conexão com o SendGrid.
ms.date: 12/08/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: f16d69deb2a0b48270ed04f9b72f03056f20b619
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268718"
---
# <a name="connector-for-sendgrid-preview"></a><span data-ttu-id="b4eec-103">Conector para SendGrid (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="b4eec-103">Connector for SendGrid (preview)</span></span>

<span data-ttu-id="b4eec-104">Exporte segmentos de perfis de clientes unificados para as listas de contato do SendGrid e use-os para campanhas e marketing por email no SendGrid.</span><span class="sxs-lookup"><span data-stu-id="b4eec-104">Export segments of unified customer profiles to SendGrid contact lists and use them for campaigns and email marketing in SendGrid.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="b4eec-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b4eec-105">Prerequisites</span></span>

-   <span data-ttu-id="b4eec-106">Você deve ter uma [conta do SendGrid](https://sendgrid.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="b4eec-106">You have a [SendGrid account](https://sendgrid.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="b4eec-107">Há listas de contato existentes no SendGrid e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="b4eec-107">There are existing contact lists in SendGrid and the corresponding IDs.</span></span> <span data-ttu-id="b4eec-108">Para obter mais informações, consulte [SendGrid – Gerenciar contatos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span><span class="sxs-lookup"><span data-stu-id="b4eec-108">For more information, see [SendGrid - Manage contacts](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).</span></span>
-   <span data-ttu-id="b4eec-109">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="b4eec-109">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="b4eec-110">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="b4eec-110">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-sendgrid"></a><span data-ttu-id="b4eec-111">Conectar-se ao SendGrid</span><span class="sxs-lookup"><span data-stu-id="b4eec-111">Connect to SendGrid</span></span>

1. <span data-ttu-id="b4eec-112">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="b4eec-112">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="b4eec-113">Em **SendGrid**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="b4eec-113">Under **SendGrid**, select **Set up**.</span></span>

1. <span data-ttu-id="b4eec-114">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="b4eec-114">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Painel de configuração de exportação do SendGrid.":::

1. <span data-ttu-id="b4eec-116">Insira a **Chave de API do SendGrid** [Chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span><span class="sxs-lookup"><span data-stu-id="b4eec-116">Enter your **SendGrid API key** [SendGrid API key](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).</span></span>

1. <span data-ttu-id="b4eec-117">Insira a **[ID de lista do SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span><span class="sxs-lookup"><span data-stu-id="b4eec-117">Enter your **[SendGrid list ID](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.</span></span>

1. <span data-ttu-id="b4eec-118">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="b4eec-118">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="b4eec-119">Selecione **Conectar** para inicializar a conexão com o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="b4eec-119">Select **Connect** to initialize the connection to SendGrid.</span></span>

1. <span data-ttu-id="b4eec-120">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="b4eec-120">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="b4eec-121">Selecione **Próximo** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="b4eec-121">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="b4eec-122">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="b4eec-122">Configure the connector</span></span>

1. <span data-ttu-id="b4eec-123">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="b4eec-123">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="b4eec-124">Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**, **País/Região**, **Estado**, **Cidade** e **CEP**.</span><span class="sxs-lookup"><span data-stu-id="b4eec-124">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Country/Region**, **State**, **City**, and **Post code**.</span></span>

1. <span data-ttu-id="b4eec-125">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="b4eec-125">Select the segments you want to export.</span></span> <span data-ttu-id="b4eec-126">É altamente **recomendável não exportar mais de 100.000 perfis de clientes no total** para o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="b4eec-126">We strongly **recommend to not export more than 100'000 customer profiles in total** to SendGrid.</span></span> 

1. <span data-ttu-id="b4eec-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="b4eec-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="b4eec-128">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="b4eec-128">Export the data</span></span>

<span data-ttu-id="b4eec-129">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="b4eec-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="b4eec-130">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="b4eec-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="b4eec-131">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="b4eec-131">Known limitations</span></span>

- <span data-ttu-id="b4eec-132">Até 100.000 perfis no total para o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="b4eec-132">Up to 100'000 profiles in total to SendGrid.</span></span>
- <span data-ttu-id="b4eec-133">A exportação para o SendGrid é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="b4eec-133">Exporting to SendGrid is limited to segments.</span></span>
- <span data-ttu-id="b4eec-134">A exportação de até 100.000 perfis para o SendGrid pode levar até algumas horas para ser concluída.</span><span class="sxs-lookup"><span data-stu-id="b4eec-134">Exporting up to 100'000 profiles to SendGrid can take up to a few hours to complete.</span></span> 
- <span data-ttu-id="b4eec-135">O número de perfis que você pode exportar para o SendGrid depende e está limitado ao seu contrato com o SendGrid.</span><span class="sxs-lookup"><span data-stu-id="b4eec-135">The number of profiles that you can export to SendGrid is dependent and limited on your contract with SendGrid.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="b4eec-136">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="b4eec-136">Data privacy and compliance</span></span>

<span data-ttu-id="b4eec-137">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao SendGrid, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como Dados Pessoais.</span><span class="sxs-lookup"><span data-stu-id="b4eec-137">When you enable Dynamics 365 Customer Insights to transmit data to SendGrid, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="b4eec-138">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o SendGrid cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="b4eec-138">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that SendGrid meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="b4eec-139">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="b4eec-139">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="b4eec-140">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="b4eec-140">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]