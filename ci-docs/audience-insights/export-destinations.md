---
title: Exportar dados do Customer Insights
description: Gerencie exportações para compartilhar dados.
ms.date: 06/14/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: be4d142e0f9f422cac459f603aa5dd8bb490321cfe1b2de58f4a128ae56f4ba3
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034668"
---
# <a name="exports-preview-overview"></a>Visão geral de exportações (versão preliminar)

A página **Exportações** mostra todas as exportações configuradas. As exportações compartilham dados específicos com vários aplicativos. Elas podem incluir perfis ou entidades de clientes, esquemas e detalhes de mapeamento. Cada exportação requer uma [conexão, configurada por um administrador, para gerenciar a autenticação e o acesso](connections.md).

Vamos para **Dados** > **Exportações** para exibir a página de exportações. Todas as funções podem visualizar exportações configuradas. Use o campo de busca na barra de comandos para encontrar as exportações por nome, nome da conexão ou tipo da conexão.

## <a name="set-up-a-new-export"></a>Configurar uma nova exportação

Para configurar ou editar uma exportação, você precisa ter conexões disponíveis. As conexões dependem da sua [função de usuário](permissions.md):
- Os administradores têm acesso a todas as conexões. Eles também podem criar novas conexões ao configurar uma exportação.
- Os colaboradores podem ter acesso a conexões específicas. Eles dependem de administradores para configurar e compartilhar conexões. A lista de exportações mostra aos colaboradores se eles podem editar ou somente visualizar uma exportação na coluna **Suas permissões**. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).
- Os visualizadores podem apenas exibir exportações existentes, mas não podem criá-las.

### <a name="define-a-new-export"></a>Definir uma nova exportação

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação** para criar uma exportação.

1. No painel **Configurar exportação**, selecione qual conexão usar. [Conexões](connections.md) são gerenciadas por administradores. 

1. Forneça os detalhes necessários e selecione **Salvar** para criar a exportação.

### <a name="define-a-new-export-based-on-an-existing-export"></a>Definir uma nova exportação com base em uma exportação existente

1. Vá para **Dados** > **Exportações**.

1. Na lista de exportações, selecione a exportação que deseja duplicar.

1. Selecione **Criar duplicata** na barra de comando para abrir o painel **Configurar exportação** com os detalhes da exportação selecionada.

1. Examine e adapte a exportação e selecione **Salvar** para criar a exportação.

### <a name="edit-an-export"></a>Editar uma exportação

1. Vá para **Dados** > **Exportações**.

1. Na lista de exportações, selecione a exportação que deseja editar.

1. Selecione **Editar** na barra de comandos.

1. Altere os valores que deseja atualizar e selecione **Salvar**.

## <a name="view-exports-and-export-details"></a>Exibir exportações e detalhes de exportações

Depois que criar os destinos de exportação, eles serão listados em **Dados** > **Exportações**. Todos os usuários podem ver quais dados são compartilhados e seu status mais recente.

1. Vá para **Dados** > **Exportações**.

1. Os usuários sem as permissões de edição devem selecionar **Visualizar** em vez de **Editar** para ver os detalhes da exportação.

1. O painel lateral mostra a configuração de uma exportação. Sem permissões de edição, você não pode alterar os valores. Selecione **Fechar** para retornar à página de exportações.

## <a name="schedule-and-run-exports"></a>Agendar e executar exportações

Cada exportação que você configura tem uma agenda de atualizações. Durante uma atualização, o sistema procura dados novos ou atualizados para incluir em uma exportação. Por padrão, as exportações são executadas como parte de cada [atualização agendada do sistema](system.md#schedule-tab). Você pode personalizar a agenda de atualização ou desativá-la para executar as exportações manualmente.

As agendas de exportação dependem do estado do seu ambiente. Se houver atualizações em andamento nas [dependências](system.md#refresh-policies) quando uma exportação agendada precisar iniciar, o sistema primeiro concluirá as atualizações e depois fará a exportação. Você pode ver quando uma exportação foi atualizada pela última vez na coluna **Atualizada**.

### <a name="schedule-exports"></a>Agenda exportações

Você pode definir agendas de atualização personalizadas para exportações individuais ou várias exportações de uma vez. A agenda definida atualmente está listada na coluna **Agenda** da lista de exportação. A permissão para alterar a agenda é a mesma que para [editar e definir exportações](export-destinations.md#set-up-a-new-export). 

1. Vá para **Dados** > **Exportações**.

1. Selecione a exportação que você quer agendar.

1. Selecione **Agendar** na barra de comandos.

1. No painel **Agendar exportação**, defina a opção **Execução da agenda** como **Ativado** para executar a exportação automaticamente. Defina-o como **Desativado** para fazer a atualização manualmente.

1. Para exportações atualizadas automaticamente, escolha um valor de **Recorrência** e especifique os detalhes para ele. O tempo definido se aplicará a todas as instâncias de recorrência. É o momento em que uma exportação deve começar a ser atualizada.

1. Aplique e ative suas alterações selecionando **Salvar**.

Ao editar a agenda para várias exportações, você deve fazer uma seleção em **Manter ou substituir agendas**:
- **Manter agendas individuais**: persiste a agenda previamente definida para as exportações selecionadas e somente as habilita ou desabilita.
- **Definir uma nova agenda para todas as exportações selecionadas**: substitua as agendas existentes das exportações selecionadas.

### <a name="run-exports-on-demand"></a>Executar exportações sob demanda

Para exportar dados sem esperar por uma atualização agendada, vá para **Dados** > **Exportações**.

- Para executar todas as exportações, selecione **Executar todas** na barra de comandos. Esta ação executará somente as exportações que tenham uma agenda ativa.
- Para executar uma única exportação, selecione-a na lista e, em seguida, selecione **Executar** na barra de comando. É assim que as exportações sem agenda ativa são executadas. 

## <a name="remove-an-export"></a>Remover uma Exportação

1. Vá para **Dados** > **Exportações**.

1. Selecione a exportação que você deseja remover.

1. Selecione **Remover** na barra de comandos.

1. Confirme a remoção selecionando **Remover** na tela de confirmação.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
