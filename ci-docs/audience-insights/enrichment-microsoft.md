---
title: Enriquecer perfis de clientes com dados da Microsoft
description: Use dados proprietários da Microsoft para enriquecer dados de clientes com afinidades de marca e interesse.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e92360bb886739cfe477ce1d2eb62219228a0292
ms.sourcegitcommit: d4b4053f6ee8f60f1a214982c4726c9de84615ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2021
ms.locfileid: "6245693"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a><span data-ttu-id="414e6-103">Enriquecer perfis de clientes com afinidades de marca e interesse (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="414e6-103">Enrich customer profiles with brand and interest affinities (preview)</span></span>

<span data-ttu-id="414e6-104">Use dados proprietários da Microsoft para enriquecer dados de clientes com afinidades de marca e interesse.</span><span class="sxs-lookup"><span data-stu-id="414e6-104">Use Microsoft's proprietary data to enrich your customer data with brand and interest affinities.</span></span> <span data-ttu-id="414e6-105">Essas afinidades são determinadas com base em dados de pessoas com dados demográficos semelhantes aos de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="414e6-105">These affinities are determined based on data from people with similar demographics to your customers.</span></span> <span data-ttu-id="414e6-106">Essas informações ajudam a entender e segmentar melhor seus clientes com base em suas afinidades com marcas e interesses específicos.</span><span class="sxs-lookup"><span data-stu-id="414e6-106">This information helps you to better understand and segment your customers based on their affinities to specific brands and interests.</span></span>

<span data-ttu-id="414e6-107">Em insights de público-alvo, acesse **Dados** > **Enriquecimento** para [configurar e exibir enriquecimentos](enrichment-hub.md).</span><span class="sxs-lookup"><span data-stu-id="414e6-107">In audience insights, go to **Data** > **Enrichment** to [configure and view enrichments](enrichment-hub.md).</span></span>

<span data-ttu-id="414e6-108">Para configurar o enriquecimento das afinidades da marca, vá para a guia **Descobrir** e selecione **Enriquecer meus dados** no bloco **Marcas**.</span><span class="sxs-lookup"><span data-stu-id="414e6-108">To configure brand affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Brands** tile.</span></span>

<span data-ttu-id="414e6-109">Para configurar o enriquecimento das afinidades do interesse, vá para a guia **Descobrir** e selecione **Enriquecer meus dados** no bloco **Interesses**.</span><span class="sxs-lookup"><span data-stu-id="414e6-109">To configure interest affinities enrichment, go to the **Discover** tab and select **Enrich my data** on the **Interests** tile.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="414e6-110">![Blocos de Marcas e Interesses](media/BrandsInterest-tile-Hub.png "Blocos de Marcas e Interesses")</span><span class="sxs-lookup"><span data-stu-id="414e6-110">![Brands & Interests tiles](media/BrandsInterest-tile-Hub.png "Brands & Interest tiles")</span></span>

## <a name="how-we-determine-affinities"></a><span data-ttu-id="414e6-111">Como determinamos afinidades</span><span class="sxs-lookup"><span data-stu-id="414e6-111">How we determine affinities</span></span>

<span data-ttu-id="414e6-112">Usamos dados de pesquisa online da Microsoft para encontrar afinidades por marcas e interesses entre vários segmentos demográficos (definidos por idade, sexo ou localização).</span><span class="sxs-lookup"><span data-stu-id="414e6-112">We use Microsoft’s online search data to find affinities for brands and interests across various demographic segments (defined by age, gender, or location).</span></span> <span data-ttu-id="414e6-113">O volume de pesquisa online de uma marca ou interesse determina quanta afinidade um segmento demográfico, em comparação com outros segmentos, tem com essa marca ou interesse.</span><span class="sxs-lookup"><span data-stu-id="414e6-113">The online search volume for a brand or interest determines how much affinity a demographic segment, compared to other segments, has to that brand or interest.</span></span>

## <a name="affinity-level-and-score"></a><span data-ttu-id="414e6-114">Nível e pontuação de afinidade</span><span class="sxs-lookup"><span data-stu-id="414e6-114">Affinity level and score</span></span>

<span data-ttu-id="414e6-115">Em cada perfil de cliente enriquecido, fornecemos dois valores relacionados – nível de afinidade e pontuação de afinidade.</span><span class="sxs-lookup"><span data-stu-id="414e6-115">On every enriched customer profile, we provide two related values – affinity level and affinity score.</span></span> <span data-ttu-id="414e6-116">Esses valores ajudam a determinar o grau de afinidade para o segmento demográfico do perfil, uma marca ou interesse, em comparação a outros segmentos demográficos.</span><span class="sxs-lookup"><span data-stu-id="414e6-116">These values help you determine how strong the affinity is for that profile’s demographic segment, for a brand or interest, as compared to other demographic segments.</span></span>

<span data-ttu-id="414e6-117">O *nível de afinidade* consiste em quatro níveis e *pontuação de afinidade* é calculado em uma escala de 100 pontos que mapeia para os níveis de afinidade.</span><span class="sxs-lookup"><span data-stu-id="414e6-117">*Affinity level* consists of four levels and *affinity score* is calculated on a 100-point scale that maps to the affinity levels.</span></span>


|<span data-ttu-id="414e6-118">Nível de afinidade</span><span class="sxs-lookup"><span data-stu-id="414e6-118">Affinity level</span></span> |<span data-ttu-id="414e6-119">Pontuação de afinidade</span><span class="sxs-lookup"><span data-stu-id="414e6-119">Affinity score</span></span>  |
|---------|---------|
|<span data-ttu-id="414e6-120">Muito alto</span><span class="sxs-lookup"><span data-stu-id="414e6-120">Very high</span></span>     | <span data-ttu-id="414e6-121">85 a 100</span><span class="sxs-lookup"><span data-stu-id="414e6-121">85-100</span></span>       |
|<span data-ttu-id="414e6-122">Alto(a)</span><span class="sxs-lookup"><span data-stu-id="414e6-122">High</span></span>     | <span data-ttu-id="414e6-123">70 a 84</span><span class="sxs-lookup"><span data-stu-id="414e6-123">70-84</span></span>        |
|<span data-ttu-id="414e6-124">Médio(a)</span><span class="sxs-lookup"><span data-stu-id="414e6-124">Medium</span></span>     | <span data-ttu-id="414e6-125">35 a 69</span><span class="sxs-lookup"><span data-stu-id="414e6-125">35-69</span></span>        |
|<span data-ttu-id="414e6-126">Baixo(a)</span><span class="sxs-lookup"><span data-stu-id="414e6-126">Low</span></span>     | <span data-ttu-id="414e6-127">1 a 34</span><span class="sxs-lookup"><span data-stu-id="414e6-127">1-34</span></span>        |

<span data-ttu-id="414e6-128">Dependendo da granularidade que deseja para medir a afinidade, é possível usar o nível ou a pontuação de afinidade.</span><span class="sxs-lookup"><span data-stu-id="414e6-128">Depending on the granularity you would like for measuring the affinity, you can use either affinity level or score.</span></span> <span data-ttu-id="414e6-129">A pontuação de afinidade oferece um controle mais preciso.</span><span class="sxs-lookup"><span data-stu-id="414e6-129">Affinity score gives you more precise control.</span></span>

## <a name="supported-countriesregions"></a><span data-ttu-id="414e6-130">Países/regiões com suporte</span><span class="sxs-lookup"><span data-stu-id="414e6-130">Supported countries/regions</span></span>

<span data-ttu-id="414e6-131">Atualmente, oferecemos suporte para as seguintes opções de país/região: Austrália, Canadá (inglês), França, Alemanha, Reino Unido ou Estados Unidos (inglês).</span><span class="sxs-lookup"><span data-stu-id="414e6-131">We currently support the following country/region options: Australia, Canada (English), France, Germany, United Kingdom, or United States (English).</span></span>

<span data-ttu-id="414e6-132">Para selecionar um país, abra o **Enriquecimento de marcas** ou **Enriquecimento de interesse** e selecione **Alterar** ao lado de **País/Região**.</span><span class="sxs-lookup"><span data-stu-id="414e6-132">To select a country, open the **Brands enrichment** or **Interest enrichment** and select **Change** next to **Country/Region**.</span></span> <span data-ttu-id="414e6-133">No painel **Configurações de país/região**, escolha uma opção e selecione **Aplicar**.</span><span class="sxs-lookup"><span data-stu-id="414e6-133">In the **Country/Region settings** pane, choose an option and select **Apply**.</span></span>

### <a name="implications-related-to-country-selection"></a><span data-ttu-id="414e6-134">Implicações relativas à seleção de país</span><span class="sxs-lookup"><span data-stu-id="414e6-134">Implications related to country selection</span></span>

- <span data-ttu-id="414e6-135">Ao [escolher suas próprias marcas](#define-your-brands-or-interests), o sistema oferece sugestões com base no país/região selecionado.</span><span class="sxs-lookup"><span data-stu-id="414e6-135">When [choosing your own brands](#define-your-brands-or-interests), the system provides suggestions based on the selected country or region.</span></span>

- <span data-ttu-id="414e6-136">Ao [escolher um setor](#define-your-brands-or-interests), você obterá as marcas ou os interesses mais relevantes com base no país/região selecionado.</span><span class="sxs-lookup"><span data-stu-id="414e6-136">When [choosing an industry](#define-your-brands-or-interests), you'll get the most relevant brands or interests based on the selected country or region.</span></span>

- <span data-ttu-id="414e6-137">Ao [enriquecer perfis](#refresh-enrichment), enriqueceremos todos os perfis de cliente para os quais obtemos dados para as marcas e os interesses selecionados.</span><span class="sxs-lookup"><span data-stu-id="414e6-137">When [enriching profiles](#refresh-enrichment), we'll enrich all customer profiles for which we get data for the selected brands and interests.</span></span> <span data-ttu-id="414e6-138">Incluindo perfis que não estão no país/região selecionado.</span><span class="sxs-lookup"><span data-stu-id="414e6-138">Including profiles that are not in the selected country or region.</span></span> <span data-ttu-id="414e6-139">Por exemplo, se você selecionou Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados disponíveis para as marcas e os interesses selecionados nos EUA.</span><span class="sxs-lookup"><span data-stu-id="414e6-139">For example, if you selected Germany, we'll enrich profiles located in the United States if we have data available for the selected brands and interests in the US.</span></span>

## <a name="configure-enrichment"></a><span data-ttu-id="414e6-140">Configurar Enriquecimento</span><span class="sxs-lookup"><span data-stu-id="414e6-140">Configure Enrichment</span></span>

<span data-ttu-id="414e6-141">Uma experiência guiada ajuda você na configuração dos enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="414e6-141">A guided experience helps you through the configuration of the enrichments.</span></span> 

### <a name="define-your-brands-or-interests"></a><span data-ttu-id="414e6-142">Definir suas marcas ou interesses</span><span class="sxs-lookup"><span data-stu-id="414e6-142">Define your brands or interests</span></span>

<span data-ttu-id="414e6-143">Escolha até cinco marcas ou interesses usando uma ou ambas as opções:</span><span class="sxs-lookup"><span data-stu-id="414e6-143">Choose up to five brands or interests using one or both of these options:</span></span>

- <span data-ttu-id="414e6-144">**Setor**: selecione seu setor na lista suspensa e escolha entre as principais marcas ou interesses desse setor.</span><span class="sxs-lookup"><span data-stu-id="414e6-144">**Industry**: Select your industry from the drop-down list and then choose from the top brands or interests for that industry.</span></span>
- <span data-ttu-id="414e6-145">**Escolher seus próprios**: insira uma marca ou interesse que seja relevante para sua organização e escolha uma das sugestões correspondentes.</span><span class="sxs-lookup"><span data-stu-id="414e6-145">**Choose your own**: Enter a brand or interest that is relevant to your organization and then choose from the matching suggestions.</span></span> <span data-ttu-id="414e6-146">Se não listarmos uma marca ou interesse que você procura, envie-nos seus comentários usando o link **Sugerir**.</span><span class="sxs-lookup"><span data-stu-id="414e6-146">If we don't list a brand or interest you're looking for, send us feedback using the **Suggest** link.</span></span>

### <a name="review-enrichment-preferences"></a><span data-ttu-id="414e6-147">Revisar preferências de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="414e6-147">Review enrichment preferences</span></span>

<span data-ttu-id="414e6-148">Revise as preferências de enriquecimento padrão e atualize-as conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="414e6-148">Review your default enrichment preferences and update them as needed.</span></span>

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de tela da janela de preferências de enriquecimento.":::

### <a name="select-entity-to-enrich"></a><span data-ttu-id="414e6-150">Selecione a entidade a ser enriquecida</span><span class="sxs-lookup"><span data-stu-id="414e6-150">Select entity to enrich</span></span>

<span data-ttu-id="414e6-151">Selecione **Entidade enriquecida** e escolha o conjunto de dados que deseja enriquecer com os dados da empresa da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="414e6-151">Select **Enriched entity** and choose the data set you want to enrich with company data from the Microsoft.</span></span> <span data-ttu-id="414e6-152">Você pode selecionar a entidade Cliente para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.</span><span class="sxs-lookup"><span data-stu-id="414e6-152">You can select the Customer entity to enrich all your customer profiles or select a segment entity to enrich only customer profiles contained in that segment.</span></span>

### <a name="map-your-fields"></a><span data-ttu-id="414e6-153">Mapear seus campos</span><span class="sxs-lookup"><span data-stu-id="414e6-153">Map your fields</span></span>

<span data-ttu-id="414e6-154">Mapeie os campos da entidade de cliente unificada para definir o segmento demográfico que deseja que o sistema use para enriquecer os dados de clientes.</span><span class="sxs-lookup"><span data-stu-id="414e6-154">Map fields from your unified customer entity to define the demographic segment you want the system to use for enriching your customer data.</span></span> <span data-ttu-id="414e6-155">Mapeie País/Região e pelo menos os atributos de Data de Nascimento ou Sexo.</span><span class="sxs-lookup"><span data-stu-id="414e6-155">Map Country/Region and at least Date of Birth or Gender attributes.</span></span> <span data-ttu-id="414e6-156">Além disso, é necessário mapear pelo menos uma Cidade (e Estado/Província) ou CEP.</span><span class="sxs-lookup"><span data-stu-id="414e6-156">Additionally, you must map at least one of City (and State/Province) or Postal code.</span></span> <span data-ttu-id="414e6-157">Selecione **Editar** para definir o mapeamento dos campos e selecione **Aplicar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="414e6-157">Select **Edit** to define the mapping of the fields and select **Apply** when you're done.</span></span> <span data-ttu-id="414e6-158">Selecione **Salvar** para concluir o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="414e6-158">Select **Save** to complete the field mapping.</span></span>

<span data-ttu-id="414e6-159">Os seguintes formatos e valores têm suporte; os valores não diferenciam maiúsculas de minúsculas:</span><span class="sxs-lookup"><span data-stu-id="414e6-159">The following formats and values are supported, values are not case-sensitive:</span></span>

- <span data-ttu-id="414e6-160">**Data de nascimento**: recomendamos que a data de nascimento seja convertida no tipo DateTime durante a ingestão de dados.</span><span class="sxs-lookup"><span data-stu-id="414e6-160">**Date of Birth**: We recommend that date of birth is converted to DateTime type during data ingestion.</span></span> <span data-ttu-id="414e6-161">Como alternativa, pode ser uma string no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ssZ".</span><span class="sxs-lookup"><span data-stu-id="414e6-161">Alternatively, it can be a string in [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) format "yyyy-MM-dd" or "yyyy-MM-ddTHH:mm:ssZ".</span></span>
- <span data-ttu-id="414e6-162">**Gênero**: Masculino, Feminino, Desconhecido</span><span class="sxs-lookup"><span data-stu-id="414e6-162">**Gender**: Male, Female, Unknown</span></span>
- <span data-ttu-id="414e6-163">**Código postal**: CEPs de cinco dígitos para os EUA, código postal padrão em todos os outros lugares</span><span class="sxs-lookup"><span data-stu-id="414e6-163">**Postal code**: Five-digit ZIP Codes for US, standard postal code everywhere else</span></span>
- <span data-ttu-id="414e6-164">**Cidade**: nome da cidade em inglês</span><span class="sxs-lookup"><span data-stu-id="414e6-164">**City**: City name in English</span></span>
- <span data-ttu-id="414e6-165">**Estado/Província**: abreviação de duas letras para os EUA e o Canadá.</span><span class="sxs-lookup"><span data-stu-id="414e6-165">**State/Province**: Two-letter abbreviation for the US and Canada.</span></span> <span data-ttu-id="414e6-166">Abreviação de duas ou três letras para a Austrália.</span><span class="sxs-lookup"><span data-stu-id="414e6-166">Two or three letter abbreviation for Australia.</span></span> <span data-ttu-id="414e6-167">Não aplicável à França, à Alemanha ou ao Reino Unido.</span><span class="sxs-lookup"><span data-stu-id="414e6-167">Not applicable for France, Germany, or the UK.</span></span>
- <span data-ttu-id="414e6-168">**País/Região**:</span><span class="sxs-lookup"><span data-stu-id="414e6-168">**Country/Region**:</span></span>

  - <span data-ttu-id="414e6-169">EUA: Estados Unidos da América, Estados Unidos, EUA, América</span><span class="sxs-lookup"><span data-stu-id="414e6-169">US: United States of America, United States, USA, US, America</span></span>
  - <span data-ttu-id="414e6-170">CA: Canadá, CA</span><span class="sxs-lookup"><span data-stu-id="414e6-170">CA: Canada, CA</span></span>
  - <span data-ttu-id="414e6-171">GB: Reino Unido, Reino Unido, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha</span><span class="sxs-lookup"><span data-stu-id="414e6-171">GB: United Kingdom, UK, Great Britain, GB, United Kingdom of Great Britain and Northern Ireland, United Kingdom of Great Britain</span></span>
  - <span data-ttu-id="414e6-172">AU: Austrália, AU, Common Wealth of Australia</span><span class="sxs-lookup"><span data-stu-id="414e6-172">AU: Australia, AU, Common Wealth of Australia</span></span>
  - <span data-ttu-id="414e6-173">FR: França, FR, República Francesa</span><span class="sxs-lookup"><span data-stu-id="414e6-173">FR: France, FR, French Republic</span></span>
  - <span data-ttu-id="414e6-174">DE: Alemanha, Alemanha, Deutschland, Allemagne, DE, República Federal da Alemanha, República da Alemanha</span><span class="sxs-lookup"><span data-stu-id="414e6-174">DE: Germany, German, Deutschland, Allemagne, DE, Federal Republic of Germany, Republic of Germany</span></span>

## <a name="review-and-name-the-enrichment"></a><span data-ttu-id="414e6-175">Revise e nomeie o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="414e6-175">Review and name the enrichment</span></span>

<span data-ttu-id="414e6-176">Por último, você pode revisar as informações e fornecer um nome para o enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="414e6-176">Finally, you get to review the information and provide a name for the enrichment.</span></span>

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisão de interesses e página de nomenclatura.":::

## <a name="refresh-enrichment"></a><span data-ttu-id="414e6-178">Atualizar enriquecimento</span><span class="sxs-lookup"><span data-stu-id="414e6-178">Refresh enrichment</span></span>

<span data-ttu-id="414e6-179">Execute o enriquecimento depois de configurar marcas, interesses e o mapeamento de campo para dados demográficos.</span><span class="sxs-lookup"><span data-stu-id="414e6-179">Run the enrichment after configuring brands, interests, and the field mapping for demographics.</span></span> <span data-ttu-id="414e6-180">Para iniciar o processo, selecione **Executar** na página de configuração de marca ou interesse.</span><span class="sxs-lookup"><span data-stu-id="414e6-180">To start the process, select **Run** on the brand or interest configuration page.</span></span> <span data-ttu-id="414e6-181">Além disso, você pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="414e6-181">Additionally, you can let the system run the enrichment automatically as part of a scheduled refresh.</span></span>
<span data-ttu-id="414e6-182">Dependendo do tamanho dos dados do cliente, pode levar alguns minutos para que uma execução de enriquecimento seja concluída.</span><span class="sxs-lookup"><span data-stu-id="414e6-182">Depending on the size of your customer data, it may take several minutes for an enrichment run to complete.</span></span>

> [!TIP]
> <span data-ttu-id="414e6-183">Existem [seis tipos de status](system.md#status-types) para tarefas/processos.</span><span class="sxs-lookup"><span data-stu-id="414e6-183">There are [six types of status](system.md#status-types) for tasks/processes.</span></span> <span data-ttu-id="414e6-184">Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).</span><span class="sxs-lookup"><span data-stu-id="414e6-184">Additionally, most processes [depend on other downstream processes](system.md#refresh-policies).</span></span> <span data-ttu-id="414e6-185">Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho.</span><span class="sxs-lookup"><span data-stu-id="414e6-185">You can select the status of a process to see details on the progress of the entire job.</span></span> <span data-ttu-id="414e6-186">Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.</span><span class="sxs-lookup"><span data-stu-id="414e6-186">After selecting **See details** for one of the job's tasks, you find additional information: processing time, the last processing date, and all errors and warnings associated with the task.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="414e6-187">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="414e6-187">Enrichment results</span></span>

<span data-ttu-id="414e6-188">Depois de executar o processo de enriquecimento, vá para **Meus enriquecimentos** para revisar o número total de clientes enriquecidos e um detalhamento de marcas ou interesses nos perfis de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="414e6-188">After running the enrichment process, go to **My enrichments** to review the total number of enriched customers and a breakdown of brands or interests in the enriched customer profiles.</span></span>

:::image type="content" source="media/my-enrichments.png" alt-text="Visualização dos resultados após a execução do processo de enriquecimento":::

<span data-ttu-id="414e6-190">Revise os dados enriquecidos selecionando **Exibir Dados enriquecidos** no gráfico.</span><span class="sxs-lookup"><span data-stu-id="414e6-190">Review the enriched data by selecting **View enriched data** in the chart.</span></span> <span data-ttu-id="414e6-191">Dados enriquecidos para marcas vão para a entidade **BrandAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="414e6-191">Enriched data for brands goes to the **BrandAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="414e6-192">Os dados para interesses estão na entidade **InterestAffinityFromMicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="414e6-192">Data for interests is in the **InterestAffinityFromMicrosoft** entity.</span></span> <span data-ttu-id="414e6-193">Você também encontrará essas entidades listadas no grupo **Enriquecimento** em **Dados** > **Entidades**.</span><span class="sxs-lookup"><span data-stu-id="414e6-193">You'll also find these entities listed in the **Enrichment** group in **Data** > **Entities**.</span></span>

## <a name="see-enrichment-data-on-the-customer-card"></a><span data-ttu-id="414e6-194">Veja dados de enriquecimento no cartão do cliente</span><span class="sxs-lookup"><span data-stu-id="414e6-194">See enrichment data on the customer card</span></span>

<span data-ttu-id="414e6-195">As afinidades de marca e interesse também podem ser visualizadas em cartões de clientes individuais.</span><span class="sxs-lookup"><span data-stu-id="414e6-195">Brand and interest affinities can also be viewed on individual customer cards.</span></span> <span data-ttu-id="414e6-196">Vá para **Clientes** e selecione um perfil do cliente.</span><span class="sxs-lookup"><span data-stu-id="414e6-196">Go to **Customers** and select a customer profile.</span></span> <span data-ttu-id="414e6-197">No cartão do cliente, você encontrará gráficos das marcas ou interesses pelos quais as pessoas no perfil demográfico desse cliente têm afinidade.</span><span class="sxs-lookup"><span data-stu-id="414e6-197">In the customer card, you'll find charts for the brands or interests that people in that customer's demographic profile have affinity for.</span></span>

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos":::

## <a name="next-steps"></a><span data-ttu-id="414e6-199">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="414e6-199">Next steps</span></span>

<span data-ttu-id="414e6-200">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="414e6-200">Build on top of your enriched customer data.</span></span> <span data-ttu-id="414e6-201">Crie [Segmentos](segments.md), [Medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="414e6-201">Create [Segments](segments.md), [Measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
