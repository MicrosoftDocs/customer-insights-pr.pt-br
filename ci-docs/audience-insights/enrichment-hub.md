---
title: Enriquecer perfis de clientes unificados
description: Use recursos para enriquecer os dados do cliente.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 10c338b89a6f9971912d05986c105cba1221b01b
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895991"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="bfba2-103">Enriquecimento para perfis de clientes (visualização)</span><span class="sxs-lookup"><span data-stu-id="bfba2-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="bfba2-104">Use dados de fontes como a Microsoft e outros parceiros para enriquecer os dados de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="bfba2-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do hub de enriquecimento":::

<span data-ttu-id="bfba2-106">Em insights de público-alvo, acesse **Dados** > **Enriquecimento** para trabalhar com as opções de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="bfba2-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="bfba2-107">Você precisa ter permissões de Colaborador ou Administrador para criar ou editar enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="bfba2-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="bfba2-108">Para obter mais informações, consulte [Permissões](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="bfba2-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="bfba2-109">Na guia **Descobrir**, você encontrará os seguintes enriquecimentos:</span><span class="sxs-lookup"><span data-stu-id="bfba2-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="bfba2-110">[Marcas](enrichment-microsoft.md) fornecidas pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="bfba2-110">[Brands](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="bfba2-111">[Interesses](enrichment-microsoft.md) fornecidos pela Microsoft</span><span class="sxs-lookup"><span data-stu-id="bfba2-111">[Interests](enrichment-microsoft.md) provided by Microsoft</span></span>
- <span data-ttu-id="bfba2-112">[Dados de empresas](enrichment-leadspace.md) fornecidos pela Leadspace</span><span class="sxs-lookup"><span data-stu-id="bfba2-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="bfba2-113">[Dados demográficos](enrichment-experian.md) fornecidos pela Experian</span><span class="sxs-lookup"><span data-stu-id="bfba2-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="bfba2-114">[Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="bfba2-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="bfba2-115">[Dados personalizados](enrichment-SFTP-custom-import.md) via SFTP</span><span class="sxs-lookup"><span data-stu-id="bfba2-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="bfba2-116">Na guia **Meus enriquecimentos**, você pode ver os enriquecimentos configurados e editar suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="bfba2-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="bfba2-117">Gerenciar enriquecimentos existentes</span><span class="sxs-lookup"><span data-stu-id="bfba2-117">Manage existing enrichments</span></span>

<span data-ttu-id="bfba2-118">Vá para **Meus enriquecimentos** para ver todos os enriquecimentos configurados.</span><span class="sxs-lookup"><span data-stu-id="bfba2-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="bfba2-119">Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="bfba2-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="bfba2-120">Selecione um enriquecimento para ver as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bfba2-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="bfba2-121">Você também pode selecionar as reticências (...) em um item da lista para ver as opções.</span><span class="sxs-lookup"><span data-stu-id="bfba2-121">You can also select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerenciar enriquecimentos na lista de enriquecimentos":::

- <span data-ttu-id="bfba2-123">**Exibir** detalhes de enriquecimento com o número de perfis de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="bfba2-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="bfba2-124">**Editar** a configuração de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="bfba2-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="bfba2-125">**Executar** o enriquecimento para atualizar os perfis dos clientes com os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="bfba2-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="bfba2-126">**Desativar** um enriquecimento existente para impedi-lo de atualizar automaticamente a cada atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="bfba2-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="bfba2-127">Os dados da última atualização bem-sucedida continuarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="bfba2-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="bfba2-128">**Ativar** um enriquecimento inativo para reiniciar a atualização automática a cada atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="bfba2-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="bfba2-129">**Exclua** um enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="bfba2-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="bfba2-130">Você pode executar ou desativar vários enriquecimentos de uma vez, selecionando-os na lista.</span><span class="sxs-lookup"><span data-stu-id="bfba2-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="bfba2-131">As opções de exibição e edição não estão disponíveis como ação em massa e funcionam apenas para um enriquecimento de cada vez.</span><span class="sxs-lookup"><span data-stu-id="bfba2-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>

## <a name="enrichments-and-connections"></a><span data-ttu-id="bfba2-132">Enriquecimentos e conexões</span><span class="sxs-lookup"><span data-stu-id="bfba2-132">Enrichments and connections</span></span>

<span data-ttu-id="bfba2-133">Os enriquecimentos de terceiros são configurados usando [conexões](connections.md), as quais um administrador configura com credenciais e fornece consentimento para a transferências de dados.</span><span class="sxs-lookup"><span data-stu-id="bfba2-133">Third-party enrichments are configured using [connections](connections.md), which an administrator sets up with credentials and provides consent for data transfers.</span></span> <span data-ttu-id="bfba2-134">A conexão pode então ser usada pelos administradores e colaboradores para a configuração de enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="bfba2-134">The connection can be used by administrators and contributors to configure enrichments.</span></span>  

## <a name="multiple-enrichments-of-the-same-type"></a><span data-ttu-id="bfba2-135">Vários enriquecimentos do mesmo tipo</span><span class="sxs-lookup"><span data-stu-id="bfba2-135">Multiple enrichments of the same type</span></span>

<span data-ttu-id="bfba2-136">A entidade a ser enriquecida é especificada durante a configuração de enriquecimento, o que permite que você enriqueça somente um subconjunto de seus perfis.</span><span class="sxs-lookup"><span data-stu-id="bfba2-136">The entity to be enriched is specified during the enrichment configuration, which allows you to enrich only a subset of your profiles.</span></span> <span data-ttu-id="bfba2-137">Por exemplo, enriqueça os dados somente para um segmento específico.</span><span class="sxs-lookup"><span data-stu-id="bfba2-137">For exmaple, enrich data only for a specific segment.</span></span> <span data-ttu-id="bfba2-138">Você pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma conexão.</span><span class="sxs-lookup"><span data-stu-id="bfba2-138">You can configure several enrichments of the same type and reuse the same connection.</span></span> <span data-ttu-id="bfba2-139">Alguns enriquecimentos terão limites para o número de enriquecimentos do mesmo tipo que podem ser criados.</span><span class="sxs-lookup"><span data-stu-id="bfba2-139">Some enrichments will have limits to the number of enrichments of the same type that can be created.</span></span> <span data-ttu-id="bfba2-140">Os limites e o uso atual podem ser vistos na página **Enriquecimento**.</span><span class="sxs-lookup"><span data-stu-id="bfba2-140">The limits and current use can be seen on the **Enrichment** page.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
