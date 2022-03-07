---
title: Exportar dados do Customer Insights
description: Gerencie exportações para compartilhar dados.
ms.date: 03/25/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c1078ed0ba259a6e9cde3c7ede3570890ae48e67
ms.sourcegitcommit: 33a8e21b3bf6521bdb8346f81f79fce88091ddfd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "6016600"
---
# <a name="exports-preview-overview"></a>Visão geral de exportações (versão preliminar)

A página **Exportações** mostra todas as exportações configuradas. As exportações compartilham dados específicos com vários aplicativos. Elas podem incluir perfis ou entidades de clientes, esquemas e detalhes de mapeamento. Cada exportação requer uma [conexão, configurada por um administrador, para gerenciar a autenticação e o acesso](connections.md).

Vamos para **Dados** > **Exportações** para exibir a página de exportações. Todas as funções de usuário têm acesso para exibir exportações configuradas. Use o campo de pesquisa na barra de comandos para localizar exportações por nome, nome de conexão ou tipo de conexão.

## <a name="set-up-a-new-export"></a>Configurar uma nova exportação

Para configurar ou editar uma exportação, você precisa ter conexões disponíveis. As conexões dependem da sua [função de usuário](permissions.md):
- Os administradores têm acesso a todas as conexões. Eles também podem criar novas conexões ao configurar uma exportação.
- Os colaboradores podem ter acesso a conexões específicas. Eles dependem de administradores para configurar e compartilhar conexões. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os visualizadores podem apenas exibir exportações existentes, mas não podem criá-las.

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação** para criar um novo destino de exportação.

1. No painel **Configurar exportação**, selecione qual conexão usar. [Conexões](connections.md) são gerenciadas por administradores. 

1. Forneça os detalhes necessários e selecione **Salvar** para criar a exportação.

### <a name="edit-an-export"></a>Editar uma exportação

1. Selecione as reticências verticais do destino de exportação que você deseja editar.

1. Selecione **Editar** no menu suspenso.

1. Altere os valores que deseja atualizar e selecione **Salvar**.

## <a name="view-exports-and-export-details"></a>Exibir Exportações e detalhes de exportações

Depois de criar destinos de exportação, eles são listados em **Dados** > **Exportações**. Todos os usuários podem ver quais dados são compartilhados e seu status mais recente.

1. Vá para **Dados** > **Exportações**.

1. Usuários sem permissões de edição selecionam **Exibir** em vez de **Editar** para ver os detalhes da exportação.

1. Este painel lateral mostra a configuração desta exportação. Sem permissões de edição, você não pode alterar os valores. Selecione **Fechar** para retornar à página de exportações.

## <a name="run-exports-on-demand"></a>Executar exportações sob demanda

Depois de configurar uma exportação, ela será executada com cada [atualização agendada](system.md#schedule-tab) desde que tenha uma conexão funcionando.

Para exportar dados sem esperar por uma atualização agendada, vá para **Dados** > **Exportações**. Você tem duas opções:

- Para executar todas as exportações, selecione **Executar todas** na barra de comandos. 
- Para executar uma única exportação, selecione as reticências (...) em um item da lista e escolha **Executar**.

## <a name="remove-an-export"></a>Remover uma Exportação

1. Vá para **Dados** > **Exportações**.

1. Selecione as reticências verticais da Exportação que você deseja remover.

1. Selecione **Remover** no menu suspenso.

1. Confirme a remoção selecionando **Remover** na tela de confirmação.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
