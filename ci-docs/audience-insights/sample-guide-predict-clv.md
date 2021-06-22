---
title: Exemplo de guia de previsão do valor de permanência do cliente
description: Use este exemplo de guia para testar o modelo de previsão do valor de permanência do cliente.
ms.date: 05/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: yashlundia
ms.author: yalundia
manager: shellyha
ms.openlocfilehash: 73d294a285b4ad706bec7fe925c1daa0b839ddd6
ms.sourcegitcommit: 7b6189e47ed1f87e7ce35d40e4cf7a6730f31ef2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6129931"
---
# <a name="customer-lifetime-value-clv-prediction-sample-guide"></a><span data-ttu-id="26f99-103">Exemplo de guia de previsão do valor de permanência do cliente (CLV)</span><span class="sxs-lookup"><span data-stu-id="26f99-103">Customer lifetime value (CLV) prediction sample guide</span></span>

<span data-ttu-id="26f99-104">Este guia orientará você usando um exemplo completo de previsão do valor de permanência do cliente (CLV) no Customer Insights por meio de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="26f99-104">This guide will walk you through an end to end example of Customer lifetime value (CLV) prediction in Customer Insights using sample data.</span></span>

## <a name="scenario"></a><span data-ttu-id="26f99-105">Cenário</span><span class="sxs-lookup"><span data-stu-id="26f99-105">Scenario</span></span>

<span data-ttu-id="26f99-106">A Contoso é uma empresa que produz café e máquinas de café de alta qualidade.</span><span class="sxs-lookup"><span data-stu-id="26f99-106">Contoso is a company that produces high-quality coffee and coffee machines.</span></span> <span data-ttu-id="26f99-107">Ela vende os produtos por meio do site Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="26f99-107">They sell the products through their Contoso Coffee website.</span></span> <span data-ttu-id="26f99-108">A empresa quer entender o valor (receita) que seus clientes podem gerar nos próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="26f99-108">The company wants to understand the value (revenue) that their customers can generate in the next 12 months.</span></span> <span data-ttu-id="26f99-109">Saber o valor esperado de seus clientes nos próximos 12 meses a ajudará a direcionar seus esforços de marketing para clientes de alto valor.</span><span class="sxs-lookup"><span data-stu-id="26f99-109">Knowing the expected value of their customers in the next 12 months will help them steer their marketing efforts on high value customers.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="26f99-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="26f99-110">Prerequisites</span></span>

- <span data-ttu-id="26f99-111">Pelo menos, [Permissões de colaborador](permissions.md) em insights do público-alvo.</span><span class="sxs-lookup"><span data-stu-id="26f99-111">At least [Contributor permissions](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="26f99-112">Recomendamos que você implemente as seguintes etapas [em um novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="26f99-112">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="26f99-113">Tarefa 1 - Ingerir dados</span><span class="sxs-lookup"><span data-stu-id="26f99-113">Task 1 - Ingest data</span></span>

<span data-ttu-id="26f99-114">Reveja os artigos [sobre ingestão de dados](data-sources.md) e [importação de fontes de dados usando conectores do Power Query](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="26f99-114">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md).</span></span> <span data-ttu-id="26f99-115">As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.</span><span class="sxs-lookup"><span data-stu-id="26f99-115">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="26f99-116">Ingerir dados do cliente da plataforma de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="26f99-116">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="26f99-117">Crie uma fonte de dados chamada **Comércio eletrônico**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="26f99-117">Create a data source named  **eCommerce** , choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="26f99-118">Insira o URL para contatos de comércio eletrônico [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span><span class="sxs-lookup"><span data-stu-id="26f99-118">Enter the URL for eCommerce contacts [https://aka.ms/ciadclasscontacts](https://aka.ms/ciadclasscontacts).</span></span>

1. <span data-ttu-id="26f99-119">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="26f99-119">While editing the data, select  **Transform**  and then  **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="26f99-120">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="26f99-120">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="26f99-121">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="26f99-121">**DateOfBirth** : Date</span></span>
   - <span data-ttu-id="26f99-122">**CreatedOn**: Data/Hora/Zona</span><span class="sxs-lookup"><span data-stu-id="26f99-122">**CreatedOn** : Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

1. <span data-ttu-id="26f99-124">No campo 'Nome' no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="26f99-124">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

1. <span data-ttu-id="26f99-125">**Salvar** a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="26f99-125">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="26f99-126">Ingerir dados de compra online</span><span class="sxs-lookup"><span data-stu-id="26f99-126">Ingest online purchase data</span></span>

1. <span data-ttu-id="26f99-127">Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="26f99-127">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="26f99-128">Escolha o conector de **Texto/CSV** novamente.</span><span class="sxs-lookup"><span data-stu-id="26f99-128">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="26f99-129">Insira o URL para dados de **Compras online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="26f99-129">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="26f99-130">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="26f99-130">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="26f99-131">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="26f99-131">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="26f99-132">**PurchasedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="26f99-132">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="26f99-133">**TotalPrice**: Moeda</span><span class="sxs-lookup"><span data-stu-id="26f99-133">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="26f99-134">No campo **Nome** no painel lateral, renomeie sua fonte de dados de **Consulta** para **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="26f99-134">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="26f99-135">**Salvar** a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="26f99-135">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="26f99-136">Ingerir dados do cliente do esquema de fidelidade</span><span class="sxs-lookup"><span data-stu-id="26f99-136">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="26f99-137">Crie uma fonte de dados chamada **LoyaltyScheme**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="26f99-137">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="26f99-138">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="26f99-138">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="26f99-139">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="26f99-139">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="26f99-140">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="26f99-140">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="26f99-141">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="26f99-141">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="26f99-142">**RewardsPoints**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="26f99-142">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="26f99-143">**CreatedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="26f99-143">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="26f99-144">No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="26f99-144">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="26f99-145">**Salvar** a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="26f99-145">**Save** the data source.</span></span>

### <a name="ingest-customer-data-from-website-reviews"></a><span data-ttu-id="26f99-146">Ingerir dados do cliente de comentários do site</span><span class="sxs-lookup"><span data-stu-id="26f99-146">Ingest customer data from website reviews</span></span>

1. <span data-ttu-id="26f99-147">Crie uma fonte de dados chamada **Site da Web**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="26f99-147">Create a data source named **Website**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="26f99-148">Insira o URL para contatos de comércio eletrônico https://aka.ms/CI-ILT/WebReviews.</span><span class="sxs-lookup"><span data-stu-id="26f99-148">Enter the URL for eCommerce contacts https://aka.ms/CI-ILT/WebReviews.</span></span>

1. <span data-ttu-id="26f99-149">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="26f99-149">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="26f99-150">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="26f99-150">Update the datatype for the columns listed below:</span></span>

   - <span data-ttu-id="26f99-151">**ReviewRating**: número decimal</span><span class="sxs-lookup"><span data-stu-id="26f99-151">**ReviewRating**: Decimal number</span></span>
   - <span data-ttu-id="26f99-152">**ReviewDate**: Data</span><span class="sxs-lookup"><span data-stu-id="26f99-152">**ReviewDate**: Date</span></span>

1. <span data-ttu-id="26f99-153">No campo "Nome" no painel direito, renomeie sua fonte de dados de **Consulta** para **Avaliações**.</span><span class="sxs-lookup"><span data-stu-id="26f99-153">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **Reviews**.</span></span>

1. <span data-ttu-id="26f99-154">**Salvar** a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="26f99-154">**Save** the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="26f99-155">Tarefa 2 - Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="26f99-155">Task 2 - Data unification</span></span>

<span data-ttu-id="26f99-156">Depois de ingerir os dados, agora começamos o processo de unificação de dados para criar um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="26f99-156">After ingesting the data, we now begin the data unification process to create a unified customer profile.</span></span> <span data-ttu-id="26f99-157">Para obter mais informações, consulte [Unificação de dados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="26f99-157">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="26f99-158">Mapa </span><span class="sxs-lookup"><span data-stu-id="26f99-158">Map</span></span>

1. <span data-ttu-id="26f99-159">Depois de ingerir os dados, mapeie os contatos dos dados de comércio eletrônico e de fidelidade para tipos de dados comuns.</span><span class="sxs-lookup"><span data-stu-id="26f99-159">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="26f99-160">Vá para **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="26f99-160">Go to **Data** > **Unify** > **Map**.</span></span>

1. <span data-ttu-id="26f99-161">Selecione as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="26f99-161">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span> <span data-ttu-id="26f99-162">Em seguida, selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="26f99-162">Then, select **Apply**.</span></span>

   ![unifique as fontes de dados de comércio eletrônico e fidelidade.](media/unify-ecommerce-loyalty.png)

1. <span data-ttu-id="26f99-164">Selecione **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="26f99-164">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifique LoyaltyId como chave primária.](media/unify-loyaltyid.png)

1. <span data-ttu-id="26f99-166">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="26f99-166">Select **Save**.</span></span>

### <a name="match"></a><span data-ttu-id="26f99-167">Corresponder</span><span class="sxs-lookup"><span data-stu-id="26f99-167">Match</span></span>

1. <span data-ttu-id="26f99-168">Vá para a guia **Corresponder** e selecione **Definir pedido**.</span><span class="sxs-lookup"><span data-stu-id="26f99-168">Go to the **Match** tab and select **Set Order**.</span></span>

1. <span data-ttu-id="26f99-169">Na lista suspensa **Primário**, escolha **eCommerceContacts : eCommerce** como fonte primária e inclua todos os registros.</span><span class="sxs-lookup"><span data-stu-id="26f99-169">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

1. <span data-ttu-id="26f99-170">Na lista suspensa **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registros.</span><span class="sxs-lookup"><span data-stu-id="26f99-170">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unificar correspondência de comércio eletrônico e fidelidade.](media/unify-match-order.png)

1. <span data-ttu-id="26f99-172">Selecione **Adicionar regra**</span><span class="sxs-lookup"><span data-stu-id="26f99-172">Select **Add rule**</span></span>

1. <span data-ttu-id="26f99-173">Adicione sua primeira condição usando FullName.</span><span class="sxs-lookup"><span data-stu-id="26f99-173">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="26f99-174">Para eCommerceContacts selecione **FullName** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="26f99-174">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="26f99-175">Para loyCustomers selecione **FullName** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="26f99-175">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="26f99-176">Selecione o menu suspenso **Normalizar** e escolha **Inserir (telefone, nome, endereço,...)**.</span><span class="sxs-lookup"><span data-stu-id="26f99-176">Select the **Normalize** drop-down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="26f99-177">Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="26f99-177">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

1. <span data-ttu-id="26f99-178">Digite o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="26f99-178">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="26f99-179">Adicione uma segunda condição para o endereço de e-mail selecionando **Adicionar condição**</span><span class="sxs-lookup"><span data-stu-id="26f99-179">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="26f99-180">Para a entidade eCommerceContacts, escolha **Email** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="26f99-180">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="26f99-181">Para a entidade loyCustomers, escolha **Email** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="26f99-181">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="26f99-182">Deixe o campo Normalizar em branco.</span><span class="sxs-lookup"><span data-stu-id="26f99-182">Leave Normalize blank.</span></span>
   - <span data-ttu-id="26f99-183">Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="26f99-183">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Regra de correspondência unificada para nome e email.](media/unify-match-rule.png)

1. <span data-ttu-id="26f99-185">Selecione **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="26f99-185">Select **Done**.</span></span>

1. <span data-ttu-id="26f99-186">Selecione **Salvar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="26f99-186">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="26f99-187">Mesclagem</span><span class="sxs-lookup"><span data-stu-id="26f99-187">Merge</span></span>

1. <span data-ttu-id="26f99-188">Vá para a guia **Mesclar**.</span><span class="sxs-lookup"><span data-stu-id="26f99-188">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="26f99-189">Na entidade **ContactId** para **loyCustomers**, altere o nome de exibição para **ContactIdLOYALTY** para diferenciá-lo dos outros IDs ingeridos.</span><span class="sxs-lookup"><span data-stu-id="26f99-189">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![renomear contactid de loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="26f99-191">Selecione **Salvar** e **Executar mesclagem e processos downstream**.</span><span class="sxs-lookup"><span data-stu-id="26f99-191">Select **Save** and **Run merge and downstream processes**.</span></span>

## <a name="task-3---configure-customer-lifetime-value-prediction"></a><span data-ttu-id="26f99-192">Tarefa 3 - Configurar a previsão do valor de permanência do cliente</span><span class="sxs-lookup"><span data-stu-id="26f99-192">Task 3 - Configure customer lifetime value prediction</span></span>

<span data-ttu-id="26f99-193">Com os perfis de cliente unificados em vigor, agora podemos executar a previsão do valor de permanência do cliente.</span><span class="sxs-lookup"><span data-stu-id="26f99-193">With the unified customer profiles in place, we can now run the customer lifetime value prediction.</span></span> <span data-ttu-id="26f99-194">Para obter etapas detalhadas, consulte [Previsão do valor de permanência do cliente (versão preliminar)](predict-customer-lifetime-value.md).</span><span class="sxs-lookup"><span data-stu-id="26f99-194">For detailed steps, see [Customer Lifetime Value prediction (preview)](predict-customer-lifetime-value.md).</span></span>

1. <span data-ttu-id="26f99-195">Acesse **Inteligência**  > **Previsões** e selecione o **Modelo de valor de permanência do cliente**.</span><span class="sxs-lookup"><span data-stu-id="26f99-195">Go to  **Intelligence**  > **Predictions**  and select the **Customer lifetime value model**.</span></span>

1. <span data-ttu-id="26f99-196">Acesse as informações no painel lateral e selecione **Introdução**.</span><span class="sxs-lookup"><span data-stu-id="26f99-196">Go through the information in the side pane and select **Get started**.</span></span>

1. <span data-ttu-id="26f99-197">Nomeie o modelo **OOB eCommerce CLV Prediction** e a entidade de saída **OOBeCommerceCLVPrediction**.</span><span class="sxs-lookup"><span data-stu-id="26f99-197">Name the model **OOB eCommerce CLV Prediction** and the output entity  **OOBeCommerceCLVPrediction**.</span></span>

1. <span data-ttu-id="26f99-198">Defina as preferências do modelo para o modelo CLV:</span><span class="sxs-lookup"><span data-stu-id="26f99-198">Define model preferences for the CLV model:</span></span>
   - <span data-ttu-id="26f99-199">**Período de previsão**: **12 meses ou 1 ano**.</span><span class="sxs-lookup"><span data-stu-id="26f99-199">**Prediction time period**: **12 months or 1 year**.</span></span> <span data-ttu-id="26f99-200">Essa configuração define o quão longe no futuro prever o valor de permanência do cliente.</span><span class="sxs-lookup"><span data-stu-id="26f99-200">This setting defines how far into the future to predict customer lifetime value.</span></span>
   - <span data-ttu-id="26f99-201">**Clientes ativos**: especifique o que os clientes ativos significam para o seu negócio.</span><span class="sxs-lookup"><span data-stu-id="26f99-201">**Active customers**: Specify what active customers mean for your business.</span></span> <span data-ttu-id="26f99-202">Defina o período histórico em que um cliente deve ter pelo menos uma transação para ser considerado ativo.</span><span class="sxs-lookup"><span data-stu-id="26f99-202">Set the historical time frame in which a customer must have had at least one transaction to be considered active.</span></span> <span data-ttu-id="26f99-203">O modelo prevê CLV somente para clientes ativos.</span><span class="sxs-lookup"><span data-stu-id="26f99-203">The model will only predict CLV for active customers.</span></span> <span data-ttu-id="26f99-204">Escolha entre deixar o modelo calcular o período com base nos dados históricos da transação ou fornecer um período específico.</span><span class="sxs-lookup"><span data-stu-id="26f99-204">Choose between letting the model calculate the time period based on historical transaction data or provide a specific time frame.</span></span> <span data-ttu-id="26f99-205">Neste exemplo de guia, **deixamos que o modelo calcule o intervalo de compra**, que é a opção padrão.</span><span class="sxs-lookup"><span data-stu-id="26f99-205">In this sample guide, we **let the model calculate purchase interval**, which is the default option.</span></span>
   - <span data-ttu-id="26f99-206">**Clientes de Alto Valor**: defina os clientes de alto valor como um percentual dos clientes que pagam mais.</span><span class="sxs-lookup"><span data-stu-id="26f99-206">**High value customers**: Define high value customers as a percentile of top-paying customers.</span></span> <span data-ttu-id="26f99-207">O modelo usa essa entrada para fornecer resultados que se encaixam na definição de negócios de clientes de alto valor.</span><span class="sxs-lookup"><span data-stu-id="26f99-207">The model uses this input to provide results that fit your business definition of high value customers.</span></span> <span data-ttu-id="26f99-208">Você pode optar por deixar o modelo definir clientes de alto valor.</span><span class="sxs-lookup"><span data-stu-id="26f99-208">You can choose to let the model define high value customers.</span></span> <span data-ttu-id="26f99-209">Ele usa uma regra heurística que deriva o percentil.</span><span class="sxs-lookup"><span data-stu-id="26f99-209">It uses a heuristic rule that derives the percentile.</span></span> <span data-ttu-id="26f99-210">Você também pode definir clientes de alto valor como um percentual dos principais clientes futuros pagantes.</span><span class="sxs-lookup"><span data-stu-id="26f99-210">You can also define high value customers as a percentile of top future paying customers.</span></span> <span data-ttu-id="26f99-211">Neste exemplo de guia, definimos manualmente os clientes de alto valor como **30% dos principais clientes pagantes ativos** e selecionamos **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="26f99-211">In this sample guide, we manually define high value customers as **top 30% of active paying customers** and select **Next**.</span></span>

    :::image type="content" source="media/clv-model-preferences.png" alt-text="As preferências são a etapa da experiência guiada para o modelo CLV.":::

1. <span data-ttu-id="26f99-213">Na etapa **Dados obrigatórios**, selecione **Adicionar dados** para fornecer os dados do histórico de transações.</span><span class="sxs-lookup"><span data-stu-id="26f99-213">In the **Required Data** step, select **Add data** to provide the transaction history data.</span></span>

1. <span data-ttu-id="26f99-214">Adicione a entidade **eCommercePurchases : eCommerce** e mapeie os atributos exigidos pelo modelo:</span><span class="sxs-lookup"><span data-stu-id="26f99-214">Add the **eCommercePurchases : eCommerce** entity and map the attributes that are required by the model:</span></span>
   - <span data-ttu-id="26f99-215">ID da transação: eCommerce.eCommercePurchases.PurchaseId</span><span class="sxs-lookup"><span data-stu-id="26f99-215">Transaction ID: eCommerce.eCommercePurchases.PurchaseId</span></span>
   - <span data-ttu-id="26f99-216">Data da transação: eCommerce.eCommercePurchases.PurchasedOn</span><span class="sxs-lookup"><span data-stu-id="26f99-216">Transaction date: eCommerce.eCommercePurchases.PurchasedOn</span></span>
   - <span data-ttu-id="26f99-217">Valor da transação: eCommerce.eCommercePurchases.TotalPrice</span><span class="sxs-lookup"><span data-stu-id="26f99-217">Transaction amount: eCommerce.eCommercePurchases.TotalPrice</span></span>
   - <span data-ttu-id="26f99-218">ID do produto: eCommerce.eCommercePurchases.ProductId</span><span class="sxs-lookup"><span data-stu-id="26f99-218">Product ID: eCommerce.eCommercePurchases.ProductId</span></span>

1. <span data-ttu-id="26f99-219">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="26f99-219">Select **Next**.</span></span>

1. <span data-ttu-id="26f99-220">Configure a relação entre a entidade **eCommercePurchases : eCommerce** e **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="26f99-220">Set up the relationship between the **eCommercePurchases : eCommerce** entity and  **eCommerceContacts : eCommerce**.</span></span>

1. <span data-ttu-id="26f99-221">A etapa **Dados adicionais (opcional)** permite adicionar mais dados de atividades do cliente.</span><span class="sxs-lookup"><span data-stu-id="26f99-221">The **Additional data (optional)** step allows you to add more customer activity data.</span></span> <span data-ttu-id="26f99-222">Esses dados podem ajudar a obter mais informações sobre as interações do cliente com sua empresa, o que pode contribuir para o CLV.</span><span class="sxs-lookup"><span data-stu-id="26f99-222">This data can help to get more insights for customer interactions with your business, which can contribute to CLV.</span></span> <span data-ttu-id="26f99-223">Adicionar as principais interações do cliente, como logs da Web, logs de SAC ou histórico do programa de recompensas, pode melhorar a precisão das previsões.</span><span class="sxs-lookup"><span data-stu-id="26f99-223">Adding key customer interactions like web logs, customer service logs, or rewards program history can improve the accuracy of predictions.</span></span> <span data-ttu-id="26f99-224">Selecione **Adicionar dados** para incluir mais dados de atividade do cliente.</span><span class="sxs-lookup"><span data-stu-id="26f99-224">Select **Add data** to include more customer activity data.</span></span>

1. <span data-ttu-id="26f99-225">Adicione a entidade de atividade do cliente e mapeie os nomes de seus campos para os campos correspondentes exigidos pelo modelo:</span><span class="sxs-lookup"><span data-stu-id="26f99-225">Add the customer activity entity and map its fields names to the corresponding fields required by the model:</span></span>
   - <span data-ttu-id="26f99-226">Entidade de atividade do cliente: Reviews:Website</span><span class="sxs-lookup"><span data-stu-id="26f99-226">Customer activity entity: Reviews:Website</span></span>
   - <span data-ttu-id="26f99-227">Chave primária: Website.Reviews.ReviewId</span><span class="sxs-lookup"><span data-stu-id="26f99-227">Primary key: Website.Reviews.ReviewId</span></span>
   - <span data-ttu-id="26f99-228">Carimbo de data/hora: Website.Reviews.ReviewDate</span><span class="sxs-lookup"><span data-stu-id="26f99-228">Timestamp: Website.Reviews.ReviewDate</span></span>
   - <span data-ttu-id="26f99-229">Evento (nome da atividade): Website.Reviews.ActivityTypeDisplay</span><span class="sxs-lookup"><span data-stu-id="26f99-229">Event (activity name): Website.Reviews.ActivityTypeDisplay</span></span>
   - <span data-ttu-id="26f99-230">Detalhes (quantidade ou valor): Website.Reviews.ReviewRating</span><span class="sxs-lookup"><span data-stu-id="26f99-230">Details (amount or value): Website.Reviews.ReviewRating</span></span>

1. <span data-ttu-id="26f99-231">Selecione **Avançar** e configure a atividade e a relação entre os dados da transação e os dados do cliente:</span><span class="sxs-lookup"><span data-stu-id="26f99-231">Select **Next** and configure the activity and the relationship between the transaction data and the customer data:</span></span>  
   - <span data-ttu-id="26f99-232">Tipo de atividade: escolha existente</span><span class="sxs-lookup"><span data-stu-id="26f99-232">Activity type: Choose existing</span></span>
   - <span data-ttu-id="26f99-233">Rótulo da atividade: revisão</span><span class="sxs-lookup"><span data-stu-id="26f99-233">Activity label: Review</span></span>
   - <span data-ttu-id="26f99-234">Rótulo correspondente: Website.Reviews.UserId</span><span class="sxs-lookup"><span data-stu-id="26f99-234">Corresponding label: Website.Reviews.UserId</span></span>
   - <span data-ttu-id="26f99-235">Entidade do cliente: eCommerceContacts:eCommerce</span><span class="sxs-lookup"><span data-stu-id="26f99-235">Customer entity: eCommerceContacts:eCommerce</span></span>
   - <span data-ttu-id="26f99-236">Relacionamento: WebsiteReviews</span><span class="sxs-lookup"><span data-stu-id="26f99-236">Relationship: WebsiteReviews</span></span>

1. <span data-ttu-id="26f99-237">Selecione **Avançar** para definir o cronograma do modelo.</span><span class="sxs-lookup"><span data-stu-id="26f99-237">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="26f99-238">O modelo precisa ser treinado regularmente para aprender novos padrões quando há novos dados ingeridos.</span><span class="sxs-lookup"><span data-stu-id="26f99-238">The model needs to train regularly to learn new patterns when there's new data ingested.</span></span> <span data-ttu-id="26f99-239">Neste exemplo, escolha **Mensal**.</span><span class="sxs-lookup"><span data-stu-id="26f99-239">For this example, choose **Monthly**.</span></span>

1. <span data-ttu-id="26f99-240">Depois de revisar todos os detalhes, selecione **Salvar e executar**.</span><span class="sxs-lookup"><span data-stu-id="26f99-240">After reviewing all the details, select  **Save and Run**.</span></span>

## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="26f99-241">Tarefa 4 - Revise os resultados e explicações do modelo</span><span class="sxs-lookup"><span data-stu-id="26f99-241">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="26f99-242">Deixe o modelo concluir o treinamento e a pontuação dos dados.</span><span class="sxs-lookup"><span data-stu-id="26f99-242">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="26f99-243">Em seguida, você pode revisar os resultados e explicações do modelo CLV.</span><span class="sxs-lookup"><span data-stu-id="26f99-243">Next, you can review the CLV model results and explanations.</span></span> <span data-ttu-id="26f99-244">Para mais informações, consulte [Analisar um status de previsão e resultados](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="26f99-244">For more information, see [Review a prediction status and results](predict-customer-lifetime-value.md#review-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-value-customers"></a><span data-ttu-id="26f99-245">Tarefa 5 - Criar um segmento de clientes de alto valor</span><span class="sxs-lookup"><span data-stu-id="26f99-245">Task 5 - Create a segment of high value customers</span></span>

<span data-ttu-id="26f99-246">Executar o modelo cria uma entidade, que é listada em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="26f99-246">Running the model creates a new entity, which is listed on **Data** > **Entities**.</span></span> <span data-ttu-id="26f99-247">Você pode criar um segmento de cliente com base na entidade criada pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="26f99-247">You can create a new customer segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="26f99-248">Vá para **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="26f99-248">Go to **Segments**.</span></span> 

1. <span data-ttu-id="26f99-249">Selecione **Novo** e escolha **Criar de** > **Inteligência**.</span><span class="sxs-lookup"><span data-stu-id="26f99-249">Select  **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Criando um segmento com a saída do modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="26f99-251">Selecione a entidade **OOBeCommerceCLVPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="26f99-251">Select the  **OOBeCommerceCLVPrediction** entity and define the segment:</span></span>
  - <span data-ttu-id="26f99-252">Campo: CLVScore</span><span class="sxs-lookup"><span data-stu-id="26f99-252">Field: CLVScore</span></span>
  - <span data-ttu-id="26f99-253">Operador: maior que</span><span class="sxs-lookup"><span data-stu-id="26f99-253">Operator: greater than</span></span>
  - <span data-ttu-id="26f99-254">Valor: 1500</span><span class="sxs-lookup"><span data-stu-id="26f99-254">Value: 1500</span></span>

1. <span data-ttu-id="26f99-255">Selecione **Revisar** e **Salvar** o segmento.</span><span class="sxs-lookup"><span data-stu-id="26f99-255">Select **Review** and **Save** the segment.</span></span>

<span data-ttu-id="26f99-256">Agora você tem um segmento que identifica os clientes que devem gerar mais de US $ 1.500 de receita nos próximos 12 meses.</span><span class="sxs-lookup"><span data-stu-id="26f99-256">You now have a segment that identifies customers who are predicted to generate more than $1500 of revenue in the next 12 months.</span></span> <span data-ttu-id="26f99-257">Este segmento é atualizado dinamicamente se mais dados forem ingeridos.</span><span class="sxs-lookup"><span data-stu-id="26f99-257">This segment gets updated dynamically if more data is ingested.</span></span>

<span data-ttu-id="26f99-258">Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="26f99-258">For more information, see [Create and manage segments](segments.md).</span></span>
