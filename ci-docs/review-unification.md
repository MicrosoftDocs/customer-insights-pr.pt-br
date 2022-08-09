---
title: Revisar a unificação de dados
description: Revise as etapas da unificação de dados, crie perfis de cliente unificados e revise os resultados
ms.date: 06/02/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: adkuppa
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: 20728ffaef9bb705410b3ac22d19868ffd5d1243
ms.sourcegitcommit: 3c5b0b40b2b45e420015bbdd228ce0e610245e6f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/12/2022
ms.locfileid: "9139556"
---
# <a name="review-data-unification"></a>Revisar a unificação de dados

Esta última etapa do processo de unificação mostra um resumo das etapas do processo e oferece a oportunidade de fazer alterações antes de criar o perfil unificado.

:::image type="content" source="media/m3_review.png" alt-text="Captura de tela de Revisar e Criar perfis de cliente.":::

## <a name="review-the-data-unification-steps"></a>Revisar as etapas da unificação de dados

1. Selecione **Editar** em qualquer uma das etapas da unificação de dados para revisar e fazer alterações.

1. Se estiver satisfeito com suas seleções, selecione **Criar perfis de cliente**. A página **Unificar** é exibida enquanto o perfil de cliente unificado é criado. Todos os blocos, exceto **Campos de origem** mostram o status **Na Fila** ou **Atualizando**.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de tela da página Unificar com blocos mostrando Na Fila ou Atualizando.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificação leva algum tempo para ser concluído e você não pode alterar a configuração até que seja concluído. Quando o processo de unificação for concluído, a entidade do perfil de cliente unificado, chamada *Cliente*, será listada na página **Entidades** na seção **Perfis**. A primeira execução de unificação bem-sucedida cria a entidade *Cliente* unificada. Todas as execuções subsequentes expandem essa entidade.

## <a name="review-the-results-of-data-unification"></a>Revisar os resultados da unificação de dados

Após a unificação, a página **Dados** > **Unificar** mostra o número de perfis de cliente unificados. Os resultados de cada etapa no processo de unificação são exibidos em cada bloco. Por exemplo, **Campos de origem** mostra o número de atributos (campos) mapeados e **Registros duplicados** mostra o número de registros duplicados encontrados.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de tela da página Dados Unificar após a unificação dos dados.":::

> [!TIP]
> O bloco **Condições correspondentes** é exibido apenas se várias entidades forem selecionadas.

É recomendável revisar os resultados, principalmente a qualidade das suas [regras de correspondência](data-unification-update.md#manage-match-rules) e refiná-las, se necessário.

Quando necessário, [faça alterações nas configurações de unificação](data-unification-update.md) e execute novamente o perfil unificado.

## <a name="next-step"></a>Próxima etapa

Configure [atividades](activities.md), [enriquecimento](enrichment-hub.md), [relacionamentos](relationships.md) ou [medidas](measures.md) para obter mais insights sobre seus clientes.

[!INCLUDE[footer-include](includes/footer-banner.md)]
