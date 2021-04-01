---
title: Ingestão de dados em tempo real e limitações
description: Informações gerais sobre recursos em tempo real em percepções de público.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: 3c84cfe7441eb026c1fd45eda1f72421388d01d7
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598555"
---
# <a name="real-time-data-ingestion-preview"></a><span data-ttu-id="9bef1-103">Ingestão de dados em tempo real (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="9bef1-103">Real-time data ingestion (preview)</span></span>

<span data-ttu-id="9bef1-104">A funcionalidade quase em tempo real permite ver, em segundos, as últimas interações que seus clientes tiveram com seus produtos ou serviços.</span><span class="sxs-lookup"><span data-stu-id="9bef1-104">The near real-time functionality lets you see, within seconds, the latest interactions that your customers have made with your products or services.</span></span>

<span data-ttu-id="9bef1-105">[Atualizações programadas](system.md#schedule-tab) incluem um grande número de registros e várias operações complexas.</span><span class="sxs-lookup"><span data-stu-id="9bef1-105">[Scheduled refreshes](system.md#schedule-tab) include large numbers of records and several complex operations.</span></span> <span data-ttu-id="9bef1-106">Primeiro, os dados são extraídos de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9bef1-106">First, data is pulled from the data source.</span></span> <span data-ttu-id="9bef1-107">Em seguida, os dados são unificados e depois enriquecidos com informações adicionais.</span><span class="sxs-lookup"><span data-stu-id="9bef1-107">Next, the data is unified, and then enriched with additional information.</span></span> <span data-ttu-id="9bef1-108">Cada execução desse processo pode levar de minutos a horas.</span><span class="sxs-lookup"><span data-stu-id="9bef1-108">Every run of this process can take minutes to hours.</span></span>

<span data-ttu-id="9bef1-109">A funcionalidade em tempo real fornece dados imediatamente para consumo, até que a atualização programada subsequente extraia esses dados de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9bef1-109">The real-time functionality provides data immediately for consumption, until the subsequent scheduled refresh pulls this data from the data source.</span></span>

<span data-ttu-id="9bef1-110">As atualizações em tempo real têm um horário de expiração após o qual não substituem mais o valor da fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="9bef1-110">Real-time updates have an expiration time after which they no longer override the value from the data source:</span></span>

- <span data-ttu-id="9bef1-111">As atualizações de perfil serão mantidas por 4 horas</span><span class="sxs-lookup"><span data-stu-id="9bef1-111">Profile updates will be kept for 4 hours</span></span>
- <span data-ttu-id="9bef1-112">As atividades serão mantidas por 30 dias</span><span class="sxs-lookup"><span data-stu-id="9bef1-112">Activities will be kept for 30 days</span></span>

<span data-ttu-id="9bef1-113">Esses valores são parâmetros de chamada à API que você pode alterar.</span><span class="sxs-lookup"><span data-stu-id="9bef1-113">These values are API call parameters that you can change.</span></span> <span data-ttu-id="9bef1-114">Eles visam garantir que seus dados de origem continuem sendo sua fonte de referência.</span><span class="sxs-lookup"><span data-stu-id="9bef1-114">They aim to ensure that your source data remains your source of truth.</span></span> <span data-ttu-id="9bef1-115">Se você deseja que as atualizações em tempo real sejam incluídas por mais tempo, você precisa adicioná-las a um fonte de dados para que sejam retiradas durante a próxima atualização programada.</span><span class="sxs-lookup"><span data-stu-id="9bef1-115">If you want real-time updates to be included for longer, you need to add them to a data source so they get pulled during the next scheduled refresh.</span></span>

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a><span data-ttu-id="9bef1-116">Atualização em tempo real dos campos do perfil de cliente unificado</span><span class="sxs-lookup"><span data-stu-id="9bef1-116">Real-time update of the unified customer profile fields</span></span>

<span data-ttu-id="9bef1-117">Os perfis atualizados serão exibidos na visualização do cartão do cliente ou em qualquer outra visualização em alguns segundos.</span><span class="sxs-lookup"><span data-stu-id="9bef1-117">Updated profiles will show in the customer card view, or any other visualization, within a few seconds.</span></span>

<span data-ttu-id="9bef1-118">Como as operações em tempo real ocorrem após a unificação de dados, elas se aplicam apenas aos perfis de cliente unificados.</span><span class="sxs-lookup"><span data-stu-id="9bef1-118">Because real-time operations take place after the data unification has happened, they only apply to the unified customer profiles.</span></span> <span data-ttu-id="9bef1-119">Consequentemente, as alterações de perfil em tempo real não atualizarão medidas, associação de segmentos ou aprimoramentos.</span><span class="sxs-lookup"><span data-stu-id="9bef1-119">Consequently, real-time profile changes will not update measures, segment membership, or enrichments.</span></span>

### <a name="limitations"></a><span data-ttu-id="9bef1-120">Limitações</span><span class="sxs-lookup"><span data-stu-id="9bef1-120">Limitations</span></span>

- <span data-ttu-id="9bef1-121">Perfis de clientes podem ser atualizados, mas não criados ou excluídos.</span><span class="sxs-lookup"><span data-stu-id="9bef1-121">Customer profiles can be updated, but not created or deleted.</span></span>
- <span data-ttu-id="9bef1-122">Exportar atualizações em tempo real para sistemas externos, como o Power BI, não é possível no momento.</span><span class="sxs-lookup"><span data-stu-id="9bef1-122">Exporting real-time updates to external systems, like Power BI, is not possible at the moment.</span></span>

## <a name="real-time-creation-of-activities"></a><span data-ttu-id="9bef1-123">Criação de atividades em tempo real</span><span class="sxs-lookup"><span data-stu-id="9bef1-123">Real-time creation of activities</span></span>

<span data-ttu-id="9bef1-124">A API em tempo real permite publicar uma nova atividade de seu sistema de origem (um registro de origem individual) para um perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="9bef1-124">The real-time API lets you publish a new activity from your source system (an individual source record) to a unified customer profile.</span></span> <span data-ttu-id="9bef1-125">A nova atividade estará disponível como uma atividade unificada na linha do tempo desse perfil de cliente unificado em segundos.</span><span class="sxs-lookup"><span data-stu-id="9bef1-125">The new activity will be available as a unified activity in that unified customer profile's timeline within seconds.</span></span> <span data-ttu-id="9bef1-126">Você pode ver a linha do tempo na visualização do cartão do cliente ou qualquer outra integração de linha do tempo que você configurou.</span><span class="sxs-lookup"><span data-stu-id="9bef1-126">You can see the timeline in the customer card view or any other timeline integration you configured.</span></span>

> [!NOTE]
>
> - <span data-ttu-id="9bef1-127">Atividades são imutáveis.</span><span class="sxs-lookup"><span data-stu-id="9bef1-127">Activities are immutable.</span></span> <span data-ttu-id="9bef1-128">Elas não mudam depois de criadas.</span><span class="sxs-lookup"><span data-stu-id="9bef1-128">They don't change once created.</span></span>
> - <span data-ttu-id="9bef1-129">Atualmente, segmentos e medidas não são atualizados com base na nova atividade.</span><span class="sxs-lookup"><span data-stu-id="9bef1-129">Currently, segments and measures won't update based on the new activity.</span></span>
> - <span data-ttu-id="9bef1-130">As atividades adicionadas apenas por meio da API em tempo real não fazem parte das exportações e não serão exibidas no Power BI.</span><span class="sxs-lookup"><span data-stu-id="9bef1-130">Activities added only through the real-time API are not part of exports and won't show up in PowerBI.</span></span>

<span data-ttu-id="9bef1-131">Existem duas maneiras de se conectar à API em tempo real:</span><span class="sxs-lookup"><span data-stu-id="9bef1-131">There are two ways to connect to the real-time API:</span></span>

- <span data-ttu-id="9bef1-132">[indiretamente](#connect-via-the-dynamics-365-customer-insights-connector), usando o [conector do Dynamics 365 Customer Insights](/connectors/customerinsights/)</span><span class="sxs-lookup"><span data-stu-id="9bef1-132">[indirectly](#connect-via-the-dynamics-365-customer-insights-connector), using the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/)</span></span>
- <span data-ttu-id="9bef1-133">[diretamente](#connect-directly-to-the-real-time-api), com código</span><span class="sxs-lookup"><span data-stu-id="9bef1-133">[directly](#connect-directly-to-the-real-time-api), with code</span></span>

<span data-ttu-id="9bef1-134">As duas maneiras compartilham os seguintes pré-requisitos:</span><span class="sxs-lookup"><span data-stu-id="9bef1-134">Both ways share the following prerequisites:</span></span>

- <span data-ttu-id="9bef1-135">Um ambiente do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9bef1-135">A Customer Insights environment</span></span>
- <span data-ttu-id="9bef1-136">Perfis de cliente unificados</span><span class="sxs-lookup"><span data-stu-id="9bef1-136">Unified customer profiles</span></span>
- <span data-ttu-id="9bef1-137">Atividades configuradas e executadas</span><span class="sxs-lookup"><span data-stu-id="9bef1-137">Activities configured and run</span></span>
- <span data-ttu-id="9bef1-138">Permissões de Colaborador ou Administrador para autenticar sua conta</span><span class="sxs-lookup"><span data-stu-id="9bef1-138">Contributor or Administrator permissions to authenticate your account</span></span>

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a><span data-ttu-id="9bef1-139">Conectar-se por meio do conector do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="9bef1-139">Connect via the Dynamics 365 Customer Insights connector</span></span>

<span data-ttu-id="9bef1-140">A API em tempo real pode ingerir dados de um conector dedicado do Power Platform, o [conector do Dynamics 365 Customer Insights](/connectors/customerinsights/), sem a necessidade de escrever e implantar nenhum código.</span><span class="sxs-lookup"><span data-stu-id="9bef1-140">The real-time API can ingest data from a dedicated Power Platform connector, the [Dynamics 365 Customer Insights connector](/connectors/customerinsights/), without the need to write and deploy any code.</span></span>    
<span data-ttu-id="9bef1-141">O conector pode executar as mesmas ações em tempo real que a API.</span><span class="sxs-lookup"><span data-stu-id="9bef1-141">The connector can do the same real-time actions as the API.</span></span> <span data-ttu-id="9bef1-142">Você precisa de uma licença válida para conectores premium.</span><span class="sxs-lookup"><span data-stu-id="9bef1-142">You need a valid license for premium connectors.</span></span> <span data-ttu-id="9bef1-143">Para obter mais informações, consulte [Perguntas frequentes sobre licenciamento do Power Apps e do Power Automate](/power-platform/admin/powerapps-flow-licensing-faq).</span><span class="sxs-lookup"><span data-stu-id="9bef1-143">For more information, see [Power Apps and Power Automate licensing FAQs](/power-platform/admin/powerapps-flow-licensing-faq).</span></span>

- <span data-ttu-id="9bef1-144">Power Platform [Power Apps e/ou Power Automate](/connectors/)</span><span class="sxs-lookup"><span data-stu-id="9bef1-144">Power Platform [Power Apps and/or Power Automate](/connectors/)</span></span>
- <span data-ttu-id="9bef1-145">[Aplicativos Lógicos](/azure/connectors/apis-list) do Azure</span><span class="sxs-lookup"><span data-stu-id="9bef1-145">Azure [Logic Apps](/azure/connectors/apis-list)</span></span>

<span data-ttu-id="9bef1-146">Para obter detalhes sobre a criação de fluxos, consulte a [documentação do Power Automate](/power-automate/).</span><span class="sxs-lookup"><span data-stu-id="9bef1-146">For details about creating flows, see the [Power Automate documentation](/power-automate/).</span></span>

## <a name="connect-directly-to-the-real-time-api"></a><span data-ttu-id="9bef1-147">Conectar-se diretamente à API em tempo real</span><span class="sxs-lookup"><span data-stu-id="9bef1-147">Connect directly to the real-time API</span></span>

<span data-ttu-id="9bef1-148">Você pode usar os recursos em tempo real criando seu próprio pipeline e conectando-se diretamente à API em tempo real.</span><span class="sxs-lookup"><span data-stu-id="9bef1-148">You can use the real-time capabilities by building your own pipeline and connecting directly to the real-time API.</span></span>    
<span data-ttu-id="9bef1-149">Você pode postar uma atividade no formato do seu sistema de origem ou no formato UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="9bef1-149">You can post an activity in the format of your source system or in the UnifiedActivity format.</span></span> <span data-ttu-id="9bef1-150">Obtenha o formato fazendo uma chamada à API para /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span><span class="sxs-lookup"><span data-stu-id="9bef1-150">Get the format by making an API call to /api/instances/{instanceId}/manage/entities/UnifiedActivity.</span></span>

<span data-ttu-id="9bef1-151">Os detalhes desta API, incluindo parâmetros e respostas, podem ser encontrados na seção **EntityData** na referência [APIs do Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="9bef1-151">Details of this API, including parameters and responses, can be found in the **EntityData** section on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="9bef1-152">Para obter mais informações, consulte [Trabalhar com APIs do Customer Insights](apis.md).</span><span class="sxs-lookup"><span data-stu-id="9bef1-152">For more information, see [Work with Customer Insights APIs](apis.md).</span></span>

## <a name="understand-your-real-time-usage-with-telemetry"></a><span data-ttu-id="9bef1-153">Entenda seu uso em tempo real com telemetria</span><span class="sxs-lookup"><span data-stu-id="9bef1-153">Understand your real-time usage with telemetry</span></span>

<span data-ttu-id="9bef1-154">Obtenha uma visão geral do volume de solicitações para a API em tempo real e informações sobre os problemas que o sistema pode encontrar.</span><span class="sxs-lookup"><span data-stu-id="9bef1-154">Get an overview of the volume of requests to the real-time API and information about issues the system may encounter.</span></span> <span data-ttu-id="9bef1-155">Você pode [acessar a telemetria em tempo real](system.md#api-usage-tab).</span><span class="sxs-lookup"><span data-stu-id="9bef1-155">You can [access the real-time telemetry](system.md#api-usage-tab).</span></span> 


[!INCLUDE[footer-include](../includes/footer-banner.md)]