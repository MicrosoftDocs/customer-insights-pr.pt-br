---
title: Segmentos sugeridos com base na atividade.
description: Deixe o Aprendizado de Máquina ajudá-lo a encontrar segmentos novos e interessantes com base na atividade do cliente.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034047"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a><span data-ttu-id="31136-103">Segmentos sugeridos com base em dados de atividade (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="31136-103">Suggested segments based on activity data (preview)</span></span>

<span data-ttu-id="31136-104">Descubra segmentos interessantes dos seus clientes com base nos dados de atividade do cliente que são ingeridos no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="31136-104">Discover interesting segments of your customers based on customer activity data that is ingested to Customer Insights.</span></span> <span data-ttu-id="31136-105">Exemplos de dados de atividades são transações, duração da chamada de suporte, compras ou devoluções.</span><span class="sxs-lookup"><span data-stu-id="31136-105">Examples of activity data are transactions, support call duration, purchases, or returns.</span></span> <span data-ttu-id="31136-106">Para sugerir segmentos, os dados de atividades são analisados quanto à atualidade, frequência e valor monetário (ou duração).</span><span class="sxs-lookup"><span data-stu-id="31136-106">To suggest segments, activity data gets analyzed for recency, frequency, and monetary value (or duration).</span></span> <span data-ttu-id="31136-107">Alternativamente, você pode gerar [segmentos sugeridos para melhorar uma medida ou entender melhor o que influencia um atributo](suggested-segments.md).</span><span class="sxs-lookup"><span data-stu-id="31136-107">Alternatively, you can generate [suggested segments to improve a measure or better understand what influences an attribute](suggested-segments.md).</span></span>

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Guia Segmentos sugeridos mostrando sugestões para segmentos baseados em atividades e em atributos.":::

## <a name="categorize-customers-by-activity"></a><span data-ttu-id="31136-109">Categorizar clientes por atividade</span><span class="sxs-lookup"><span data-stu-id="31136-109">Categorize customers by activity</span></span>

<span data-ttu-id="31136-110">Com os [dados de atividade](activities.md) disponíveis no Customer Insights, podemos gerar sugestões que representam grupos de clientes:</span><span class="sxs-lookup"><span data-stu-id="31136-110">With [activity data](activities.md) available in Customer Insights, we can generate suggestions that represent customer groups:</span></span>

- <span data-ttu-id="31136-111">maioria de clientes ativos</span><span class="sxs-lookup"><span data-stu-id="31136-111">most active customers</span></span> 
- <span data-ttu-id="31136-112">clientes que fizeram mais compras</span><span class="sxs-lookup"><span data-stu-id="31136-112">customers that have made the most purchases</span></span> 
- <span data-ttu-id="31136-113">clientes que geraram mais receita</span><span class="sxs-lookup"><span data-stu-id="31136-113">customers that generated the most revenue</span></span> 
- <span data-ttu-id="31136-114">clientes que não têm estado ativos recentemente</span><span class="sxs-lookup"><span data-stu-id="31136-114">customers who haven’t been active lately</span></span> 
- <span data-ttu-id="31136-115">clientes que interagem com sua empresa frequentemente</span><span class="sxs-lookup"><span data-stu-id="31136-115">customers who frequently interact with your business</span></span>  

<span data-ttu-id="31136-116">Se tiver uma empresa de varejo, você pode descobrir quais clientes geram mais receita e recompensá-los com um cupom.</span><span class="sxs-lookup"><span data-stu-id="31136-116">If you have a retail business, you could find out which customers generate the most revenue and reward them with a coupon.</span></span> <span data-ttu-id="31136-117">Ou você pode identificar clientes ocasionais e convidá-los a participar de um programa de recompensas para que visitem sua empresa mais frequentemente.</span><span class="sxs-lookup"><span data-stu-id="31136-117">Or you can identify occasional customers and offer them to join a rewards program so they visit your business more often.</span></span>
<span data-ttu-id="31136-118">Se você estiver no ramo de assistência médica fornecendo assistência médica pública e sua meta for reduzir as despesas de pacientes individuais.</span><span class="sxs-lookup"><span data-stu-id="31136-118">If you're in the healthcare business providing public healthcare and your goal is to minimize the expenses for individual patients.</span></span> <span data-ttu-id="31136-119">Uma forma de fazer isso seria reduzir as visitas recorrentes, dando o melhor atendimento possível no menor número de visitas possível.</span><span class="sxs-lookup"><span data-stu-id="31136-119">A way to do so could be to reduce recurring visits by providing best possible care in as few visits as possible.</span></span> <span data-ttu-id="31136-120">Nesse caso, seu objetivo é manter baixa a frequência de visitas e reduzir os custos recorrentes para os pacientes.</span><span class="sxs-lookup"><span data-stu-id="31136-120">In this case, your goal is to keep the visit frequency low and minimize recurring cost for the patients.</span></span> <span data-ttu-id="31136-121">Ou você pode identificar segmentos de pacientes que tenham consultas frequentes e altos custos recorrentes e analisar esses casos para melhorar o tratamento do indivíduo.</span><span class="sxs-lookup"><span data-stu-id="31136-121">Or you can identify segments of patients who have frequent appointments and high recurring costs and analyze these cases to improve the treatment of the individual.</span></span> 

## <a name="required-data"></a><span data-ttu-id="31136-122">Dados obrigatórios</span><span class="sxs-lookup"><span data-stu-id="31136-122">Required data</span></span>

<span data-ttu-id="31136-123">As sugestões são geradas com base nos dados de entrada selecionados.</span><span class="sxs-lookup"><span data-stu-id="31136-123">Suggestions are generated based on the selected input data.</span></span> 

- <span data-ttu-id="31136-124">Perfis do cliente: todos os clientes ou membros de um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="31136-124">Customer profiles: All customers or members of a specific segment.</span></span> 

- <span data-ttu-id="31136-125">Período: mês passado, ano passado ou qualquer período de tempo personalizado.</span><span class="sxs-lookup"><span data-stu-id="31136-125">Time period: Last month, last year, or any custom time frame.</span></span>

- <span data-ttu-id="31136-126">Tipo de atividade: compras, transações de varejo, transações online, casos de atendimento ao cliente, assinaturas e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="31136-126">Activity type: purchases, retail transactions, online transactions, customer support cases, subscriptions, and so on.</span></span>  

- <span data-ttu-id="31136-127">Entidade no Customer Insights que contém os dados da atividade: a entidade UnifiedActivity ou a entidade para uma atividade específica.</span><span class="sxs-lookup"><span data-stu-id="31136-127">Entity in Customer Insights that contains the activity data: The UnifiedActivity entity or the entity for a specific activity.</span></span> 

- <span data-ttu-id="31136-128">Dimensões a serem incluídas: atualidade, frequência ou dimensão monetária, dependendo dos requisitos de negócios.</span><span class="sxs-lookup"><span data-stu-id="31136-128">Dimensions to include: Recency, frequency, or monetary dimension, depending on your business requirements.</span></span>

## <a name="generate-suggested-segments"></a><span data-ttu-id="31136-129">Gerar segmentos sugeridos</span><span class="sxs-lookup"><span data-stu-id="31136-129">Generate suggested segments</span></span>

1. <span data-ttu-id="31136-130">Vá para **Segmentos**.</span><span class="sxs-lookup"><span data-stu-id="31136-130">Go to **Segments**.</span></span>

1. <span data-ttu-id="31136-131">Selecione a guia **Sugestões (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="31136-131">Select the **Suggestions (preview)** tab.</span></span>

1. <span data-ttu-id="31136-132">Selecione **Encontre novas sugestões** e escolha **Ver ou prever o comportamento do cliente**.</span><span class="sxs-lookup"><span data-stu-id="31136-132">Select **Find new suggestions** and choose **See or anticipate customer behavior**.</span></span> <span data-ttu-id="31136-133">Selecione **Iniciar** para executar a experiência guiada.</span><span class="sxs-lookup"><span data-stu-id="31136-133">Select **Start** to run the guided experience.</span></span>

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeira etapa do assistente de configuração para um segmento sugerido com base na atividade.":::

1. <span data-ttu-id="31136-135">Forneça os dados de entrada necessários e selecione **Avançar** para continuar.</span><span class="sxs-lookup"><span data-stu-id="31136-135">Provide the required input data and select **Next** proceed.</span></span>

   - <span data-ttu-id="31136-136">Escolha os clientes: inclua todos os clientes ou um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="31136-136">Choose customers: Include all customers or a specific segment.</span></span>
   - <span data-ttu-id="31136-137">Escolha a atividade: selecione o tipo de atividade e as entidades que a descrevem.</span><span class="sxs-lookup"><span data-stu-id="31136-137">Choose activity: Select the activity type and the entities that describe the activity.</span></span>
   - <span data-ttu-id="31136-138">Preferências: defina o período a ser considerado, os fatores para sugestões e mapeie os atributos.</span><span class="sxs-lookup"><span data-stu-id="31136-138">Preferences: Set the time period to consider, the factors for suggestions, and map the attributes.</span></span>

1. <span data-ttu-id="31136-139">Revise sua entrada e selecione **Executar** para executar o modelo e gerar sugestões.</span><span class="sxs-lookup"><span data-stu-id="31136-139">Review your input and select **Run** to run the model and generate suggestions.</span></span>

1. <span data-ttu-id="31136-140">Dependendo da quantidade de perfis de clientes e atividades selecionadas, pode levar alguns minutos para isso ser concluído.</span><span class="sxs-lookup"><span data-stu-id="31136-140">Depending on the number of customer profiles and selected activities, it can take a few minutes to complete.</span></span> 

<span data-ttu-id="31136-141">Depois de gerar as sugestões, você pode filtrá-las pela dimensão ou pelo valor em que tem mais interesse.</span><span class="sxs-lookup"><span data-stu-id="31136-141">After generating the suggestions, you can filter them by the dimension or value you're most interested in.</span></span> 

## <a name="view-details-of-a-suggested-segment"></a><span data-ttu-id="31136-142">Exibir detalhes do segmento sugerido</span><span class="sxs-lookup"><span data-stu-id="31136-142">View details of a suggested segment</span></span>

<span data-ttu-id="31136-143">Assim que as sugestões forem geradas, você as encontrará listadas em **Segmentos** > **Sugestões (versão preliminar)** na seção **Sugestões baseadas em atividades**.</span><span class="sxs-lookup"><span data-stu-id="31136-143">Once the suggestions are generated, you'll find them listed on **Segments** > **Suggestions (preview)** in the **Activity-based suggestions** section.</span></span>

:::image type="content" source="media/suggested-segments-details.png" alt-text="Painel lateral expandido exibindo os dados detalhados de um segmento sugerido.":::

<span data-ttu-id="31136-145">Selecione **Ver sugestão** em um segmento sugerido para ver os detalhes desse segmento.</span><span class="sxs-lookup"><span data-stu-id="31136-145">Select **See suggestion** on a suggested segment to view the details of that segment.</span></span> <span data-ttu-id="31136-146">O painel lateral dá os detalhes, como a extensão de cada dimensão em comparação com o grupo-alvo.</span><span class="sxs-lookup"><span data-stu-id="31136-146">The side pane provides details like the extent of each dimension in comparison to the target group.</span></span> <span data-ttu-id="31136-147">Ele também destaca o número de membros potenciais no segmento e o percentual correspondente do total de clientes.</span><span class="sxs-lookup"><span data-stu-id="31136-147">It also highlights the number of potential members in the segment and the corresponding percentage of the total customers.</span></span> <span data-ttu-id="31136-148">Se você quiser manter a sugestão como um segmento, selecione **Criar segmento**.</span><span class="sxs-lookup"><span data-stu-id="31136-148">If you want to keep the suggestion as a segment, select **Create segment**.</span></span>    

## <a name="save-a-suggestion-as-a-segment"></a><span data-ttu-id="31136-149">Salvar uma sugestão como um segmento</span><span class="sxs-lookup"><span data-stu-id="31136-149">Save a suggestion as a segment</span></span>

1. <span data-ttu-id="31136-150">Vá para **Segmentos** > **Sugestões (versão preliminar)**.</span><span class="sxs-lookup"><span data-stu-id="31136-150">Go to **Segments** > **Suggestions (preview)**.</span></span>

1. <span data-ttu-id="31136-151">Selecione o segmento que você quer salvar.</span><span class="sxs-lookup"><span data-stu-id="31136-151">Select the segment you want to save.</span></span> 

1. <span data-ttu-id="31136-152">No painel lateral, selecione **Criar segmento**.</span><span class="sxs-lookup"><span data-stu-id="31136-152">In the side pane, select **Create segment**.</span></span> 

1. <span data-ttu-id="31136-153">Depois de salvar o segmento, ele aparecerá na lista de segmentos na guia **Todos os segmentos**. Agora, ele pode ser [atualizado ou excluído assim como qualquer outro segmento](segments.md).</span><span class="sxs-lookup"><span data-stu-id="31136-153">After saving the segment, it will show in the list of segments on the **All segments** tab. It can now be [refreshed or deleted like any other segment](segments.md).</span></span> <span data-ttu-id="31136-154">Você não pode editar os detalhes do segmento.</span><span class="sxs-lookup"><span data-stu-id="31136-154">You can't edit the segment details.</span></span> <span data-ttu-id="31136-155">Porém, você pode alterar os critérios de entrada para as sugestões e gerar outras sugestões.</span><span class="sxs-lookup"><span data-stu-id="31136-155">However, you can change the input criteria for the suggestions and generate different suggestions.</span></span>

## <a name="refresh-or-edit-a-set-of-suggestions"></a><span data-ttu-id="31136-156">Atualize ou edite um conjunto de sugestões</span><span class="sxs-lookup"><span data-stu-id="31136-156">Refresh or edit a set of suggestions</span></span>

1. <span data-ttu-id="31136-157">Acesse **Segmentos** > **Sugestões (versão preliminar)** e procure o segmento na seção **Sugestões baseadas em atividades**.</span><span class="sxs-lookup"><span data-stu-id="31136-157">Go to **Segments** > **Suggestions (preview)** and look for the segment in the **Activity-based suggestions** section.</span></span>

1. <span data-ttu-id="31136-158">Selecione **Atualizar sugestões** para atualizar as sugestões, mantendo os atributos configurados.</span><span class="sxs-lookup"><span data-stu-id="31136-158">Select **Refresh suggestions** to refresh the suggestions while keeping configured attributes.</span></span> <span data-ttu-id="31136-159">Ou selecione **Editar sugestões** para modificar os atributos configurados.</span><span class="sxs-lookup"><span data-stu-id="31136-159">Or select **Edit suggestions** to modify the configured attributes.</span></span> <span data-ttu-id="31136-160">O sistema irá executar o processo novamente, gerar sugestões de segmento com base nos dados mais recentes e substituir as sugestões atuais.</span><span class="sxs-lookup"><span data-stu-id="31136-160">The system will rerun the process, generate segment suggestions based on the latest data, and replace the current suggestions.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
