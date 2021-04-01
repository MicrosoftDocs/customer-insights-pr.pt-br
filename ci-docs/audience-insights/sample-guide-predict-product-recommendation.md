---
title: Guia de amostra para previsão de recomendação do produto
description: Use este guia de amostra para experimentar o modelo de previsão de recomendação do produto pronto para uso.
ms.date: 02/10/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: 20072d14b160e54f5ad044adc1de6c079bf790e4
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595259"
---
# <a name="product-recommendation-prediction-preview-sample-guide"></a><span data-ttu-id="31422-103">Guia de amostra para previsão de recomendação do produto (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="31422-103">Product recommendation prediction (preview) sample guide</span></span>

<span data-ttu-id="31422-104">Explicaremos a você um exemplo de ponta a ponta de previsão de recomendação do produto usando os dados de exemplo fornecidos abaixo.</span><span class="sxs-lookup"><span data-stu-id="31422-104">We'll walk you through an end to end example of product recommendation prediction using the sample data provided below.</span></span>

## <a name="scenario"></a><span data-ttu-id="31422-105">Cenário</span><span class="sxs-lookup"><span data-stu-id="31422-105">Scenario</span></span>

<span data-ttu-id="31422-106">A Contoso é uma empresa que produz café e máquinas de café de alta qualidade, que são vendidas por meio do site Contoso Coffee.</span><span class="sxs-lookup"><span data-stu-id="31422-106">Contoso is a company that produces high-quality coffee and coffee machines, which they sell through their Contoso Coffee website.</span></span> <span data-ttu-id="31422-107">O objetivo deles é entender quais produtos eles devem recomendar a seus clientes recorrentes.</span><span class="sxs-lookup"><span data-stu-id="31422-107">Their goal is to understand which products should they recommend to their recurring customers.</span></span> <span data-ttu-id="31422-108">Saber o que os clientes estão mais **propenso a comprar**, pode ajudá-los a economizar esforços de marketing, concentrando-se em itens específicos.</span><span class="sxs-lookup"><span data-stu-id="31422-108">Knowing what customers are more **likely to purchase**, can help them save marketing efforts by focusing on specific items.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="31422-109">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="31422-109">Prerequisites</span></span>

- <span data-ttu-id="31422-110">Por último, [Permissões de colaborador](permissions.md) em Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="31422-110">At least [Contributor permissions](permissions.md) in Customer Insights.</span></span>
- <span data-ttu-id="31422-111">Recomendamos que você implemente as seguintes etapas [em um novo ambiente](manage-environments.md).</span><span class="sxs-lookup"><span data-stu-id="31422-111">We recommend that you implement the following steps [in a new environment](manage-environments.md).</span></span>

## <a name="task-1---ingest-data"></a><span data-ttu-id="31422-112">Tarefa 1 - Ingerir dados</span><span class="sxs-lookup"><span data-stu-id="31422-112">Task 1 - Ingest data</span></span>

<span data-ttu-id="31422-113">Reveja os artigos [sobre ingestão de dados](data-sources.md) e [importar fontes de dados usando Power Query conectores](connect-power-query.md), especificamente.</span><span class="sxs-lookup"><span data-stu-id="31422-113">Review the articles [about data ingestion](data-sources.md) and [importing data sources using Power Query connectors](connect-power-query.md) specifically.</span></span> <span data-ttu-id="31422-114">As informações a seguir pressupõem que você está familiarizado com a ingestão de dados em geral.</span><span class="sxs-lookup"><span data-stu-id="31422-114">The following information assumes you familiarized with ingesting data in general.</span></span>

### <a name="ingest-customer-data-from-ecommerce-platform"></a><span data-ttu-id="31422-115">Ingerir dados do cliente da plataforma de comércio eletrônico</span><span class="sxs-lookup"><span data-stu-id="31422-115">Ingest customer data from eCommerce platform</span></span>

1. <span data-ttu-id="31422-116">Crie uma fonte de dados chamada **Comércio eletrônico**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="31422-116">Create a data source named **eCommerce**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="31422-117">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscontacts.</span><span class="sxs-lookup"><span data-stu-id="31422-117">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscontacts.</span></span>

1. <span data-ttu-id="31422-118">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="31422-118">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="31422-119">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="31422-119">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="31422-120">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="31422-120">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="31422-121">**CreatedOn**: Data/Hora/Zona</span><span class="sxs-lookup"><span data-stu-id="31422-121">**CreatedOn**: Date/Time/Zone</span></span>

   :::image type="content" source="media/ecommerce-dob-date.PNG" alt-text="Transformar data de nascimento em data.":::

5. <span data-ttu-id="31422-123">No campo 'Nome' no painel direito, renomeie sua fonte de dados de **Consulta** para **eCommerceContacts**</span><span class="sxs-lookup"><span data-stu-id="31422-123">In the 'Name' field on the right-hand pane, rename your data source from **Query** to **eCommerceContacts**</span></span>

6. <span data-ttu-id="31422-124">**Salvar** a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="31422-124">**Save** the data source.</span></span>

### <a name="ingest-online-purchase-data"></a><span data-ttu-id="31422-125">Ingerir dados de compra online</span><span class="sxs-lookup"><span data-stu-id="31422-125">Ingest online purchase data</span></span>

1. <span data-ttu-id="31422-126">Adicione outro conjunto de dados à mesma fonte de dados do **comércio eletrônico**.</span><span class="sxs-lookup"><span data-stu-id="31422-126">Add another data set to the same **eCommerce** data source.</span></span> <span data-ttu-id="31422-127">Escolha o conector de **Texto/CSV** novamente.</span><span class="sxs-lookup"><span data-stu-id="31422-127">Choose the **Text/CSV** connector again.</span></span>

1. <span data-ttu-id="31422-128">Insira o URL para dados de **Compras online** https://aka.ms/ciadclassonline.</span><span class="sxs-lookup"><span data-stu-id="31422-128">Enter the URL for **Online Purchases** data https://aka.ms/ciadclassonline.</span></span>

1. <span data-ttu-id="31422-129">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="31422-129">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="31422-130">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="31422-130">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="31422-131">**PurchasedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="31422-131">**PurchasedOn**: Date/Time</span></span>
   - <span data-ttu-id="31422-132">**TotalPrice**: Moeda</span><span class="sxs-lookup"><span data-stu-id="31422-132">**TotalPrice**: Currency</span></span>

1. <span data-ttu-id="31422-133">No campo **Nome** no painel lateral, renomeie sua fonte de dados de **Consulta** para **eCommercePurchases**.</span><span class="sxs-lookup"><span data-stu-id="31422-133">In the **Name** field on the side pane, rename your data source from **Query** to **eCommercePurchases**.</span></span>

1. <span data-ttu-id="31422-134">Salvar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="31422-134">Save the data source.</span></span>


### <a name="ingest-customer-data-from-loyalty-schema"></a><span data-ttu-id="31422-135">Ingerir dados do cliente do esquema de fidelidade</span><span class="sxs-lookup"><span data-stu-id="31422-135">Ingest customer data from loyalty schema</span></span>

1. <span data-ttu-id="31422-136">Crie uma fonte de dados chamada **LoyaltyScheme**, escolha a opção de importação e selecione o conector **Texto/CSV**.</span><span class="sxs-lookup"><span data-stu-id="31422-136">Create a data source named **LoyaltyScheme**, choose the import option, and select the **Text/CSV** connector.</span></span>

1. <span data-ttu-id="31422-137">Insira o URL para contatos de comércio eletrônico https://aka.ms/ciadclasscustomerloyalty.</span><span class="sxs-lookup"><span data-stu-id="31422-137">Enter the URL for eCommerce contacts https://aka.ms/ciadclasscustomerloyalty.</span></span>

1. <span data-ttu-id="31422-138">Ao editar os dados, selecione **Transformar** e, em seguida, **Usar a primeira linha como cabeçalhos**.</span><span class="sxs-lookup"><span data-stu-id="31422-138">While editing the data, select **Transform** and then **Use First Row as Headers**.</span></span>

1. <span data-ttu-id="31422-139">Atualize o tipo de dados para as colunas listadas abaixo:</span><span class="sxs-lookup"><span data-stu-id="31422-139">Update the datatype for the columns listed below:</span></span>
   - <span data-ttu-id="31422-140">**DateOfBirth**: Data</span><span class="sxs-lookup"><span data-stu-id="31422-140">**DateOfBirth**: Date</span></span>
   - <span data-ttu-id="31422-141">**RewardsPoints**: Número inteiro</span><span class="sxs-lookup"><span data-stu-id="31422-141">**RewardsPoints**: Whole Number</span></span>
   - <span data-ttu-id="31422-142">**CreatedOn**: Data/Hora</span><span class="sxs-lookup"><span data-stu-id="31422-142">**CreatedOn**: Date/Time</span></span>

1. <span data-ttu-id="31422-143">No campo **Nome** no painel direito, renomeie sua fonte de dados de **Consulta** para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="31422-143">In the **Name** field on the right-hand pane, rename your data source from **Query** to **loyCustomers**.</span></span>

1. <span data-ttu-id="31422-144">Salvar a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="31422-144">Save the data source.</span></span>

## <a name="task-2---data-unification"></a><span data-ttu-id="31422-145">Tarefa 2 - Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="31422-145">Task 2 - Data unification</span></span>

<span data-ttu-id="31422-146">Depois de ingerir os dados, agora iniciamos o processo de **Mapear, Corresponder, Mesclar** para criar um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="31422-146">After ingesting the data we now begin the **Map, Match, Merge** process to create a unified customer profile.</span></span> <span data-ttu-id="31422-147">Para obter mais informações, consulte [Unificação de dados](data-unification.md).</span><span class="sxs-lookup"><span data-stu-id="31422-147">For more information, see [Data unification](data-unification.md).</span></span>

### <a name="map"></a><span data-ttu-id="31422-148">Mapa </span><span class="sxs-lookup"><span data-stu-id="31422-148">Map</span></span>

1. <span data-ttu-id="31422-149">Depois de ingerir os dados, mapeie os contatos dos dados de comércio eletrônico e de fidelidade para tipos de dados comuns.</span><span class="sxs-lookup"><span data-stu-id="31422-149">After ingesting the data, map contacts from eCommerce and Loyalty data to common data types.</span></span> <span data-ttu-id="31422-150">Vá para **Dados** > **Unificar** > **Mapear**.</span><span class="sxs-lookup"><span data-stu-id="31422-150">Go to **Data** > **Unify** > **Map**.</span></span>

2. <span data-ttu-id="31422-151">Selecione as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="31422-151">Select the entities that represent the customer profile – **eCommerceContacts** and **loyCustomers**.</span></span>

   ![unifique as fontes de dados de comércio eletrônico e fidelidade.](media/unify-ecommerce-loyalty.png)

3. <span data-ttu-id="31422-153">Selecione **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.</span><span class="sxs-lookup"><span data-stu-id="31422-153">Select **ContactId** as the primary key for **eCommerceContacts** and **LoyaltyID** as the primary key for **loyCustomers**.</span></span>

   ![Unifique LoyaltyId como chave primária.](media/unify-loyaltyid.png)

### <a name="match"></a><span data-ttu-id="31422-155">Corresponder</span><span class="sxs-lookup"><span data-stu-id="31422-155">Match</span></span>

1. <span data-ttu-id="31422-156">Vá para a guia **Corresponder** e selecione **Definir pedido**.</span><span class="sxs-lookup"><span data-stu-id="31422-156">Go to the **Match** tab and select **Set Order**.</span></span>

2. <span data-ttu-id="31422-157">Na lista suspensa **Primário**, escolha **eCommerceContacts : eCommerce** como fonte primária e inclua todos os registros.</span><span class="sxs-lookup"><span data-stu-id="31422-157">In the **Primary** drop-down list, choose **eCommerceContacts : eCommerce** as the primary source and include all records.</span></span>

3. <span data-ttu-id="31422-158">Na lista suspensa **Entidade 2**, escolha **loyCustomers : LoyaltyScheme** e inclua todos os registros.</span><span class="sxs-lookup"><span data-stu-id="31422-158">In the **Entity 2** drop-down list, choose **loyCustomers : LoyaltyScheme** and include all records.</span></span>

   ![Unificar correspondência de comércio eletrônico e fidelidade.](media/unify-match-order.png)

4. <span data-ttu-id="31422-160">Selecione **Criar uma nova regra**</span><span class="sxs-lookup"><span data-stu-id="31422-160">Select **Create a new rule**</span></span>

5. <span data-ttu-id="31422-161">Adicione sua primeira condição usando FullName.</span><span class="sxs-lookup"><span data-stu-id="31422-161">Add your first condition using FullName.</span></span>

   - <span data-ttu-id="31422-162">Para eCommerceContacts selecione **FullName** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="31422-162">For eCommerceContacts select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="31422-163">Para loyCustomers selecione **FullName** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="31422-163">For loyCustomers select **FullName** in the drop-down.</span></span>
   - <span data-ttu-id="31422-164">Selecione o menu suspenso **Normalizar** e escolha **Inserir (telefone, nome, endereço,...)**.</span><span class="sxs-lookup"><span data-stu-id="31422-164">Select the **Normalize** drop down and choose **Type (Phone, Name, Address, ...)**.</span></span>
   - <span data-ttu-id="31422-165">Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="31422-165">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

6. <span data-ttu-id="31422-166">Digite o nome **FullName, Email** para a nova regra.</span><span class="sxs-lookup"><span data-stu-id="31422-166">Enter the name **FullName, Email** for the new rule.</span></span>

   - <span data-ttu-id="31422-167">Adicione uma segunda condição para o endereço de e-mail selecionando **Adicionar condição**</span><span class="sxs-lookup"><span data-stu-id="31422-167">Add a second condition for email address by selecting **Add Condition**</span></span>
   - <span data-ttu-id="31422-168">Para a entidade eCommerceContacts, escolha **Email** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="31422-168">For entity eCommerceContacts, choose **EMail** in drop-down.</span></span>
   - <span data-ttu-id="31422-169">Para a entidade loyCustomers, escolha **Email** no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="31422-169">For entity loyCustomers, choose **EMail** in the drop-down.</span></span>
   - <span data-ttu-id="31422-170">Deixe o campo Normalizar em branco.</span><span class="sxs-lookup"><span data-stu-id="31422-170">Leave Normalize blank.</span></span>
   - <span data-ttu-id="31422-171">Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.</span><span class="sxs-lookup"><span data-stu-id="31422-171">Set **Precision Level**: **Basic** and **Value**: **High**.</span></span>

   ![Regra de correspondência unificada para nome e email.](media/unify-match-rule.png)

7. <span data-ttu-id="31422-173">Selecione **Salvar** e **Executar**.</span><span class="sxs-lookup"><span data-stu-id="31422-173">Select **Save** and **Run**.</span></span>

### <a name="merge"></a><span data-ttu-id="31422-174">Merge</span><span class="sxs-lookup"><span data-stu-id="31422-174">Merge</span></span>

1. <span data-ttu-id="31422-175">Vá para a guia **Mesclar**.</span><span class="sxs-lookup"><span data-stu-id="31422-175">Go to the **Merge** tab.</span></span>

1. <span data-ttu-id="31422-176">Na entidade **ContactId** para **loyCustomers**, altere o nome de exibição para **ContactIdLOYALTY** para diferenciá-lo dos outros IDs ingeridos.</span><span class="sxs-lookup"><span data-stu-id="31422-176">On the **ContactId** for **loyCustomers** entity, change the display name to **ContactIdLOYALTY** to differentiate it from the other IDs ingested.</span></span>

   ![renomear contactid de loyalty id.](media/unify-merge-contactid.png)

1. <span data-ttu-id="31422-178">Selecione **Salvar** e **Executar** para iniciar o processo de mesclagem.</span><span class="sxs-lookup"><span data-stu-id="31422-178">Select **Save** and **Run** to start the Merge Process.</span></span>

## <a name="task-3---configure-product-recommendation-prediction"></a><span data-ttu-id="31422-179">Tarefa 3 - Configurar previsão de recomendação de produto</span><span class="sxs-lookup"><span data-stu-id="31422-179">Task 3 - Configure product recommendation prediction</span></span>

<span data-ttu-id="31422-180">Com os perfis de cliente unificados em vigor, agora podemos executar a previsão de rotatividade de assinatura.</span><span class="sxs-lookup"><span data-stu-id="31422-180">With the unified customer profiles in place, we can now run the subscription churn prediction.</span></span>

1. <span data-ttu-id="31422-181">Vá para **Inteligência** > **Previsão** escolha **Recomendação do produto**.</span><span class="sxs-lookup"><span data-stu-id="31422-181">Go to **Intelligence** > **Prediction** choose **Product recommendation**.</span></span>

1. <span data-ttu-id="31422-182">Selecione **Começar**.</span><span class="sxs-lookup"><span data-stu-id="31422-182">Select **Get started**.</span></span>

1. <span data-ttu-id="31422-183">Nomeie o modelo **Previsão do modelo de recomendação do produto OOB** e a entidade de saída **OOBProductRecommendationModelPrediction**.</span><span class="sxs-lookup"><span data-stu-id="31422-183">Name the model **OOB Product Recommendation Model Prediction** and the output entity **OOBProductRecommendationModelPrediction**.</span></span>

1. <span data-ttu-id="31422-184">Defina três condições para o modelo:</span><span class="sxs-lookup"><span data-stu-id="31422-184">Define three conditions for the model:</span></span>

   - <span data-ttu-id="31422-185">**Número de produtos**: Defina este valor como **5**.</span><span class="sxs-lookup"><span data-stu-id="31422-185">**Number of products**: Set this value to **5**.</span></span> <span data-ttu-id="31422-186">Esta configuração define quantos produtos você deseja recomendar aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="31422-186">This setting defines how many products you want to recommend to your customers.</span></span>

   - <span data-ttu-id="31422-187">**Sugerir produtos que os clientes compraram recentemente?**: Selecione **Sim** para indicar que deseja incluir produtos na recomendação que seus clientes compraram antes.</span><span class="sxs-lookup"><span data-stu-id="31422-187">**Suggest products customers have recently purchased?**: Select **Yes** to indicate that you want to include products in the recommendation that your customers have purchased before.</span></span>

   - <span data-ttu-id="31422-188">**Janela do passado:** Selecione pelo menos **365 dias**.</span><span class="sxs-lookup"><span data-stu-id="31422-188">**Look back window:** Select at least **365 days**.</span></span> <span data-ttu-id="31422-189">Essa configuração define até que ponto o modelo retrocederá na atividade do cliente para usá-la como entrada para suas recomendações.</span><span class="sxs-lookup"><span data-stu-id="31422-189">This setting defines how far the model will look back at the customer's activity to use it as input to their recommendations.</span></span>
   
   :::image type="content" source="media/product-recommendation-model-preferences.png" alt-text="Preferências do modelo para o modelo de recomendação do produto.":::

1. <span data-ttu-id="31422-191">Selecione **Dados obrigatórios** e **Adicionar dados** para histórico de compras.</span><span class="sxs-lookup"><span data-stu-id="31422-191">Select **Required data** and select **Add data** for purchase history.</span></span>

1. <span data-ttu-id="31422-192">Adicione a entidade **eCommercePurchases : eCommerce** e mapeie os campos do eCommerce para os campos correspondentes exigidos pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="31422-192">Add the **eCommercePurchases : eCommerce** entity and map the fields from eCommerce to the corresponding fields required by the model.</span></span>

1. <span data-ttu-id="31422-193">Junte-se à entidade **eCommercePurchases : eCommerce** com **eCommerceContacts : eCommerce**.</span><span class="sxs-lookup"><span data-stu-id="31422-193">Join the **eCommercePurchases : eCommerce** entity with **eCommerceContacts : eCommerce**.</span></span>

   ![Junte-se a entidades de comércio eletrônico.](media/model-purchase-join.png)

1. <span data-ttu-id="31422-195">Selecione **Avançar** para definir o cronograma do modelo.</span><span class="sxs-lookup"><span data-stu-id="31422-195">Select **Next** to set the model schedule.</span></span>

   <span data-ttu-id="31422-196">O modelo precisa ser treinado regularmente para aprender novos padrões quando novos dados forem ingeridos.</span><span class="sxs-lookup"><span data-stu-id="31422-196">The model needs to train regularly to learn new patterns when there is new data ingested.</span></span> <span data-ttu-id="31422-197">Para este exemplo, selecione **Mensal**.</span><span class="sxs-lookup"><span data-stu-id="31422-197">For this example, select **Monthly**.</span></span>

1. <span data-ttu-id="31422-198">Depois de revisar todos os detalhes, selecione **Salvar e executar**.</span><span class="sxs-lookup"><span data-stu-id="31422-198">After reviewing all the details, select **Save and Run**.</span></span>


## <a name="task-4---review-model-results-and-explanations"></a><span data-ttu-id="31422-199">Tarefa 4 - Revise os resultados e explicações do modelo</span><span class="sxs-lookup"><span data-stu-id="31422-199">Task 4 - Review model results and explanations</span></span>

<span data-ttu-id="31422-200">Deixe o modelo concluir o treinamento e a pontuação dos dados.</span><span class="sxs-lookup"><span data-stu-id="31422-200">Let the model complete the training and scoring of the data.</span></span> <span data-ttu-id="31422-201">Agora, você pode revisar as explicações do modelo de recomendação do produto.</span><span class="sxs-lookup"><span data-stu-id="31422-201">You can now review the product recommendation model explanations.</span></span> <span data-ttu-id="31422-202">Para mais informações, consulte [Analisar um status de previsão e resultados](predict-subscription-churn.md#review-a-prediction-status-and-results).</span><span class="sxs-lookup"><span data-stu-id="31422-202">For more information, see [Review a prediction status and results](predict-subscription-churn.md#review-a-prediction-status-and-results).</span></span>

## <a name="task-5---create-a-segment-of-high-purchased-products"></a><span data-ttu-id="31422-203">Tarefa 5 - Crie um segmento de produtos altamente comprados</span><span class="sxs-lookup"><span data-stu-id="31422-203">Task 5 - Create a segment of high purchased products</span></span>

<span data-ttu-id="31422-204">Executar o modelo de produção cria uma nova entidade que você pode ver em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="31422-204">Running the production model creates a new entity that you can see in **Data** > **Entities**.</span></span>

<span data-ttu-id="31422-205">Você pode criar um novo segmento com base na entidade criada pelo modelo.</span><span class="sxs-lookup"><span data-stu-id="31422-205">You can create a new segment based on the entity created by the model.</span></span>

1. <span data-ttu-id="31422-206">Vá para **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="31422-206">Go to **Segments**.</span></span> <span data-ttu-id="31422-207">Selecione **Novo** e escolha **Criar de** > **Inteligência**.</span><span class="sxs-lookup"><span data-stu-id="31422-207">Select **New** and choose **Create from** > **Intelligence**.</span></span>

   ![Criando um segmento com a saída do modelo.](media/segment-intelligence.png)

1. <span data-ttu-id="31422-209">Selecione o ponto de extremidade **OOBSubscriptionChurnPrediction** e defina o segmento:</span><span class="sxs-lookup"><span data-stu-id="31422-209">Select the **OOBProductRecommendationModelPrediction** endpoint and define the segment:</span></span>

   - <span data-ttu-id="31422-210">Campo: ProductID</span><span class="sxs-lookup"><span data-stu-id="31422-210">Field: ProductID</span></span>
   - <span data-ttu-id="31422-211">Operador: Valor</span><span class="sxs-lookup"><span data-stu-id="31422-211">Operator: Value</span></span>
   - <span data-ttu-id="31422-212">Valor: selecione os três principais IDs de produto</span><span class="sxs-lookup"><span data-stu-id="31422-212">Value: Select the top three product IDs</span></span>

   :::image type="content" source="media/product-recommendation-quick-segment.png" alt-text="Criar um segmento a partir dos resultados do modelo.":::

<span data-ttu-id="31422-214">Agora você tem um segmento que é atualizado dinamicamente que identifica os clientes que estão mais dispostos a comprar os três produtos mais recomendados</span><span class="sxs-lookup"><span data-stu-id="31422-214">You now have a segment that is dynamically updated which identifies the customers who are more willing to purchase the three most recommended products</span></span> 

<span data-ttu-id="31422-215">Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).</span><span class="sxs-lookup"><span data-stu-id="31422-215">For more information, see [Create and manage segments](segments.md).</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]