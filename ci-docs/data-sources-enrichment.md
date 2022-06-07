---
title: Enriquecimento da fonte de dados
description: Enriqueça as fontes de dados antes de passar pelo processo de unificação de dados.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: how-to
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
ms.openlocfilehash: 1225482c4bf432ed747537b2c9bec9ab0e692a51
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800267"
---
# <a name="enrichment-for-data-sources-preview"></a>Enriquecimento de fontes de dados (versão preliminar)

Use dados de fontes como a Microsoft e outros de parceiros para enriquecer os dados de clientes antes da unificação de dados. Os enriquecimentos da fonte de dados ajudam a produzir dados mais completos e de qualidade que podem ajudar a alcançar melhores resultados depois de unificar seus dados. Por exemplo, usar um formato normalizado e padronizado para endereços aumenta a qualidade dos resultados de correspondência. Para obter uma lista de enriquecimentos compatíveis, consulte as [opções de enriquecimento de fonte de dados compatíveis](#supported-data-source-enrichments).

## <a name="enrich-a-data-source"></a>Enriquecer uma fonte de dados

Você deve ter permissões de Colaborador ou Administrador para criar ou editar enriquecimentos. Para obter mais informações, consulte [Permissões](permissions.md).  

1. Acesse **Dados** > **Unificar**. Selecione a entidade que deseja enriquecer e selecione um atributo como chave primária para a entidade. Para obter mais informações, consulte a seção [Selecionar chave primária](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione as reticências verticais (&vellip;) ao lado da fonte de dados que deseja enriquecer e selecione **Enriquecer**.

   :::image type="content" source="media/data_sources_enrich_discover.png" alt-text="Página de enriquecimento de fontes de dados":::

   A guia **Descobrir** exibe as [opções de enriquecimento de fonte de dados compatíveis](#supported-data-source-enrichments).

1. Selecione **Enriquecer meus dados** para configurar um enriquecimento de fonte de dados. O nome da entidade de saída é preenchido automaticamente.

## <a name="supported-data-source-enrichments"></a>Enriquecimentos de fonte de dados compatíveis

Estes são os enriquecimentos disponíveis no momento para fontes de dados. Revise as etapas detalhadas do enriquecimento para saber como configurá-lo.

- [Endereços aprimorados](enrichment-enhanced-addresses.md)
- [Dados da empresa aprimorados](enrichment-enhanced-company-data.md)
- [Dados de identidade do LiveRamp](enrichment-liveramp.md)

## <a name="manage-existing-data-source-enrichments"></a>Gerenciar enriquecimentos de fonte de dados existentes

Acesse a guia **Meus enriquecimentos** para ver todos os enriquecimentos configurados.

Selecione o enriquecimento para ver as opções disponíveis. Você também pode selecionar as reticências verticais (&vellip;) em um item de lista para ver as opções. Se configurou vários enriquecimentos, você poderá usar a caixa de pesquisa para encontrá-los rapidamente.

Você pode exibir, editar, executar ou excluir um enriquecimento de fonte de dados. Para obter mais informações, consulte a seção [Gerenciar enriquecimentos existentes](enrichment-hub.md).
