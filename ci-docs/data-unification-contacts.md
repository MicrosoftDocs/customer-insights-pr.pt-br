---
title: Criar um perfil de contato unificado (versão preliminar)
description: Passe pelo processo de unificação de dados para criar um único conjunto de dados mestre de contatos.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- ci-match
- ci-merge
- customerInsights
ms.openlocfilehash: 721f47563582a94b5b8244ca5d5d7d1350695512
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9305008"
---
# <a name="create-a-unified-contact-profile-preview"></a>Criar um perfil de contato unificado (versão preliminar)

Depois de [unificar as contas corporativas](map-entities.md), é possível unificar os contatos dessas contas e vincular os contatos unificados às contas unificadas. O processo de unificação de contatos mapeia dados de contato de várias fontes de dados, remove duplicatas, faz a correspondência de dados entre entidades, configura mapeamento semântico, cria relacionamentos entre contatos e contas e, depois, cria um perfil de contato unificado.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

As primeiras etapas são idênticas às etapas de unificação de contas.

## <a name="prerequisites"></a>Pré-requisitos

Os registros de conta e contato devem ter uma chave exclusiva (chamada chave estrangeira) que os conecta. Por exemplo, uma ID de conta que existe no registro da conta e no registro do contato que une a conta e o contato.

## <a name="preview-limitations"></a>Limitações da versão preliminar

- Os contatos sem um link para uma conta são descartados.
- Se uma conta for desduplicada, um registro vencedor será identificado com base nas preferências de mesclagem. Os registros perdedores não são selecionados e, portanto, são descartados. Os contatos associados aos registros perdedores são descartados.
- Uma conta pode ter vários contatos, mas um contato está vinculado a uma única conta.
- Os atributos de contato mapeados na etapa de mapeamento semântico são os únicos atributos que podem ser exibidos no cartão do cliente. Contudo, 17 atributos estão disponíveis.

## <a name="select-source-fields"></a>Selecionar campos de origem

1. Em **Unificar contatos (versão preliminar)**, selecione **Começar agora**.

1. [Selecione as entidades e os campos](map-entities.md) para suas fontes de dados de contato, incluindo as chaves primárias e os tipos de atributo.

1. Selecione **Avançar**

## <a name="remove-duplicate-records"></a>Remover registros duplicados

1. Ou [defina regras de desduplicação](remove-duplicates.md) para suas entidades selecionadas.

1. Selecione **Avançar**

## <a name="match-conditions"></a>Condições de correspondência

1. [Defina a ordem de correspondência e as regras](match-entities.md) para a correspondência entre entidades.

1. Selecione **Avançar**

## <a name="unify-contact-fields"></a>Unificar campos de contato

1. [Combinar e excluir campos de contato](merge-entities.md).

1. Selecione **Avançar**

## <a name="define-the-semantic-fields-for-unified-contacts"></a>Definir os campos semânticos dos contatos unificados

Esta etapa no processo de unificação mapeia seus campos de contato unificados para tipos semânticos. Em B-to-B, os cartões de cliente mostram contas. Quando o cartão é selecionado, todos os contatos associados à conta são exibidos. Os campos mapeados nesta etapa são os campos que serão exibidos nos cartões.

1. Selecione o tipo semântico que mapeia para cada campo unificado. Selecione **Nenhum** se um tipo semântico não estiver disponível.

   :::image type="content" source="media/semantic_mapping.png" alt-text="Captura de tela da página Campos semânticos para definir os tipos semânticos." lightbox="media/semantic_mapping.png":::

1. Após mapear todos os campos unificados, selecione **Próximo**.

## <a name="set-the-relationship-between-contacts-and-accounts"></a>Definir a relação entre contatos e contas

Esta etapa do processo de unificação conecta seus dados de contato aos dados de conta correspondentes.

1. Para cada entidade, insira as seguintes informações:

   - **Chave estrangeira da entidade de contato**: escolha o atributo que conecta sua entidade de contato à conta.
   - **Para a entidade de conta**: escolha a entidade da conta associada ao contato.

   :::image type="content" source="media/contact_relationship.png" alt-text="Captura de tela da página Relacionamento para conectar as entidades de contato e conta.":::

1. Selecione **Avançar**

## <a name="review-contact-unification"></a>Revisar a unificação de contatos

Revise o resumo das alterações, crie o perfil unificado e revise os resultados.

### <a name="review-and-create-contact-profiles"></a>Revisar e criar perfis de contato

Esta última etapa do processo de unificação mostra um resumo das etapas do processo e oferece a oportunidade de fazer alterações antes de criar o perfil de contato unificado.

:::image type="content" source="media/b2b_review_contacts.png" alt-text="Captura de tela de Revisar e criar perfis de contato.":::

1. Selecione **Editar** em qualquer uma das etapas da unificação de contatos para revisar e fazer alterações.

1. Se estiver satisfeito com suas seleções, selecione **Criar perfis de contato**. A página **Unificar** é exibida enquanto o perfil de contato unificado é criado.
  
   :::image type="content" source="media/b2b_unify_refreshing.png" alt-text="Captura de tela da página Unificar Contatos com blocos mostrando Na Fila ou Atualizando.":::

   [!INCLUDE [progress-details-pane-include](includes/progress-details-pane.md)]

O algoritmo de unificação leva algum tempo para ser concluído e você não pode alterar a configuração até que seja concluído.

### <a name="view-the-results-of-contact-unification"></a>Exibir os resultados da unificação de contatos

Após a conclusão da unificação, a página **Dados** > **Unificar** mostra o número de perfis de contato unificados. Os resultados de cada etapa no processo de unificação são exibidos em cada bloco. Por exemplo, **Campos de origem** mostra o número de atributos (campos) mapeados e **Registros duplicados** mostra o número de registros duplicados encontrados.

:::image type="content" source="media/unified_contacts.png" alt-text="Captura de tela da página Unificação de dados após a unificação dos contatos.":::

> [!TIP]
> O bloco **Condições correspondentes** é exibido apenas se várias entidades forem selecionadas.

É recomendável revisar os resultados, principalmente a qualidade das suas [regras de correspondência](data-unification-update.md#manage-match-rules) e refiná-las, se necessário.

Quando necessário, [faça alterações nas configurações de unificação de contato](data-unification-update.md) e execute novamente o perfil unificado.

### <a name="verify-output-entities-from-data-unification"></a>Verificar as entidades de saída da unificação de dados

Acesse **Dados** > **Entidades** para verificar as entidades de saída.

A entidade unificada do perfil de contato, chamada *ContactProfile*, é exibida na seção **Entidades semânticas**. A primeira execução de unificação bem-sucedida cria a entidade *ContactProfile* unificada. Todas as execuções subsequentes expandem essa entidade.

A entidade *ContactsCustomer* (versão preliminar) é criada e exibida na seção **Perfis**. Essa entidade contém os dados de contato sem os links para as contas. Essa entidade é usada como entrada no mapeamento semântico e nas etapas de relacionamento da unificação de contatos.

As entidades de desduplicação e conflação são criadas e exibidas na seção **Sistema**. Uma entidade deduplicada para cada uma das entidades de origem é criada com o nome **Deduplication_DataSource_Entity**. A entidade **ContactsConflationMatchPairs** contém informações sobre correspondências entre entidades.

Uma entidade de saída de eliminação de duplicação contém as seguintes informações:
- IDs/chaves
  - Campos Chave primária e ID Alternativa. O campo ID Alternativa consiste em todas as IDs alternativas identificadas para um registro.
  - O campo Deduplication_GroupId mostra o grupo ou cluster identificado em uma entidade que agrupa todos os registros semelhantes com base nos campos de eliminação de duplicação especificados. Ele é usado para fins de processamento do sistema. Se não houver regras de eliminação de duplicação manual especificadas e as regras de eliminação de duplicação definidas pelo sistema se aplicarem, talvez você não encontre esse campo na entidade de saída de eliminação de duplicação.
  - Deduplication_WinnerId: este campo contém a ID do vencedor dos grupos ou clusters identificados. Se a Deduplication_WinnerId for igual ao valor da chave primária para um registro, isso significa que o registro é o registro vencedor.
- Campos usados para definir as regras de eliminação de duplicação.
- Campos de regra e pontuação para denotar quais das regras de eliminação de duplicação foram aplicadas e a pontuação retornada pelo algoritmo de correspondência.

## <a name="next-step"></a>Próxima Etapa

Configurar [atividades](activities.md), [enriquecimento](enrichment-hub.md) ou [relacionamentos](relationships.md) para obter mais informações sobre seus contatos.
