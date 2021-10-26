---
title: Mesclar entidades na unificação de dados
description: Mescle entidades para criar perfis de clientes unificados.
ms.date: 10/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-merge
ms.openlocfilehash: 6b3002b21ea043315e50724ec103aef8a3ced98e
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648240"
---
# <a name="merge-entities"></a>Mesclar entidades

A fase de mesclagem na última fase no processo de unificação de dados. Seu objetivo é reconciliar dados conflitantes. Exemplos de dados conflitantes podem incluir um nome de cliente encontrado em dois de seus conjuntos de dados, mas que mostra um pouco diferente em cada um ("Grant Marshall" versus "Grant Marshal") ou um número de telefone que difere no formato (617-803-091X versus 617803091X). A mesclagem desses pontos de dados conflitantes é feita atributo a atributo.

:::image type="content" source="media/merge-fields-page.png" alt-text="Página da mesclagem no processo de unificação de dados que mostra a tabela com campos mesclados que definem o perfil unificado do cliente.":::

Depois de concluir a [fase de correspondência](match-entities.md), você inicia a fase de mesclagem selecionando o bloco **Mesclar** na página **Unificar**.

## <a name="review-system-recommendations"></a>Revisar recomendações do sistema

Em **Dados** > **Unificar** > **Mesclar**, você escolhe e exclui atributos para mesclar dentro de sua entidade de perfil unificado do cliente. O perfil unificado do cliente é o resultado do processo de unificação dos dados. Alguns atributos são mesclados automaticamente pelo sistema.

Para ver os atributos incluídos em um de seus atributos mesclados automaticamente, selecione esse atributo mesclado na guia **Campos do cliente** da tabela. Os atributos que compõem esse atributo mesclado aparecem em duas novas linhas abaixo do atributo mesclado.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separar, renomear, excluir e editar campos mesclados

Você pode mudar a forma como o sistema processa atributos mesclados para gerar o perfil unificado do cliente. Selecione **Mostrar mais** e escolha o que você quer alterar.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opções no menu suspenso Mostrar mais para gerenciar atributos mesclados.":::

Para obter mais informações, consulte as seções a seguir.

## <a name="separate-merged-fields"></a>Separar campos mesclados

Para separar os campos mesclados, localize o atributo na tabela. Os campos separados aparecem como pontos de dados individuais no perfil unificado do cliente. 

1. Selecione o campo mesclado.
  
1. Selecione **Mostrar mais** e escolha **Campos separados**.
 
1. Confirme a separação.

1. Selecione **Salvar** e **Executar** para processar as alterações.

## <a name="rename-merged-fields"></a>Renomear campos mesclados

Altere o nome de exibição dos atributos mesclados. Não é possível alterar o nome da entidade de saída.

1. Selecione o campo mesclado.
  
1. Selecione **Mostrar mais** e escolha **Renomear**.

1. Confirme o nome de exibição alterado. 

1. Selecione **Salvar** e **Executar** para processar as alterações.

## <a name="exclude-merged-fields"></a>Excluir campos mesclados

Exclua um atributo do perfil unificado do cliente. Se o campo for usado em outros processos, por exemplo, em um segmento, remova-o desses processos antes de excluí-lo do perfil do cliente. 

1. Selecione um campo mesclado.
  
1. Selecione **Mostrar mais** e escolha **Excluir**.

1. Confirme a exclusão.

1. Selecione **Salvar** e **Executar** para processar as alterações. 

Na página **Meslar**, selecione **Campos excluídos** para ver a lista de todos os campos excluídos. Este painel lhe permite adicionar novamente campos excluídos.

## <a name="edit-a-merged-field"></a>Editar um campo mesclado

1.  Selecione um campo mesclado.

1.  Selecione **Mostrar mais** e escolha **Editar**.

1.  Especifique como combinar ou mesclar os campos de uma das três opções:
    - **Importância**: identifica o valor vencedor com base na classificação de importância especificada para os campos participantes. É a opção de mesclagem padrão. Selecione **Mover para cima/baixo** para definir a classificação de importância.
    :::image type="content" source="media/importance-merge-option.png" alt-text="Opção de importância na caixa de diálogo de campos de mesclagem."::: 
    - **Mais recente**: identifica o valor vencedor com base no maior nível de atualização. Requer uma data ou um campo numérico para cada entidade participante no escopo dos campos de mesclagem para definir o nível de atualização.
    :::image type="content" source="media/recency-merge-option.png" alt-text="Opção de nível de atualização na caixa de diálogo de campos de mesclagem.":::
    - **Menos recente**: identifica o valor vencedor com base no menor nível de atualização. Requer uma data ou um campo numérico para cada entidade participante no escopo dos campos de mesclagem para definir o nível de atualização.

1.  Você pode adicionar mais campos para participar do processo de mesclagem.

1.  Você pode renomear o campo mesclado.

1. Selecione **Concluído** para aplicar suas alterações.

1. Selecione **Salvar** e **Executar** para processar as alterações. 

## <a name="manually-combine-fields"></a>Combinar campos manualmente

Especifique um atributo mesclado manualmente. 

1. Na página **Mesclar**, selecione **Combinar campos**.

1. Especifique a política do vencedor de mesclagem no menu suspenso **Combinar campos por**.

1. Escolha um campo para adicionar. Selecione **Adicionar campos** para combinar outros campos.

1. Forneça um **Nome** e um **Nome do campo de saída**.

1. Selecione **Concluído** para aplicar as alterações.

1. Selecione **Salvar** e **Executar** para processar as alterações. 

## <a name="change-the-order-of-fields"></a>Alterar a ordem dos campos

Algumas entidades contêm mais detalhes que outras. Se uma entidade tiver os dados mais recentes sobre um campo, você pode priorizá-los sobre outras entidades ao mesclar valores.

1. Selecione o campo mesclado.
  
1. Selecione **Mostrar mais** e escolha **Editar**.

1. No painel **Combinar campos**, selecione **Mover para cima/para baixo** para definir a ordem ou arraste e solte-os na posição desejada.

1. Confirme a alteração.

1. Selecione **Salvar** e **Executar** para processar as alterações.

## <a name="configure-customer-id-generation"></a>Configurar geração de ID do cliente 

Após configurar os campos de mesclagem, você pode definir como gerar valores CustomerId, os identificadores exclusivos de perfil do cliente. A etapa de mesclagem no processo de unificação de dados gera o identificador exclusivo de perfil do cliente. O identificador é o CustomerId na entidade *Cliente* resultante do processo de unificação de dados. 

O CustomerId na entidade Cliente é baseado em um hash do primeiro valor das chaves primárias vencedoras não nulas. Essas chaves são obtidas das entidades usadas na fase de correspondência e mesclagem e são influenciadas pela ordem de correspondência. Portanto, o CustomerID gerado pode mudar quando um valor de chave primária muda na entidade primária da ordem de correspondência. Portanto, o valor da chave primária nem sempre representa o mesmo cliente.

Configurar um ID de cliente estável permite evitar esse comportamento.

**Configurar uma ID do cliente exclusiva**

1. Acesse **Unify** > **Mesclar**.

1. Selecione a guia **Chaves**. 

1. Passe o mouse sobre a linha **CustomerId** e selecione a opção **Configurar**.
   :::image type="content" source="media/customize-stable-id.png" alt-text="Controle para personalizar a geração de ID.":::

1. Selecione até cinco campos que contenham uma ID de cliente exclusiva e sejam mais estáveis. Os registros que não correspondem à sua configuração usam uma ID configurada pelo sistema.  

1. Selecione **Concluído** e execute o processo de mesclagem para aplicar as alterações.

## <a name="group-profiles-into-households-or-clusters"></a>Perfis de grupo em famílias ou clusters

Como parte do processo de configuração de geração de perfil de cliente, você pode definir regras para agrupar perfis relacionados em um cluster. Atualmente, existem dois tipos de clusters disponíveis - clusters domésticos e customizados. O sistema escolhe automaticamente uma família com regras predefinidas se a entidade *Cliente* contiver os campos semânticos *Person.LastName* e *Location.Address*. Você também pode criar um cluster com suas próprias regras e condições, semelhantes a [regras de correspondência](match-entities.md#define-rules-for-match-pairs).

**Defina uma família ou um cluster**

1. Acesse **Unify** > **Mesclar**.

1. Na guia **Mesclar**, selecione **Avançado** > **Criar cluster**.

   :::image type="content" source="media/create-cluster.png" alt-text="Controle para criar um novo cluster.":::

1. Escolha entre um cluster **Doméstico** ou **Personalizado**. Se os campos semânticos *Person.LastName* e *Location.Address* existirem na entidade *Cliente*, a família é selecionada automaticamente.

1. Forneça um nome para o cluster e selecione **Finalizar**.

1. Selecione a guia **Clusters** para encontrar o cluster que você criou.

1. Especifique as regras e condições para definir seu cluster.

1. Selecione **Executar** para executar o processo de mesclagem e criar o cluster.

Depois de executar o processo de mesclagem, os identificadores de cluster são adicionados como novos campos na entidade *Cliente*.

## <a name="run-your-merge"></a>Execute sua mesclagem

Quer você mescle atributos manualmente ou permita que o sistema os mescle, sempre é possível executar sua mesclagem. Selecione **Executar** na página **Mesclar** para iniciar o processo.

> [!div class="mx-imgBorder"]
> ![Salvar e Executar a mesclagem de dados.](media/configure-data-merge-save-run.png "Mesclagem de dados Salvar e Executar")

Escolha **Executar somente Mesclagem** se você só quiser ver a saída refletida na entidade unificada do cliente. Os processos posteriores serão atualizados conforme [definida agenda de atualização](system.md#schedule-tab).

Escolha **Executar processos de mesclagem e posteriores** para atualizar o sistema com suas alterações. Todos os processos, incluindo enriquecimento, segmentos e medidas, serão executados novamente automaticamente. Após o término de todos os processos posteriores, os perfis do cliente refletirão as alterações.

Para fazer mais alterações e executar a etapa novamente, cancele uma mesclagem em andamento. Selecione **Atualizando...** e selecione **Cancelar o trabalho** no painel lateral exibido.

> [!TIP]
> Depois de executar o processo de mesclagem, selecione o status do processo para abrir o painel **Detalhes da tarefa**. Ele oferece uma visão geral sobre o tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa. Selecione **Ver detalhes** para ver que entidades participaram do processo de correspondência, se a resolução de conflitos e as publicação das atualizações tiveram êxito.  
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies).  
> :::image type="content" source="media/process-detail-path.png" alt-text="Caminho detalhado para obter os detalhes do processo por meio do link de status da tarefa.":::

## <a name="next-step"></a>Próxima Etapa

Configurar [atividades](activities.md), [enriquecimento](enrichment-hub.md) ou [relacionamentos](relationships.md) para obter mais informações sobre seus clientes.

Se você já tiver configurado atividades, enriquecimento ou segmentos, eles serão processados automaticamente para usar os dados mais recentes do cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
