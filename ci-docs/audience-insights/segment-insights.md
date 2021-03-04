---
title: Insights de segmento para segmentos existentes
description: Obtenha insights sobre os segmentos existentes para ver diferenças e semelhanças.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: d731d21462b5a31aba0653f87e299d98373bbf49
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270006"
---
# <a name="segment-insights-preview"></a><span data-ttu-id="63c8b-103">Insights do segmento (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="63c8b-103">Segment insights (preview)</span></span>

<span data-ttu-id="63c8b-104">Descubra informações e insights adicionais sobre segmentos existentes.</span><span class="sxs-lookup"><span data-stu-id="63c8b-104">Discover additional information and insights around your existing segments.</span></span> <span data-ttu-id="63c8b-105">Descubra o que diferencia dois segmentos ou o que eles têm em comum.</span><span class="sxs-lookup"><span data-stu-id="63c8b-105">Find out what differentiates two segments or what they have in common.</span></span>

## <a name="segment-overlap"></a><span data-ttu-id="63c8b-106">Sobreposição de segmentos</span><span class="sxs-lookup"><span data-stu-id="63c8b-106">Segment overlap</span></span>

<span data-ttu-id="63c8b-107">A análise de sobreposição de segmentos mostra quantos e quais clientes são comuns a dois ou mais segmentos.</span><span class="sxs-lookup"><span data-stu-id="63c8b-107">Segment overlap analysis shows how many and which customers are common to two or more segments.</span></span> <span data-ttu-id="63c8b-108">Por exemplo, como um segmento de clientes frequentes se sobrepõe a um segmento que contém clientes satisfeitos com seu serviço ou produto.</span><span class="sxs-lookup"><span data-stu-id="63c8b-108">For example, how a segment of frequent customers overlaps with a segment that contains customers that are satisfied with your service or product.</span></span>
<span data-ttu-id="63c8b-109">Você também pode analisar como a sobreposição muda para atributos específicos.</span><span class="sxs-lookup"><span data-stu-id="63c8b-109">You can also analyze how the overlap changes for specific attributes.</span></span>

### <a name="run-an-overlap-analysis"></a><span data-ttu-id="63c8b-110">Executar uma análise de sobreposição</span><span class="sxs-lookup"><span data-stu-id="63c8b-110">Run an overlap analysis</span></span>

1. <span data-ttu-id="63c8b-111">Vá para **Segmentos** e selecione a guia **Insights (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-111">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="63c8b-112">Selecione **Novo** e escolha a opção **Sobreposição** no painel **Escolher Tipo de Insight**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-112">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="63c8b-113">Escolha os segmentos de interesse e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-113">Choose the segments of interest and select **Next**.</span></span>

1. <span data-ttu-id="63c8b-114">Opcionalmente, escolha um ou mais campos de interesse para analisar sobreposições para cada valor de campo possível e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-114">Optionally, choose one or more fields of interest to analyze overlaps for every possible field value and select **Next**.</span></span>

1. <span data-ttu-id="63c8b-115">Forneça um nome para a análise de sobreposição, um nome de exibição opcional e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="63c8b-115">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="63c8b-116">Selecione **Salvar** para iniciar a análise.</span><span class="sxs-lookup"><span data-stu-id="63c8b-116">Select **Save** to start the analysis.</span></span> <span data-ttu-id="63c8b-117">A análise de sobreposição está pronta quando o status muda de Atualizando para Bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="63c8b-117">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-an-overlap-analysis"></a><span data-ttu-id="63c8b-118">Exibir e otimizar uma análise de sobreposição</span><span class="sxs-lookup"><span data-stu-id="63c8b-118">View and optimize an overlap analysis</span></span>

<span data-ttu-id="63c8b-119">Após concluir a análise, encontre detalhes sobre esse insight em **Segmentos** > **Insights (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-119">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalhes de insight de sobreposição de segmentos":::

<span data-ttu-id="63c8b-121">Selecione um insight para ver os resultados da análise:</span><span class="sxs-lookup"><span data-stu-id="63c8b-121">Select an insight to see the analysis results:</span></span>

- <span data-ttu-id="63c8b-122">O número de membros que se sobrepõem aos segmentos selecionados para análise.</span><span class="sxs-lookup"><span data-stu-id="63c8b-122">The number of members overlapping the segments selected for analysis.</span></span>
- <span data-ttu-id="63c8b-123">O número de membros incluídos em um dos segmentos, mas não no restante dos segmentos.</span><span class="sxs-lookup"><span data-stu-id="63c8b-123">The number of members included in one of the segments but not in the rest of the segments.</span></span>
- <span data-ttu-id="63c8b-124">Se você selecionou campos ao configurar a análise de sobreposição, encontre-os nas guias correspondentes.</span><span class="sxs-lookup"><span data-stu-id="63c8b-124">If you selected fields while configuring the overlap analysis, you'll find them in the corresponding tabs.</span></span> <span data-ttu-id="63c8b-125">Você pode usar o menu suspenso do filtro para selecionar qualquer nível de atributo de interesse e a tabela na parte inferior mostrará os dados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="63c8b-125">You can use the filter drop-down to select any attribute level of interest and the table at the bottom will show the corresponding data.</span></span>

## <a name="segment-differentiators"></a><span data-ttu-id="63c8b-126">Diferenciadores de segmento</span><span class="sxs-lookup"><span data-stu-id="63c8b-126">Segment differentiators</span></span>

<span data-ttu-id="63c8b-127">Os diferenciadores de segmento ajudam a descobrir o que diferencia um segmento dos demais clientes ou de outro segmento.</span><span class="sxs-lookup"><span data-stu-id="63c8b-127">Segment differentiators help you find out what differentiates a segment from the rest of your customers or from another segment.</span></span> <span data-ttu-id="63c8b-128">Você só precisa selecionar um segmento e o sistema identificará atributos e medidas do perfil que distinguem o segmento selecionado.</span><span class="sxs-lookup"><span data-stu-id="63c8b-128">You just have to select a segment and the system will identify profile attributes and measures that distinguish the selected segment.</span></span>

### <a name="run-a-differentiator-analysis"></a><span data-ttu-id="63c8b-129">Executar uma análise diferenciadora</span><span class="sxs-lookup"><span data-stu-id="63c8b-129">Run a differentiator analysis</span></span>

1. <span data-ttu-id="63c8b-130">Vá para **Segmentos** e selecione a guia **Insights (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-130">Go to **Segments** and select the **Insights (preview)** tab.</span></span>

1. <span data-ttu-id="63c8b-131">Selecione **Novo** e escolha a opção **Sobreposição** no painel **Escolher Tipo de Insight**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-131">Select **New** and choose the **Overlap** option in the **Choose Insight Type** pane.</span></span>

1. <span data-ttu-id="63c8b-132">Escolha o segmento que você deseja analisar como **Segmento primário** e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-132">Choose the segment you want to analyze as **Primary segment** and select **Next**.</span></span>

1. <span data-ttu-id="63c8b-133">Escolha **Todos os clientes** ou um **Segmento secundário** para comparar com o segmento primário e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-133">Choose **All customers** or a **Secondary segment** to compare your primary segment with and select **Next**.</span></span>

1. <span data-ttu-id="63c8b-134">Opcionalmente, escolha um ou mais campos de interesse para concentrar a análise em atributos específicos e selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-134">Optionally, choose one or more fields of interest to focus the analysis on specific attributes and select **Next**.</span></span>

1. <span data-ttu-id="63c8b-135">Forneça um nome para a análise de sobreposição, um nome de exibição opcional e uma descrição.</span><span class="sxs-lookup"><span data-stu-id="63c8b-135">Provide a name for you overlap analysis, an optional display name, and a description.</span></span>

1. <span data-ttu-id="63c8b-136">Selecione **Salvar** para iniciar a análise.</span><span class="sxs-lookup"><span data-stu-id="63c8b-136">Select **Save** to start the analysis.</span></span> <span data-ttu-id="63c8b-137">A análise de sobreposição está pronta quando o status muda de Atualizando para Bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="63c8b-137">The overlap analysis is ready when the status changes from Refreshing to Successful.</span></span>

### <a name="view-and-optimize-a-differentiators-analysis"></a><span data-ttu-id="63c8b-138">Exibir e otimizar uma análise de diferenciadores</span><span class="sxs-lookup"><span data-stu-id="63c8b-138">View and optimize a differentiators analysis</span></span>

<span data-ttu-id="63c8b-139">Após concluir a análise, encontre detalhes sobre esse insight em **Segmentos** > **Insights (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="63c8b-139">After completing the analysis, find details on this insight on **Segments** > **Insights (preview)**.</span></span>

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalhes de insight de diferenciador de segmentos":::

<span data-ttu-id="63c8b-141">Selecione um insight para ver os resultados da análise.</span><span class="sxs-lookup"><span data-stu-id="63c8b-141">Select an insight to see the analysis results.</span></span> <span data-ttu-id="63c8b-142">Uma análise diferenciadora inclui duas guias.</span><span class="sxs-lookup"><span data-stu-id="63c8b-142">A differentiator analysis includes two tabs.</span></span> <span data-ttu-id="63c8b-143">A guia **Atributos** lista os atributos de perfil considerados como diferenciadores.</span><span class="sxs-lookup"><span data-stu-id="63c8b-143">The **Attributes** tab lists profile attributes considered as differentiators.</span></span> <span data-ttu-id="63c8b-144">A guia **Medidas** lista diferenciadores.</span><span class="sxs-lookup"><span data-stu-id="63c8b-144">The **Measures** tab lists differentiators.</span></span> <span data-ttu-id="63c8b-145">Cada guia inclui os seguintes detalhes:</span><span class="sxs-lookup"><span data-stu-id="63c8b-145">Each tab includes the following details:</span></span>

- <span data-ttu-id="63c8b-146">Lista classificada de diferenciadores, ordenada pela pontuação da diferença.</span><span class="sxs-lookup"><span data-stu-id="63c8b-146">Ranked list of differentiators, sorted by difference score.</span></span>
- <span data-ttu-id="63c8b-147">A **Pontuação da diferença** para cada diferenciador.</span><span class="sxs-lookup"><span data-stu-id="63c8b-147">The **Difference score** for each differentiator.</span></span> <span data-ttu-id="63c8b-148">A pontuação da diferença representa o grau de diferença de um atributo entre dois segmentos.</span><span class="sxs-lookup"><span data-stu-id="63c8b-148">The difference score represents the degree of difference of an attribute between two segments.</span></span> <span data-ttu-id="63c8b-149">Quanto maior a pontuação da diferença, mais os atributos diferem entre os dois segmentos.</span><span class="sxs-lookup"><span data-stu-id="63c8b-149">The higher the difference score, the more the attributes differ between the two segments.</span></span> <span data-ttu-id="63c8b-150">Selecione uma pontuação para abrir o painel **Pontuação da diferença** com as distribuições de valores desse atributo.</span><span class="sxs-lookup"><span data-stu-id="63c8b-150">Select a score to open the **Difference score** pane with the distributions of values for that attribute.</span></span>

## <a name="manage-segment-insights"></a><span data-ttu-id="63c8b-151">Gerenciar insights de segmentos</span><span class="sxs-lookup"><span data-stu-id="63c8b-151">Manage segment insights</span></span>

<span data-ttu-id="63c8b-152">Você pode usar as seguintes opções em insights na barra de comandos:</span><span class="sxs-lookup"><span data-stu-id="63c8b-152">You can use the following options on your insights from the command bar:</span></span>

- <span data-ttu-id="63c8b-153">**Voltar** para retornar à lista de insights</span><span class="sxs-lookup"><span data-stu-id="63c8b-153">**Back** to return the list of insights</span></span>
- <span data-ttu-id="63c8b-154">**Atualizar** para executar a análise novamente</span><span class="sxs-lookup"><span data-stu-id="63c8b-154">**Refresh** to run the analysis again</span></span>
- <span data-ttu-id="63c8b-155">**Excluir** para remover esse insight</span><span class="sxs-lookup"><span data-stu-id="63c8b-155">**Delete** to remove this insight</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]