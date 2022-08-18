---
title: Atualizar as configurações de unificação
description: Atualize as regras duplicadas, as regras de correspondência ou os campos unificados nas configurações de unificação.
ms.date: 06/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: a7cf06c07e4b95b848a55dfe5fe0b09397fe744e
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245580"
---
# <a name="update-the-unification-settings"></a>Atualizar as configurações de unificação

Para revisar ou alterar qualquer configuração de unificação após a criação de um perfil unificado, execute as etapas a seguir.

1. Acesse **Dados** > **Unificar**.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de tela da página Dados Unificar após a unificação dos dados.":::

   > [!TIP]
   > O bloco **Condições correspondentes** é exibido apenas se várias entidades forem selecionadas.

1. Escolha o que você deseja atualizar:
   - [Campos de origem](#edit-source-fields) para adicionar entidades ou atributos ou alterar tipos de atributos.
   - [Registros duplicados](#manage-deduplication-rules) para gerenciar regras de eliminação de duplicação ou preferências de mesclagem.
   - [Condições correspondentes](#manage-match-rules) para atualizar as regras de correspondência em duas ou mais entidades.
   - [Campos de cliente unificados](#manage-unified-fields) para combinar ou excluir campos. Você também pode agrupar perfis relacionados em clusters.

1. Depois de fazer as alterações, escolha sua próxima opção:

   :::image type="content" source="media/m3_run_match_merge.png" alt-text="Captura de tela da página Data Unify com as opções do Unify em destaque.":::

   - [Execute as condições de correspondência](#run-matching-conditions) para avaliar rapidamente a qualidade das condições correspondentes (eliminação de duplicação e regras de correspondência) sem atualizar o perfil unificado. A opção **Executar apenas condições correspondentes** não é exibida para uma única entidade.
   - [Unifique os perfis de cliente](#run-updates-to-the-unified-customer-profile) para executar as condições correspondentes e atualizar a entidade do Unified customer profile sem afetar as dependências (como enriquecimentos, segmentos ou medidas). Os processos dependentes não são executados, mas serão atualizados conforme [definido na agenda de atualização](schedule-refresh.md).
   - [Unifique os perfis de cliente e as dependências](#run-updates-to-the-unified-customer-profile) para executar as condições correspondentes e atualizar a entidade do Unified customer profile sem afetar as dependências (como enriquecimentos, segmentos ou medidas). Todos os processos são executados novamente automaticamente.

## <a name="edit-source-fields"></a>Editar campos de origem

Não é possível remover um atributo ou uma entidade se eles já tiverem sido unificados.

1. Selecione **Editar** no bloco **Campos de origem**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de tela da página Campos de origem mostrando o número de chaves primárias e campos mapeados e não mapeados":::

   O número de campos mapeados e não mapeados é exibido.

1. Selecione **Selecionar entidades e campos** para adicionar outros atributos ou entidades. Use a pesquisa ou role para localizar e selecionar seus atributos e entidades de interesse. Selecione **Aplicar**.

1. Opcionalmente, você pode alterar a chave primária de uma entidade e os tipos de atributo e ativar ou desativar o **Mapeamento inteligente**. Para mais informações, consulte [Selecionar a chave primária e o tipo semântico para atributos](map-entities.md#select-primary-key-and-semantic-type-for-attributes).

1. Selecione **Próximo** para fazer alterações nas regras de eliminação de duplicação ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-the-unification-settings).

## <a name="manage-deduplication-rules"></a>Gerenciar regras de eliminação de duplicação

1. Selecione **Editar** no bloco **Registros duplicados**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de tela da página de registros duplicados mostrando o número de registros duplicados" lightbox="media/m3_duplicates_edit.png":::

   O número de registros duplicados encontrados é exibido em **Duplicatas**. A coluna **Registros com duplicação eliminada** mostra quais entidades tinham registros duplicados e a porcentagem de registros duplicados.

1. Se você adicionou uma entidade enriquecida, selecione **Usar entidades enriquecidas**. Para obter mais informações, consulte [Enriquecimento de fontes de dados](data-sources-enrichment.md).

1. Para gerenciar as regras de eliminação de duplicação, escolha uma das seguintes opções:
   - **Criar uma nova regra**: selecione **Adicionar regra** na entidade apropriada. Para mais informações, consulte [Definir regras de eliminação de duplicação](remove-duplicates.md#define-deduplication-rules).
   - **Alterar condições da regra**: selecione a regra e **Editar**. Altere campos, adicione ou remova condições ou adicione ou remova exceções.
   - **Pré-visualização**: selecione a regra e, em seguida, **Pré-visualização** para visualizar os resultados da última execução para esta regra.
   - **Desativar uma regra**: selecione a regra e, em seguida, **Desativar** para reter uma regra de eliminação de duplicação enquanto a exclui do processo de correspondência.
   - **Duplicar uma regra**: selecione a regra e, em seguida, **Duplicar** para criar uma regra semelhante com modificações.
   - **Excluir uma regra**: selecione a regra e, em seguida, **Excluir**.

1. Para alterar as preferências de mesclagem, selecione a entidade. Só é possível alterar as preferências se uma regra for criada.
   1. Selecione **Editar preferências de mesclagem** e altere a opção **Registro a ser mantido**.
   1. Para alterar as preferências de mesclagem em atributos individuais de uma entidade, selecione **Avançado** e fazer as alterações necessárias.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Captura de tela das preferências de mesclagem avançadas mostrando o e-mail mais recente e o endereço mais completo":::

   1. Selecione **Concluído**.

1. Selecione **Próximo** para fazer alterações nas condições correspondentes ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-the-unification-settings).

## <a name="manage-match-rules"></a>Gerenciar regras de correspondência

Você pode reconfigurar e ajustar a maioria dos parâmetros de correspondência. Não é possível adicionar ou excluir entidades. As regras de correspondência não se aplicam a uma única entidade.

1. Selecione **Editar** no bloco **Condições correspondentes**.

   :::image type="content" source="media/m3_match_edit.png" alt-text="Captura de tela da página de condições e regras de correspondência com estatísticas." lightbox="media/m3_match_edit.png":::

   A página exibe a ordem de correspondência, as regras definidas e as seguintes estatísticas:
   - **Registros de origem exclusivos** mostra o número de registros de origem individuais que foram processados na última execução de correspondências.
   - **Registros com e sem correspondências** destaca quantos registros únicos permanecem após o processamento das regras de correspondência.
   - **Somente registros com correspondência** mostra o número de correspondências em todos os seus pares de correspondência.

1. Para exibir os resultados de todas as regras e as pontuações, selecione **Exibir última execução**. Os resultados são exibidos, inclusive as IDs de contato alternativas. Você pode baixar os resultados.

1. Para exibir os resultados e as pontuações de uma regra específica, selecione a regra e, em seguida, **Pré-visualização**. Os resultados são exibidos. Você pode baixar os resultados.

1. Para exibir os resultados de uma condição específica em uma regra, selecione a regra e, em seguida, **Editar**. No painel Editar, selecione **Pré-visualização** na condição. Você pode baixar os resultados.

   :::image type="content" source="media/m3_match_condition_preview.png" alt-text="Representação gráfica de registros não correspondentes e correspondentes, incluindo uma lista dos dados.":::

1. Se você adicionou uma entidade enriquecida, selecione **Usar entidades enriquecidas**. Para obter mais informações, consulte [Enriquecimento de fontes de dados](data-sources-enrichment.md).

1. Para gerenciar as regras, escolha uma das seguintes opções:
   - **Criar uma nova regra**: selecione **Adicionar regra** na entidade apropriada. Para mais informações, consulte [Definir regras para pares correspondentes](match-entities.md#define-rules-for-match-pairs).
   - **Altere a ordem suas regras** se você definiu várias regras: arraste e solte as regras na ordem desejada. Para obter mais informações, consulte [Especificar a ordem de correspondência](match-entities.md#specify-the-match-order).
   - **Alterar condições da regra**: selecione a regra e **Editar**. Altere campos, adicione ou remova condições ou adicione ou remova exceções.
   - **Desativar uma regra**: selecione a regra e, em seguida, **Desativar** para manter uma regra de correspondência enquanto a exclui do processo de correspondência.
   - **Duplicar uma regra**: selecione a regra e, em seguida, **Duplicar** para criar uma regra semelhante com modificações.
   - **Excluir uma regra**: selecione a regra e, em seguida, **Excluir**.

1. Selecione **Próximo** para fazer alterações nos campos unificados ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-the-unification-settings).

## <a name="manage-unified-fields"></a>Gerenciar campos unificados

1. Selecione **Editar** no bloco **Campos de cliente unificados**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de tela dos campos de cliente unificados":::

1. Revise os campos combinados e excluídos e faça as alterações necessárias. Adicione ou edite a chave CustomerID ou os perfis de grupo em clusters. Para obter mais informações, consulte [Unificar campos de cliente](merge-entities.md).

1. Selecione **Próximo** para revisar as configurações de unificação e [atualize o perfil unificado e as dependências](#run-updates-to-the-unified-customer-profile) ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-the-unification-settings) para fazer mais mudanças.

## <a name="run-matching-conditions"></a>Executar condições correspondentes

Executar condições de correspondência só executa a eliminação de duplicação e as regras de correspondência e atualiza as entidades *Deduplication_* e *ConflationMatchPair*.

1. Na página **Dados** > **Unificar**, selecione **Executar apenas condições correspondentes**.

   Os blocos **Registros duplicados** e **Condições correspondentes** mostram **Na Fila** ou **Atualizando**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Quando o processo de correspondência for concluído, selecione **Editar** no bloco **Condições correspondentes**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de tela recortada das métricas principais na página Corresponder com números e detalhes.":::

1. Para fazer alterações, consulte [Gerenciar regras de eliminação de duplicação](#manage-deduplication-rules) ou [Gerenciar regras de correspondência](#manage-match-rules).

1. Execute o processo de correspondência novamente ou [execute atualizações no perfil do cliente](#run-updates-to-the-unified-customer-profile).

## <a name="run-updates-to-the-unified-customer-profile"></a>Execute atualizações no perfil de cliente unificado

1. Na página **Dados** > **Unificar**, selecione:

   - **Unificar perfis de cliente**: executa as condições correspondentes e atualiza a entidade do Unified customer profile sem afetar as dependências (como enriquecimentos, segmentos ou medidas). Os processos dependentes não são executados, mas serão atualizados conforme [definido na agenda de atualização](schedule-refresh.md).

   - **Unificar perfis de cliente e dependências**: executa as condições correspondentes e atualiza a entidade do Unified customer profile sem afetar as dependências (como enriquecimentos, segmentos ou medidas). Todos os processos são executados novamente automaticamente. Após a conclusão de todos os processos downstream, o perfil do cliente reflete os dados atualizados.

   Os blocos **Registros duplicados**, **Condições correspondentes** e **Campos de cliente unificados** mostram o status **Na Fila** ou **Atualizando**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Os resultados de uma execução bem-sucedida são exibidos na página **Unify** que mostra o número de perfis de cliente unificados.
