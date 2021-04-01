---
title: Mesclar entidades na unificação de dados
description: Mescle entidades para criar perfis de clientes unificados.
ms.date: 04/16/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 737c593353878a5e322488d00de5dc5db5befda9
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597819"
---
# <a name="merge-entities"></a>Mesclar entidades

A fase de mesclagem na última fase no processo de unificação de dados. Seu objetivo é reconciliar dados conflitantes. Exemplos de dados conflitantes podem incluir um nome de cliente encontrado em dois de seus conjuntos de dados, mas que mostra um pouco diferente em cada um ("Grant Marshall" versus "Grant Marshal") ou um número de telefone que difere no formato (617-803-091X versus 617803091X). A mesclagem desses pontos de dados conflitantes é feita atributo a atributo.

Depois de concluir a [fase de correspondência](match-entities.md), você inicia a fase de mesclagem selecionando o bloco **Mesclar** na página **Unificar**.

## <a name="review-system-recommendations"></a>Revisar recomendações do sistema

Na página **Mesclar**, você pode escolher e excluir atributos para mesclar a sua entidade de perfil de cliente unificado (o resultado do processo de configuração). Alguns atributos são mesclados automaticamente pelo sistema.

### <a name="view-merged-attributes"></a>Exibir atributos mesclados

Para exibir os atributos incluídos em um dos atributos mesclados automaticamente, selecione esse atributo mesclado. Os dois atributos que compõem esse atributo mesclado são exibidos em duas novas linhas abaixo do atributo mesclado.

> [!div class="mx-imgBorder"]
> ![Selecionar atributo mesclado](media/configure-data-merge-profile-attributes.png "Selecionar atributo mesclado")

### <a name="separate-merged-attributes"></a>Separar atributos mesclados

Para separar ou desmembrar qualquer um dos atributos mesclados automaticamente, localize o atributo na tabela **Atributos do perfil**.

1. Selecione o botão de reticências (...).
  
2. Na lista suspensa, selecione **Campos separados**.

### <a name="remove-merged-attributes"></a>Remova os atributos mesclados

Para excluir um atributo da entidade do perfil do cliente final, localize-o na tabela **Atributos do perfil**.

1. Selecione o botão de reticências (...).
  
2. Na lista suspensa, selecione **Não mesclar**.

   O atributo é movido para a seção **Removido do registro do cliente**.

## <a name="manually-add-a-merged-attribute"></a>Adicionar manualmente um atributo mesclado

Para adicionar um atributo mesclado, vá para a página **Mesclar**.

1. Selecione **Adicionar atributo mesclado**.

2. Forneça um **Nome** para identificá-lo na página **Mesclar** posteriormente.

3. Se preferir, forneça um **Nome para exibição** para aparecer na entidade unificada do Perfil do Cliente.

4. Configure **Selecionar atributos duplicados** para selecionar os atributos que você deseja mesclar nas entidades correspondentes. Você também pode procurar por atributos.

5. Defina **Classificar por importância** para priorizar um atributo acima dos outros. Por exemplo, se a entidade *WebAccountCSV* tiver os dados mais precisos sobre o atributo *Nomes Completos*, você pode priorizar essa entidade em vez de *ContactCSV*, selecionando *WebAccountCSV*. Como um resultado, *WebAccountCSV* passa para a primeira prioridade, enquanto *ContactCSV* passa para a segunda prioridade ao extrair valores para o atributo *Nome Completo*.

## <a name="run-your-merge"></a>Execute sua mesclagem

Quer você mescle atributos manualmente ou permita que o sistema os mescle, sempre é possível executar sua mesclagem. Selecione **Executar** na página **Mesclar** para iniciar o processo.

> [!div class="mx-imgBorder"]
> ![Mesclagem de dados Salvar e Executar](media/configure-data-merge-save-run.png "Mesclagem de dados Salvar e Executar")

Para fazer alterações adicionais e executar novamente a etapa, você pode cancelar uma mesclagem em andamento. Selecione **Atualizando...** e selecione **Cancelar o trabalho** no painel lateral exibido.

Após o texto **Atualizando...** mudar para **Bem-sucedido**, a mesclagem concluiu e resolveu as contradições nos seus dados de acordo com as políticas que você definiu. Atributos mesclados e não mesclados são incluídos na entidade de perfil unificado. Atributos excluídos não estão incluídos na entidade de perfil unificado.

Se não foi a primeira vez que você executou uma mesclagem com êxito, todos os processos posteriores, incluindo enriquecimento, segmentação e medidas, serão executados novamente de forma automática. Depois que todos os processos posteriores foram executados novamente, os perfis dos clientes refletem todas as alterações feitas.

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="next-step"></a>Próxima Etapa

Configurar [atividades](activities.md), [enriquecimento](enrichment-microsoft-graph.md) ou [relacionamentos](relationships.md) para obter mais informações sobre seus clientes.

Se você já configurou atividades, enriquecimento ou relacionamentos, ou se definiu segmentos, eles serão processados automaticamente para usar os dados mais recentes do cliente.




[!INCLUDE[footer-include](../includes/footer-banner.md)]