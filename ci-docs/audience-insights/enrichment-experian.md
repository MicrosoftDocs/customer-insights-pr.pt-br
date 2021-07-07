---
title: Enriquecimento com o enriquecimento de terceiros da Experian
description: Informações gerais sobre o enriquecimento de terceiros da Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 7c82fe92b3351a782a4fa6510300d870b742d042
ms.sourcegitcommit: 42b3bce1e20e7cc707d232844dacfeed3d6fc096
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/28/2021
ms.locfileid: "6309806"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="58392-103">Enriqueça os perfis dos clientes com dados demográficos da Experian (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="58392-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="58392-104">Experian é uma líder global em serviços de marketing e relatórios de crédito para consumidores e empresas.</span><span class="sxs-lookup"><span data-stu-id="58392-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="58392-105">Com os serviços de enriquecimento de dados da Experian, você pode obter uma compreensão mais profunda de seus clientes, enriquecendo seus perfis de clientes com dados demográficos, como o tamanho da família, renda e muito mais.</span><span class="sxs-lookup"><span data-stu-id="58392-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="58392-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="58392-106">Prerequisites</span></span>

<span data-ttu-id="58392-107">Para configurar a Experian, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="58392-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="58392-108">Você deve ter uma assinatura ativa da Experian.</span><span class="sxs-lookup"><span data-stu-id="58392-108">You have an active Experian subscription.</span></span> <span data-ttu-id="58392-109">Para obter uma assinatura, [contate a Experian](https://www.experian.com/marketing-services/contact) diretamente.</span><span class="sxs-lookup"><span data-stu-id="58392-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="58392-110">[Saiba mais sobre o enriquecimento de dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="58392-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="58392-111">Uma conexão da Experian já foi configurada por um administrador *ou* você tem permissões de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="58392-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="58392-112">Você também precisa da ID do Usuário, da ID do Participante e do número do modelo para sua conta de Transporte Seguro (ST) habilitada para SSH que a Experian criou para você.</span><span class="sxs-lookup"><span data-stu-id="58392-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="58392-113">Países/regiões com suporte</span><span class="sxs-lookup"><span data-stu-id="58392-113">Supported countries/regions</span></span>

<span data-ttu-id="58392-114">No momento, oferecemos suporte ao enriquecimento de perfis de clientes somente nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="58392-114">We currently support enriching customer profiles in the United States only.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="58392-115">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="58392-115">Configure the enrichment</span></span>

1. <span data-ttu-id="58392-116">Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="58392-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="58392-117">Selecione **Enriquecer meus dados** no bloco da Experian.</span><span class="sxs-lookup"><span data-stu-id="58392-117">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="58392-118">![Bloco do Experian](media/experian-tile.png "Experian tile")</span><span class="sxs-lookup"><span data-stu-id="58392-118">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="58392-119">Selecione uma [conexão](connections.md) na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="58392-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="58392-120">Contate um administrador se nenhuma conexão estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="58392-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="58392-121">Se for um administrador, você poderá criar uma conexão selecionando **Adicionar conexão** e escolhendo Experian na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="58392-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the dropdown list.</span></span> 

1. <span data-ttu-id="58392-122">Selecione **Conectar à Experian** para confirmar a seleção da conexão.</span><span class="sxs-lookup"><span data-stu-id="58392-122">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="58392-123">Selecione **Avançar** e escolha o **Conjunto de dados do cliente** que deseja enriquecer com dados demográficos da Experian.</span><span class="sxs-lookup"><span data-stu-id="58392-123">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="58392-124">Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="58392-124">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. <span data-ttu-id="58392-126">Selecione **Avançar** e defina quais tipos de campos de seus perfis unificados devem ser usados para procurar dados demográficos correspondentes na Experian.</span><span class="sxs-lookup"><span data-stu-id="58392-126">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="58392-127">Pelo menos um dos campos **Nome e endereço**, **Telefone**, ou **E-mail** é necessário.</span><span class="sxs-lookup"><span data-stu-id="58392-127">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="58392-128">Para uma maior precisão de correspondência, até dois outros campos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="58392-128">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="58392-129">Esta seleção afetará os campos de mapeamento aos quais você tem acesso na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="58392-129">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="58392-130">É provável que mais atributos de identificador de chave enviados para a Experian rendam uma taxa de correspondência mais alta.</span><span class="sxs-lookup"><span data-stu-id="58392-130">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="58392-131">Selecione **Avançar** para iniciar o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="58392-131">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="58392-132">Defina quais tipos de campos de seus perfis unificados devem ser usados para procurar dados demográficos correspondentes na Experian.</span><span class="sxs-lookup"><span data-stu-id="58392-132">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="58392-133">Os campos obrigatórios são marcados.</span><span class="sxs-lookup"><span data-stu-id="58392-133">Required fields are marked.</span></span>

1. <span data-ttu-id="58392-134">Forneça um nome para o enriquecimento e um nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="58392-134">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="58392-135">Selecione **Salvar enriquecimento** depois de revisar suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="58392-135">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="58392-136">Configurar a conexão para a Experian</span><span class="sxs-lookup"><span data-stu-id="58392-136">Configure the connection for Experian</span></span> 

<span data-ttu-id="58392-137">Você deve ser um administrador para configurar as conexões.</span><span class="sxs-lookup"><span data-stu-id="58392-137">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="58392-138">Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da Experian.</span><span class="sxs-lookup"><span data-stu-id="58392-138">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="58392-139">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="58392-139">Select **Get Started**.</span></span>

1. <span data-ttu-id="58392-140">Insira um nome para a conexão na caixa **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="58392-140">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="58392-141">Insira uma ID de Usuário, uma ID de Participante e um número de modelo válidos para sua conta de Transporte Seguro da Experian.</span><span class="sxs-lookup"><span data-stu-id="58392-141">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="58392-142">Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** selecionando **Eu concordo**.</span><span class="sxs-lookup"><span data-stu-id="58392-142">Review and provide your consent for **Data privacy and compliance** by selecting **I agree**.</span></span>

1. <span data-ttu-id="58392-143">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="58392-143">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="58392-144">Depois de concluir a verificação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="58392-144">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Painel de configuração de conexão da Experian":::

## <a name="enrichment-results"></a><span data-ttu-id="58392-146">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="58392-146">Enrichment results</span></span>

<span data-ttu-id="58392-147">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="58392-147">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="58392-148">Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="58392-148">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="58392-149">O tempo de processamento dependerá do tamanho dos dados do cliente e dos processos de enriquecimento configurados para sua conta pela Experian.</span><span class="sxs-lookup"><span data-stu-id="58392-149">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="58392-150">Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="58392-150">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="58392-151">Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="58392-151">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="58392-152">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="58392-152">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="58392-153">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="58392-153">Next steps</span></span>

<span data-ttu-id="58392-154">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="58392-154">Build on top of your enriched customer data.</span></span> <span data-ttu-id="58392-155">Crie [segmentos](segments.md) e [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="58392-155">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="58392-156">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="58392-156">Data privacy and compliance</span></span>

<span data-ttu-id="58392-157">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para a Experian, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="58392-157">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="58392-158">A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que a Experian cumpra quaisquer obrigações de privacidade ou segurança que você possa ter.</span><span class="sxs-lookup"><span data-stu-id="58392-158">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="58392-159">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="58392-159">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="58392-160">Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="58392-160">Your Dynamics 365 Customer Insights administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
