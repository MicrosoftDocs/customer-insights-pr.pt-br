---
title: Enriquecimento com o enriquecimento de terceiros da Experian
description: Informações gerais sobre o enriquecimento de terceiros da Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597773"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="ee958-103">Enriquecer os perfis dos clientes com dados demográficos da Experian (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="ee958-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="ee958-104">A Experian é líder global em serviços de marketing e relatórios de crédito para consumidores e empresas.</span><span class="sxs-lookup"><span data-stu-id="ee958-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="ee958-105">Com os serviços de enriquecimento de dados da Experian, você pode compreender melhor seus clientes enriquecendo os perfis desses clientes com dados demográficos, como número de pessoas na família, renda e muito mais.</span><span class="sxs-lookup"><span data-stu-id="ee958-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="ee958-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="ee958-106">Prerequisites</span></span>

<span data-ttu-id="ee958-107">Para configurar a Experian, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="ee958-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="ee958-108">Você ter uma assinatura ativa da Experian.</span><span class="sxs-lookup"><span data-stu-id="ee958-108">You have an active Experian subscription.</span></span> <span data-ttu-id="ee958-109">Para obter uma assinatura, [entre em contato com a Experian](https://www.experian.com/marketing-services/contact) diretamente.</span><span class="sxs-lookup"><span data-stu-id="ee958-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="ee958-110">[Saiba mais sobre o Enriquecimento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="ee958-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>
- <span data-ttu-id="ee958-111">Você ter a ID de Usuário, a ID do Participante e o Número do Modelo da conta de Transporte Seguro (ST) habilitada para SSH que a Experian criou para você.</span><span class="sxs-lookup"><span data-stu-id="ee958-111">You have the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>
- <span data-ttu-id="ee958-112">Você tem permissões de [Administrador](permissions.md#administrator) em insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="ee958-112">You have [Administrator](permissions.md#administrator) permissions in audience insights.</span></span>

## <a name="configuration"></a><span data-ttu-id="ee958-113">Configuração</span><span class="sxs-lookup"><span data-stu-id="ee958-113">Configuration</span></span>

1. <span data-ttu-id="ee958-114">Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="ee958-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="ee958-115">Selecione **Enriquecer meus dados** no bloco da Experian.</span><span class="sxs-lookup"><span data-stu-id="ee958-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="ee958-116">![Bloco da Experian](media/experian-tile.png "Bloco da Experian")</span><span class="sxs-lookup"><span data-stu-id="ee958-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>

1. <span data-ttu-id="ee958-117">Selecione **Começar** e insira a ID de Usuário, a ID do Participante e o Número do Modelo da sua conta de Transporte Seguro da Experian.</span><span class="sxs-lookup"><span data-stu-id="ee958-117">Select **Get started** and enter the User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span> <span data-ttu-id="ee958-118">Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="ee958-118">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span> <span data-ttu-id="ee958-119">Confirme todas as entradas selecionando **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="ee958-119">Confirm all inputs by selecting **Apply**.</span></span>

## <a name="map-your-fields"></a><span data-ttu-id="ee958-120">Mapear seus campos</span><span class="sxs-lookup"><span data-stu-id="ee958-120">Map your fields</span></span>

1.  <span data-ttu-id="ee958-121">Selecione **Adicionar dados** e escolha o **Conjunto de dados do cliente** que deseja enriquecer com dados demográficos da Experian.</span><span class="sxs-lookup"><span data-stu-id="ee958-121">Select **Add data** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="ee958-122">Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="ee958-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="ee958-123">Selecione os identificadores de chave de **Nome e Endereço**, **Email** ou **Telefone** para enviar à Experian para resolução de identidade.</span><span class="sxs-lookup"><span data-stu-id="ee958-123">Select your key identifiers from **Name and Address**, **E-mail**, or **Phone** to send to Experian for identity resolution.</span></span>

   > [!TIP]
   > <span data-ttu-id="ee958-124">Mais atributos de identificadores de chave enviados à Experian provavelmente geram uma taxa de correspondência mais alta.</span><span class="sxs-lookup"><span data-stu-id="ee958-124">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="ee958-125">Selecione **Avançar** e mapeie os atributos correspondentes da sua entidade de cliente unificada para os campos de identificadores de chave selecionados.</span><span class="sxs-lookup"><span data-stu-id="ee958-125">Select **Next** and map the corresponding attributes from your unified customer entity for the selected key identifier fields.</span></span>

1. <span data-ttu-id="ee958-126">Selecione **Adicionar atributo** para mapear quaisquer atributos adicionais que você gostaria de enviar à Experian.</span><span class="sxs-lookup"><span data-stu-id="ee958-126">Select **Add attribute** to map any additional attributes you would like to send to Experian.</span></span>

1.  <span data-ttu-id="ee958-127">Selecione **Salvar** para concluir o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="ee958-127">Select **Save** to complete the field mapping.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="ee958-128">![Mapeamento de campos da Experian](media/experian-field-mapping.png "Mapeamento de campos da Experian")</span><span class="sxs-lookup"><span data-stu-id="ee958-128">![Experian field mapping](media/experian-field-mapping.png "Experian field mapping")</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ee958-129">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="ee958-129">Enrichment results</span></span>

<span data-ttu-id="ee958-130">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ee958-130">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ee958-131">Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ee958-131">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ee958-132">O tempo de processamento dependerá do tamanho dos dados dos clientes e dos processos de enriquecimento configurados para sua conta pela Experian.</span><span class="sxs-lookup"><span data-stu-id="ee958-132">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="ee958-133">Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="ee958-133">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ee958-134">Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="ee958-134">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ee958-135">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="ee958-135">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ee958-136">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ee958-136">Next steps</span></span>

<span data-ttu-id="ee958-137">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="ee958-137">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ee958-138">Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="ee958-138">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="ee958-139">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="ee958-139">Data privacy and compliance</span></span>

<span data-ttu-id="ee958-140">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Experian, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="ee958-140">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="ee958-141">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Experian cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="ee958-141">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="ee958-142">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="ee958-142">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="ee958-143">Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="ee958-143">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]