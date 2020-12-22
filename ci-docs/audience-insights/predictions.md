---
title: Preencher dados parciais usando previsões
description: Use previsões para preencher dados incompletos dos clientes.
ms.date: 05/05/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: zacook
manager: shellyha
ms.openlocfilehash: 66f0b16b5d05741ab98ca5ce2157da8c46b6d9e0
ms.sourcegitcommit: 5379c2b77d613d071a177f509e6417ebf3c47516
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/26/2020
ms.locfileid: "4648697"
---
# <a name="complete-your-partial-data-with-predictions"></a><span data-ttu-id="18794-103">Concluir seus dados parciais com previsões</span><span class="sxs-lookup"><span data-stu-id="18794-103">Complete your partial data with predictions</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="18794-104">As previsões permitem criar facilmente valores previstos que podem melhorar sua compreensão de um cliente.</span><span class="sxs-lookup"><span data-stu-id="18794-104">Predictions lets you easily create predicted values that can enhance your understanding of a customer.</span></span> <span data-ttu-id="18794-105">Na página **Inteligência** > **Previsões** , é possível selecionar **Minhas previsões** para ver as previsões que você configurou em outras partes dos insights de público-alvo e personalizá-las ainda mais.</span><span class="sxs-lookup"><span data-stu-id="18794-105">On the **Intelligence** > **Predictions** page, you can select **My predictions** to see predictions that you've configured in other parts of audience insights, and allow you to further customize them.</span></span>

> [!NOTE]
> <span data-ttu-id="18794-106">Você não poderá usar esse recurso se o seu ambiente usar o armazenamento do Azure Data Lake Gen 2.</span><span class="sxs-lookup"><span data-stu-id="18794-106">You can't use this feature if your environment uses Azure Data Lake Gen 2 storage.</span></span>
>
> <span data-ttu-id="18794-107">O recurso de previsões usa meios automatizados para avaliar dados e fazer previsões com base nesses dados e, portanto, tem a capacidade de ser usado como um método de criação de perfil, pois esse termo é definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD").</span><span class="sxs-lookup"><span data-stu-id="18794-107">The predictions feature uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation ("GDPR").</span></span> <span data-ttu-id="18794-108">O uso desse recurso pelo cliente para processar dados pode estar sujeito ao RGPD ou a outras leis ou regulamentos.</span><span class="sxs-lookup"><span data-stu-id="18794-108">Customer's use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="18794-109">Você é responsável por garantir que o uso do Dynamics 365 Customer Insights, incluindo as previsões, esteja em conformidade com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.</span><span class="sxs-lookup"><span data-stu-id="18794-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18794-110">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="18794-110">Prerequisites</span></span>

<span data-ttu-id="18794-111">Antes de sua organização poder usar o recurso de previsões, verifique se os seguintes pré-requisitos foram atendidos:</span><span class="sxs-lookup"><span data-stu-id="18794-111">Before your organization can use the predictions feature, the following prerequisites must be met:</span></span>

1. <span data-ttu-id="18794-112">Sua organização tem uma instância [configurada no Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) e está na mesma organização que o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="18794-112">Your organization has an instance [set up in the Common Data Service](https://docs.microsoft.com/ai-builder/build-model#prerequisites) and it's in the same organization as Customer Insights.</span></span>

2. <span data-ttu-id="18794-113">Seu ambiente está anexado à sua instância do Common Data Service.</span><span class="sxs-lookup"><span data-stu-id="18794-113">Your environment is attached to your Common Data Service instance.</span></span>

<span data-ttu-id="18794-114">Se você estiver [criando o primeiro ambiente](manage-environments.md), configure-o no diálogo **Criar um ambiente** e selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="18794-114">If you're [creating a new environment](manage-environments.md), configure it in the **Create an environment** dialog and select **Advanced**.</span></span> <span data-ttu-id="18794-115">Se você já criou um ambiente, vá para as configurações e selecione **Avançado**.</span><span class="sxs-lookup"><span data-stu-id="18794-115">If you've already created an environment, go to its settings and select **Advanced**.</span></span> <span data-ttu-id="18794-116">De qualquer forma, na seção **Usar previsões**, insira a URL da instância do Common Data Service à qual você deseja anexar seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="18794-116">Either way, in the **Use predictions** section, enter the Common Data Service instance URL to which you want to attach your environment.</span></span>

## <a name="create-a-prediction-in-the-customer-entity"></a><span data-ttu-id="18794-117">Criar uma previsão na entidade Cliente</span><span class="sxs-lookup"><span data-stu-id="18794-117">Create a prediction in the Customer entity</span></span>

1. <span data-ttu-id="18794-118">Nos insights de público-alvo, vá para **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="18794-118">In audience insights, go to **Data** > **Entities**.</span></span>

2. <span data-ttu-id="18794-119">Selecione a entidade **Cliente**.</span><span class="sxs-lookup"><span data-stu-id="18794-119">Select the **Customer** entity.</span></span>

3. <span data-ttu-id="18794-120">Na entidade **Cliente: CustomerInsights**, selecione a guia **Campos**.</span><span class="sxs-lookup"><span data-stu-id="18794-120">In the **Customer:CustomerInsights** entity, select on the **Fields** tab.</span></span>

4. <span data-ttu-id="18794-121">Localize o nome do atributo para o qual deseja prever valores e selecione o ícone **Visão geral** na coluna **Resumo**.</span><span class="sxs-lookup"><span data-stu-id="18794-121">Find the attribute name you wish to predict values for, then select the **Overview** icon in the **Summary** column.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18794-122">![Ícone de Visão geral](media/intelligence-overviewicon.png "Ícone de Visão geral")</span><span class="sxs-lookup"><span data-stu-id="18794-122">![Overview icon](media/intelligence-overviewicon.png "Overview icon")</span></span>

5. <span data-ttu-id="18794-123">Se houver uma alta taxa de valores ausentes para o seu atributo, selecione **Prever valores ausentes** para prosseguir com sua previsão.</span><span class="sxs-lookup"><span data-stu-id="18794-123">If there's a high rate of missing values for your attribute, select **Predict missing values** to continue with your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18794-124">![Status da visão geral com o botão prever valores ausentes mostrado](media/intelligence-overviewpredictmissingvalues.png "Status da visão geral com o botão prever valores ausentes mostrado")</span><span class="sxs-lookup"><span data-stu-id="18794-124">![Overview status with predict missing values button shown](media/intelligence-overviewpredictmissingvalues.png "Overview status with predict missing values button shown")</span></span>

6. <span data-ttu-id="18794-125">Forneça um **Nome de exibição** e um **Nome da entidade de saída** para os resultados da previsão.</span><span class="sxs-lookup"><span data-stu-id="18794-125">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="18794-126">Uma lista de opções preenchida previamente mostrará onde você pode mapear os valores para uma categoria prevista.</span><span class="sxs-lookup"><span data-stu-id="18794-126">A pre-populated list of options will show where you can map the values to a predicted category.</span></span> <span data-ttu-id="18794-127">Nesse caso, suas únicas opções de categoria serão 0 ou 1, pois mapeiam para verdadeiro/falso ou a natureza binária da previsão.</span><span class="sxs-lookup"><span data-stu-id="18794-127">In this case, your only category options will be 0 or 1, as they map to the true/false or binary nature of the prediction.</span></span> <span data-ttu-id="18794-128">Na coluna Categoria, mapeie os valores do campo que você deseja classificar como "0" na previsão final para "0" e os itens que você deseja classificar como "1" na previsão final para o "1".</span><span class="sxs-lookup"><span data-stu-id="18794-128">In the Category column, map the field values you'd like to be classified as "0" in the final prediction to "0", and the items you'd like to be classified as "1" in the final prediction to "1".</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18794-129">![Exemplo mostrando valores de campo mapeado para categorias](media/intelligence-categorymapping.png "Exemplo mostrando valores de campo mapeado para categorias")</span><span class="sxs-lookup"><span data-stu-id="18794-129">![Example showing mapped field values to categories](media/intelligence-categorymapping.png "Example showing mapped field values to categories")</span></span>

8. <span data-ttu-id="18794-130">Selecione **Concluído** e a previsão será processada.</span><span class="sxs-lookup"><span data-stu-id="18794-130">Select **Done** and the prediction will be processed.</span></span> <span data-ttu-id="18794-131">O processamento levará algum tempo, dependendo do tamanho e da complexidade dos dados.</span><span class="sxs-lookup"><span data-stu-id="18794-131">The processing will take some time, depending on the size and complexity of data.</span></span> <span data-ttu-id="18794-132">Os resultados estarão disponíveis em uma nova entidade com base no **Nome da entidade de saída** da previsão que você criou.</span><span class="sxs-lookup"><span data-stu-id="18794-132">Results will be available in a new entity based on the **Output entity name** of the prediction you created.</span></span>

## <a name="create-a-prediction-while-creating-a-segment"></a><span data-ttu-id="18794-133">Criar uma previsão ao criar um segmento</span><span class="sxs-lookup"><span data-stu-id="18794-133">Create a prediction while creating a segment</span></span>

<span data-ttu-id="18794-134">Também é possível prever valores ausentes para um atributo específico à sua escolha ao criar um segmento.</span><span class="sxs-lookup"><span data-stu-id="18794-134">Predicting missing values for a specific attribute of choice is also possible when creating a segment.</span></span> <span data-ttu-id="18794-135">Especificamente, quando você cria rapidamente um segmento com base na sua entidade Cliente ou na entidade Medida_do_Cliente unificadas.</span><span class="sxs-lookup"><span data-stu-id="18794-135">Specifically, when you quickly create a segment based on either your unified Customer entity or Customer_Measure entity.</span></span>

<span data-ttu-id="18794-136">Como parte desse fluxo, você escolherá um atributo específico para basear seu segmento, como Satisfação do Cliente ou Valor da Compra.</span><span class="sxs-lookup"><span data-stu-id="18794-136">As part of this flow, you'll choose a specific attribute to base your segment on, such as Customer Satisfaction or Purchase Amount.</span></span> <span data-ttu-id="18794-137">Na criação do segmento, o sistema sugere um método para prever quaisquer valores ausentes para esse atributo.</span><span class="sxs-lookup"><span data-stu-id="18794-137">Upon segment creation, the system will suggest a method for predicting any missing values for this attribute.</span></span>

1. <span data-ttu-id="18794-138">Nos insights de público-alvo, vá para **Segmentos** e selecione o bloco **Perfis**.</span><span class="sxs-lookup"><span data-stu-id="18794-138">In audience insights, go to **Segments** and select the **Profiles** tile.</span></span>

2. <span data-ttu-id="18794-139">Escolha um **Campo** para criar um segmento e selecione um **Operador** e selecione **Revisar**.</span><span class="sxs-lookup"><span data-stu-id="18794-139">Choose a **Field** to create a segment on and select an **Operator**, then select **Review**.</span></span>

3. <span data-ttu-id="18794-140">Forneça um **Nome** e um **Nome de exibição** para o segmento.</span><span class="sxs-lookup"><span data-stu-id="18794-140">Provide a **Name** and a **Display name** for the segment.</span></span>

4. <span data-ttu-id="18794-141">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="18794-141">Select **Save**.</span></span>

5. <span data-ttu-id="18794-142">Se o segmento que criou tiver dados incompletos no campo de origem, você poderá optar por prever os valores ausentes.</span><span class="sxs-lookup"><span data-stu-id="18794-142">If the segment you created has incomplete data in the source field, you can choose to predict the missing values.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18794-143">![Botão Previsão](media/segments-predictoption.png "Botão Previsão")</span><span class="sxs-lookup"><span data-stu-id="18794-143">![Prediction button](media/segments-predictoption.png "Prediction button")</span></span>

6. <span data-ttu-id="18794-144">Forneça um **Nome de exibição** e um **Nome da entidade de saída** para os resultados da previsão.</span><span class="sxs-lookup"><span data-stu-id="18794-144">Provide a **Display name** and an **Output entity name** for the results of the prediction.</span></span>

7. <span data-ttu-id="18794-145">Escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="18794-145">Select **Done**.</span></span> <span data-ttu-id="18794-146">Sua previsão será gerada pouco tempo depois em uma nova entidade com o nome que você forneceu para o **Nome da entidade de saída**.</span><span class="sxs-lookup"><span data-stu-id="18794-146">Your prediction will be generated shortly in a new entity with the name you provided for the **Output entity name**.</span></span>

## <a name="view-a-prediction"></a><span data-ttu-id="18794-147">Exibir uma previsão</span><span class="sxs-lookup"><span data-stu-id="18794-147">View a prediction</span></span>

1. <span data-ttu-id="18794-148">Nos insights de público-alvo, vá para **Inteligência** > **Previsões** > **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="18794-148">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="18794-149">Selecione a previsão que você deseja revisar.</span><span class="sxs-lookup"><span data-stu-id="18794-149">Select the prediction you want to review.</span></span>

3. <span data-ttu-id="18794-150">Selecione as reticências na coluna **Ações** e escolha **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="18794-150">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="18794-151">Você verá alguns pontos de dados na exibição de sua previsão.</span><span class="sxs-lookup"><span data-stu-id="18794-151">You'll see a number of data points in the view of your prediction.</span></span>
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="18794-152">![Página Previsões](media/intelligence-predictionsviewpage.png "Página Previsões")</span><span class="sxs-lookup"><span data-stu-id="18794-152">![Predictions page](media/intelligence-predictionsviewpage.png "Predictions page")</span></span>

   - <span data-ttu-id="18794-153">**Valores previstos** mostra o mapeamento criado durante o Valor de campo para a fase Mapeamento de categoria.</span><span class="sxs-lookup"><span data-stu-id="18794-153">**Predicted values** shows the mapping you created during the Field value to Category mapping phase.</span></span> <span data-ttu-id="18794-154">Esses são os valores em seu conjunto de dados que foram mapeados para uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="18794-154">These are the values in your dataset that have been mapped to a specific category.</span></span>
   <span data-ttu-id="18794-155">-**Principais influenciadores** são os fatores em seu conjunto de dados que mais provavelmente influenciarão a confiança da previsão do Valor de campo que está sendo mapeado para uma categoria específica.</span><span class="sxs-lookup"><span data-stu-id="18794-155">-**Top influencers** are the factors within your dataset that were most likely to influence the prediction's confidence of your Field value being mapped to a specific category.</span></span>
   - <span data-ttu-id="18794-156">**Desempenho** indica como estão as previsões.</span><span class="sxs-lookup"><span data-stu-id="18794-156">**Performance** indicates how the predictions are doing.</span></span> <span data-ttu-id="18794-157">Selecione o link para saber mais.</span><span class="sxs-lookup"><span data-stu-id="18794-157">Select the link to learn more.</span></span>
   - <span data-ttu-id="18794-158">**Visualização** exibe amostras do conjunto de dados de saída de sua previsão e a probabilidade, ou nossa confiança, do valor previsto em que 0 é incerto e 1 é certo.</span><span class="sxs-lookup"><span data-stu-id="18794-158">**Preview** shows samples of the output dataset from your prediction and the likelihood, or our confidence, of the predicted value where 0 is uncertain, and 1 is certain.</span></span>

## <a name="update-a-prediction"></a><span data-ttu-id="18794-159">Atualizar uma previsão</span><span class="sxs-lookup"><span data-stu-id="18794-159">Update a prediction</span></span>

1. <span data-ttu-id="18794-160">Nos insights de público-alvo, vá para **Inteligência** > **Previsões** > **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="18794-160">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="18794-161">Selecione a previsão que você quer atualizar e selecione o ícone **Atualização**.</span><span class="sxs-lookup"><span data-stu-id="18794-161">Select the prediction you want to update and select the **Update** icon.</span></span>

3. <span data-ttu-id="18794-162">A previsão será agendada para processamento.</span><span class="sxs-lookup"><span data-stu-id="18794-162">The prediction will be scheduled for processing.</span></span> <span data-ttu-id="18794-163">Você pode ver a hora em que foi atualizada pela última vez na coluna **Atualizado** da página **Previsões**.</span><span class="sxs-lookup"><span data-stu-id="18794-163">You can see the time it was last updated in the **Updated** column of the **Predictions** page.</span></span>

## <a name="edit-a-prediction"></a><span data-ttu-id="18794-164">Editar uma previsão</span><span class="sxs-lookup"><span data-stu-id="18794-164">Edit a prediction</span></span>

<span data-ttu-id="18794-165">Depois de criar uma previsão, você poderá personalizar o modelo no AI Builder para aumentar a eficácia do seu modelo.</span><span class="sxs-lookup"><span data-stu-id="18794-165">After you've created a prediction, you can customize the model in the AI Builder to increase the effectiveness of your model.</span></span>  

1. <span data-ttu-id="18794-166">Nos insights de público-alvo, vá para **Inteligência** > **Previsões** > **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="18794-166">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="18794-167">Selecione a previsão que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="18794-167">Select the prediction you want to edit.</span></span>

3. <span data-ttu-id="18794-168">Selecione as reticências na coluna **Ações** e escolha **Exibir**.</span><span class="sxs-lookup"><span data-stu-id="18794-168">Select the ellipsis in the **Actions** column and choose **View**.</span></span>

4. <span data-ttu-id="18794-169">Selecione **Personalizar no AI Builder**.</span><span class="sxs-lookup"><span data-stu-id="18794-169">Select **Customize in AI Builder**.</span></span>

5. <span data-ttu-id="18794-170">Atualize seu modelo no AI Builder.</span><span class="sxs-lookup"><span data-stu-id="18794-170">Update your model in the AI Builder.</span></span> <span data-ttu-id="18794-171">[Saiba mais sobre o gerenciamento de modelos no AI Builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span><span class="sxs-lookup"><span data-stu-id="18794-171">[Learn more about managing models in the AI builder](https://docs.microsoft.com/ai-builder/manage-model#retrain-and-republish-existing-models).</span></span>

<span data-ttu-id="18794-172">A próxima execução da sua previsão usará o modelo atualizado que você criou.</span><span class="sxs-lookup"><span data-stu-id="18794-172">The next run of your prediction will use the updated model you've created.</span></span>

> [!NOTE]
> <span data-ttu-id="18794-173">Novos modelos criados no AI Builder não serão exibidos nos insights de público-alvo, a menos que o modelo tenha sido criado a partir das experiências listadas acima.</span><span class="sxs-lookup"><span data-stu-id="18794-173">New models created in AI Builder will not be displayed in audience insights unless the model was created from the experiences listed above.</span></span>

## <a name="remove-a-prediction"></a><span data-ttu-id="18794-174">Remover uma previsão</span><span class="sxs-lookup"><span data-stu-id="18794-174">Remove a prediction</span></span>

1. <span data-ttu-id="18794-175">Nos insights de público-alvo, vá para **Inteligência** > **Previsões** > **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="18794-175">In audience insights, go to **Intelligence** > **Predictions** > **My predictions**.</span></span>

2. <span data-ttu-id="18794-176">Selecione a previsão que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="18794-176">Select the prediction you want to delete.</span></span>

3. <span data-ttu-id="18794-177">Selecione as reticências na coluna **Ações** e escolha **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="18794-177">Select the ellipsis in the **Actions** column and choose **Delete**.</span></span>

4. <span data-ttu-id="18794-178">Confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="18794-178">Confirm the deletion.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="18794-179">Solução de Problemas</span><span class="sxs-lookup"><span data-stu-id="18794-179">Troubleshooting</span></span>

<span data-ttu-id="18794-180">Se você não conseguir concluir o processo anexo do Common Data Service por causa de um erro, tente concluí-lo manualmente.</span><span class="sxs-lookup"><span data-stu-id="18794-180">If you can't complete the attach Common Data Service process due to an error, you can try to complete the process manually.</span></span> <span data-ttu-id="18794-181">Há dois problemas conhecidos que podem ocorrer no processo de anexo:</span><span class="sxs-lookup"><span data-stu-id="18794-181">There are two known issues that can occur in the attach process:</span></span>

- <span data-ttu-id="18794-182">A solução Complemento do Cartão do Cliente não foi instalada.</span><span class="sxs-lookup"><span data-stu-id="18794-182">The Customer Card Add-in solution is not installed.</span></span>
    1. <span data-ttu-id="18794-183">Siga as instruções para [instalar e configurar a solução](customer-card-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="18794-183">Complete the instructions to [install and configure the solution](customer-card-add-in.md).</span></span>

- <span data-ttu-id="18794-184">As permissões de aplicativo não foram concedidas.</span><span class="sxs-lookup"><span data-stu-id="18794-184">App permissions aren't granted.</span></span>
    1. <span data-ttu-id="18794-185">Vá para [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="18794-185">Go to [https://admin.powerplatform.microsoft.com](https://admin.powerplatform.microsoft.com).</span></span>
    1. <span data-ttu-id="18794-186">Selecione **Ambientes**.</span><span class="sxs-lookup"><span data-stu-id="18794-186">Select **Environments**.</span></span>
    1. <span data-ttu-id="18794-187">Selecione as reticências ao lado do ambiente ao qual você deseja adicionar a permissão e selecione **Configurações**.</span><span class="sxs-lookup"><span data-stu-id="18794-187">Select the ellipsis next to the environment you want to add the permission to and select **Settings**.</span></span>
    1. <span data-ttu-id="18794-188">Expanda **Usuários e permissões** e selecione **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="18794-188">Expand **Users + permissions** and select **Users**.</span></span>
    1. <span data-ttu-id="18794-189">Selecione **+ Novo** e selecione **Usuário**.</span><span class="sxs-lookup"><span data-stu-id="18794-189">Select **+ New** and select **User**.</span></span>
    1. <span data-ttu-id="18794-190">Selecione **Usuário do Aplicativo** se ainda não estiver selecionado e insira as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="18794-190">Select **Application User** if it's not already selected and enter the following information:</span></span>
        - <span data-ttu-id="18794-191">**Nome de usuário:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18794-191">**User Name:** cihelp@microsoft.com</span></span>
        - <span data-ttu-id="18794-192">**ID do Aplicativo:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span><span class="sxs-lookup"><span data-stu-id="18794-192">**Application ID:** 38c77d00-5fcb-4cce-9d93-af4738258e3c</span></span>
        - <span data-ttu-id="18794-193">**Nome:** Cliente</span><span class="sxs-lookup"><span data-stu-id="18794-193">**First Name:** Customer</span></span>
        - <span data-ttu-id="18794-194">**Sobrenome:** Insights</span><span class="sxs-lookup"><span data-stu-id="18794-194">**Last Name:** Insights</span></span>
        - <span data-ttu-id="18794-195">**Email Principal:** cihelp@microsoft.com</span><span class="sxs-lookup"><span data-stu-id="18794-195">**Primary Email:** cihelp@microsoft.com</span></span>
    1. <span data-ttu-id="18794-196">Selecione **Salvar e fechar**.</span><span class="sxs-lookup"><span data-stu-id="18794-196">Select **Save & Close**.</span></span>
    1. <span data-ttu-id="18794-197">Selecione o usuário que você acabou de criar.</span><span class="sxs-lookup"><span data-stu-id="18794-197">Select the user you just created.</span></span>
    1. <span data-ttu-id="18794-198">Selecione **Gerenciar funções** na barra de menus superior.</span><span class="sxs-lookup"><span data-stu-id="18794-198">Select **Manage Roles** in the top menu bar.</span></span>
    1. <span data-ttu-id="18794-199">Selecione **Administrador do Sistema** e selecione **OK**.</span><span class="sxs-lookup"><span data-stu-id="18794-199">Select **System Administrator**, then select **OK**.</span></span>
