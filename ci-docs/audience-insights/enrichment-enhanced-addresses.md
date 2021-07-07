---
title: Enriquecimento de aprimoramento de endereço
description: Enriqueça e normalize as informações de endereço de perfis de clientes com modelos da Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305418"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a><span data-ttu-id="ed02d-103">Enriquecimento de perfis de clientes com endereços aprimorados</span><span class="sxs-lookup"><span data-stu-id="ed02d-103">Enrichment of customer profiles with enhanced addresses</span></span>

<span data-ttu-id="ed02d-104">Os endereços dos seus dados podem ser não estruturados, incompletos ou incorretos.</span><span class="sxs-lookup"><span data-stu-id="ed02d-104">Addresses in your data can be unstructured, incomplete, or incorrect.</span></span> <span data-ttu-id="ed02d-105">Use os modelos da Microsoft para normalizar e enriquecer seus endereços no [formato de Common Data Model](/common-data-model/schema/core/applicationcommon/address) para ter melhor precisão e insights.</span><span class="sxs-lookup"><span data-stu-id="ed02d-105">Use Microsoft's models to normalize and enrich your addresses into the [Common Data Model format](/common-data-model/schema/core/applicationcommon/address) for better accuracy and insights.</span></span>

## <a name="how-we-enhance-addresses"></a><span data-ttu-id="ed02d-106">Como aprimoramos os endereços</span><span class="sxs-lookup"><span data-stu-id="ed02d-106">How we enhance addresses</span></span>

<span data-ttu-id="ed02d-107">Nosso modelo passa por um processo de duas etapas para aprimorar endereços.</span><span class="sxs-lookup"><span data-stu-id="ed02d-107">Our model goes through a two-step process to enhance an address.</span></span> <span data-ttu-id="ed02d-108">Primeiro, ele analisa o endereço para identificar seus componentes e os coloca em um formato estruturado.</span><span class="sxs-lookup"><span data-stu-id="ed02d-108">First, it parses the address to identify its components and puts them into a structured format.</span></span> <span data-ttu-id="ed02d-109">Em seguida, usamos a IA para corrigir, completar e padronizar os valores no endereço.</span><span class="sxs-lookup"><span data-stu-id="ed02d-109">Then, we use AI to correct, complete, and standardize the values in the address.</span></span>

### <a name="example"></a><span data-ttu-id="ed02d-110">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ed02d-110">Example</span></span>

<span data-ttu-id="ed02d-111">As informações de endereço podem estar em um formato não padrão e conter erros de ortografia.</span><span class="sxs-lookup"><span data-stu-id="ed02d-111">Address information might be in a nonstandard format and contain spelling errors.</span></span> <span data-ttu-id="ed02d-112">O modelo pode corrigir esses problemas e criar endereços consistentes em perfis unificados de clientes.</span><span class="sxs-lookup"><span data-stu-id="ed02d-112">The model can fix these issues and create consistent addresses in unified customer profiles.</span></span>

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a><span data-ttu-id="ed02d-113">Limitações</span><span class="sxs-lookup"><span data-stu-id="ed02d-113">Limitations</span></span>

<span data-ttu-id="ed02d-114">Os endereços avançados só funcionam com os valores que já existem nos dados de endereço processados.</span><span class="sxs-lookup"><span data-stu-id="ed02d-114">Enhanced addresses only works with the values that already exist in your ingested address data.</span></span> <span data-ttu-id="ed02d-115">O que o modelo não faz:</span><span class="sxs-lookup"><span data-stu-id="ed02d-115">The model doesn't:</span></span> 

1. <span data-ttu-id="ed02d-116">Verificar se o endereço é válido.</span><span class="sxs-lookup"><span data-stu-id="ed02d-116">Verify if the address is a valid address.</span></span>
2. <span data-ttu-id="ed02d-117">Verificar se algum dos valores, como CEPs ou nomes de ruas, é válido.</span><span class="sxs-lookup"><span data-stu-id="ed02d-117">Verify if any of the values, such as ZIP codes or street names, are valid.</span></span>
3. <span data-ttu-id="ed02d-118">Alterar valores que não reconhece.</span><span class="sxs-lookup"><span data-stu-id="ed02d-118">Change values it doesn't recognize.</span></span>

<span data-ttu-id="ed02d-119">O modelo usa técnicas com base em aprendizado de máquina para aprimorar os endereços.</span><span class="sxs-lookup"><span data-stu-id="ed02d-119">The model uses machine learning-based techniques to enhance addresses.</span></span> <span data-ttu-id="ed02d-120">Embora apliquemos um limite de alta confiança para quando o modelo altera um valor de entrada, como acontece com qualquer modelo baseado em aprendizado de máquina, a precisão de 100% não é garantida.</span><span class="sxs-lookup"><span data-stu-id="ed02d-120">While we apply a high confidence threshold for when the model changes an input value, as with any machine learning-based model, 100 percent accuracy is not guaranteed.</span></span>

## <a name="supported-countries-or-regions"></a><span data-ttu-id="ed02d-121">Países ou regiões com suporte</span><span class="sxs-lookup"><span data-stu-id="ed02d-121">Supported countries or regions</span></span>

<span data-ttu-id="ed02d-122">Atualmente, damos suporte a endereços de enriquecimento nestes países ou regiões:</span><span class="sxs-lookup"><span data-stu-id="ed02d-122">We currently support enriching addresses in these countries or regions:</span></span> 

- <span data-ttu-id="ed02d-123">Austrália</span><span class="sxs-lookup"><span data-stu-id="ed02d-123">Australia</span></span>
- <span data-ttu-id="ed02d-124">Canadá</span><span class="sxs-lookup"><span data-stu-id="ed02d-124">Canada</span></span>
- <span data-ttu-id="ed02d-125">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="ed02d-125">United Kingdom</span></span>
- <span data-ttu-id="ed02d-126">Estados Unidos</span><span class="sxs-lookup"><span data-stu-id="ed02d-126">United States</span></span>

<span data-ttu-id="ed02d-127">Os endereços devem conter um valor de país/região.</span><span class="sxs-lookup"><span data-stu-id="ed02d-127">Addresses must contain a country/region value.</span></span> <span data-ttu-id="ed02d-128">Não processamos endereços para países ou regiões que não têm suporte e endereços que não tenham país ou região fornecidos.</span><span class="sxs-lookup"><span data-stu-id="ed02d-128">We don't process addresses for countries or regions that aren't supported and addresses that have no country or region provided.</span></span>

## <a name="configure-the-enrichment"></a><span data-ttu-id="ed02d-129">Configurar o enriquecimento</span><span class="sxs-lookup"><span data-stu-id="ed02d-129">Configure the enrichment</span></span>

1. <span data-ttu-id="ed02d-130">Vá para **Dados** > **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="ed02d-130">Go to **Data** > **Enrichment**.</span></span>

1. <span data-ttu-id="ed02d-131">Selecione **Enriquecer meus dados** no bloco **Endereços aprimorados**.</span><span class="sxs-lookup"><span data-stu-id="ed02d-131">Select **Enrich my data** on the **Enhanced addresses** tile.</span></span>

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de tela do bloco Endereços aprimorados.":::

1. <span data-ttu-id="ed02d-133">Selecione os **Conjunto de dados do cliente** e escolha a entidade que contém os endereços que deseja enriquecer.</span><span class="sxs-lookup"><span data-stu-id="ed02d-133">Select the **Customer data set** and choose the entity containing the addresses you want to enrich.</span></span> <span data-ttu-id="ed02d-134">Você pode selecionar a entidade *Cliente* para enriquecer endereços em todos os seus perfis de clientes ou selecione uma entidade de segmento para enriquecer endereços somente em perfis de clientes contidos naquele segmento.</span><span class="sxs-lookup"><span data-stu-id="ed02d-134">You can select the *Customer* entity to enrich addresses in all your customer profiles or select a segment entity to enrich addresses only in customer profiles contained in that segment.</span></span>

1. <span data-ttu-id="ed02d-135">Selecione como os endereços serão formatados em seu conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="ed02d-135">Select how addresses are formatted in your data set.</span></span> <span data-ttu-id="ed02d-136">Escolha **Endereço com um único atributo** se os endereços em seus dados usarem um único campo.</span><span class="sxs-lookup"><span data-stu-id="ed02d-136">Choose **Single-attribute address** if addresses in your data use a single field.</span></span> <span data-ttu-id="ed02d-137">Escolha **Endereço com vários atributos** se os endereços em seus dados usarem mais de um campo de dados.</span><span class="sxs-lookup"><span data-stu-id="ed02d-137">Choose **Multiple-attribute address** if addresses in your data use more than one data field.</span></span>

   > [!NOTE]
   > <span data-ttu-id="ed02d-138">País/região é obrigatório em endereços de atributo único e de vários atributos.</span><span class="sxs-lookup"><span data-stu-id="ed02d-138">Country/Region is mandatory in both single-attribute and multiple-attribute addresses.</span></span> <span data-ttu-id="ed02d-139">Endereços que não contiverem valores de país/região válidos ou com suporte não serão enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="ed02d-139">Addresses that don't contain valid or supported country/region values won't be enriched.</span></span>

1.  <span data-ttu-id="ed02d-140">Mapeie os campos de endereço da sua entidade de cliente unificada.</span><span class="sxs-lookup"><span data-stu-id="ed02d-140">Map the address fields from your unified customer entity.</span></span>

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Página de mapeamento de campo de endereço aprimorado.":::

1. <span data-ttu-id="ed02d-142">Selecione **Avançar** para concluir o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="ed02d-142">Select **Next** to complete the field mapping.</span></span>

1. <span data-ttu-id="ed02d-143">Forneça um nome para o enriquecimento para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="ed02d-143">Provide a name for the enrichment and the output entity.</span></span>

1. <span data-ttu-id="ed02d-144">Selecione **Salvar enriquecimento** depois de revisar suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="ed02d-144">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="enrichment-results"></a><span data-ttu-id="ed02d-145">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="ed02d-145">Enrichment results</span></span>

<span data-ttu-id="ed02d-146">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="ed02d-146">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="ed02d-147">Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="ed02d-147">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="ed02d-148">A duração do processamento depende do tamanho dos dados do cliente.</span><span class="sxs-lookup"><span data-stu-id="ed02d-148">The processing time depends on the size of your customer data.</span></span>

<span data-ttu-id="ed02d-149">Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="ed02d-149">After the enrichment process completes, you can review the newly enriched customer profiles data under **My enrichments**.</span></span> <span data-ttu-id="ed02d-150">Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="ed02d-150">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="ed02d-151">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="ed02d-151">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ed02d-152">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="ed02d-152">Next steps</span></span>

<span data-ttu-id="ed02d-153">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="ed02d-153">Build on top of your enriched customer data.</span></span> <span data-ttu-id="ed02d-154">Crie [segmentos](segments.md) e [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="ed02d-154">Create [segments](segments.md) and [measures](measures.md), and even [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
