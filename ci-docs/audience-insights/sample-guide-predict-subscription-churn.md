---
title: Guia de amostra para previsão de rotatividade de assinaturas
description: Use este guia de amostra para experimentar o modelo de previsão de rotatividade de assinatura pronto para uso.
ms.date: 11/19/2020
ms.reviewer: digranad
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 3f1019ace424f89320c5a0d5058e928f4cbc7e62
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269822"
---
# <a name="subscription-churn-prediction-preview-sample-guide"></a><span data-ttu-id="7e572-103">Guia de amostra para previsão de rotatividade de assinaturas (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="7e572-103">Subscription churn prediction (preview) sample guide</span></span>

<span data-ttu-id="7e572-104">Explicaremos a você um exemplo de ponta a ponta de previsão de rotatividade de assinatura usando os dados de amostra fornecidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="7e572-104">We'll walk you through an end to end example of subscription churn prediction using the sample data provided below.</span></span> 

## <a name="scenario"></a><span data-ttu-id="7e572-105">Cenário</span><span class="sxs-lookup"><span data-stu-id="7e572-105">Scenario</span></span>

<span data-ttu-id="7e572-106">A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que são vendidas por meio do site Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="7e572-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="7e572-107">Recentemente, eles começaram um negócio de assinatura para seus clientes obterem café regularmente.</span><span class="sxs-lookup"><span data-stu-id="7e572-107">They recently started a subscription business for their customers to get coffee on a regular basis.</span></span> <span data-ttu-id="7e572-108">O objetivo deles é entender quais clientes assinantes podem cancelar sua assinatura nos próximos meses.</span><span class="sxs-lookup"><span data-stu-id="7e572-108">Their goal is to understand, which subscribed customers might cancel their subscription in the next few months.</span></span> <span data-ttu-id="7e572-109">Saber qual de seus clientes está **propenso a rotacionar**, pode ajudá-los a economizar esforços de marketing, concentrando-se em mantê-los.</span><span class="sxs-lookup"><span data-stu-id="7e572-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7e572-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7e572-110">Prerequisites</span></span>

- <span data-ttu-id="7e572-111">Por último, [Permissões de colaborador](permissions.md) em Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7e572-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="7e572-112">Recomendamos que você implemente as seguintes etapas [em um novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="7e572-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="7e572-113">Tarefa 1 - Ingerir dados</span><span class="sxs-lookup"><span data-stu-id="7e572-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="7e572-114">Reveja os artigos [sobre ingestão de dados](data-sources.md) e [importar fontes de dados usando Power Query conectores](connect-power-query.md), especificamente.</span><span class="sxs-lookup"><span data-stu-id="7e572-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="7e572-115">As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.</span><span class="sxs-lookup"><span data-stu-id="7e572-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="7e572-116">Ingerir dados do cliente da plataforma de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="7e572-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="7e572-117">Crie uma fonte de dados chamada **Comércio eletrônico**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="7e572-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7e572-118">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="7e572-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="7e572-119">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="7e572-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7e572-120">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="7e572-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="7e572-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="7e572-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7e572-122">**CreatedOn**: Data/Hora/Zona</span><span class="sxs-lookup"><span data-stu-id="7e572-122">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. <span data-ttu-id="7e572-124">No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="7e572-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="7e572-125">Salvar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e572-125">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="7e572-126">Ingerir dados do cliente do esquema de fidelidade</span><span class="sxs-lookup"><span data-stu-id="7e572-126">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="7e572-127">Crie uma fonte de dados chamada **LoyaltyScheme**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="7e572-127">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7e572-128">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="7e572-128">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="7e572-129">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="7e572-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7e572-130">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="7e572-130">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="7e572-131">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="7e572-131">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="7e572-132">**RewardsPoints**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="7e572-132">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="7e572-133">**CreatedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="7e572-133">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="7e572-134">No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7e572-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="7e572-135">Salvar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e572-135">Save the data source.</span></span>

### <a name="ingest-subscription-information"></a><span data-ttu-id="7e572-136">Ingerir informações de assinatura</span><span class="sxs-lookup"><span data-stu-id="7e572-136">Ingest subscription information</span></span>

1. <span data-ttu-id="7e572-137">Crie uma fonte de dados chamada **SubscriptionHistory**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="7e572-137">Create a data source named **SubscriptionHistory**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7e572-138">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadchurnsubscriptionhistory.</span><span class="sxs-lookup"><span data-stu-id="7e572-138">Enter the URL for eCommerce contacts https://aka.ms/ciadchurnsubscriptionhistory.</span></span>

1. <span data-ttu-id="7e572-139">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="7e572-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7e572-140">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="7e572-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="7e572-141">**SubscriptioID**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="7e572-141">**SubscriptioID**: Whole Number</span></span>
   - <span data-ttu-id="7e572-142">**SubscriptionAmount**: Moeda</span><span class="sxs-lookup"><span data-stu-id="7e572-142">**SubscriptionAmount**: Currency</span></span>
   - <span data-ttu-id="7e572-143">**SubscriptionEndDate**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="7e572-143">**SubscriptionEndDate**: Date/Time</span></span>
   - <span data-ttu-id="7e572-144">**SubscriptionStartDate**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="7e572-144">**SubscriptionStartDate**: Date/Time</span></span>
   - <span data-ttu-id="7e572-145">**TransactionDate**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="7e572-145">**TransactionDate**: Date/Time</span></span>
   - <span data-ttu-id="7e572-146">**IsRecurring**: Verdadeiro/Falso</span><span class="sxs-lookup"><span data-stu-id="7e572-146">**IsRecurring**: True/False</span></span>
   - <span data-ttu-id="7e572-147">**Is_auto_renew**: Verdadeiro/Falso</span><span class="sxs-lookup"><span data-stu-id="7e572-147">**Is_auto_renew**: True/False</span></span>
   - <span data-ttu-id="7e572-148">**RecurringFrequencyInMonths**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="7e572-148">**RecurringFrequencyInMonths**: Whole Number</span></span>

1. <span data-ttu-id="7e572-149">No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **SubscriptionHistory**.</span><span class="sxs-lookup"><span data-stu-id="7e572-149">In the **Name** field on the right-hand pane, rename your data source from **Query** to **SubscriptionHistory**.</span></span>

1. <span data-ttu-id="7e572-150">Salvar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="7e572-150">Save the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="7e572-151">Ingerir dados do cliente de comentários do site</span><span class="sxs-lookup"><span data-stu-id="7e572-151">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="7e572-152">Crie uma fonte de dados chamada **Site da Web**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="7e572-152">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="7e572-153">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasswebsite.</span><span class="sxs-lookup"><span data-stu-id="7e572-153">Enter the URL for eCommerce contacts https://aka.ms/ciadclasswebsite.</span></span>

1. <span data-ttu-id="7e572-154">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="7e572-154">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="7e572-155">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="7e572-155">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="7e572-156">**ReviewRating**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="7e572-156">**ReviewRating**: Whole Number</span></span>
   - <span data-ttu-id="7e572-157">**ReviewDate**: Data</span><span class="sxs-lookup"><span data-stu-id="7e572-157">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="7e572-158">No campo 'Nome' no painel direito, renomeie sua fonte de dados de **Consulta** para **webReviews**.</span><span class="sxs-lookup"><span data-stu-id="7e572-158">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **webReviews**.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="7e572-159">Tarefa 2 - Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="7e572-159">Task 2 - Data unification</span></span>

<span data-ttu-id="7e572-160">Depois de ingerir os dados, agora iniciamos o processo de **Mapear, Corresponder, Mesclar** para criar um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="7e572-160">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="7e572-161">Para obter mais informações, consulte [Unificação de dados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="7e572-161">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="7e572-162">Mapa </span><span class="sxs-lookup"><span data-stu-id="7e572-162">Map</span></span>

1. <span data-ttu-id="7e572-163">Depois de ingerir os dados, mapeie os contatos dos dados de comércio eletrônico e de fidelidade para tipos de dados comuns.</span><span class="sxs-lookup"><span data-stu-id="7e572-163">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="7e572-164">Vá para **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="7e572-164">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="7e572-165">Selecione as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7e572-165">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unifique as fontes de dados de comércio eletrônico e fidelidade.":::

1. <span data-ttu-id="7e572-167">Selecione **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="7e572-167">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifique LoyaltyId como chave primária.":::

### <a name="match"></a><span data-ttu-id="7e572-169">Corresponder</span><span class="sxs-lookup"><span data-stu-id="7e572-169">Match</span></span>

1. <span data-ttu-id="7e572-170">Vá para a guia **Corresponder** e selecione **Definir pedido**.</span><span class="sxs-lookup"><span data-stu-id="7e572-170">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="7e572-171">Na lista suspensa **Primário**, escolha **eCommerceContacts : eCommerce** como fonte primária e inclua todos os registros.</span><span class="sxs-lookup"><span data-stu-id="7e572-171">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="7e572-172">Na lista suspensa **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registros.</span><span class="sxs-lookup"><span data-stu-id="7e572-172">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificar correspondência de comércio eletrônico e fidelidade.":::

1. <span data-ttu-id="7e572-174">Selecione **Criar uma nova regra**</span><span class="sxs-lookup"><span data-stu-id="7e572-174">Select **Create a new rule**</span></span>

1. <span data-ttu-id="7e572-175">Adicione sua primeira condição usando FullName.</span><span class="sxs-lookup"><span data-stu-id="7e572-175">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="7e572-176">Para eCommerceContacts selecione **FullName** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="7e572-176">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="7e572-177">Para loyCustomers selecione **FullName** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="7e572-177">For loyCustomers select **FullName** in the drop-down.</span></span>
   * <span data-ttu-id="7e572-178">Selecione o menu suspenso **Normalizar** e escolha **Inserir (telefone, nome, endereço,...)**.</span><span class="sxs-lookup"><span data-stu-id="7e572-178">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="7e572-179">Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="7e572-179">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="7e572-180">Digite o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="7e572-180">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="7e572-181">Adicione uma segunda condição para o endereço de e-mail selecionando **Adicionar condição**</span><span class="sxs-lookup"><span data-stu-id="7e572-181">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="7e572-182">Para a entidade eCommerceContacts, escolha **Email** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="7e572-182">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   * <span data-ttu-id="7e572-183">Para a entidade loyCustomers, escolha **Email** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="7e572-183">For entity loyCustomers, choose **EMail** in the drop-down.</span></span> 
   * <span data-ttu-id="7e572-184">Deixe o campo Normalizar em branco.</span><span class="sxs-lookup"><span data-stu-id="7e572-184">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="7e572-185">Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="7e572-185">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Regra de correspondência unificada para nome e email.":::

7. <span data-ttu-id="7e572-187">Selecione **Salvar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="7e572-187">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="7e572-188">Merge</span><span class="sxs-lookup"><span data-stu-id="7e572-188">Merge</span></span>

1. <span data-ttu-id="7e572-189">Vá para a guia **Mesclar**.</span><span class="sxs-lookup"><span data-stu-id="7e572-189">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="7e572-190">Na entidade **ContactId** para **loyCustomers**, altere o nome de exibição para **ContactIdLOYALTY** para diferenciá-lo dos outros IDs ingeridos.</span><span class="sxs-lookup"><span data-stu-id="7e572-190">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid de loyalty id.":::

1. <span data-ttu-id="7e572-192">Selecione **Salvar** e **Executar** para iniciar o processo de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="7e572-192">Select **Save** and **Run** to start the Merge Process.</span></span>


## <a name="task-3---configure-the-subscription-churn-prediction"></a><span data-ttu-id="7e572-193">Tarefa 3 - Configurar a rotatividade de previsão de assinatura</span><span class="sxs-lookup"><span data-stu-id="7e572-193">Task 3 - Configure the subscription churn prediction</span></span>

<span data-ttu-id="7e572-194">Com os perfis de cliente unificados em vigor, agora podemos executar a previsão de rotatividade de assinatura.</span><span class="sxs-lookup"><span data-stu-id="7e572-194">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="7e572-195">Para obter etapas detalhadas, consulte o artigo [Previsão de rotatividade de assinatura (versão preliminar)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="7e572-195">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="7e572-196">Vá para **Inteligência** > **Descobrir** e selecione usar o **Modelo de rotatividade do cliente**.</span><span class="sxs-lookup"><span data-stu-id="7e572-196">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="7e572-197">Selecione a opção **Inscrição** e selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="7e572-197">Select the **Subscription** option and select **Get started**.</span></span>

1. <span data-ttu-id="7e572-198">Nomeie o modelo **Previsão de rotatividade de transação de assinaturas OOB** e a entidade de saída **OOBSubscriptionChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="7e572-198">Name the model **OOB Subscription Churn Prediction** and the output entity **OOBSubscriptionChurnPrediction**.</span></span>

1. <span data-ttu-id="7e572-199">Defina duas condições para o modelo de rotatividade:</span><span class="sxs-lookup"><span data-stu-id="7e572-199">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="7e572-200">**Dias desde o término da assinatura**: **pelo menos 60** dias.</span><span class="sxs-lookup"><span data-stu-id="7e572-200">**Days since subscription ended**: **at least 60** days.</span></span> <span data-ttu-id="7e572-201">Se um cliente não tiver renovado a assinatura nesse período depois do término da assinatura, ele será considerado rotacionado.</span><span class="sxs-lookup"><span data-stu-id="7e572-201">If a customer doesn't renew the subscription in this period after their subscription ended, they are considered churned.</span></span> 

   * <span data-ttu-id="7e572-202">**Definição de rotatividade**: **pelo menos 93** dias.</span><span class="sxs-lookup"><span data-stu-id="7e572-202">**Churn definition**: **at least 93** days.</span></span> <span data-ttu-id="7e572-203">A duração em que o modelo prevê quais clientes podem se desligar.</span><span class="sxs-lookup"><span data-stu-id="7e572-203">The duration the model predict which customers might churn.</span></span> <span data-ttu-id="7e572-204">Quanto mais longe você olhar no futuro, menos precisos serão os resultados.</span><span class="sxs-lookup"><span data-stu-id="7e572-204">The further in the future you look, the less precise the results.</span></span>

     :::image type="content" source="media/model-subs-levers.PNG" alt-text="Selecione a janela de previsão de niveladores de modelo e definição de rotatividade.":::

1. <span data-ttu-id="7e572-206">Selecione **Adicionar data necessária** e selecione **Adicionar dados** para histórico de assinaturas.</span><span class="sxs-lookup"><span data-stu-id="7e572-206">Select **Add required data** and select **Add data** for subscription history.</span></span>

1. <span data-ttu-id="7e572-207">Adicione a entidade **Subscription : SubscriptionHistory** e mapeie os campos do eCommerce para os campos correspondentes exigidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="7e572-207">Add the **Subscription : SubscriptionHistory** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="7e572-208">Junte-se à entidade **Subscription : SubscriptionHistory** com **eCommerceContacts : eCommerce**, nomeie o relacionamento de **eCommerceSubscription**.</span><span class="sxs-lookup"><span data-stu-id="7e572-208">Join the **Subscription : SubscriptionHistory** entity with **eCommerceContacts : eCommerce**, name the relationship **eCommerceSubscription**.</span></span>

   :::image type="content" source="media/model-subscription-join.PNG" alt-text="Junte-se a entidades de comércio eletrônico.":::

1. <span data-ttu-id="7e572-210">Em Atividades do cliente, adicione a entidade **webReviews : Website** e mapeie os campos do webReviews para os campos correspondentes exigidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="7e572-210">Under Customer Activities, add the **webReviews : Website** entity and map the fields from webReviews to the corresponding fields required by the model.</span></span> 
   - <span data-ttu-id="7e572-211">Chave primária: ReviewId</span><span class="sxs-lookup"><span data-stu-id="7e572-211">Primary key: ReviewId</span></span>
   - <span data-ttu-id="7e572-212">Carimbo de data/hora: ReviewDate</span><span class="sxs-lookup"><span data-stu-id="7e572-212">Timestamp: ReviewDate</span></span>
   - <span data-ttu-id="7e572-213">Evento: ReviewRating</span><span class="sxs-lookup"><span data-stu-id="7e572-213">Event: ReviewRating</span></span>

1. <span data-ttu-id="7e572-214">Configurar uma atividade para revisões do site.</span><span class="sxs-lookup"><span data-stu-id="7e572-214">Configure an activity for website reviews.</span></span> <span data-ttu-id="7e572-215">Selecione a atividade **Revisão** e junte-se à entidade **webReviews : Website** com **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="7e572-215">Select the activity **Review** and join the **webReviews : Website** entity with **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="7e572-216">Selecione **Avançar** para definir o cronograma do modelo.</span><span class="sxs-lookup"><span data-stu-id="7e572-216">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="7e572-217">O modelo precisa ser treinado regularmente para aprender novos padrões quando novos dados forem ingeridos.</span><span class="sxs-lookup"><span data-stu-id="7e572-217">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="7e572-218">Para este exemplo, selecione **Mensal**.</span><span class="sxs-lookup"><span data-stu-id="7e572-218">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="7e572-219">Depois de revisar todos os detalhes, selecione **Salvar e executar**.</span><span class="sxs-lookup"><span data-stu-id="7e572-219">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="7e572-220">Tarefa 4 - Revise os resultados e explicações do modelo</span><span class="sxs-lookup"><span data-stu-id="7e572-220">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="7e572-221">Deixe o modelo concluir o treinamento e a pontuação dos dados.</span><span class="sxs-lookup"><span data-stu-id="7e572-221">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="7e572-222">Agora, você pode revisar as explicações do modelo de rotatividade de assinatura.</span><span class="sxs-lookup"><span data-stu-id="7e572-222">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="7e572-223">Para mais informações, consulte [Analisar um status de previsão e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="7e572-223">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="7e572-224">Tarefa 5 - Crie um segmento de clientes de alto risco de rotatividade</span><span class="sxs-lookup"><span data-stu-id="7e572-224">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="7e572-225">Executar o modelo de produção cria uma nova entidade que você pode ver em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="7e572-225">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="7e572-226">Você pode criar um novo segmento com base na entidade criada pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="7e572-226">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="7e572-227">Vá para **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="7e572-227">Go to **Segments**.</span></span> <span data-ttu-id="7e572-228">Selecione **Novo** e escolha **Criar de** > **Inteligência**.</span><span class="sxs-lookup"><span data-stu-id="7e572-228">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Criando um segmento com a saída do modelo.":::

1. <span data-ttu-id="7e572-230">Selecione o ponto de extremidade **OOBSubscriptionChurnPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="7e572-230">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="7e572-231">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="7e572-231">Field: ChurnScore</span></span>
   - <span data-ttu-id="7e572-232">Operador: maior que</span><span class="sxs-lookup"><span data-stu-id="7e572-232">Operator: greater than</span></span>
   - <span data-ttu-id="7e572-233">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="7e572-233">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configure o segmento de rotatividade de assinaturas.":::

<span data-ttu-id="7e572-235">Agora, você tem um segmento que é atualizado dinamicamente que identifica clientes de alto risco de rotatividade para este negócio de assinatura.</span><span class="sxs-lookup"><span data-stu-id="7e572-235">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="7e572-236">Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="7e572-236">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]