---
title: Mesclar entidades na unificação de dados
description: Mescle entidades para criar perfis de clientes unificados.
ms.date: 05/10/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2cab702509596dd87c0c9b9769d1af8ba8387f9d
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085562"
---
# <a name="merge-entities"></a>Mesclar entidades

A fase de mesclagem na última fase no processo de unificação de dados. Seu objetivo é reconciliar dados conflitantes. Exemplos de dados conflitantes podem incluir um nome de cliente encontrado em dois de seus conjuntos de dados, mas que mostra um pouco diferente em cada um ("Grant Marshall" versus "Grant Marshal") ou um número de telefone que difere no formato (617-803-091X versus 617803091X). A mesclagem desses pontos de dados conflitantes é feita atributo a atributo.

:::image type="content" source="media/merge-fields-page.png" alt-text="Página da mesclagem no processo de unificação de dados mostrando a tabela com campos mesclados que definem o perfil unificado do cliente.":::

Depois de concluir a [fase de correspondência](match-entities.md), você inicia a fase de mesclagem selecionando o bloco **Mesclar** na página **Unificar**.

## <a name="review-system-recommendations"></a>Revisar recomendações do sistema

Em **Dados** > **Unificar** > **Mesclar**, você escolhe e exclui atributos para mesclar dentro de sua entidade de perfil unificado do cliente. O perfil unificado do cliente é o resultado do processo de unificação dos dados. Alguns atributos são mesclados automaticamente pelo sistema.

Para ver os atributos incluídos em um de seus atributos mesclados automaticamente, selecione esse atributo mesclado na guia **Campos do cliente** da tabela. Os atributos que compõem esse atributo mesclado aparecem em duas novas linhas abaixo do atributo mesclado.

## <a name="separate-rename-exclude-and-edit-merged-fields"></a>Separar, renomear, excluir e editar campos mesclados

Você pode mudar a forma como o sistema processa atributos mesclados para gerar o perfil unificado do cliente. Selecione **Mostrar mais** e escolha o que você quer alterar.

:::image type="content" source="media/manage-merged-attributes.png" alt-text="Opções do menu suspenso Mostrar mais para gerenciar atributos mesclados.":::

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

1. Selecione o campo mesclado.
  
1. Selecione **Mostrar mais** e escolha **Excluir**.

1. Confirme a exclusão.

1. Selecione **Salvar** e **Executar** para processar as alterações. 

Na página **Meslar**, selecione **Campos excluídos** para ver a lista de todos os campos excluídos. Este painel lhe permite adicionar novamente campos excluídos.

## <a name="manually-combine-fields"></a>Combinar campos manualmente

Especifique um atributo mesclado manualmente. 

1. Na página **Mesclar**, selecione **Combinar campos**.

1. Forneça um **Nome** e um **Nome do campo de saída**.

1. Escolha um campo para adicionar. Selecione **Adicionar campos** para combinar outros campos.

1. Confirme a exclusão.

1. Selecione **Salvar** e **Executar** para processar as alterações. 

## <a name="change-the-order-of-fields"></a>Alterar a ordem dos campos

Algumas entidades contêm mais detalhes que outras. Se uma entidade tiver os dados mais recentes sobre um campo, você pode priorizá-los sobre outras entidades ao mesclar valores.

1. Selecione o campo mesclado.
  
1. Selecione **Mostrar mais** e escolha **Editar**.

1. No painel **Combinar campos**, selecione **Mover para cima/para baixo** para definir a ordem ou arraste e solte-os na posição desejada.

1. Confirme a alteração.

1. Selecione **Salvar** e **Executar** para processar as alterações.

## <a name="run-your-merge"></a>Execute sua mesclagem

Quer você mescle atributos manualmente ou permita que o sistema os mescle, sempre é possível executar sua mesclagem. Selecione **Executar** na página **Mesclar** para iniciar o processo.

> [!div class="mx-imgBorder"]
> ![Mesclagem de dados Salvar e Executar](media/configure-data-merge-save-run.png "Mesclagem de dados Salvar e Executar")

Escolha **Executar somente Mesclagem** se você só quiser ver a saída refletida na entidade unificada do cliente. Os processos posteriores serão atualizados conforme [definida agenda de atualização](system.md#schedule-tab).

Escolha **Executar processos de mesclagem e posteriores** para atualizar o sistema com suas alterações. Todos os processos, incluindo enriquecimento, segmentos e medidas, serão executados novamente automaticamente. Após o término de todos os processos posteriores, os perfis do cliente refletirão as alterações.

Para fazer mais alterações e executar a etapa novamente, cancele uma mesclagem em andamento. Selecione **Atualizando...** e selecione **Cancelar o trabalho** no painel lateral exibido.

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="next-step"></a>Próxima Etapa

Configurar [atividades](activities.md), [enriquecimento](enrichment-hub.md) ou [relacionamentos](relationships.md) para obter mais informações sobre seus clientes.

Se você já tiver configurado atividades, enriquecimento ou segmentos, eles serão processados automaticamente para usar os dados mais recentes do cliente.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
