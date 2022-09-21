---
title: Visão geral de exportações (versão preliminar)
description: Gerencie exportações para compartilhar dados.
ms.date: 08/12/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- ci-connections
- customerInsights
ms.openlocfilehash: 44f58d694b9bd35a8d8c04d487d40743291e0566
ms.sourcegitcommit: ef3e17134d44d2731605381ea0385dbc5aef6120
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2022
ms.locfileid: "9460176"
---
# <a name="exports-preview-overview"></a>Visão geral de exportações (versão preliminar)

 As exportações permitem compartilhar dados específicos com vários aplicativos. Estes podem incluir perfis de clientes, entidades, esquemas e detalhes de mapeamento. Cada exportação requer uma [conexão, configurada por um administrador, para gerenciar a autenticação e o acesso](connections.md). A página **Exportações** mostra todas as exportações configuradas.

## <a name="export-types"></a>Tipos de exportação

Há dois tipos principais de exportações:  

- **Exportações de saída de dados** permitem exportar qualquer tipo de entidade disponível no Customer Insights. As entidades selecionadas para exportação são exportadas com todos os campos de dados, metadados, esquemas e detalhes de mapeamento.
- **Exportações de segmento** permitem exportar entidades de segmento do Customer Insights. Para consumidores individuais (B-to-C), os segmentos representam uma lista de perfis de clientes. Para empresas (B-to-B), [segmentos podem representar uma lista de contas ou contatos](segment-builder.md#create-a-new-segment-with-segment-builder). Ao configurar a exportação, você seleciona os campos de dados incluídos, dependendo do sistema de destino para o qual está exportando os dados.

### <a name="export-segments"></a>Exportar segmentos

**Exportar segmentos em ambientes para contas comerciais (B2B) ou clientes individuais (B2C)**  
A maioria das opções de exportação aceitam os dois tipos de ambientes. A exportação de segmentos para vários sistemas de destino tem requisitos específicos. 

**Exportações de segmento em ambientes para clientes individuais (B2C)**  
- Os segmentos no contexto de ambientes para contas individuais são construídos na entidade *conta de cliente unificada*. Cada segmento que atende às exigências dos sistemas-alvo (por exemplo, um endereço de email) pode ser exportado.

**Exportação de segmentos em ambientes para contas comerciais (B-to-B)**  
- Os segmentos no contexto de ambientes para contas comerciais são criados na entidade *conta* ou na entidade *contato*. Para exportar segmentos de conta como estão, o sistema de destino precisa oferecer suporte a segmentos de conta puros. Este é o caso do [LinkedIn](export-linkedin-ads.md) quando você escolhe a opção **empresa** ao definir a exportação.
- Todos os outros sistemas de destino exigem campos da entidade de contato.
- Com dois tipos de segmento (contatos e contas), o Customer Insights identifica automaticamente quais tipos de segmentos são elegíveis para exportação com base no sistema de destino. Por exemplo, para um sistema de destino focado em contato como o MailChimp, o Customer Insights só permite que você escolha segmentos de contato para exportar.

**Limites nas exportações de segmento**  
- Os sistemas de destino de terceiros podem limitar o número de perfis de clientes que você pode exportar. 
- Para clientes individuais, você verá o número real de membros do segmento ao selecionar um segmento para exportação. Você receberá um aviso se um segmento for muito grande. 
- Para contas comerciais, você verá o número de contas ou contatos dependendo do segmento. Você receberá um aviso se o segmento for muito grande. Exceder os limites dos resultados dos sistemas de destino irá ignorar a exportação.

## <a name="set-up-a-new-export"></a>Configurar uma nova exportação

Para configurar ou editar uma exportação, você precisa ter as conexões certas disponíveis. As conexões dependem da sua [função de usuário](permissions.md):
- **Administradores** têm acesso a todas as conexões. Eles também podem criar novas conexões ao configurar uma exportação.
- **Colaboradores** podem ter acesso a conexões específicas. Eles dependem de administradores para configurar e compartilhar conexões. A lista de exportações mostra aos colaboradores se eles podem editar ou somente visualizar uma exportação na coluna **Suas permissões**. Para obter mais informações, vá para [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).
- **Visualizadores** só podem ver as exportações existentes - não criá-las.

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação** para criar uma exportação.

1. No painel **Configurar exportação**, selecione qual [conexão](connections.md) usar.

1. Forneça os detalhes necessários e selecione **Salvar** para criar a exportação. Para obter os detalhes necessários, leia a documentação do Customer Insights referente à exportação específica.

## <a name="manage-existing-exports"></a>Gerenciar exportações existentes

Vá para **Dados** > **Exportações** para ver as exportações, o nome da conexão, o tipo de conexão e o status. Todas as funções podem visualizar exportações configuradas. Você pode classificar a lista de exportações por qualquer coluna ou usar a caixa de pesquisa para encontrar a exportação que deseja gerenciar.

Selecione uma exportação para exibir as ações disponíveis.

:::image type="content" source="media/exports_showmore.png" alt-text="Página Exportações.":::

- **Visualizar** ou **Editar** a exportação. Os usuários sem as permissões de edição devem selecionar **Visualizar** em vez de **Editar** para ver os detalhes da exportação.
- **Executar** a exportação para exportar os dados mais recentes.
- **Criar duplicidade** de uma exportação.
- **[Agendar](#schedule-and-run-exports)** a exportação.
- **Desanexar conexão** para remover a conexão dessa exportação. Desanexar não remove a conexão, mas desativa a exportação. A coluna **Conexão usada** exibe Sem Conexão.
- **Remover** a exportação.

## <a name="schedule-and-run-exports"></a>Agendar e executar exportações

Cada exportação que você configura tem uma agenda de atualizações. Durante uma atualização, o sistema procura dados novos ou atualizados para incluir em uma exportação. Por padrão, as exportações são executadas como parte de cada [atualização agendada do sistema](schedule-refresh.md). Você pode personalizar a agenda de atualização ou desativá-la para executar as exportações manualmente.

> [!TIP]
> Minimize o tempo de processamento das exportações do segmento com as seguintes práticas recomendadas:
> - Distribua entidades de segmento em várias exportações.
> - Evite agendar todas as exportações ao mesmo tempo. Deixe 30 minutos ou uma hora entre o horário programado de cada exportação.

As agendas de exportação dependem do estado do seu ambiente. Se houver atualizações em andamento nas [dependências](system.md#refresh-processes) quando uma exportação agendada precisar iniciar, o sistema primeiro concluirá as atualizações e depois fará a exportação. A coluna **Atualizada** mostra quando uma exportação foi atualizada pela última vez.

### <a name="schedule-exports"></a>Agenda exportações

Defina agendas de atualização personalizadas para exportações individuais ou várias exportações de uma vez. A agenda definida atualmente está listada na coluna **Agenda** da lista de exportação. A permissão para alterar a agenda é a mesma para [editar e definir exportações](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Selecione a exportação que você quer agendar.

1. Selecione **Agendar**.

1. No painel **Agendar exportação**, defina a opção **Execução da agenda** como **Ativado** para executar a exportação automaticamente. Defina-o como **Desativado** para fazer a atualização manualmente.

1. Para exportações atualizadas automaticamente, escolha um valor de **Recorrência** e especifique os detalhes para ele. O tempo definido se aplicará a todas as instâncias de recorrência. É o momento em que uma exportação deve começar a ser atualizada.

1. Selecione **Salvar**.

Ao editar a agenda para várias exportações, faça uma seleção em **Manter ou substituir agendas**:

- **Manter agendas individuais**: mantém a agenda previamente definida para as exportações selecionadas e somente as habilita ou desabilita.
- **Definir uma nova agenda para todas as exportações selecionadas**: substitua as agendas existentes das exportações selecionadas.

### <a name="run-exports-on-demand"></a>Executar exportações sob demanda

Para exportar dados sem esperar por uma atualização agendada, vá para **Dados** > **Exportações**.

- Para executar todas as exportações, selecione **Executar todas** na barra de comandos. Somente as exportações que têm uma agenda ativa são executadas. Para executar uma exportação que não está ativa, execute uma única exportação.
- Para executar uma única exportação, selecione-a na lista e, em seguida, selecione **Executar** na barra de comando.

## <a name="troubleshooting"></a>Solução de Problemas

### <a name="segment-not-eligible-for-export"></a>Segmento não qualificado para exportação

**Problema** Em um ambiente de contas comerciais, suas exportações falharão com a mensagem de erro: "O segmento a seguir não é elegível para este destino de exportação: "{nome do segmento}". Escolha apenas segmentos do tipo ContactProfile e tente novamente."

**Resolução** Os ambientes do Customer Insights para contas comerciais foram atualizados para oferecer suporte a segmentos de contato, além de segmentos de conta. Devido a essa mudança, as exportações que precisam de detalhes de contato funcionam apenas com segmentos baseados em contatos.

1. [Crie um segmento com base em contatos](segment-builder.md) que corresponde ao segmento usado anteriormente.

1. Uma vez executado esse segmento de contato, edite a respectiva exportação e selecione o novo segmento.

1. Selecione **Salvar** para salvar a configuração ou **Salvar e executar** para testar essa exportação imediatamente.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
