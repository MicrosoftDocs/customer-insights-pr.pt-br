---
title: Revisar a unificação de dados
description: Revise as etapas da unificação de dados, crie perfis de cliente unificados e revise os resultados
ms.date: 05/04/2022
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
ms.openlocfilehash: 4c709dfb55bf079dd2fe99e41adb4c77c2bece4b
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741612"
---
# <a name="review-data-unification"></a>Revisar a unificação de dados

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Esta última etapa do processo de unificação mostra um resumo das etapas do processo e oferece a oportunidade de fazer alterações antes de criar o perfil unificado.

:::image type="content" source="media/m3_review.png" alt-text="Captura de tela de Revisar e Criar perfis de cliente.":::

## <a name="review-the-data-unification-steps"></a>Revisar as etapas da unificação de dados

1. Selecione **Editar** em qualquer uma das etapas da unificação de dados para revisar e fazer alterações.

1. Se estiver satisfeito com suas seleções, selecione **Criar perfis de cliente**. A página **Unificar** é exibida enquanto o perfil de cliente unificado é criado. O algoritmo de unificação leva algum tempo para ser concluído e você não pode alterar a configuração até que seja concluído.

   [!INCLUDE [m3-task-details-include](includes/m3-task-details.md)]

Quando o processo de unificação for concluído, a entidade do perfil de cliente unificado, chamada *Cliente*, será listada na página **Entidades** na seção **Perfis**. A primeira execução de unificação bem-sucedida cria a entidade *Cliente* unificada. Todas as execuções subsequentes expandem essa entidade.

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
