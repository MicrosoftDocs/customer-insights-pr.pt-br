---
title: Encontrar clientes semelhantes com IA
description: Encontrar segmentos de clientes semelhantes com inteligência artificial.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: b9b2e7fa862b595c6a364a7208e42295b4f9df83
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268856"
---
# <a name="similar-customers-preview"></a><span data-ttu-id="3090d-103">Clientes Semelhantes (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="3090d-103">Similar Customers (preview)</span></span>

<span data-ttu-id="3090d-104">Esse recurso permite encontrar clientes semelhantes em sua base de clientes usando inteligência artificial.</span><span class="sxs-lookup"><span data-stu-id="3090d-104">This feature lets you find similar customers in your customer base using artificial intelligence.</span></span> <span data-ttu-id="3090d-105">Você precisa ter pelo menos um segmento criado para usar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="3090d-105">You need to have at least one segment created to use this feature.</span></span> <span data-ttu-id="3090d-106">A expansão dos critérios de um segmento existente ajuda a encontrar clientes semelhantes a esse segmento.</span><span class="sxs-lookup"><span data-stu-id="3090d-106">Expanding the criteria of an existing segment help find customers that are similar to that segment.</span></span>

> [!NOTE]
> <span data-ttu-id="3090d-107">*Encontrar clientes semelhantes* usa meios automatizados para avaliar dados e fazer previsões com base nesses dados e, portanto, tem a capacidade de ser usado como um método de criação de perfil, pois esse termo é definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD").</span><span class="sxs-lookup"><span data-stu-id="3090d-107">*Find similar customers* uses automated means to evaluate data and make predictions based on that data, and therefore has the capability to be used as a method of profiling, as that term is defined by the General Data Protection Regulation (“GDPR”).</span></span> <span data-ttu-id="3090d-108">O uso desse recurso pelo cliente para processar dados pode estar sujeito ao RGPD ou a outras leis ou regulamentos.</span><span class="sxs-lookup"><span data-stu-id="3090d-108">Customer’s use of this feature to process data may be subject to GDPR or other laws or regulations.</span></span> <span data-ttu-id="3090d-109">Você é responsável por garantir que o uso do Dynamics 365 Customer Insights, incluindo as previsões, esteja em conformidade com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.</span><span class="sxs-lookup"><span data-stu-id="3090d-109">You are responsible for ensuring that your use of Dynamics 365 Customer Insights, including predictions, complies with all applicable laws and regulations, including laws related to privacy, personal data, biometric data, data protection, and confidentiality of communications.</span></span>

## <a name="finding-similar-customers"></a><span data-ttu-id="3090d-110">Encontrando clientes semelhantes</span><span class="sxs-lookup"><span data-stu-id="3090d-110">Finding similar customers</span></span>

1. <span data-ttu-id="3090d-111">Nos insights de público-alvo, vá para **Segmentos** e selecione o segmento no qual deseja basear seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="3090d-111">In audience insights, go to **Segments** and select the segment you want to base your new segment on.</span></span> <span data-ttu-id="3090d-112">Esse é o seu *segmento de origem*.</span><span class="sxs-lookup"><span data-stu-id="3090d-112">That's your *source segment*.</span></span>

1. <span data-ttu-id="3090d-113">Na barra de ação, selecione **Encontrar clientes semelhantes**.</span><span class="sxs-lookup"><span data-stu-id="3090d-113">In the action bar, select **Find similar customers**.</span></span>

1. <span data-ttu-id="3090d-114">Revise o nome sugerido para o seu novo segmento e altere-o, se necessário.</span><span class="sxs-lookup"><span data-stu-id="3090d-114">Review the suggested name for your new segment and change it if necessary.</span></span>

1. <span data-ttu-id="3090d-115">Revise os campos que definem seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="3090d-115">Review the fields that define your new segment.</span></span> <span data-ttu-id="3090d-116">Esses campos definem a base na qual o sistema tentará encontrar clientes semelhantes ao seu segmento de origem.</span><span class="sxs-lookup"><span data-stu-id="3090d-116">These fields define the basis on which the system will try to find similar customers to your source segment.</span></span> <span data-ttu-id="3090d-117">O sistema selecionará os campos recomendados por padrão.</span><span class="sxs-lookup"><span data-stu-id="3090d-117">The system will select recommended fields by default.</span></span>
  <span data-ttu-id="3090d-118">Os campos que podem reduzir significativamente o desempenho do modelo são excluídos automaticamente:</span><span class="sxs-lookup"><span data-stu-id="3090d-118">Fields that can significantly reduce the model performance are automatically excluded:</span></span>
  
   - <span data-ttu-id="3090d-119">Campos com os seguintes tipos de dados: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span><span class="sxs-lookup"><span data-stu-id="3090d-119">Fields with the following data types: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType</span></span>
   - <span data-ttu-id="3090d-120">Campos com cardinalidade (o número de elementos em um campo) menor que 2 ou maior que 30</span><span class="sxs-lookup"><span data-stu-id="3090d-120">Fields with a cardinality (the number of elements in a field) of less than 2 or more than 30</span></span>

1. <span data-ttu-id="3090d-121">Escolha se você deseja incluir **Todos os cliente** ou apenas clientes em um **Segmento existente específico** no seu novo segmento.</span><span class="sxs-lookup"><span data-stu-id="3090d-121">Choose if you want to include **All customers** or only customers in a **Specific existing segment** in your new segment.</span></span>

1. <span data-ttu-id="3090d-122">Excluir clientes no seu segmento de origem selecionando a caixa de seleção **Excluir todos no segmento de origem**.</span><span class="sxs-lookup"><span data-stu-id="3090d-122">Exclude customers in your source segment by selecting the **Exclude everyone in source segment** checkbox.</span></span>

1. <span data-ttu-id="3090d-123">Por padrão, o sistema sugere incluir apenas 20% do tamanho do público-alvo em sua saída.</span><span class="sxs-lookup"><span data-stu-id="3090d-123">By default, the system suggests including only 20% of the target audience size in your output.</span></span> <span data-ttu-id="3090d-124">Edite esse limite, conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="3090d-124">Edit this threshold as needed.</span></span> <span data-ttu-id="3090d-125">Aumentar o limite reduzirá a precisão.</span><span class="sxs-lookup"><span data-stu-id="3090d-125">Increasing the threshold will reduce the precision.</span></span>

1. <span data-ttu-id="3090d-126">Selecione **Executar** na parte inferior da página, para iniciar uma tarefa de classificação binária (um método de aprendizado de máquina) que analisa o conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="3090d-126">Select **Run** at the bottom of the page to start a binary classification task (a method of machine learning) which analyzes the dataset.</span></span>

## <a name="view-the-similar-segment"></a><span data-ttu-id="3090d-127">Ver o segmento semelhante</span><span class="sxs-lookup"><span data-stu-id="3090d-127">View the similar segment</span></span>

<span data-ttu-id="3090d-128">Depois de processar o segmento semelhante, você encontrará o novo segmento listado na página **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="3090d-128">After processing the similar segment, you'll find the new segment listed on the **Segments** page.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="3090d-129">![Segmento de clientes semelhante](media/expanded-segment.png "Segmento de clientes semelhante")</span><span class="sxs-lookup"><span data-stu-id="3090d-129">![Similar customers segment](media/expanded-segment.png "Similar customers segment")</span></span>

<span data-ttu-id="3090d-130">Selecione **Exibir** na barra de ação para abrir os detalhes do segmento.</span><span class="sxs-lookup"><span data-stu-id="3090d-130">Select **View** in the action bar to open the segment detail.</span></span> <span data-ttu-id="3090d-131">Essa exibição contém informações sobre a distribuição de resultados entre [pontuações de similaridade](#about-similarity-scores).</span><span class="sxs-lookup"><span data-stu-id="3090d-131">This view contains information about the result distribution across [similarity scores](#about-similarity-scores).</span></span> <span data-ttu-id="3090d-132">Você também encontrará os valores da pontuação de similaridade na **Visualização Membros do segmento**.</span><span class="sxs-lookup"><span data-stu-id="3090d-132">You'll also find the similarity score values in the **Segment members preview**.</span></span>

## <a name="use-the-output-of-a-similar-segment"></a><span data-ttu-id="3090d-133">Use a saída de um segmento semelhante</span><span class="sxs-lookup"><span data-stu-id="3090d-133">Use the output of a similar segment</span></span>

<span data-ttu-id="3090d-134">Você pode [trabalhar com a saída de um segmento semelhante](segments.md), como você faz com outros segmentos.</span><span class="sxs-lookup"><span data-stu-id="3090d-134">You can [work with the output of a similar segment](segments.md) as you do with other segments.</span></span> <span data-ttu-id="3090d-135">Por exemplo, exporte o segmento ou crie uma medida.</span><span class="sxs-lookup"><span data-stu-id="3090d-135">For example, export the segment or build a measure.</span></span>

## <a name="refresh-and-edit-a-similar-segment"></a><span data-ttu-id="3090d-136">Atualize e edite um segmento semelhante</span><span class="sxs-lookup"><span data-stu-id="3090d-136">Refresh and edit a similar segment</span></span>

<span data-ttu-id="3090d-137">Para atualizar um segmento semelhante, selecione-o na página **Segmentos** e selecione **Atualizar** na barra de ação.</span><span class="sxs-lookup"><span data-stu-id="3090d-137">To refresh a similar segment, select it on the **Segments** page and select **Refresh** in the action bar.</span></span>

<span data-ttu-id="3090d-138">A edição de um segmento semelhante reprocessará seus dados.</span><span class="sxs-lookup"><span data-stu-id="3090d-138">Editing a similar segment will reprocess your data.</span></span> <span data-ttu-id="3090d-139">O segmento criado anteriormente é atualizado com dados atualizados.</span><span class="sxs-lookup"><span data-stu-id="3090d-139">The previously created segment gets updated with refreshed data.</span></span>    
<span data-ttu-id="3090d-140">Para editar um segmento semelhante, selecione-o na página **Segmentos** e selecione **Editar** na barra de ação.</span><span class="sxs-lookup"><span data-stu-id="3090d-140">To edit a similar segment, select it on the **Segments** page and select **Edit** in the action bar.</span></span> <span data-ttu-id="3090d-141">Aplique suas alterações e selecione **Executar** para iniciar o processamento.</span><span class="sxs-lookup"><span data-stu-id="3090d-141">Apply your changes and select **Run** to start the processing.</span></span>

## <a name="delete-a-similar-segment"></a><span data-ttu-id="3090d-142">Excluir um segmento semelhante</span><span class="sxs-lookup"><span data-stu-id="3090d-142">Delete a similar segment</span></span>

<span data-ttu-id="3090d-143">Selecione o segmento na página **Segmentos** e selecione **Excluir** na barra de ação.</span><span class="sxs-lookup"><span data-stu-id="3090d-143">Select the segment on the **Segments** page and select **Delete** in the action bar.</span></span> <span data-ttu-id="3090d-144">Em seguida, confirme a exclusão.</span><span class="sxs-lookup"><span data-stu-id="3090d-144">Then, confirm your deletion.</span></span>

## <a name="about-similarity-scores"></a><span data-ttu-id="3090d-145">Sobre pontuações de similaridade</span><span class="sxs-lookup"><span data-stu-id="3090d-145">About similarity scores</span></span>

<span data-ttu-id="3090d-146">O modelo de machine learning de classificação binário atribui uma pontuação aos clientes no segmento semelhante.</span><span class="sxs-lookup"><span data-stu-id="3090d-146">The binary classification machine learning model assigns a score to customers in the similar segment.</span></span> <span data-ttu-id="3090d-147">A pontuação é baseada na semelhança com os clientes no segmento de origem.</span><span class="sxs-lookup"><span data-stu-id="3090d-147">The score is based on the similarity to customers in the source segment.</span></span>

- <span data-ttu-id="3090d-148">Pontuações de similaridade abaixo de 0,55 são clientes classificados pelo sistema como *não similar* para clientes no segmento de origem</span><span class="sxs-lookup"><span data-stu-id="3090d-148">Similarity scores below 0.55 are customers the system classified as *not similar* to customers in the source segment</span></span>
- <span data-ttu-id="3090d-149">As pontuações de similaridade entre 0,55 - 0,7 são classificados como *um pouco semelhante*</span><span class="sxs-lookup"><span data-stu-id="3090d-149">Similarity scores between 0.55 – 0.7 are classified as *somewhat similar*</span></span>
- <span data-ttu-id="3090d-150">As pontuações de similaridade entre 0,7 - 0,85 são classificados como *um pouco semelhante*</span><span class="sxs-lookup"><span data-stu-id="3090d-150">Similarity scores between 0.7 – 0.85 are classified as *similar*</span></span>
- <span data-ttu-id="3090d-151">Pontuações de similaridade entre 0,85 - 1 são clientes classificados pelo sistema como *muito parecido*</span><span class="sxs-lookup"><span data-stu-id="3090d-151">Similarity scores between 0.85 – 1 are customers the system classified as *very similar*</span></span>

<span data-ttu-id="3090d-152">Clientes com pontuações de similaridade abaixo de 0,4 não são incluídos na saída do modelo.</span><span class="sxs-lookup"><span data-stu-id="3090d-152">Customers with similarity scores below 0.4 aren't included in the model output.</span></span> <span data-ttu-id="3090d-153">O sistema não os considera semelhantes o suficiente para o segmento de origem.</span><span class="sxs-lookup"><span data-stu-id="3090d-153">The system doesn't consider them similar enough to the source segment.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]