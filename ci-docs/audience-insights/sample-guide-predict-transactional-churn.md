---
title: Guia de amostra de previsão de rotatividade transacional
description: Use este guia de amostra para experimentar o modelo de previsão de rotatividade transacional pronto para uso.
ms.date: 11/19/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 49dad45c951f3c00d77ddd99faec48bfccada8b0
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6306106"
---
# <a name="transactional-churn-prediction-preview-sample-guide"></a><span data-ttu-id="db36f-103">Guia de amostra para previsão de rotatividade transacional (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="db36f-103">Transactional churn prediction (preview) sample guide</span></span>

<span data-ttu-id="db36f-104">Este guia mostrará a você um exemplo de ponta a ponta de previsão de rotatividade transacional no Customer Insights usando usando os dados fornecidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="db36f-104">This guide will walk you through an end to end example of Transactional Churn prediction in Customer Insights using the data provided below.</span></span> <span data-ttu-id="db36f-105">Todos os dados usados neste guia não são dados de cliente reais e são parte do conjunto de dados da Contoso encontrados no ambiente *Demonstração* na sua Assinatura do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="db36f-105">All data used in this guide is not real customer data and is part of the Contoso dataset found in the *Demo* environment within your Customer Insights Subscription.</span></span>

## <a name="scenario"></a><span data-ttu-id="db36f-106">Cenário</span><span class="sxs-lookup"><span data-stu-id="db36f-106">Scenario</span></span>

<span data-ttu-id="db36f-107">A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que vendem por meio do site Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="db36f-107">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="db36f-108">Seu objetivo é saber quais clientes que normalmente compram seus produtos com regularidade deixarão de ser clientes ativos nos próximos 60 dias.</span><span class="sxs-lookup"><span data-stu-id="db36f-108">Their goal is to know which customers who typically purchase their products on a regular basis, will stop being active customers in the next 60 days.</span></span> <span data-ttu-id="db36f-109">Saber qual de seus clientes está **propenso a rotacionar**, pode ajudá-los a economizar esforços de marketing, concentrando-se em mantê-los.</span><span class="sxs-lookup"><span data-stu-id="db36f-109">Knowing which of their customers is **likely to churn**, can help them save marketing efforts by focusing on keeping them.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="db36f-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="db36f-110">Prerequisites</span></span>

- <span data-ttu-id="db36f-111">Por último, [Permissões de colaborador](permissions.md) em Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="db36f-111">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="db36f-112">Recomendamos que você implemente as seguintes etapas [em um novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="db36f-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="db36f-113">Tarefa 1 - Ingerir dados</span><span class="sxs-lookup"><span data-stu-id="db36f-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="db36f-114">Reveja os artigos [sobre ingestão de dados](data-sources.md) e [importar fontes de dados usando Power Query conectores](connect-power-query.md), especificamente.</span><span class="sxs-lookup"><span data-stu-id="db36f-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="db36f-115">As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.</span><span class="sxs-lookup"><span data-stu-id="db36f-115">The following information assumes you familiarized with ingesting data in general.</span></span> 

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="db36f-116">Ingerir dados do cliente da plataforma de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="db36f-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="db36f-117">Crie uma fonte de dados chamada **Comércio eletrônico**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="db36f-117">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="db36f-118">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="db36f-118">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="db36f-119">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="db36f-119">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="db36f-120">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="db36f-120">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="db36f-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="db36f-121">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="db36f-122">**CreatedOn**: Data/Hora/Zona</span><span class="sxs-lookup"><span data-stu-id="db36f-122">**CreatedOn**: Date/Time/Zone</span></span>

   [!div class="mx-imgBorder"]
   <span data-ttu-id="db36f-123">![Transformar Data de nascimento em Data](media/ecommerce-dob-date.PNG "transformar data de nascimento em data")</span><span class="sxs-lookup"><span data-stu-id="db36f-123">![Transform DoB to Date](media/ecommerce-dob-date.PNG "transform date of birth to date")</span></span>

1. <span data-ttu-id="db36f-124">No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="db36f-124">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="db36f-125">Salvar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="db36f-125">Save the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="db36f-126">Ingerir dados de compra online</span><span class="sxs-lookup"><span data-stu-id="db36f-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="db36f-127">Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="db36f-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="db36f-128">Escolha o conector de **Texto/CSV** novamente.</span><span class="sxs-lookup"><span data-stu-id="db36f-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="db36f-129">Insira o URL para dados de **Compras online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="db36f-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="db36f-130">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="db36f-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="db36f-131">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="db36f-131">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="db36f-132">**PurchasedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="db36f-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="db36f-133">**TotalPrice**: Moeda</span><span class="sxs-lookup"><span data-stu-id="db36f-133">**TotalPrice**: Currency</span></span>
   
1. <span data-ttu-id="db36f-134">No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="db36f-134">In the **Name** field on the right-hand pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="db36f-135">Salvar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="db36f-135">Save the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="db36f-136">Ingerir dados do cliente do esquema de fidelidade</span><span class="sxs-lookup"><span data-stu-id="db36f-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="db36f-137">Crie uma fonte de dados chamada **LoyaltyScheme**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="db36f-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="db36f-138">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="db36f-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="db36f-139">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="db36f-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="db36f-140">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="db36f-140">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="db36f-141">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="db36f-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="db36f-142">**RewardsPoints**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="db36f-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="db36f-143">**CreatedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="db36f-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="db36f-144">No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="db36f-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="db36f-145">Salvar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="db36f-145">Save the data source.</span></span>


## <a name="task-2---data-unification"></a><span data-ttu-id="db36f-146">Tarefa 2 - Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="db36f-146">Task 2 - Data unification</span></span>

<span data-ttu-id="db36f-147">Depois de ingerir os dados, agora iniciamos o processo de **Mapear, Corresponder, Mesclar** para criar um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="db36f-147">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="db36f-148">Para obter mais informações, consulte [Unificação de dados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="db36f-148">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="db36f-149">Mapa </span><span class="sxs-lookup"><span data-stu-id="db36f-149">Map</span></span>

1. <span data-ttu-id="db36f-150">Depois de ingerir os dados, mapeie os contatos dos dados de comércio eletrônico e de fidelidade para tipos de dados comuns.</span><span class="sxs-lookup"><span data-stu-id="db36f-150">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="db36f-151">Vá para **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="db36f-151">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="db36f-152">Selecione as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="db36f-152">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> 

   :::image type="content" source="media/unify-ecommerce-loyalty.PNG" alt-text="unifique as fontes de dados de comércio eletrônico e fidelidade.":::

1. <span data-ttu-id="db36f-154">Selecione **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="db36f-154">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   :::image type="content" source="media/unify-loyaltyid.PNG" alt-text="Unifique LoyaltyId como chave primária.":::

### <a name="match"></a><span data-ttu-id="db36f-156">Corresponder</span><span class="sxs-lookup"><span data-stu-id="db36f-156">Match</span></span>

1. <span data-ttu-id="db36f-157">Vá para a guia **Corresponder** e selecione **Definir pedido**.</span><span class="sxs-lookup"><span data-stu-id="db36f-157">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="db36f-158">Na lista suspensa **Primária**, escolha **eCommerceContacts : eCommerce** como sua fonte primária e inclua todos os registros.</span><span class="sxs-lookup"><span data-stu-id="db36f-158">In the **Primary** dropdown list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="db36f-159">Na lista suspensa **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registros.</span><span class="sxs-lookup"><span data-stu-id="db36f-159">In the **Entity 2** dropdown list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   :::image type="content" source="media/unify-match-order.PNG" alt-text="Unificar correspondência de comércio eletrônico e fidelidade.":::

1. <span data-ttu-id="db36f-161">Selecione **Criar uma nova regra**</span><span class="sxs-lookup"><span data-stu-id="db36f-161">Select **Create a new rule**</span></span>

1. <span data-ttu-id="db36f-162">Adicione sua primeira condição usando FullName.</span><span class="sxs-lookup"><span data-stu-id="db36f-162">Add your first condition using FullName.</span></span>

   * <span data-ttu-id="db36f-163">Para eCommerceContacts, selecione **FullName** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="db36f-163">For eCommerceContacts select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="db36f-164">Para loyCustomers, selecione **FullName** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="db36f-164">For loyCustomers select **FullName** in the dropdown.</span></span>
   * <span data-ttu-id="db36f-165">Selecione o menu suspenso **Normalizar** e escolha **Inserir (telefone, nome, endereço,...)**.</span><span class="sxs-lookup"><span data-stu-id="db36f-165">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   * <span data-ttu-id="db36f-166">Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="db36f-166">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="db36f-167">Digite o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="db36f-167">Enter the name **FullName, Email** for the new rule.</span></span>

   * <span data-ttu-id="db36f-168">Adicione uma segunda condição para o endereço de e-mail selecionando **Adicionar condição**</span><span class="sxs-lookup"><span data-stu-id="db36f-168">Add a second condition for email address by selecting **Add Condition**</span></span>
   * <span data-ttu-id="db36f-169">Para a entidade eCommerceContacts, selecione **Email** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="db36f-169">For entity eCommerceContacts, choose **EMail** in dropdown.</span></span>
   * <span data-ttu-id="db36f-170">Para a entidade loyCustomers, selecione **Email** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="db36f-170">For entity loyCustomers, choose **EMail** in the dropdown.</span></span> 
   * <span data-ttu-id="db36f-171">Deixe o campo Normalizar em branco.</span><span class="sxs-lookup"><span data-stu-id="db36f-171">Leave Normalize blank.</span></span> 
   * <span data-ttu-id="db36f-172">Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="db36f-172">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   :::image type="content" source="media/unify-match-rule.PNG" alt-text="Regra de correspondência unificada para nome e email.":::

7. <span data-ttu-id="db36f-174">Selecione **Salvar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="db36f-174">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="db36f-175">Merge</span><span class="sxs-lookup"><span data-stu-id="db36f-175">Merge</span></span>

1. <span data-ttu-id="db36f-176">Vá para a guia **Mesclar**.</span><span class="sxs-lookup"><span data-stu-id="db36f-176">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="db36f-177">Na entidade **ContactId** para **loyCustomers**, altere o nome de exibição para **ContactIdLOYALTY** para diferenciá-lo dos outros IDs ingeridos.</span><span class="sxs-lookup"><span data-stu-id="db36f-177">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   :::image type="content" source="media/unify-merge-contactid.PNG" alt-text="renomear contactid de loyalty id.":::

1. <span data-ttu-id="db36f-179">Selecione **Salvar** e **Executar** para iniciar o processo de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="db36f-179">Select **Save** and **Run** to start the Merge Process.</span></span>



## <a name="task-3---configure-transaction-churn-prediction"></a><span data-ttu-id="db36f-180">Tarefa 3 - Configurar a previsão de rotatividade da transação</span><span class="sxs-lookup"><span data-stu-id="db36f-180">Task 3 - Configure transaction churn prediction</span></span>

<span data-ttu-id="db36f-181">Com os perfis de cliente unificados em vigor, agora podemos executar a previsão de rotatividade de assinatura.</span><span class="sxs-lookup"><span data-stu-id="db36f-181">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span> <span data-ttu-id="db36f-182">Para obter etapas detalhadas, consulte o artigo [Previsão de rotatividade de assinatura (versão preliminar)](predict-subscription-churn.md).</span><span class="sxs-lookup"><span data-stu-id="db36f-182">For detailed steps, see the [Subscription churn prediction (preview)](predict-subscription-churn.md) article.</span></span> 

1. <span data-ttu-id="db36f-183">Vá para **Inteligência** > **Descobrir** e selecione usar o **Modelo de rotatividade do cliente**.</span><span class="sxs-lookup"><span data-stu-id="db36f-183">Go to **Intelligence** > **Discover** and select to use the **Customer churn model**.</span></span>

1. <span data-ttu-id="db36f-184">Selecione a opção **Transacional** e selecione **Iniciar**.</span><span class="sxs-lookup"><span data-stu-id="db36f-184">Select the **Transactional** option and select **Get started**.</span></span>

1. <span data-ttu-id="db36f-185">Nomeie o modelo **Previsão de rotatividade de transação OOB eCommerce** e a entidade de saída **OOBeCommerceChurnPrediction**.</span><span class="sxs-lookup"><span data-stu-id="db36f-185">Name the model **OOB eCommerce Transaction Churn Prediction** and the output entity **OOBeCommerceChurnPrediction**.</span></span>

1. <span data-ttu-id="db36f-186">Defina duas condições para o modelo de rotatividade:</span><span class="sxs-lookup"><span data-stu-id="db36f-186">Define two conditions for the churn model:</span></span>

   * <span data-ttu-id="db36f-187">**Amplitude da previsão**: **pelo menos 60** dias.</span><span class="sxs-lookup"><span data-stu-id="db36f-187">**Prediction window**: **at least 60** days.</span></span> <span data-ttu-id="db36f-188">Essa configuração define o quão longe no futuro queremos prever a rotatividade de clientes.</span><span class="sxs-lookup"><span data-stu-id="db36f-188">This setting defines how far into the future do we want to predict customer churn.</span></span>

   * <span data-ttu-id="db36f-189">**Definição de rotatividade**: **pelo menos 60** dias.</span><span class="sxs-lookup"><span data-stu-id="db36f-189">**Churn definition**: **at least 60** days.</span></span> <span data-ttu-id="db36f-190">O período sem compra após o qual um cliente é considerado rotacionado.</span><span class="sxs-lookup"><span data-stu-id="db36f-190">The duration without purchase after which a customer is considered churned.</span></span>

     :::image type="content" source="media/model-levers.PNG" alt-text="Selecione a janela de previsão de niveladores de modelo e definição de rotatividade.":::

1. <span data-ttu-id="db36f-192">Selecione **Histórico de Compras (obrigatório)** e selecione **Adicionar dados** para histórico de compra.</span><span class="sxs-lookup"><span data-stu-id="db36f-192">Select **Purchase History (required)** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="db36f-193">Adicione a entidade **eCommercePurchases : eCommerce** e mapeie os campos do eCommerce para os campos correspondentes exigidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="db36f-193">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="db36f-194">Junte-se à entidade **eCommercePurchases : eCommerce** com **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="db36f-194">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   :::image type="content" source="media/model-purchase-join.PNG" alt-text="Junte-se a entidades de comércio eletrônico.":::

1. <span data-ttu-id="db36f-196">Selecione **Avançar** para definir o cronograma do modelo.</span><span class="sxs-lookup"><span data-stu-id="db36f-196">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="db36f-197">O modelo precisa ser treinado regularmente para aprender novos padrões quando novos dados forem ingeridos.</span><span class="sxs-lookup"><span data-stu-id="db36f-197">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="db36f-198">Para este exemplo, selecione **Mensal**.</span><span class="sxs-lookup"><span data-stu-id="db36f-198">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="db36f-199">Depois de revisar todos os detalhes, selecione **Salvar e executar**.</span><span class="sxs-lookup"><span data-stu-id="db36f-199">After reviewing all the details, select **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="db36f-200">Tarefa 4 - Revise os resultados e explicações do modelo</span><span class="sxs-lookup"><span data-stu-id="db36f-200">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="db36f-201">Deixe o modelo concluir o treinamento e a pontuação dos dados.</span><span class="sxs-lookup"><span data-stu-id="db36f-201">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="db36f-202">Agora, você pode revisar as explicações do modelo de rotatividade de assinatura.</span><span class="sxs-lookup"><span data-stu-id="db36f-202">You can now review the subscription churn model explanations.</span></span> <span data-ttu-id="db36f-203">Para mais informações, consulte [Analisar um status de previsão e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="db36f-203">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-churn-risk-customers"></a><span data-ttu-id="db36f-204">Tarefa 5 - Crie um segmento de clientes de alto risco de rotatividade</span><span class="sxs-lookup"><span data-stu-id="db36f-204">Task 5 - Create a segment of high churn-risk customers</span></span>

<span data-ttu-id="db36f-205">Executar o modelo de produção cria uma nova entidade que você pode ver em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="db36f-205">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>   

<span data-ttu-id="db36f-206">Você pode criar um novo segmento com base na entidade criada pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="db36f-206">You can create a new segment based on the entity created by the model.</span></span>

1.  <span data-ttu-id="db36f-207">Vá para **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="db36f-207">Go to **Segments**.</span></span> <span data-ttu-id="db36f-208">Selecione **Novo** e escolha **Criar de** > **Inteligência**.</span><span class="sxs-lookup"><span data-stu-id="db36f-208">Select **New** and choose **Create from** > **Intelligence**.</span></span> 

   :::image type="content" source="media/segment-intelligence.PNG" alt-text="Criando um segmento com a saída do modelo.":::

1. <span data-ttu-id="db36f-210">Selecione o ponto de extremidade **OOBSubscriptionChurnPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="db36f-210">Select the **OOBSubscriptionChurnPrediction** endpoint and define the segment:</span></span> 
   - <span data-ttu-id="db36f-211">Campo: ChurnScore</span><span class="sxs-lookup"><span data-stu-id="db36f-211">Field: ChurnScore</span></span>
   - <span data-ttu-id="db36f-212">Operador: maior que</span><span class="sxs-lookup"><span data-stu-id="db36f-212">Operator: greater than</span></span>
   - <span data-ttu-id="db36f-213">Valor: 0,6</span><span class="sxs-lookup"><span data-stu-id="db36f-213">Value: 0.6</span></span>
   
   :::image type="content" source="media/segment-setup-subs.PNG" alt-text="Configure o segmento de rotatividade de assinaturas.":::

<span data-ttu-id="db36f-215">Agora, você tem um segmento que é atualizado dinamicamente que identifica clientes de alto risco de rotatividade para este negócio de assinatura.</span><span class="sxs-lookup"><span data-stu-id="db36f-215">You now have a segment that is dynamically updated which identifies high churn-risk customers for this subscription business.</span></span>

<span data-ttu-id="db36f-216">Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="db36f-216">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]