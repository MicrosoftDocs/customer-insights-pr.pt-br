---
title: Home page nos insights de público-alvo
description: Comece a explorar o aplicativo na Home page.
ms.date: 01/07/2021
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7cc767f5d80b213a4c1bb5b2e8062bd44c15279b
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477027"
---
# <a name="create-a-new-environment"></a><span data-ttu-id="15751-103">Criar um novo ambiente</span><span class="sxs-lookup"><span data-stu-id="15751-103">Create a new environment</span></span>

## <a name="create-a-trial-environment"></a><span data-ttu-id="15751-104">Criar um ambiente de avaliação</span><span class="sxs-lookup"><span data-stu-id="15751-104">Create a trial environment</span></span>

<span data-ttu-id="15751-105">Você pode se inscrever em uma avaliação na [página de inscrição de avaliação](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span><span class="sxs-lookup"><span data-stu-id="15751-105">You can sign up for a trial on the [trial sign up page](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights).</span></span> 

> [!NOTE]
> <span data-ttu-id="15751-106">As avaliações expiram após 30 dias.</span><span class="sxs-lookup"><span data-stu-id="15751-106">Trials expire after 30 days.</span></span>

1. <span data-ttu-id="15751-107">Escolha a opção **Inscrever-se em uma avaliação gratuita** e selecione **Inscrever-se agora**.</span><span class="sxs-lookup"><span data-stu-id="15751-107">Choose the **Sign up for a free trial** option and select **Sign up now**.</span></span>

1. <span data-ttu-id="15751-108">Forneça seu endereço corporativo ou de estudante, conte-nos mais sobre você e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="15751-108">Provide your work or school email address, tell us a more about yourself and select **Next**.</span></span>

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Caixa de diálogo para se inscrever em uma instância de avaliação":::

1. <span data-ttu-id="15751-110">Forneça um **Nome** para o novo ambiente.</span><span class="sxs-lookup"><span data-stu-id="15751-110">Provide a **Name** for your new environment.</span></span> 

1. <span data-ttu-id="15751-111">Selecione o tipo de avaliação.</span><span class="sxs-lookup"><span data-stu-id="15751-111">Select the trial type.</span></span>

1. <span data-ttu-id="15751-112">Escolha a **Região** para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="15751-112">Choose the **Region** for your environment.</span></span>

1. <span data-ttu-id="15751-113">Opcionalmente, para administradores de uma organização do Dynamics 365: Selecione **Configurações avançadas** e forneça a URL da sua organização para usar recursos de previsão, como rotatividade de clientes.</span><span class="sxs-lookup"><span data-stu-id="15751-113">Optionally, for admins of a Dynamics 365 organization: Select **Advanced settings** and provide the URL of your organization to use prediction features like customer churn.</span></span>

1. <span data-ttu-id="15751-114">Selecione **Criar**.</span><span class="sxs-lookup"><span data-stu-id="15751-114">Select **Create**.</span></span> 

<span data-ttu-id="15751-115">Após a criação do ambiente, você verá o ambiente **Demonstração**, que permite explorar o aplicativo com dados fictícios.</span><span class="sxs-lookup"><span data-stu-id="15751-115">After the environment was created, you'll see the **Demo** environment which lets you explore the app with fictitious data.</span></span> <span data-ttu-id="15751-116">É possível alterar os dados de exemplo para corresponder ao seu setor.</span><span class="sxs-lookup"><span data-stu-id="15751-116">You can change the sample data to match your industry.</span></span> <span data-ttu-id="15751-117">Selecione o ícone **Configurações** no cabeçalho e, em seguida, selecione **Configurações da demonstração**.</span><span class="sxs-lookup"><span data-stu-id="15751-117">Select the **Settings** icon in the header and select **Demo settings**.</span></span> <span data-ttu-id="15751-118">Além disso, você pode alterar o tema visual.</span><span class="sxs-lookup"><span data-stu-id="15751-118">Additionally, you can change the visual theme.</span></span> 

<span data-ttu-id="15751-119">Você pode [alternar para o ambiente](#switch-environments) criado durante o processo de inscrição para trabalhar com seus próprios dados.</span><span class="sxs-lookup"><span data-stu-id="15751-119">You [switch to the environment](#switch-environments) you created during the sign-up process to work with your own data.</span></span>

## <a name="create-a-new-production-or-sandbox-environment"></a><span data-ttu-id="15751-120">Criar um novo ambiente de produção ou área restrita</span><span class="sxs-lookup"><span data-stu-id="15751-120">Create a new production or sandbox environment</span></span>

<span data-ttu-id="15751-121">No seu ambiente, clique no seletor de **Ambientes** no cabeçalho do aplicativo e selecione **Novo**.</span><span class="sxs-lookup"><span data-stu-id="15751-121">In your environment, select the **Environments** picker in the app header and select **New**.</span></span>

<span data-ttu-id="15751-122">Siga as etapas como se você fosse [criar um ambiente de avaliação](#create-a-trial-environment).</span><span class="sxs-lookup"><span data-stu-id="15751-122">Follow the steps as if you [create a trial environment](#create-a-trial-environment).</span></span> <span data-ttu-id="15751-123">Por padrão, os dados são armazenados no data lake gerenciado do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="15751-123">By default, data is stored in the Customer Insights managed data lake.</span></span> <span data-ttu-id="15751-124">Você recebe uma opção adicional ao selecionar **Configurações avançadas** para armazenar os dados no seu próprio Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="15751-124">You get an additional option when selecting **Advanced settings** to store your data in your own Azure Data Lake.</span></span> <span data-ttu-id="15751-125">Forneça o nome e a chave da conta para estabelecer uma conexão com o Azure Data Lake.</span><span class="sxs-lookup"><span data-stu-id="15751-125">Provide your account name and account key to establish a connection to your Azure Data Lake.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="15751-126">Ao salvar dados no Azure Data Lake Storage, você concorda que esses dados serão transferidos e armazenados no local geográfico adequado para a conta de armazenamento do Azure, que pode ser diferente de onde os dados são armazenados no Dynamics 365 Customer Insights. </span><span class="sxs-lookup"><span data-stu-id="15751-126">By saving data to your Azure Data Lake Storage, you agree that data will be transferred to and stored in the appropriate geographic location for that Azure storage account, which may differ from where data is stored in Dynamics 365 Customer Insights.</span></span> [<span data-ttu-id="15751-127">Saiba mais no Microsoft Trust Center.</span><span class="sxs-lookup"><span data-stu-id="15751-127">Learn more at the Microsoft Trust Center.</span></span>](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a><span data-ttu-id="15751-128">Explore a home page</span><span class="sxs-lookup"><span data-stu-id="15751-128">Explore the home page</span></span>

<span data-ttu-id="15751-129">Você pode [acessar insights de público-alvo do Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) na seguinte URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span><span class="sxs-lookup"><span data-stu-id="15751-129">You can [access audience insights from Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) on the following URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).</span></span>
<span data-ttu-id="15751-130">A **Página Inicial** mostra uma visão geral de segmentos, medidas e dados de enriquecimento (se configurados) após concluir as fases de [mapeamento](map-entities.md), [correspondência](match-entities.md) e [mesclagem](merge-entities.md).</span><span class="sxs-lookup"><span data-stu-id="15751-130">The **Home** page shows an overview of segments, measures, and enrichment data (if configured)after completing the [map](map-entities.md), [match](match-entities.md), and [merge](merge-entities.md) phases.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="15751-131">![Insights na Home page](media/home-page-insights.png "Insights na Home page")</span><span class="sxs-lookup"><span data-stu-id="15751-131">![Insights on Home page](media/home-page-insights.png "Insights on Home page")</span></span>

<span data-ttu-id="15751-132">Em **Segmentos recentes**, você vê grupos de clientes com base em atributos demográficos, comportamentais ou transacionais que você definiu.</span><span class="sxs-lookup"><span data-stu-id="15751-132">Under **Recent segments**, you see groups of customers based on demographic, behavioral, or transactional attributes that you've defined.</span></span> <span data-ttu-id="15751-133">[Criar segmentos](segments.md) ajuda a agrupar a base de clientes e direcionar melhor as atividades comerciais.</span><span class="sxs-lookup"><span data-stu-id="15751-133">[Creating segments](segments.md) helps you to group your customer base and better target your business activities.</span></span>

<span data-ttu-id="15751-134">As **medidas recentes** mostram blocos com [indicadores chave de desempenho (KPIs)](measures.md) que você definiu.</span><span class="sxs-lookup"><span data-stu-id="15751-134">**Recent measures** show tiles with [key performance indicators (KPIs)](measures.md) that you've defined.</span></span> <span data-ttu-id="15751-135">Por exemplo, a probabilidade média de um cliente se desligar ou o gasto online médio por cliente.</span><span class="sxs-lookup"><span data-stu-id="15751-135">For example, average likelihood of a customer to churn or the average online spend per customer.</span></span>

<span data-ttu-id="15751-136">A seção **Enriquecimentos recentes** lista os resultados das execuções de enriquecimentos recém-concluídos.</span><span class="sxs-lookup"><span data-stu-id="15751-136">The **Recent enrichments** section lists the results of the enrichment runs that completed recently.</span></span> <span data-ttu-id="15751-137">Os [enriquecimentos](enrichment-hub.md) adicionam informações sobre a base de clientes.</span><span class="sxs-lookup"><span data-stu-id="15751-137">[Enrichments](enrichment-hub.md) add information about your customer base.</span></span> <span data-ttu-id="15751-138">Por exemplo, entender os interesses e marcas com os quais eles têm afinidade.</span><span class="sxs-lookup"><span data-stu-id="15751-138">For example, by understanding the interests and brands that they have affinity for.</span></span>

## <a name="switch-environments"></a><span data-ttu-id="15751-139">Alternar ambientes</span><span class="sxs-lookup"><span data-stu-id="15751-139">Switch environments</span></span>

<span data-ttu-id="15751-140">Selecione o controle de **Ambiente** no canto superior direito da página para alterar os ambientes.</span><span class="sxs-lookup"><span data-stu-id="15751-140">Select the **Environment** control in the upper-right corner of the page to change environments.</span></span>

> [!div class="mx-imgBorder"] 
> <span data-ttu-id="15751-141">![Alterar ambiente](media/home-page-environment-switcher.png "Alterar ambiente")</span><span class="sxs-lookup"><span data-stu-id="15751-141">![Switch environment](media/home-page-environment-switcher.png "Switch environment")</span></span>

<span data-ttu-id="15751-142">Os administradores podem criar e gerenciar [vários ambientes](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="15751-142">Administrators can create and manage [multiple environments](manage-environments.md).</span></span> <span data-ttu-id="15751-143">Manter mais de um ambiente pode ser útil se, por exemplo, sua organização operar internacionalmente e você precisar segregar dados e insights de maneiras diferentes.</span><span class="sxs-lookup"><span data-stu-id="15751-143">Maintaining more than one environment may be useful if, for example, your organization operates internationally and you need to segregate data and insights in different ways.</span></span>

## <a name="next-step"></a><span data-ttu-id="15751-144">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="15751-144">Next step</span></span>

<span data-ttu-id="15751-145">Para ver seus próprios insights na home page, primeiro você precisa [adicionar fontes de dados](data-sources.md) e [unificar](data-unification.md) seus dados para criar perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="15751-145">To see your own insights on the home page, you'll first need to [add data sources](data-sources.md) and [unify](data-unification.md) your data to build customer profiles.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]