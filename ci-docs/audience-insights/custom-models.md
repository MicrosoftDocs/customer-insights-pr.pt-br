---
title: Modelos de aprendizado de máquina personalizados | Microsoft Docs
description: Trabalhar com modelos personalizados do Azure Machine Learning no Dynamics 365 Customer Insights.
ms.date: 11/19/2020
ms.reviewer: zacook
ms.service: dynamics-365-ai
ms.topic: article
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ef248086b30b870359970529a7bfb37792be62d5
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668889"
---
# <a name="custom-machine-learning-models"></a><span data-ttu-id="a4d4c-103">Modelos de aprendizado de máquina personalizados</span><span class="sxs-lookup"><span data-stu-id="a4d4c-103">Custom machine learning models</span></span>

<span data-ttu-id="a4d4c-104">**Inteligência** > **Modelos personalizados** permite que você gerencie fluxos de trabalho com base nos modelos do Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-104">**Intelligence** > **Custom models** lets you manage workflows based on Azure Machine Learning models.</span></span> <span data-ttu-id="a4d4c-105">Os fluxos de trabalho ajudam você a escolher os dados dos quais deseja gerar insights e mapear os resultados para os dados unificados do cliente.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-105">Workflows help you choose the data you want to generate insights from and map the results to your unified customer data.</span></span> <span data-ttu-id="a4d4c-106">Para obter mais informações sobre a criação de modelos do ML personalizados, consulte [Usar modelos baseados em Aprendizado de Máquina do Azure](azure-machine-learning-experiments.md).</span><span class="sxs-lookup"><span data-stu-id="a4d4c-106">For more information about building custom ML models, see [Use Azure Machine Learning-based models](azure-machine-learning-experiments.md).</span></span>

## <a name="responsible-ai"></a><span data-ttu-id="a4d4c-107">IA responsável</span><span class="sxs-lookup"><span data-stu-id="a4d4c-107">Responsible AI</span></span>

<span data-ttu-id="a4d4c-108">As previsões oferecem recursos para criar melhores experiências para o cliente, melhorar os recursos de negócios e fluxos de receita.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-108">Predictions offer capabilities to create better customer experiences, improve business capabilities, and revenue streams.</span></span> <span data-ttu-id="a4d4c-109">Recomendamos fortemente que você equilibre o valor de sua previsão com o impacto que ela tem e os desvios que podem ser introduzidos de maneira ética.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-109">We strongly recommend you balance the value of your prediction against the impact it has and biases that may be introduced in an ethical manner.</span></span> <span data-ttu-id="a4d4c-110">Saiba mais sobre como a Microsoft está [tratando a IA responsável](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span><span class="sxs-lookup"><span data-stu-id="a4d4c-110">Learn more about how Microsoft is [addressing Responsible AI](https://www.microsoft.com/ai/responsible-ai?activetab=pivot1%3aprimaryr6).</span></span> <span data-ttu-id="a4d4c-111">Você também pode conhecer [técnicas e processos de aprendizado de máquina responsável](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) específico para o Azure Machine Learning.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-111">You can also learn about [techniques and processes for responsible machine learning](https://docs.microsoft.com/azure/machine-learning/concept-responsible-ml) specific to Azure Machine Learning.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a4d4c-112">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="a4d4c-112">Prerequisites</span></span>

- <span data-ttu-id="a4d4c-113">Atualmente, esse recurso oferece suporte a serviços da Web publicados por meio de [Machine Learning Studio (clássico)](https://studio.azureml.net) e [Pipelines em lote do Azure Machine Learning](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span><span class="sxs-lookup"><span data-stu-id="a4d4c-113">Currently, this feature supports web services published through [Machine Learning Studio (classic)](https://studio.azureml.net) and [Azure Machine Learning batch pipelines](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines).</span></span>

- <span data-ttu-id="a4d4c-114">Você precisa de uma conta de armazenamento Gen2 do Azure Data Lake associada à sua instância do Azure Studio para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-114">You need an Azure Data Lake Gen2 storage account associated with your Azure Studio instance to use this feature.</span></span> <span data-ttu-id="a4d4c-115">Para obter mais informações, consulte [Criar uma conta de armazenamento do Azure Data Lake Storage Gen2](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span><span class="sxs-lookup"><span data-stu-id="a4d4c-115">For more information, see [Create an Azure Data Lake Storage Gen2 storage account](https://docs.microsoft.com/azure/storage/blobs/data-lake-storage-quickstart-create-account)</span></span>

## <a name="add-a-new-workflow"></a><span data-ttu-id="a4d4c-116">Adicionar um novo fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="a4d4c-116">Add a new workflow</span></span>

1. <span data-ttu-id="a4d4c-117">Vamos para **Inteligência** > **Modelos personalizados** e selecione **Novo Fluxo de Trabalho**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-117">Go to **Intelligence** > **Custom models** and select **New workflow**.</span></span>

1. <span data-ttu-id="a4d4c-118">Dê ao seu modelo personalizado um nome reconhecível no campo **Nome**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-118">Give your custom model a recognizable name in the **Name** field.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4d4c-119">![Captura de tela do painel Novo fluxo de trabalho](media/new-workflowv2.png "Captura de tela do painel Novo fluxo de trabalho")</span><span class="sxs-lookup"><span data-stu-id="a4d4c-119">![Screenshot of the New workflow pane](media/new-workflowv2.png "Screenshot of the New workflow pane")</span></span>

1. <span data-ttu-id="a4d4c-120">Selecione a organização que contém o serviço Web em **Locatário que contém seu serviço Web**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-120">Select the organization that contains the web service in **Tenant that contains your web service**.</span></span>

1. <span data-ttu-id="a4d4c-121">Se sua assinatura do Aprendizado de Máquina do Azure estiver em um locatário diferente do Customer Insights, selecione **Entrar** com suas credenciais para a organização selecionada.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-121">If your Azure Machine Learning subscription is in a different tenant than Customer Insights, select **Sign in** with your credentials for the selected organization.</span></span>

1. <span data-ttu-id="a4d4c-122">Selecione **Espaços de Trabalho** associado ao seu serviço da Web.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-122">Select the **Workspaces** associated with your web service.</span></span> <span data-ttu-id="a4d4c-123">Há duas seções listadas, uma para o Azure Machine Learning v1 (Machine Learning Studio [clássico]) e o Azure Machine Learning v2 (Azure Machine Learning).</span><span class="sxs-lookup"><span data-stu-id="a4d4c-123">There are two sections listed, one for Azure Machine Learning v1 (Machine Learning Studio (classic)) and Azure Machine Learning v2 (Azure Machine Learning).</span></span> <span data-ttu-id="a4d4c-124">Se você não tiver certeza de qual espaço de trabalho é o correto para seu serviço da Web do Machine Learning Studio (clássico), selecione **Qualquer um**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-124">If you're not sure which workspace is the right one for your Machine Learning Studio (classic) web service, select **Any**.</span></span>

1. <span data-ttu-id="a4d4c-125">Escolha o serviço Web do Machine Learning Studio (clássico) ou o pipeline do Azure Machine Learning na lista suspensa **Serviço Web que contém seu modelo**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-125">Choose the Machine Learning Studio (classic) web service or Azure Machine Learning pipeline in the **Web service that contains your model** dropdown.</span></span> <span data-ttu-id="a4d4c-126">Em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-126">Then, select **Next**.</span></span>
   - <span data-ttu-id="a4d4c-127">Saiba mais sobre como [publicar um serviço Web no Machine Learning Studio (clássico)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span><span class="sxs-lookup"><span data-stu-id="a4d4c-127">Learn more about [publishing a web service in Machine Learning Studio (classic)](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service#deploy-it-as-a-new-web-service)</span></span>
   - <span data-ttu-id="a4d4c-128">Saiba mais sobre como [publicar um pipeline no Azure Machine Learning usando o designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) ou [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span><span class="sxs-lookup"><span data-stu-id="a4d4c-128">Learn more about [publishing a pipeline in Azure Machine Learning using the designer](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-designer) or [SDK](https://docs.microsoft.com/azure/machine-learning/concept-ml-pipelines#building-pipelines-with-the-python-sdk).</span></span> 
     > [!NOTE]
     > <span data-ttu-id="a4d4c-129">Seu pipeline deve ser publicado em um [ponto de extremidade do pipeline](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span><span class="sxs-lookup"><span data-stu-id="a4d4c-129">Your pipeline must be published under a [pipeline endpoint](https://docs.microsoft.com/azure/machine-learning/how-to-run-batch-predictions-designer#submit-a-pipeline-run).</span></span>

1. <span data-ttu-id="a4d4c-130">Para cada **Entrada do serviço Web**, selecione **Entidade** correspondente nos insights de público-alvo e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-130">For each **Web service input**, select the matching **Entity** from audience insights and select **Next**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4d4c-131">![Configurar um fluxo de trabalho](media/intelligence-screen2-updated.png "Configurar um fluxo de trabalho")</span><span class="sxs-lookup"><span data-stu-id="a4d4c-131">![Configure a workflow](media/intelligence-screen2-updated.png "Configure a workflow")</span></span>

1. <span data-ttu-id="a4d4c-132">Na etapa **Parâmetros de saída do modelo**, defina as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="a4d4c-132">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="a4d4c-133">Machine Learning Studio (clássico)</span><span class="sxs-lookup"><span data-stu-id="a4d4c-133">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="a4d4c-134">Insira a saída **Nome da entidade** para a qual deseja que os resultados de saída do serviço Web fluam.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-134">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="a4d4c-135">Aprendizado de Máquina do Azure</span><span class="sxs-lookup"><span data-stu-id="a4d4c-135">Azure Machine Learning</span></span>
      1. <span data-ttu-id="a4d4c-136">Insira a saída **Nome da entidade** para a qual deseja que os resultados de saída do pipeline fluam.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-136">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="a4d4c-137">Selecione **Nome do parâmetro de armazenamento de dados de saída** do pipeline em lote no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-137">Select the **Output data store parameter name** of your batch pipeline from the dropdown.</span></span>
      1. <span data-ttu-id="a4d4c-138">Selecione **Nome do parâmetro do Caminho de Saída** do pipeline em lote no menu suspenso.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-138">Select the **Output Path parameter name** of your batch pipeline from the dropdown.</span></span>
      
      > [!div class="mx-imgBorder"]
      > <span data-ttu-id="a4d4c-139">![Painel de parâmetros de saída do modelo](media/intelligence-screen3-outputparameters.png "Painel de parâmetros de saída do modelo")</span><span class="sxs-lookup"><span data-stu-id="a4d4c-139">![Model Output Parameter Pane](media/intelligence-screen3-outputparameters.png "Model Output Parameter Pane")</span></span>

1. <span data-ttu-id="a4d4c-140">Selecione o atributo correspondente na lista suspensa **ID do cliente nos resultados** que identifica os clientes e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-140">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   
   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="a4d4c-141">![Relacionar os resultados ao painel de dados do cliente](media/intelligence-screen4-relatetocustomer.png "Relacionar os resultados ao painel de dados do cliente")</span><span class="sxs-lookup"><span data-stu-id="a4d4c-141">![Relate results to Customer data pane](media/intelligence-screen4-relatetocustomer.png "Relate results to Customer data pane")</span></span>

1. <span data-ttu-id="a4d4c-142">Você verá a tela **Fluxo de Trabalho Salvo** com detalhes sobre o fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-142">You'll see the **Workflow Saved** screen with details about the workflow.</span></span>    
   <span data-ttu-id="a4d4c-143">Se você configurou um fluxo de trabalho para um pipeline do Azure Machine Learning, os insights de público-lavo serão anexados ao espaço de trabalho que contém o pipeline.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-143">If you configured a workflow for an Azure Machine Learning pipeline, audience insights will attach to the workspace that contains the pipeline.</span></span> <span data-ttu-id="a4d4c-144">Os insights de público-alvo receberão uma função **Colaborador** no espaço de trabalho do Azure.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-144">Audience insights will get a **Contributor** role on the Azure workspace.</span></span>

1. <span data-ttu-id="a4d4c-145">Escolha **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-145">Select **Done**.</span></span>

1. <span data-ttu-id="a4d4c-146">Agora é possível executar o fluxo de trabalho na página **Modelos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-146">You can now run the workflow from the **Custom Models** page.</span></span>

## <a name="edit-a-workflow"></a><span data-ttu-id="a4d4c-147">Editar um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="a4d4c-147">Edit a workflow</span></span>

1. <span data-ttu-id="a4d4c-148">Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** ao lado de um fluxo de trabalho que você criou anteriormente e selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-148">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created and select **Edit**.</span></span>

1. <span data-ttu-id="a4d4c-149">Você pode atualizar o nome reconhecível do seu fluxo de trabalho no campo **Nome de exibição**, mas não pode alterar o serviço Web ou pipeline configurado.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-149">You can update your workflow's recognizable name in the **Display name** field, but you can't change the configured web service or pipeline.</span></span> <span data-ttu-id="a4d4c-150">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-150">Select **Next**.</span></span>

1. <span data-ttu-id="a4d4c-151">Para cada **entrada de serviço Web**, você pode atualizar a **Entidade** correspondente usando insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-151">For each **Web service input**, you can update the matching **Entity** from audience insights.</span></span> <span data-ttu-id="a4d4c-152">Em seguida, selecione **Próximo**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-152">Then, select **Next**.</span></span>

1. <span data-ttu-id="a4d4c-153">Na etapa **Parâmetros de saída do modelo**, defina as seguintes propriedades:</span><span class="sxs-lookup"><span data-stu-id="a4d4c-153">In the **Model Output Parameters** step, set the following properties:</span></span>
   - <span data-ttu-id="a4d4c-154">Machine Learning Studio (clássico)</span><span class="sxs-lookup"><span data-stu-id="a4d4c-154">Machine Learning Studio (classic)</span></span>
      1. <span data-ttu-id="a4d4c-155">Insira a saída **Nome da entidade** para a qual deseja que os resultados de saída do serviço Web fluam.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-155">Enter the output **Entity name** you want web service output results to flow into.</span></span>
   - <span data-ttu-id="a4d4c-156">Aprendizado de Máquina do Azure</span><span class="sxs-lookup"><span data-stu-id="a4d4c-156">Azure Machine Learning</span></span>
      1. <span data-ttu-id="a4d4c-157">Insira a saída **Nome da entidade** para a qual deseja que os resultados de saída do pipeline fluam.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-157">Enter the output **Entity name** you want pipeline output results to flow into.</span></span>
      1. <span data-ttu-id="a4d4c-158">Selecione **Nome do parâmetro de armazenamento de dados de saída** para seu pipeline de teste.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-158">Select the **Output data store parameter name** for your test pipeline.</span></span>
      1. <span data-ttu-id="a4d4c-159">Selecione **Nome do parâmetro do Caminho de Saída** para seu pipeline de teste.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-159">Select the **Output Path parameter name** for your test pipeline.</span></span>

1. <span data-ttu-id="a4d4c-160">Selecione o atributo correspondente na lista suspensa **ID do cliente nos resultados** que identifica os clientes e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-160">Select the matching attribute from the **Customer ID in results** drop-down list that identifies customers and select **Save**.</span></span>
   <span data-ttu-id="a4d4c-161">Você precisa escolher um atributo da saída de inferência com valores semelhantes à coluna ID do cliente da entidade Cliente.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-161">You need to choose an attribute from the inference output with values similar to the Customer ID column of the Customer entity.</span></span> <span data-ttu-id="a4d4c-162">Se não tiver essa coluna em seu conjunto de dados, escolha um atributo que identifique a linha de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-162">If don't have such a column in your data set, choose an attribute that uniquely identifies the row.</span></span>

## <a name="run-a-workflow"></a><span data-ttu-id="a4d4c-163">Executar um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="a4d4c-163">Run a workflow</span></span>

1. <span data-ttu-id="a4d4c-164">Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** ao lado de um fluxo de trabalho que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-164">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="a4d4c-165">Selecione **Executar**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-165">Select **Run**.</span></span>

<span data-ttu-id="a4d4c-166">Seu fluxo de trabalho também é executado automaticamente com cada atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-166">Your workflow also runs automatically with every scheduled refresh.</span></span> <span data-ttu-id="a4d4c-167">Saiba mais sobre como [configurar atualizações agendadas](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="a4d4c-167">Learn more about [setting up scheduled refreshes](system.md#schedule-tab).</span></span>

## <a name="delete-a-workflow"></a><span data-ttu-id="a4d4c-168">Excluir um fluxo de trabalho</span><span class="sxs-lookup"><span data-stu-id="a4d4c-168">Delete a workflow</span></span>

1. <span data-ttu-id="a4d4c-169">Na página **Modelos Personalizados**, selecione as reticências verticais na coluna **Ações** ao lado de um fluxo de trabalho que você criou anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-169">On the **Custom Models** page, select the vertical ellipsis in the **Actions** column next to a workflow you've previously created.</span></span>

1. <span data-ttu-id="a4d4c-170">Selecione **Excluir** e confirme sua exclusão.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-170">Select **Delete** and confirm your deletion.</span></span>

<span data-ttu-id="a4d4c-171">Seu fluxo de trabalho será excluído.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-171">Your workflow will be deleted.</span></span> <span data-ttu-id="a4d4c-172">A [entidade](entities.md) criada quando você criou o fluxo de trabalho persiste e pode ser visualizada na página **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="a4d4c-172">The [entity](entities.md) that was created when you created the workflow persists, and can be viewed from the **Entities** page.</span></span>
