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
ms.openlocfilehash: 9cf2a7fa18ecc022ea67f6829f52381ad59f3172
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896359"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a><span data-ttu-id="255d5-103">Enriquecer os perfis dos clientes com dados demográficos da Experian (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="255d5-103">Enrich customer profiles with demographics from Experian (preview)</span></span>

<span data-ttu-id="255d5-104">A Experian é líder global em serviços de marketing e relatórios de crédito para consumidores e empresas.</span><span class="sxs-lookup"><span data-stu-id="255d5-104">Experian is a global leader in consumer and business credit reporting and marketing services.</span></span> <span data-ttu-id="255d5-105">Com os serviços de enriquecimento de dados da Experian, você pode compreender melhor seus clientes enriquecendo os perfis desses clientes com dados demográficos, como número de pessoas na família, renda e muito mais.</span><span class="sxs-lookup"><span data-stu-id="255d5-105">With Experian’s data enrichment services, you can build a deeper understanding of your customers by enriching your customer profiles with demographic data such as household size, income, and more.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="255d5-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="255d5-106">Prerequisites</span></span>

<span data-ttu-id="255d5-107">Para configurar a Experian, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="255d5-107">To configure Experian, the following prerequisites must be met:</span></span>

- <span data-ttu-id="255d5-108">Você ter uma assinatura ativa da Experian.</span><span class="sxs-lookup"><span data-stu-id="255d5-108">You have an active Experian subscription.</span></span> <span data-ttu-id="255d5-109">Para obter uma assinatura, [entre em contato com a Experian](https://www.experian.com/marketing-services/contact) diretamente.</span><span class="sxs-lookup"><span data-stu-id="255d5-109">To get a subscription, [contact Experian](https://www.experian.com/marketing-services/contact) directly.</span></span> <span data-ttu-id="255d5-110">[Saiba mais sobre o Enriquecimento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span><span class="sxs-lookup"><span data-stu-id="255d5-110">[Learn more about Experian Data Enrichment](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).</span></span>

- <span data-ttu-id="255d5-111">Uma conexão da Experian já foi configurada por um administrador *ou* você tem permissões de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="255d5-111">An Experian connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="255d5-112">Você também precisa da ID do Usuário, da ID do Participante e do Número do Modelo de sua conta de Transporte Seguro (ST) habilitada para SSH que a Experian criou para você.</span><span class="sxs-lookup"><span data-stu-id="255d5-112">You also need the User ID, Party ID, and Model Number for your SSH-enabled Secure Transport (ST) account that Experian created for you.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="255d5-113">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="255d5-113">Configure the enrichment</span></span>

1. <span data-ttu-id="255d5-114">Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="255d5-114">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="255d5-115">Selecione **Enriquecer meus dados** no bloco da Experian.</span><span class="sxs-lookup"><span data-stu-id="255d5-115">Select **Enrich my data** on the Experian tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="255d5-116">![Bloco da Experian](media/experian-tile.png "Bloco da Experian")</span><span class="sxs-lookup"><span data-stu-id="255d5-116">![Experian tile](media/experian-tile.png "Experian tile")</span></span>
   > 

1. <span data-ttu-id="255d5-117">Selecione uma [conexão](connections.md) na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="255d5-117">Select a [connection](connections.md) from the drop-down.</span></span> <span data-ttu-id="255d5-118">Contate um administrador se nenhuma conexão estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="255d5-118">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="255d5-119">Se for administrador, você poderá criar uma conexão selecionando **Adicionar conexão** e escolhendo Experian no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="255d5-119">If you are an administrator, you can create a connection by selecting **Add connection** and choosing Experian from the drop-down.</span></span> 

1. <span data-ttu-id="255d5-120">Selecione **Conectar-se à Experian** para confirmar a seleção da conexão.</span><span class="sxs-lookup"><span data-stu-id="255d5-120">Select **Connect to Experian** to confirm the connection selection.</span></span>

1.  <span data-ttu-id="255d5-121">Selecione **Avançar** e escolha o **Conjunto de dados do cliente** que você deseja enriquecer com os dados demográficos da Experian.</span><span class="sxs-lookup"><span data-stu-id="255d5-121">Select **Next** and choose the **Customer data set** you want to enrich with demographics data from Experian.</span></span> <span data-ttu-id="255d5-122">Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="255d5-122">You can select the **Customer** entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. <span data-ttu-id="255d5-124">Selecione **Avançar** e defina quais tipos de campos de seus perfis unificados devem ser usados para procurar dados demográficos correspondentes da Experian.</span><span class="sxs-lookup"><span data-stu-id="255d5-124">Select **Next** and define which type of fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="255d5-125">Pelo menos um dos campos **Nome e endereço**, **Telefone**, ou **E-mail** é necessário.</span><span class="sxs-lookup"><span data-stu-id="255d5-125">At least one of the fields **Name and address**, **Phone**, or **Email** is required.</span></span> <span data-ttu-id="255d5-126">Para uma maior precisão de correspondência, até dois outros campos podem ser adicionados.</span><span class="sxs-lookup"><span data-stu-id="255d5-126">For a higher match accuracy, up to two other fields can be added.</span></span> <span data-ttu-id="255d5-127">Esta seleção afetará os campos de mapeamento aos quais você tem acesso na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="255d5-127">This selection will affect the mapping fields you have access to in the next step.</span></span>

    > [!TIP]
    > <span data-ttu-id="255d5-128">Mais atributos de identificadores de chave enviados à Experian provavelmente geram uma taxa de correspondência mais alta.</span><span class="sxs-lookup"><span data-stu-id="255d5-128">More key identifier attributes sent to Experian likely yield a higher match rate.</span></span>

1. <span data-ttu-id="255d5-129">Selecione **Avançar** para iniciar o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="255d5-129">Select **Next** to start the field mapping.</span></span>

1. <span data-ttu-id="255d5-130">Defina quais tipos de campos de seus perfis unificados devem ser usados para procurar dados demográficos correspondentes da Experian.</span><span class="sxs-lookup"><span data-stu-id="255d5-130">Define which fields from your unified profiles should be used to look for matching demographics data from Experian.</span></span> <span data-ttu-id="255d5-131">Os campos obrigatórios são marcados.</span><span class="sxs-lookup"><span data-stu-id="255d5-131">Required fields are marked.</span></span>

1. <span data-ttu-id="255d5-132">Forneça um nome para o enriquecimento e um nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="255d5-132">Provide a name for the enrichment and a name for the output entity.</span></span>

1. <span data-ttu-id="255d5-133">Selecione **Salvar enriquecimento** depois de revisar suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="255d5-133">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-experian"></a><span data-ttu-id="255d5-134">Configurar a conexão para a Experian</span><span class="sxs-lookup"><span data-stu-id="255d5-134">Configure the connection for Experian</span></span> 

<span data-ttu-id="255d5-135">Você deve ser um administrador para configurar as conexões.</span><span class="sxs-lookup"><span data-stu-id="255d5-135">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="255d5-136">Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da Experian.</span><span class="sxs-lookup"><span data-stu-id="255d5-136">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Experian tile.</span></span>

1. <span data-ttu-id="255d5-137">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="255d5-137">Select **Get Started**.</span></span>

1. <span data-ttu-id="255d5-138">Insira um nome para a conexão na caixa **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="255d5-138">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="255d5-139">Insira uma ID de Usuário, uma ID de Participante e um Número de Modelo válidos para sua conta de Transporte Seguro da Experian.</span><span class="sxs-lookup"><span data-stu-id="255d5-139">Enter valid User ID, Party ID, and Model Number for your Experian Secure Transport account.</span></span>

1. <span data-ttu-id="255d5-140">Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**</span><span class="sxs-lookup"><span data-stu-id="255d5-140">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox</span></span>

1. <span data-ttu-id="255d5-141">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="255d5-141">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="255d5-142">Depois de concluir a verificação, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="255d5-142">After completing the verification, select **Save**.</span></span>
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Painel de configuração de conexão da Experian.":::

## <a name="enrichment-results"></a><span data-ttu-id="255d5-144">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="255d5-144">Enrichment results</span></span>

<span data-ttu-id="255d5-145">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="255d5-145">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="255d5-146">Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="255d5-146">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="255d5-147">O tempo de processamento dependerá do tamanho dos dados dos clientes e dos processos de enriquecimento configurados para sua conta pela Experian.</span><span class="sxs-lookup"><span data-stu-id="255d5-147">The processing time will depend on the size of your customer data and the enrichment processes set up for your account by Experian.</span></span>

<span data-ttu-id="255d5-148">Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="255d5-148">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="255d5-149">Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="255d5-149">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="255d5-150">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="255d5-150">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="255d5-151">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="255d5-151">Next steps</span></span>

<span data-ttu-id="255d5-152">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="255d5-152">Build on top of your enriched customer data.</span></span> <span data-ttu-id="255d5-153">Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="255d5-153">Create [segments](segments.md), [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="255d5-154">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="255d5-154">Data privacy and compliance</span></span>

<span data-ttu-id="255d5-155">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Experian, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="255d5-155">When you enable Dynamics 365 Customer Insights to transmit data to Experian, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="255d5-156">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Experian cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="255d5-156">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that Experian meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="255d5-157">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="255d5-157">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="255d5-158">Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="255d5-158">Your Dynamics 365 Customer Insights Administrator can remove this enrichment at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
