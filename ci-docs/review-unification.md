---
title: Revisar a unificação de dados
description: Revise as etapas da unificação de dados, crie perfis de cliente unificados e revise os resultados
ms.date: 08/12/2022
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
ms.openlocfilehash: b4d77effc347e40fecde625a1a42a24900456471
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303953"
---
# <a name="review-data-unification"></a>Revisar a unificação de dados

Revise o resumo das alterações, crie o perfil unificado e revise os resultados.

## <a name="review-and-create-customer-profiles"></a>Revisar e criar perfis de cliente

Esta última etapa do processo de unificação mostra um resumo das etapas do processo e oferece a oportunidade de fazer alterações antes de criar o perfil unificado.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

:::image type="content" source="media/m3_review.png" alt-text="Captura de tela de Revisar e criar perfis de cliente.":::

1. Selecione **Editar** em qualquer uma das etapas da unificação de dados para revisar e fazer alterações.

1. Se estiver satisfeito com suas seleções, selecione **Criar perfis de cliente** (ou **Criar perfis da conta** para B-to-B). A página **Unificar** é exibida enquanto o perfil de cliente unificado é criado.

   :::image type="content" source="media/m3_unify_refreshing.png" alt-text="Captura de tela da página Unificar com blocos mostrando Na Fila ou Atualizando.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificação leva algum tempo para ser concluído e você não pode alterar a configuração até que seja concluído.

## <a name="view-the-results-of-data-unification"></a>Exibir os resultados da unificação de dados

Após a unificação, a página **Dados** > **Unificar** mostra o número de perfis de cliente unificados (ou perfis de conta para B-to-B). Os resultados de cada etapa no processo de unificação são exibidos em cada bloco. Por exemplo, **Campos de origem** mostra o número de atributos (campos) mapeados e **Registros duplicados** mostra o número de registros duplicados encontrados.

:::image type="content" source="media/m3_unified.png" alt-text="Captura de tela da página Dados Unificar após a unificação dos dados.":::

> [!TIP]
> O bloco **Condições correspondentes** é exibido apenas se várias entidades forem selecionadas.

É recomendável revisar os resultados, principalmente a qualidade das suas [regras de correspondência](data-unification-update.md#manage-match-rules) e refiná-las, se necessário.

Quando necessário, [faça alterações nas configurações de unificação](data-unification-update.md) e execute novamente o perfil unificado.

### <a name="verify-output-entities-from-data-unification"></a>Verificar as entidades de saída da unificação de dados

Acesse **Dados** > **Entidades** para verificar as entidades de saída.

A entidade Perfil unificado de cliente, chamada *Cliente*, é exibida na seção **Perfis**. A primeira execução de unificação bem-sucedida cria a entidade *Cliente* unificada. Todas as execuções subsequentes expandem essa entidade.

As entidades de desduplicação e conflação são criadas e exibidas na seção **Sistema**. Uma entidade deduplicada para cada uma das entidades de origem é criada com o nome **Deduplication_DataSource_Entity**. A entidade **ConflationMatchPairs** contém informações sobre correspondências entre entidades.

Uma entidade de saída de eliminação de duplicação contém as seguintes informações:
- IDs/chaves
  - Campos Chave primária e ID Alternativa. O campo ID Alternativa consiste em todas as IDs alternativas identificadas para um registro.
  - O campo Deduplication_GroupId mostra o grupo ou cluster identificado em uma entidade que agrupa todos os registros semelhantes com base nos campos de eliminação de duplicação especificados. Ele é usado para fins de processamento do sistema. Se não houver regras de eliminação de duplicação manual especificadas e as regras de eliminação de duplicação definidas pelo sistema se aplicarem, talvez você não encontre esse campo na entidade de saída de eliminação de duplicação.
  - Deduplication_WinnerId: este campo contém a ID do vencedor dos grupos ou clusters identificados. Se a Deduplication_WinnerId for igual ao valor da chave primária para um registro, isso significa que o registro é o registro vencedor.
- Campos usados para definir as regras de eliminação de duplicação.
- Campos de regra e pontuação para denotar quais das regras de eliminação de duplicação foram aplicadas e a pontuação retornada pelo algoritmo de correspondência.

## <a name="next-step"></a>Próxima Etapa

- Para B-to-B, opcionalmente, realize a [unificação de contatos](data-unification-contacts.md).

- Para B-to-C, configure [atividades](activities.md), [enriquecimentos](enrichment-hub.md), [relacionamentos](relationships.md) ou [medidas](measures.md) para obter mais insights sobre seus clientes.

[!INCLUDE[footer-include](includes/footer-banner.md)]
