---
title: Exportar dados do Customer Insights
description: Gerencie exportações para compartilhar dados.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 45a4c964e9810640c764357a72b9794f4fda89f4
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623087"
---
# <a name="exports-preview-overview"></a>Visão geral de exportações (versão preliminar)

A página **Exportações** mostra todas as exportações configuradas. As exportações compartilham dados específicos com vários aplicativos. Estes podem incluir perfis de clientes, entidades, esquemas e detalhes de mapeamento. Cada exportação requer uma [conexão, configurada por um administrador, para gerenciar a autenticação e o acesso](connections.md).

Vamos para **Dados** > **Exportações** para exibir a página de exportações. Todas as funções podem visualizar exportações configuradas. Use o campo de busca na barra de comandos para encontrar as exportações por nome, nome da conexão ou tipo da conexão.

## <a name="export-types"></a>Tipos de exportação

Há dois tipos principais de exportações:  

- **Exportações de saída de dados** permitem exportar qualquer tipo de entidade disponível nos insights do público-alvo. As entidades selecionadas para exportação são exportadas com todos os campos de dados, metadados, esquemas e detalhes de mapeamento. 
- **Exportações de segmento** permitem exportar entidades de segmento de insights do público-alvo. Os segmentos representam uma lista de perfis de clientes. Ao configurar a exportação, você seleciona os campos de dados incluídos, dependendo do sistema de destino para o qual você está exportando os dados. 

### <a name="export-segments"></a>Exportar segmentos

**Exportar segmentos em ambientes para contas comerciais (B2B) ou clientes individuais (B2C)**  
A maioria das opções de exportação oferece suporte a ambos os tipos de ambientes. Exportar segmentos para vários sistemas de destino possui requisitos específicos. De modo geral, um membro do segmento, o perfil do cliente, contém informações de contato. Embora este seja geralmente o caso de segmentos construídos sobre clientes individuais (B2C), não é necessariamente o caso de segmentos baseados em contas comerciais (B2B). 

**Ambientes de exportação de segmento para contas comerciais (B2B)**  
- Os segmentos no contexto de ambientes para contas comerciais são construídos na entidade *conta*. Para exportar segmentos de conta como estão, o sistema de destino precisa oferecer suporte a segmentos de conta puros. Este é o caso do [LinkedIn](export-linkedin-ads.md) quando você escolhe a opção **empresa** ao definir a exportação.
- Todos os outros sistemas de destino exigem campos da entidade de contato. Para garantir que os segmentos de conta possam recuperar dados de contatos relacionados, sua definição de segmento precisa projetar atributos da entidade de contato. Saiba mais sobre como [configurar segmentos e atributos do projeto](segment-builder.md).

**Exportações de segmento em ambientes para clientes pessoa física (B2C)**  
- Os segmentos no contexto de ambientes para contas individuais são construídos na entidade *conta de cliente unificada*. Cada segmento que atende às exigências dos sistemas-alvo (por exemplo, um endereço de email) pode ser exportado.

**Limites nas exportações de segmento**  
- Os sistemas de destino de terceiros podem limitar o número de perfis de clientes que você pode exportar. 
- Para clientes individuais, você verá o número real de membros do segmento ao selecionar um segmento para exportação. Você receberá um aviso se um segmento for muito grande. 
- Para contas comerciais, você verá o número de contas em um segmento; no entanto, o número de contatos que podem ser projetados não aparece. Em alguns casos, isso pode fazer com que o segmento exportado contenha, na verdade, mais perfis de clientes do que o sistema de destino aceita. Exceder os limites dos resultados dos sistemas de destino irá ignorar a exportação. 

## <a name="set-up-a-new-export"></a>Configurar uma nova exportação  
Para configurar ou editar uma exportação, você precisa ter conexões disponíveis. As conexões dependem da sua [função de usuário](permissions.md):
- **Administradores** têm acesso a todas as conexões. Eles também podem criar novas conexões ao configurar uma exportação.
- **Colaboradores** podem ter acesso a conexões específicas. Eles dependem de administradores para configurar e compartilhar conexões. A lista de exportações mostra aos colaboradores se eles podem editar ou somente visualizar uma exportação na coluna **Suas permissões**. Para obter mais informações, vá para [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Visualizadores** só podem ver as exportações existentes - não criá-las.

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
