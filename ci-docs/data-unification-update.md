---
title: Atualizar as configurações de unificação de clientes, contas ou contatos
description: Atualize as regras duplicadas, as regras de correspondência ou os campos unificados nas configurações de unificação de cliente ou conta.
ms.date: 08/26/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: Scott-Stabbert
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-relationships
- customerInsights
ms.openlocfilehash: e893e66fd7691b9703d51ed8f87cfad63880cc3b
ms.sourcegitcommit: 560c4ee16376a9c6fdd7860988ce2d2440194fa5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/01/2022
ms.locfileid: "9392457"
---
# <a name="update-unification-settings"></a>Atualizar as configurações de unificação

Para revisar ou alterar qualquer configuração de unificação após a criação de um perfil unificado, execute as etapas a seguir.

1. Acesse **Dados** > **Unificar**.

   Para clientes individuais (B-to-C), a página **Unificar** exibe o número de perfis e blocos de clientes unificados para cada uma das etapas de unificação.

   :::image type="content" source="media/m3_unified.png" alt-text="Captura de tela da página Dados Unificar após a unificação dos dados." lightbox="media/m3_unified.png":::

   Para contas comerciais (B-to-B), a página **Unificar** exibe o número de perfis e blocos de contas unificados para cada uma das etapas de unificação de contas. Se os contatos foram unificados, o número de perfis e blocos de contatos unificados para cada uma das etapas de unificação de contatos será exibido. Escolha o bloco apropriado em **Unificar contas** ou **Unificar contatos (versão preliminar)** dependendo do que você deseja atualizar.

   :::image type="content" source="media/b2b_unified.png" alt-text="Captura de tela da página Unificação de dados após a unificação dos dados de conta e contato." lightbox="media/b2b_unified.png":::

   > [!TIP]
   > O bloco **Condições correspondentes** é exibido apenas se várias entidades forem selecionadas.

1. Escolha o que você deseja atualizar:
   - [Campos de origem](#edit-source-fields) para adicionar atributos ou entidades ou alterar tipos de atributos. Para remover um atributo, consulte [Remover um campo unificado](#remove-a-unified-field). Para remover uma entidade, consulte [Remover uma entidade unificada](#remove-a-unified-entity).
   - [Registros duplicados](#manage-deduplication-rules) para gerenciar regras de eliminação de duplicação ou preferências de mesclagem.
   - [Condições correspondentes](#manage-match-rules) para atualizar as regras de correspondência em duas ou mais entidades.
   - [Campos de cliente unificados](#manage-unified-fields) para combinar ou excluir campos. Você também pode agrupar perfis relacionados em clusters.
   - [Campos semânticos](#manage-semantic-fields-for-unified-contacts) para gerenciar tipos semânticos para campos de contato unificados.
   - [Relacionamentos](#manage-contact-and-account-relationships) para gerenciar o relacionamento entre contato e conta.

1. Depois de fazer as alterações, escolha sua próxima opção:

   - [Execute as condições de correspondência](#run-matching-conditions) para avaliar rapidamente a qualidade das condições correspondentes (eliminação de duplicação e regras de correspondência) sem atualizar o perfil unificado. A opção **Executar apenas condições correspondentes** não é exibida para uma única entidade.
   - [Unifique os perfis](#run-updates-to-the-unified-profile) para executar condições de correspondência e atualizar a entidade de perfil unificada sem afetar as dependências (como enriquecimentos, segmentos ou medidas). Os processos dependentes não são executados, mas serão atualizados conforme [definido na agenda de atualização](schedule-refresh.md).
   - [Unifique os perfis e as dependências](#run-updates-to-the-unified-profile) para executar condições de correspondência, atualizar a entidade de perfil unificada e atualizar todas as dependências (como enriquecimentos, segmentos ou medidas). Todos os processos são executados novamente automaticamente. Em B-to-B, a unificação é executada na conta e nas entidades de contato que atualizam os perfis unificados.

## <a name="edit-source-fields"></a>Editar campos de origem

1. Selecione **Editar** no bloco **Campos de origem**.

   :::image type="content" source="media/m3_source_edit.png" alt-text="Captura de tela da página Campos de origem mostrando o número de chaves primárias e campos mapeados e não mapeados":::

   O número de campos mapeados e não mapeados é exibido.

1. Para adicionar outros atributos ou entidades, selecione **Selecionar entidades e campos**.

1. Opcionalmente, você pode alterar a chave primária de uma entidade e os tipos de atributo e ativar ou desativar o **Mapeamento inteligente**. Para obter mais informações, consulte [Selecionar campos de origem](map-entities.md).

1. Selecione **Próximo** para fazer alterações nas regras de eliminação de duplicação ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-unification-settings).

### <a name="remove-a-unified-field"></a>Remover um campo unificado

Para remover um campo que foi unificado, o campo deve ser removido de quaisquer dependências, como segmentos, medidas, enriquecimentos ou relacionamentos.

1. Depois que todas as dependências do campo forem removidas, vá para **Dados** > **Unificar**.

1. Selecione **Editar** no bloco **Campos de cliente unificados**.

1. Selecione todas as ocorrências do campo e, em seguida, selecione **Excluir**.

   :::image type="content" source="media/m3_remove_attribute1.png" alt-text="Captura de tela da página Campos unificados mostrando os campos selecionados e o botão Excluir":::

1. Selecione **Concluído** para confirmar e, em seguida, selecione **Salvar e fechar**.

   > [!TIP]
   > Se vir a mensagem "Não foi possível salvar a unificação O recurso especificado não pode ser modificado nem excluído devido a dependências de downstream", o campo ainda será usado em uma dependência de downstream.

1. Se o campo for usado em uma regra para registros duplicados ou condições de correspondência, execute as etapas a seguir. Caso contrário, vá para a próxima etapa.
   1. Selecione **Editar** no bloco **Registros duplicados**.
   1. Se houver, remova o campo de todas as regras em que é usado e selecione **Próximo**.
   1. Na página **Condições correspondentes**, remova o campo de todas as regras em que é usado, se houver, e selecione **Salvar e fechar**.
   1. Selecione **Unificar** > **Unificar perfis e dependências do cliente**. Aguarde a conclusão da unificação antes de ir para a próxima etapa.

1. Selecione **Editar** no bloco **Campos de origem**.

1. Selecione **Selecionar entidades e campos** e desmarque a caixa de seleção ao lado de cada ocorrência do campo.

   :::image type="content" source="media/m3_remove_attribute2.png" alt-text="Captura de tela da caixa de diálogo Selecionar entidades e campos mostrando as caixas de seleção desmarcadas":::

1. Selecione **Aplicar**.

1. Selecione **Salvar e fechar**.

1. Selecione **Unificar** > **Unificar perfis e dependências de clientes** para atualizar o perfil unificado.

### <a name="remove-a-unified-entity"></a>Remover uma entidade unificada

Para remover uma entidade que foi unificada, a entidade deve ser removida de quaisquer dependências, como segmentos, medidas, enriquecimentos ou relacionamentos.

1. Depois que todas as dependências da entidade forem removidas, vá para **Dados** > **Unificar**.

1. Selecione **Editar** no bloco **Campos de cliente unificados**.

1. Selecione todos os campos para a entidade e, em seguida, selecione **Excluir**.

   :::image type="content" source="media/m3_remove_entity1.png" alt-text="Captura de tela de Campos unificados com todos os campos de uma entidade selecionada e o botão Excluir":::

1. Selecione **Concluído** para confirmar e, em seguida, selecione **Salvar e fechar**.

   > [!TIP]
   > Se vir a mensagem "Não foi possível salvar a unificação O recurso especificado não pode ser modificado nem excluído devido a dependências de downstream", a entidade ainda será usada em uma dependência de downstream.

1. Selecione **Editar** no bloco **Registros duplicados**.

1. Remova todas as regras da entidade, se houver, e selecione **Próximo**.

1. Na página **Condições correspondentes**, selecione a entidade e, em seguida, selecione **Excluir**.

   :::image type="content" source="media/m3_remove_entity2.png" alt-text="Captura de tela das Condições correspondentes com a entidade selecionada e o botão Excluir":::

1. Selecione **Salvar e fechar**.

1. Selecione **Editar** no bloco **Campos de origem**.

1. Selecione **Selecionar entidades e campos** e desmarque a caixa de seleção ao lado da entidade.

   :::image type="content" source="media/m3_remove_entity3.png" alt-text="Captura de tela da caixa de diálogo Selecionar entidades e campos com a caixa de seleção da entidade desmarcada":::

1. Selecione **Aplicar**.

1. Selecione **Salvar e fechar**.

1. Selecione **Unificar** > **Unificar perfis e dependências de clientes** para atualizar o perfil unificado.

## <a name="manage-deduplication-rules"></a>Gerenciar regras de eliminação de duplicação

1. Selecione **Editar** no bloco **Registros duplicados**.

   :::image type="content" source="media/m3_duplicates_edit.png" alt-text="Captura de tela da página de registros duplicados mostrando o número de registros duplicados" lightbox="media/m3_duplicates_edit.png":::

   O número de registros duplicados encontrados é exibido em **Duplicatas**. A coluna **Registros com duplicação eliminada** mostra quais entidades tinham registros duplicados e a porcentagem de registros duplicados.

1. Para usar uma entidade enriquecida, selecione **Usar entidades enriquecidas**. Para obter mais informações, consulte [Enriquecimento de fontes de dados](data-sources-enrichment.md).

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

   1. Selecione **Concluído**.

1. Selecione **Próximo** para fazer alterações nas condições correspondentes ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-unification-settings).

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

1. Selecione **Próximo** para fazer alterações nos campos unificados ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-unification-settings).

## <a name="manage-unified-fields"></a>Gerenciar campos unificados

1. Selecione **Editar** no bloco **Campos de cliente unificados**.

    :::image type="content" source="media/m3_merge_edit.png" alt-text="Captura de tela dos campos de cliente unificados":::

1. Revise os campos combinados e excluídos e faça as alterações necessárias. Adicione ou edite a chave CustomerID ou os perfis de grupo em clusters. Para obter mais informações, consulte [Unificar campos de cliente](merge-entities.md).

1. Para clientes ou contas, selecione **Próximo** para revisar e [atualizar o perfil unificado e as dependências](#run-updates-to-the-unified-profile). Ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-unification-settings) para fazer mais mudanças.

   Para contatos, selecione **Próximo** para gerenciar campos semânticos. Ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-unification-settings) para fazer mais mudanças.

## <a name="manage-semantic-fields-for-unified-contacts"></a>Gerenciar os campos semânticos dos contatos unificados

1. Selecione **Editar** no bloco **Campos semânticos**.

1. Para alterar o tipo semântico de um campo unificado, selecione um novo tipo. Para obter mais informações, consulte [Definir os campos semânticos dos contatos unificados](data-unification-contacts.md#define-the-semantic-fields-for-unified-contacts).

1. Selecione **Próximo** para gerenciar os relacionamentos de contatos e contas ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-unification-settings) para fazer mais mudanças.

## <a name="manage-contact-and-account-relationships"></a>Gerenciar relacionamentos de contatos e contas

1. Selecione **Editar** no bloco **Relacionamentos**.

1. Para mudar o relacionamento de contato e conta, altere qualquer uma das seguintes informações:

   - **Chave estrangeira da entidade de contato**: escolha o atributo que conecta sua entidade de contato à conta.
   - **Para a entidade de conta**: escolha a entidade da conta associada ao contato.

1. Selecione **Próximo** para revisar as configurações de unificação e [atualize o perfil unificado e as dependências](#run-updates-to-the-unified-profile) ou selecione **Salvar e fechar** e volte para [Atualizar as configurações de unificação](#update-unification-settings) para fazer mais mudanças.

## <a name="run-matching-conditions"></a>Executar condições correspondentes

Executar condições de correspondência só executa a eliminação de duplicação e as regras de correspondência e atualiza as entidades *Deduplication_* e *ConflationMatchPair*.

1. Na página **Dados** > **Unificar**, selecione **Executar apenas condições correspondentes**.

   Os blocos **Registros duplicados** e **Condições correspondentes** mostram **Na Fila** ou **Atualizando**.

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

1. Quando o processo de correspondência for concluído, selecione **Editar** no bloco **Condições correspondentes**.

   :::image type="content" source="media/match-KPIs.png" alt-text="Captura de tela recortada das métricas principais na página Corresponder com números e detalhes.":::

1. Para fazer alterações, consulte [Gerenciar regras de eliminação de duplicação](#manage-deduplication-rules) ou [Gerenciar regras de correspondência](#manage-match-rules).

1. Execute o processo de correspondência novamente ou [execute atualizações no perfil](#run-updates-to-the-unified-profile).

## <a name="run-updates-to-the-unified-profile"></a>Execute atualizações no perfil unificado

- Para executar condições de correspondência e atualizar a entidade de perfil unificada *sem* afetar as dependências (como cartões de cliente, enriquecimentos, segmentos ou medidas), selecione **Unificar perfis de cliente**. Para contas, selecione **Unificar contas** > **Unificar perfis**. Para contatos, selecione **Unificar contatos (versão preliminar)** > **Unificar perfis**. Os processos dependentes não são executados, mas serão atualizados conforme [definido na agenda de atualização](schedule-refresh.md).
- Para executar condições correspondentes, atualizar o perfil unificado e executar todas as dependências, selecione **Unificar perfis e dependências de clientes**. Todos os processos são executados novamente automaticamente. Para contas e contatos, selecione **Unificar contas** > **Unificar perfis e dependências**. As condições de correspondência são executadas para contas e contatos que atualizam os perfis unificados e todas as outras dependências são executadas.

Todos os blocos, exceto **Campos de origem**, mostram **Na Fila** ou **Atualizando**.

[!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

Os resultados de uma execução bem-sucedida são exibidos na página **Unify** que mostra o número de perfis unificados.
