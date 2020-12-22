---
title: Enriquecer perfis de clientes unificados
description: Use recursos para enriquecer os dados do cliente.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c25cfbf3808fc1534b54d2d834f1c63ff4c9fe0a
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667080"
---
# <a name="enrichment-for-customer-profiles-preview"></a><span data-ttu-id="505fc-103">Enriquecimento para perfis de clientes (visualização)</span><span class="sxs-lookup"><span data-stu-id="505fc-103">Enrichment for customer profiles (preview)</span></span>

<span data-ttu-id="505fc-104">Use dados de fontes como a Microsoft e outros parceiros para enriquecer os dados de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="505fc-104">Use data from sources like Microsoft and other partners to enrich your customer data.</span></span>

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do hub de enriquecimento":::

<span data-ttu-id="505fc-106">Em insights de público-alvo, acesse **Dados** > **Enriquecimento** para trabalhar com as opções de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="505fc-106">In audience insights, go to **Data** > **Enrichment** to work with enrichment options.</span></span>    
<span data-ttu-id="505fc-107">Você precisa ter permissões de Colaborador ou Administrador para criar ou editar enriquecimentos.</span><span class="sxs-lookup"><span data-stu-id="505fc-107">You need to have Contributor or Administrator permissions to create or edit enrichments.</span></span> <span data-ttu-id="505fc-108">Para obter mais informações, consulte [Permissões](permissions.md).</span><span class="sxs-lookup"><span data-stu-id="505fc-108">For more information, see [Permissions](permissions.md).</span></span>

<span data-ttu-id="505fc-109">Na guia **Descobrir**, você encontrará os seguintes enriquecimentos:</span><span class="sxs-lookup"><span data-stu-id="505fc-109">On the **Discover** tab, you'll find the following enrichments:</span></span>

- <span data-ttu-id="505fc-110">[Marcas](enrichment-microsoft-graph.md) fornecidas pelo Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="505fc-110">[Brands](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="505fc-111">[Interesses](enrichment-microsoft-graph.md) fornecidos pelo Microsoft Graph</span><span class="sxs-lookup"><span data-stu-id="505fc-111">[Interests](enrichment-microsoft-graph.md) provided by Microsoft Graph</span></span>
- <span data-ttu-id="505fc-112">[Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace</span><span class="sxs-lookup"><span data-stu-id="505fc-112">[Company data](enrichment-leadspace.md) provided by Leadspace</span></span>
- <span data-ttu-id="505fc-113">[Dados demográficos](enrichment-experian.md) fornecidos pela Experian</span><span class="sxs-lookup"><span data-stu-id="505fc-113">[Demographics](enrichment-experian.md) provided by Experian</span></span>
- <span data-ttu-id="505fc-114">[Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies</span><span class="sxs-lookup"><span data-stu-id="505fc-114">[Location data](enrichment-here.md) provided by HERE Technologies</span></span>
- <span data-ttu-id="505fc-115">[Dados personalizados](enrichment-SFTP-custom-import.md) via SFTP</span><span class="sxs-lookup"><span data-stu-id="505fc-115">[Custom data](enrichment-SFTP-custom-import.md) through Secure File Transfer Protocol (SFTP)</span></span>

<span data-ttu-id="505fc-116">Na guia **Meus enriquecimentos**, você pode ver os enriquecimentos configurados e editar suas propriedades.</span><span class="sxs-lookup"><span data-stu-id="505fc-116">On the **My enrichments** tab, you can see the enrichments you've configured and edit their properties.</span></span>

## <a name="manage-existing-enrichments"></a><span data-ttu-id="505fc-117">Gerenciar enriquecimentos existentes</span><span class="sxs-lookup"><span data-stu-id="505fc-117">Manage existing enrichments</span></span>

<span data-ttu-id="505fc-118">Vá para **Meus enriquecimentos** para ver todos os enriquecimentos configurados.</span><span class="sxs-lookup"><span data-stu-id="505fc-118">Go to the **My enrichments** to see all configured enrichments.</span></span> <span data-ttu-id="505fc-119">Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="505fc-119">Each enrichment is represented as a row that includes additional information about the enrichment.</span></span>

<span data-ttu-id="505fc-120">Selecione um enriquecimento para ver as opções disponíveis.</span><span class="sxs-lookup"><span data-stu-id="505fc-120">Select an enrichment to see the available options.</span></span> <span data-ttu-id="505fc-121">Como alternativa, você pode selecionar as reticências (...) em um item da lista para ver as opções.</span><span class="sxs-lookup"><span data-stu-id="505fc-121">Alternatively, you can select the ellipsis (...) on a list item to see the options.</span></span>

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerenciar enriquecimentos na lista de enriquecimentos":::

- <span data-ttu-id="505fc-123">**Exibir** detalhes de enriquecimento com o número de perfis de clientes enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="505fc-123">**View** enrichment details with the number of enriched customer profiles.</span></span>
- <span data-ttu-id="505fc-124">**Editar** a configuração de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="505fc-124">**Edit** the enrichment configuration.</span></span>
- <span data-ttu-id="505fc-125">**Executar** o enriquecimento para atualizar os perfis dos clientes com os dados mais recentes.</span><span class="sxs-lookup"><span data-stu-id="505fc-125">**Run** the enrichment to update customer profiles with the latest data.</span></span>
- <span data-ttu-id="505fc-126">**Desativar** um enriquecimento existente para impedi-lo de atualizar automaticamente a cada atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="505fc-126">**Deactivate** an existing enrichment to stop it from refreshing automatically with every scheduled refresh.</span></span> <span data-ttu-id="505fc-127">Os dados da última atualização bem-sucedida continuarão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="505fc-127">Data from the last successful refresh will continue to be available.</span></span> <span data-ttu-id="505fc-128">**Ativar** um enriquecimento inativo para reiniciar a atualização automática a cada atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="505fc-128">**Activate** an inactive enrichment to restart automatic refreshing with every scheduled refresh.</span></span>
- <span data-ttu-id="505fc-129">**Exclua** um enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="505fc-129">**Delete** an enrichment.</span></span>

<span data-ttu-id="505fc-130">Você pode executar ou desativar vários enriquecimentos de uma vez, selecionando-os na lista.</span><span class="sxs-lookup"><span data-stu-id="505fc-130">You can run or deactivate multiple enrichments at once by selecting them in the list.</span></span> <span data-ttu-id="505fc-131">As opções de exibição e edição não estão disponíveis como ação em massa e funcionam apenas para um enriquecimento de cada vez.</span><span class="sxs-lookup"><span data-stu-id="505fc-131">View and edit options aren't available as bulk action and only work for one enrichment at a time.</span></span>
