---
title: Unificação de dados
description: Saiba como unificar os dados ingeridos.
ms.date: 04/16/2020
ms.reviewer: adkuppa
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 24321e9e11f9fd4e800526673726e5146ed33674
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405017"
---
# <a name="data-unification"></a><span data-ttu-id="3c80e-103">Unificação de dados</span><span class="sxs-lookup"><span data-stu-id="3c80e-103">Data unification</span></span>

<span data-ttu-id="3c80e-104">Após a [configuração das fontes de dados](data-sources.md), você pode unificar os dados.</span><span class="sxs-lookup"><span data-stu-id="3c80e-104">After [setting up the data sources](data-sources.md), you can unify the data.</span></span> <span data-ttu-id="3c80e-105">A unificação de dados inclui três etapas: **Mapear**, **Corresponder** e **Mesclar**.</span><span class="sxs-lookup"><span data-stu-id="3c80e-105">Data unification includes three steps: **Map**, **Match**, and **Merge**.</span></span>

<span data-ttu-id="3c80e-106">O processo de unificação de dados permite unificar fontes de dados antes díspares em um único conjunto de dados mestre que fornece uma visão unificada de seus clientes.</span><span class="sxs-lookup"><span data-stu-id="3c80e-106">The data unification process lets you unify once-disparate data sources into a single master dataset that provides a unified view of your customers.</span></span> <span data-ttu-id="3c80e-107">Os estágios de unificação são obrigatórios e executados na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="3c80e-107">Unification stages are mandatory, and performed in the following order:</span></span>

1. [<span data-ttu-id="3c80e-108">Mapa</span><span class="sxs-lookup"><span data-stu-id="3c80e-108">Map</span></span>](map-entities.md)
2. [<span data-ttu-id="3c80e-109">Corresponder</span><span class="sxs-lookup"><span data-stu-id="3c80e-109">Match</span></span>](match-entities.md)
3. [<span data-ttu-id="3c80e-110">Mesclar</span><span class="sxs-lookup"><span data-stu-id="3c80e-110">Merge</span></span>](merge-entities.md)

<span data-ttu-id="3c80e-111">Depois de concluir a unificação de dados, como opção você pode</span><span class="sxs-lookup"><span data-stu-id="3c80e-111">After completing the data unification, you can optionally</span></span>

- <span data-ttu-id="3c80e-112">[configurar relacionamentos entre entidades](relationships.md) para criar segmentos sofisticados</span><span class="sxs-lookup"><span data-stu-id="3c80e-112">[set up relationships between entities](relationships.md) to create sophisticated segments</span></span>
- <span data-ttu-id="3c80e-113">[enriquecer seus dados](enrichment-hub.md) para obter um intervalo maior de informações sobre seus clientes</span><span class="sxs-lookup"><span data-stu-id="3c80e-113">[enrich your data](enrichment-hub.md) to get a wider range of insights about your customers</span></span>
- <span data-ttu-id="3c80e-114">[definir atividades](activities.md) a partir de alguns dos atributos ingeridos</span><span class="sxs-lookup"><span data-stu-id="3c80e-114">[define activities](activities.md) from some of the ingested attributes</span></span>
