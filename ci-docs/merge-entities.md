---
title: Unificar campos de cliente ou conta
description: Mescle entidades para criar perfis de clientes unificados.
recommendations: false
ms.date: 05/04/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-merge
- ci-match
- ci-relationships
- customerInsights
ms.openlocfilehash: 78e2528d4a3058f879d83952f72ed88a1da065b6
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8740843"
---
# <a name="unify-customer-fields"></a>Unificar campos de cliente

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Nesta etapa do processo de unificação, escolha e exclua atributos para mesclar na sua entidade de perfil unificado. Por exemplo, se três entidades tiverem dados de email, talvez você queira manter todos os três campos de email separados ou mesclá-los em um único campo de email para o perfil unificado. Alguns atributos são combinados automaticamente pelo sistema. Você pode criar IDs de cliente estáveis e exclusivas e agrupar perfis relacionados em um cluster.

:::image type="content" source="media/m3_unify.png" alt-text="Página da mesclagem no processo de unificação de dados que mostra a tabela com campos mesclados que definem o perfil de cliente unificado.":::

## <a name="review-and-update-the-customer-fields"></a>Revisar e atualizar os campos de cliente

1. Revise a lista de campos que serão unificados na guia **Campos de cliente** da tabela. Faça as alterações, se aplicável.

   1. Para os campos combinados, você pode:
      - [Editar](#edit-a-merged-field)
      - [Renomear](#rename-fields)
      - [Separar](#separate-merged-fields)
      - [Excluir](#exclude-fields)
      - [Mover-se para cima ou para baixo](#change-the-order-of-fields)

   1. Para os campos individuais, você pode:
      - [Combinar campos](#combine-fields-manually)
      - [Combinar um grupo de campos](#combine-a-group-of-fields)
      - [Renomear](#rename-fields)
      - [Excluir](#exclude-fields)
      - [Mover-se para cima ou para baixo](#change-the-order-of-fields)

1. Opcionalmente, [gerar a configuração da ID do cliente](#configure-customer-id-generation).

1. Opcionalmente, [agrupar perfis em residências ou clusters](#group-profiles-into-households-or-clusters)

> [!div class="nextstepaction"]
> [Próxima etapa: Revisar a unificação](review-unification.md)

### <a name="edit-a-merged-field"></a>Editar um campo mesclado

1. Selecione um campo mesclado e escolha **Editar**. O painel Combinar campos é exibido.

1. Especifique como combinar ou mesclar os campos de uma das três opções:
    - **Importância**: identifica o valor vencedor com base na classificação de importância especificada para os campos participantes. É a opção de mesclagem padrão. Selecione **Mover para cima/baixo** para definir a classificação de importância.

      :::image type="content" source="media/importance-merge-option.png" alt-text="Opção de importância na caixa de diálogo de campos de mesclagem.":::

    - **Mais recente**: identifica o valor vencedor com base no maior nível de atualização. Requer uma data ou um campo numérico para cada entidade participante no escopo dos campos de mesclagem para definir o nível de atualização.

      :::image type="content" source="media/recency-merge-option.png" alt-text="Opção de nível de atualização na caixa de diálogo de campos de mesclagem.":::

    - **Menos recente**: identifica o valor vencedor com base no menor nível de atualização. Requer uma data ou um campo numérico para cada entidade participante no escopo dos campos de mesclagem para definir o nível de atualização.

1. Você pode adicionar mais campos para participar do processo de mesclagem.

1. Você pode renomear o campo mesclado.

1. Selecione **Concluído** para aplicar suas alterações.

### <a name="rename-fields"></a>Renomear campos

Altere o nome de exibição de campos mesclados ou separados. Não é possível alterar o nome da entidade de saída.

1. Selecione o campo e escolha **Renomear**.

1. Insira o novo nome de exibição.

1. Selecione **Concluído**.

### <a name="separate-merged-fields"></a>Separar campos mesclados

Para separar os campos mesclados, localize o atributo na tabela. Os campos separados aparecem como pontos de dados individuais no perfil de cliente unificado.

1. Selecione o campo mesclado e escolha **Separar campos**.

1. Confirme a separação.

### <a name="exclude-fields"></a>Excluir campos

Exclua um campo mesclado ou separado do perfil de cliente unificado. Se o campo for usado em outros processos, por exemplo, em um segmento, remova-o desses processos antes de excluí-lo do perfil do cliente.

1. Selecione um campo e escolha **Excluir**.

1. Confirme a exclusão.

Para ver a lista de todos os campos excluídos, selecione **Campos excluídos**. Se necessário, você pode adicionar novamente o campo excluído.

### <a name="change-the-order-of-fields"></a>Alterar a ordem dos campos

Algumas entidades contêm mais detalhes que outras. Se uma entidade tiver os dados mais recentes sobre um campo, você pode priorizá-los sobre outras entidades ao mesclar valores.

1. Selecionar o campo.
  
1. Escolha **Mover para cima/para baixo** para definir a ordem ou arraste e solte os campos na posição desejada.

### <a name="combine-fields-manually"></a>Combinar os campos manualmente

Combine campos separados para criar um atributo mesclado.

1. Selecione **Combinar** > **Campos**. O painel Combinar campos é exibido.

1. Especifique a política do vencedor de mesclagem no menu suspenso **Combinar campos por**.

1. Selecione **Adicionar campo** para combinar mais campos.

1. Forneça um **Nome** e um **Nome do campo de saída**.

1. Selecione **Concluído** para aplicar as alterações.

### <a name="combine-a-group-of-fields"></a>Combinar um grupo de campos

Trate um grupo de campos como uma unidade. Por exemplo, se nossos registros contiverem os campos Endereço1, Endereço2, Cidade, Estado e CEP, não convém mesclar no Endereço2 de um registro diferente, achando que isso tornaria nossos dados mais completos.

1. Selecione **Combinar** > **Grupo de campos**.

1. Especifique a política do vencedor de mesclagem no menu suspenso **Classificar grupos por**.

1. Selecione **Adicionar** e escolha se deseja adicionar mais campos ou grupos aos campos.

1. Informe um **Nome** e um **Nome de saída** para cada campo combinado.

1. Informe um **Nome** para o grupo de campos.

1. Selecione **Concluído** para aplicar as alterações.

## <a name="configure-customer-id-generation"></a>Configurar geração de ID do cliente

Defina como gerar valores de ID do cliente, os identificadores exclusivos do perfil do cliente. A etapa de unificação de campos no processo de unificação de dados gera o identificador exclusivo do perfil do cliente. O identificador é a *CustomerId* na entidade *Cliente* resultante do processo de unificação de dados.

A *CustomerId*  é baseada em um hash do primeiro valor das chaves primárias de vencedores não nulos. Essas chaves vêm das entidades usadas na unificação de dados e são influenciadas pela ordem de correspondência. Portanto, a ID de cliente gerada pode ser alterada quando um valor de chave primária é alterado na entidade principal da ordem de correspondência. O valor da chave primária nem sempre representa o mesmo cliente.

Configurar um ID de cliente estável permite evitar esse comportamento.

1. Selecione a guia **Chaves**.

1. Passe o mouse sobre a linha **CustomerId** e selecione **Configurar**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controle para personalizar a geração de ID.":::

1. Selecione até cinco campos que contenham uma ID de cliente exclusiva e sejam mais estáveis. Os registros que não correspondem à sua configuração usam uma ID configurada pelo sistema.  

1. Selecione **Concluído**.

## <a name="group-profiles-into-households-or-clusters"></a>Perfis de grupo em famílias ou clusters

Você pode definir regras para agrupar perfis relacionados em um cluster. Atualmente, existem dois tipos de clusters disponíveis - clusters domésticos e customizados. O sistema escolhe automaticamente uma família com regras predefinidas se a entidade *Cliente* contiver os campos semânticos *Person.LastName* e *Location.Address*. Você também pode criar um cluster com suas próprias regras e condições, semelhantes a [regras de correspondência](match-entities.md#define-rules-for-match-pairs).

1. Selecione **Avançado** > **Criar cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Controle para criar um novo cluster.":::

1. Escolha entre um cluster **Doméstico** ou **Personalizado**. Se os campos semânticos *Person.LastName* e *Location.Address* existirem na entidade *Cliente*, a família é selecionada automaticamente.

1. Forneça um nome para o cluster e selecione **Finalizar**.

1. Selecione a guia **Clusters** para encontrar o cluster que você criou.

1. Especifique as regras e condições para definir seu cluster.

1. Selecione **Concluído**. O cluster é criado quando o processo de unificação é concluído. Os identificadores do cluster são adicionados como novos campos à entidade *Cliente*.

> [!div class="nextstepaction"]
> [Próxima etapa: Revisar a unificação](review-unification.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
