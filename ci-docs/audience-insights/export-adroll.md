---
title: Exportar dados do Customer Insights para o AdRoll
description: Saiba como configurar a conexão com o AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697060"
---
# <a name="connector-for-adroll-preview"></a><span data-ttu-id="cf24f-103">Conector para AdRoll (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="cf24f-103">Connector for AdRoll (preview)</span></span>

<span data-ttu-id="cf24f-104">Exporte segmentos de perfis de clientes unificados para o AdRoll e use-os para publicidade.</span><span class="sxs-lookup"><span data-stu-id="cf24f-104">Export segments of unified customer profiles to AdRoll and use them for advertising.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="cf24f-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="cf24f-105">Prerequisites</span></span>

-   <span data-ttu-id="cf24f-106">Você deve ter uma [conta do AdRoll](https://www.adroll.com/) e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="cf24f-106">You have an [AdRoll account](https://www.adroll.com/) and corresponding administrator credentials.</span></span>
-   <span data-ttu-id="cf24f-107">Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="cf24f-107">You have [configured segments](segments.md) in audience insights.</span></span>
-   <span data-ttu-id="cf24f-108">Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.</span><span class="sxs-lookup"><span data-stu-id="cf24f-108">Unified customer profiles in the exported segments contain a field representing an email address.</span></span>

## <a name="connect-to-adroll"></a><span data-ttu-id="cf24f-109">Conectar-se ao AdRoll</span><span class="sxs-lookup"><span data-stu-id="cf24f-109">Connect to AdRoll</span></span>

1. <span data-ttu-id="cf24f-110">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="cf24f-110">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="cf24f-111">Em **AdRoll**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="cf24f-111">Under **AdRoll**, select **Set up**.</span></span>

1. <span data-ttu-id="cf24f-112">Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="cf24f-112">Give your export destination a recognizable name in the **Display name** field.</span></span>

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Painel de configuração para conexão do AdRoll.":::

1. <span data-ttu-id="cf24f-114">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="cf24f-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="cf24f-115">Selecione **Conectar** para inicializar a conexão com o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="cf24f-115">Select **Connect** to initialize the connection to AdRoll.</span></span>

1. <span data-ttu-id="cf24f-116">Selecione **Autenticar com o AdRoll** e forneça suas credenciais de administrador do AdRoll.</span><span class="sxs-lookup"><span data-stu-id="cf24f-116">Select **Authenticate with AdRoll** and provide your admin credentials for AdRoll.</span></span> 

1. <span data-ttu-id="cf24f-117">Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="cf24f-117">Select **Add yourself as export user** and provide your Customer Insights credentials.</span></span>

1. <span data-ttu-id="cf24f-118">Insira sua **ID de Anunciante do AdRoll** [Anunciável no AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span><span class="sxs-lookup"><span data-stu-id="cf24f-118">Enter your **AdRoll Advertiser ID** [AdRoll Advertisable](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).</span></span>

1. <span data-ttu-id="cf24f-119">Selecione **Próximo** para configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="cf24f-119">Select **Next** to configure the export.</span></span>

## <a name="configure-the-connector"></a><span data-ttu-id="cf24f-120">Configurar o conector</span><span class="sxs-lookup"><span data-stu-id="cf24f-120">Configure the connector</span></span>

1. <span data-ttu-id="cf24f-121">Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente.</span><span class="sxs-lookup"><span data-stu-id="cf24f-121">In the **Data matching** section, in the **Email** field, select the field in your unified customer profile that represents a customer's email address.</span></span> <span data-ttu-id="cf24f-122">É necessário exportar os segmentos para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="cf24f-122">It's required to export segments to AdRoll.</span></span>

1. <span data-ttu-id="cf24f-123">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="cf24f-123">Select the segments you want to export.</span></span> <span data-ttu-id="cf24f-124">Selecione um segmento com pelo menos 100 membros.</span><span class="sxs-lookup"><span data-stu-id="cf24f-124">Select a segment with a least 100 members.</span></span> <span data-ttu-id="cf24f-125">Você não poderá exportar segmentos menores.</span><span class="sxs-lookup"><span data-stu-id="cf24f-125">You can't export smaller segments.</span></span> <span data-ttu-id="cf24f-126">Além disso, o tamanho máximo de um segmento para exportação é de 250.000 membros por exportação.</span><span class="sxs-lookup"><span data-stu-id="cf24f-126">Additionally the maximum size of a segment to export is 250'000 members per export.</span></span> 

1. <span data-ttu-id="cf24f-127">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cf24f-127">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="cf24f-128">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="cf24f-128">Export the data</span></span>

<span data-ttu-id="cf24f-129">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="cf24f-129">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="cf24f-130">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="cf24f-130">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="cf24f-131">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="cf24f-131">Known limitations</span></span>

- <span data-ttu-id="cf24f-132">É possível exportar até 250.000 perfis por vez para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="cf24f-132">You can export up to 250'000 profiles in per export to AdRoll.</span></span>
- <span data-ttu-id="cf24f-133">Não é possível exportar segmentos com menos de 100 perfis para o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="cf24f-133">You can't export segments with fewer than 100 profiles to AdRoll.</span></span> 
- <span data-ttu-id="cf24f-134">A exportação para o AdRoll é limitada a segmentos.</span><span class="sxs-lookup"><span data-stu-id="cf24f-134">Exporting to AdRoll is limited to segments.</span></span>
- <span data-ttu-id="cf24f-135">Exportar até 250.000 perfis para AdRoll pode levar até 10 minutos para a conclusão.</span><span class="sxs-lookup"><span data-stu-id="cf24f-135">Exporting up to 250'000 profiles to AdRoll can take up to 10 minutes to complete.</span></span> 
- <span data-ttu-id="cf24f-136">O número de perfis que você pode exportar para o AdRoll depende e está limitado ao seu contrato com o AdRoll.</span><span class="sxs-lookup"><span data-stu-id="cf24f-136">The number of profiles that you can export to AdRoll is dependent and limited on your contract with AdRoll.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="cf24f-137">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="cf24f-137">Data privacy and compliance</span></span>

<span data-ttu-id="cf24f-138">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao AdRoll, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="cf24f-138">When you enable Dynamics 365 Customer Insights to transmit data to AdRoll, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="cf24f-139">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o AdRoll cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="cf24f-139">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that AdRoll meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="cf24f-140">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="cf24f-140">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>

<span data-ttu-id="cf24f-141">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="cf24f-141">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
