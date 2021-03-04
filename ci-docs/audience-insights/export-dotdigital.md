---
title: Exportar dados do Customer Insights para o DotDigital
description: Saiba como configurar a conexão com o DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 573a22e24f84c65fc4d21faf823cace801cc7ea3
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269086"
---
# <a name="connector-for-dotdigital-preview"></a><span data-ttu-id="76c80-103">Conector para DotDigital (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="76c80-103">Connector for DotDigital (preview)</span></span>

<span data-ttu-id="76c80-104">Exporte segmentos de perfis de clientes unificados para catálogos de endereços do DotDigital e use-os para campanhas, marketing por email e para criar segmentos de clientes com o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="76c80-104">Export segments of unified customer profiles to DotDigital address books and use them for campaigns, email marketing, and to build customer segments with DotDigital.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="76c80-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="76c80-105">Prerequisites</span></span>

-   <span data-ttu-id="76c80-106">Você deve ter uma [conta do DotDigital](https://dotdigital.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="76c80-106">You have a [DotDigital account](https://dotdigital.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="76c80-107">Há catálogos de endereços existentes no DotDigital e as IDs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="76c80-107">There are existing address books in DotDigital and the corresponding IDs.</span></span> <span data-ttu-id="76c80-108">A ID pode ser encontrada na URL ao selecionar e abrir um catálogo de endereços.</span><span class="sxs-lookup"><span data-stu-id="76c80-108">The ID can be found in the URL when you select and open an address book.</span></span> <span data-ttu-id="76c80-109">Para obter mais informações, consulte [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="76c80-109">For more information, see [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>
-   <span data-ttu-id="76c80-110">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="76c80-110">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="76c80-111">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="76c80-111">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-dotdigital"></a><span data-ttu-id="76c80-112">Conectar-se ao DotDigital</span><span class="sxs-lookup"><span data-stu-id="76c80-112">Connect to DotDigital</span></span>

1. <span data-ttu-id="76c80-113">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="76c80-113">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="76c80-114">Em **DotDigital**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="76c80-114">Under **DotDigital**, select **Set up**.</span></span>

1. <span data-ttu-id="76c80-115">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="76c80-115">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Painel de configuração da exportação para o DotDigital.":::

1. <span data-ttu-id="76c80-117">Insira seu **nome de usuário e senha do DotDigital**.</span><span class="sxs-lookup"><span data-stu-id="76c80-117">Enter your **DotDigital username and password**.</span></span>

1. <span data-ttu-id="76c80-118">Insira sua **[ID do catálogo de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span><span class="sxs-lookup"><span data-stu-id="76c80-118">Enter your **[DotDigital address book ID](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.</span></span>

1. <span data-ttu-id="76c80-119">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="76c80-119">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="76c80-120">Selecione **Conectar** para inicializar a conexão com o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="76c80-120">Select **Connect** to initialize the connection to DotDigital.</span></span>

1. <span data-ttu-id="76c80-121">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="76c80-121">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="76c80-122">Selecione **Próximo** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="76c80-122">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="76c80-123">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="76c80-123">Configure the connector</span></span>

1. <span data-ttu-id="76c80-124">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="76c80-124">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="76c80-125">Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**, **Nome completo**, **Gênero** e **Código postal**.</span><span class="sxs-lookup"><span data-stu-id="76c80-125">Repeat the same steps for other optional fields such as **First name**, **Last name**, **Full name**, **Gender**, and **Post code**.</span></span>

1. <span data-ttu-id="76c80-126">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="76c80-126">Select the segments you want to export.</span></span> <span data-ttu-id="76c80-127">Você pode exportar até 1 milhão de perfis de clientes no total para o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="76c80-127">You can export up to 1 million customer profiles in total to DotDigital.</span></span>

1. <span data-ttu-id="76c80-128">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="76c80-128">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="76c80-129">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="76c80-129">Export the data</span></span>

<span data-ttu-id="76c80-130">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="76c80-130">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="76c80-131">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="76c80-131">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="76c80-132">No DotDigital, agora você pode encontrar seus segmentos nos [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span><span class="sxs-lookup"><span data-stu-id="76c80-132">In DotDigital, you can now find your segments in [DotDigital address books](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="76c80-133">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="76c80-133">Known limitations</span></span>

- <span data-ttu-id="76c80-134">Até 1 milhão de perfis por exportação para o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="76c80-134">Up to 1 million profiles per export to DotDigital.</span></span>
- <span data-ttu-id="76c80-135">A exportação para o DotDigital é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="76c80-135">Exporting to DotDigital is limited to segments.</span></span>
- <span data-ttu-id="76c80-136">A exportação de segmentos com um total de 1 milhão de perfis pode levar até 3 horas devido a limitações do provedor.</span><span class="sxs-lookup"><span data-stu-id="76c80-136">Exporting segments with a total of 1 million profiles can take up to 3 hours because of limitations on the provider side.</span></span> 
- <span data-ttu-id="76c80-137">O número de perfis que você pode exportar para o DotDigital depende e está limitado ao seu contrato com o DotDigital.</span><span class="sxs-lookup"><span data-stu-id="76c80-137">The number of profiles that you can export to DotDigital is dependent and limited on your contract with DotDigital.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="76c80-138">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="76c80-138">Data privacy and compliance</span></span>

<span data-ttu-id="76c80-139">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao DotDigital, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="76c80-139">When you enable Dynamics 365 Customer Insights to transmit data to DotDigital, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="76c80-140">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o DotDigital cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="76c80-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that DotDigital meet any privacy or security obligations you may have.</span></span> <span data-ttu-id="76c80-141">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="76c80-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="76c80-142">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="76c80-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]