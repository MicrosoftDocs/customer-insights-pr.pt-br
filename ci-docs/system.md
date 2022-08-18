---
title: Exibir a configuração do sistema
description: Saiba sobre as configurações do sistema no Dynamics 365 Customer Insights.
ms.date: 08/09/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-system-status
- ci-system-about
- ci-system-general
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: 2498814a3d2e6330124fb97c036b9b310bcf1f7a
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9246233"
---
# <a name="view-system-configuration"></a>Exibir a configuração do sistema

Exiba informações do sistema, o status do sistema e uso da API.

## <a name="view-api-usage"></a>Exibir o uso da API

Exiba detalhes sobre o uso da API em tempo real e veja quais eventos aconteceram em um determinado período.

1. Acesse **Administrador** > **Sistema** e selecione a guia **Uso da API**.

1. **Selecione um período** a ser exibido.

   A página **Uso da API** contém três seções:

   - **Chamadas de API** - um gráfico que visualiza o número agregado de chamadas para a API no período selecionado.
   - **Transferência de dados** - um gráfico que mostra o volume de dados que foram transferidos por meio da API no período selecionado.
   - **Operações** - uma tabela com linhas para cada operação de API disponível e detalhes sobre o uso das operações. Selecione um nome de operação para acessar [a referência da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operações que usam a [ingestão de dados em tempo real](real-time-data-ingestion.md) contém um símbolo de binóculos para exibir o uso da API em tempo real.

   1. Selecione os binóculos para abrir o painel **Uso da API em tempo real** contendo detalhes de uso para a operação.
   1. **Selecione um período** a ser exibido.
   1. Use a caixa **Agrupar por** para escolher a melhor forma de apresentar suas interações em tempo real. Agrupe os dados pelo **Método** da API, **Nome qualificado da entidade** (entidade ingerida), **Criação de** (origem do evento), **Resultado** (êxito ou falha) ou **Códigos de erro**. Os dados estão disponíveis como um gráfico de histórico e como uma tabela.

## <a name="view-system-information"></a>Exibir informações do sistema

Exiba o nome de exibição do ambiente, a ID, a região, o tipo e a ID da sessão.

1. Acesse **Administrador** > **Sistema** e selecione a guia **Sobre**.

1. Para exibir o idioma e o país/região, selecione a guia **Geral**.

### <a name="update-preferred-language-or-countryregion"></a>Atualizar idioma preferido ou o país/região

O Customer Insights [oferece suporte a vários idiomas](/dynamics365/get-started/availability). O aplicativo usa sua preferência de idioma para exibir elementos como menu, texto de rótulo e mensagens do painel em seu idioma de preferência.

Os dados importados e as informações inseridas manualmente não são traduzidas.

1. Acesse **Administrador** > **Sistema** e selecione a guia **Geral**.

1. Para alterar seu idioma preferido, escolha um **Idioma** no menu suspenso.

1. Para alterar sua formatação preferida para datas, hora e números, use o menu suspenso **Formato de País/Região**. Uma visualização de formatação é exibida. O sistema sugere automaticamente uma seleção quando você escolher um novo idioma.

1. Selecione **Salvar**.

## <a name="view-system-status"></a>Exibir status do sistema

Acompanhe o andamento das tarefas, a ingestão de dados, a exportação de dados e vários outros processos importantes do produto. Examine as informações para garantir a conclusão de suas tarefas e processos ativos.

1. Acesse **Administrador** > **Sistema** e selecione a guia **Status**.

   O status e informações de processamento para vários processos são exibidos. Exiba o **Nome** da tarefa, o **Status** de sua execução mais recente e quando foi a **Ultima atualização**.

1. Para exibir os detalhes das várias últimas execuções selecione a tarefa ou o nome do processo.

1. Para exibir os detalhes do progresso de uma tarefa, selecione o status. O painel **Detalhes do progresso** é exibido.

   :::image type="content" source="media/system-progress-details.png" alt-text="Painel de detalhes do progresso do sistema":::

1. Para visualizar os detalhes do progresso de todas as tarefas, selecione **Todo o fluxo de trabalho**.

### <a name="status-definitions"></a>Definições de status

O sistema usa os seguintes status para as tarefas e os processos:

|Status  |Definição  |
|---------|---------|
|Cancelado(a) |A tarefa ou o processo foi cancelado pelo usuário antes de ser concluído.   |
|Falhou   |A tarefa ou processo apresentou erros.         |
|Falha  |Houve falha na tarefa ou no processo.  |
|Não Iniciado   |A fonte de dados ainda não tem dados ingeridos ou a tarefa ainda está no modo de rascunho.         |
|Processamento  |Tarefa ou processo em andamento.  |
|Atualizando    |Tarefa ou processo em andamento. Para cancelar esta operação, selecione **Atualizando** e **Cancelar o trabalho**. Parar a atualização de uma tarefa ou de um processo reverterá para o estado de sua última atualização.       |
|Ignorado  |A tarefa ou o processo foi ignorado. Um ou mais dos processos de downstream dos quais essa tarefa depende estão falhando ou foram ignorados.|
|Êxito  |A tarefa ou o processo foi concluído com êxito. Para fontes de dados, indica que os dados foram ingeridos com êxito se um horário for mencionado na coluna **Atualizado**.|
|Na Fila | O processamento está na fila e será iniciado assim que todas as tarefas e processos upstream forem concluídos. Para obter mais informações, consulte [Atualizar processos](#refresh-processes).|

### <a name="refresh-processes"></a>Processos de atualização

A atualização de tarefas e processos é executada de acordo com a [agenda configurada](schedule-refresh.md).

|Process  |Descrição  |
|---------|---------|
|Atividade  |É executada manualmente (atualização única). Depende do processo de mesclagem. Os insights dependem do seu processamento.|
|Vinculação de análise |É executada manualmente (atualização única). Depende dos segmentos.  |
|Preparação da análise |É executada manualmente (atualização única). Depende dos segmentos.  |
|Preparação de dados   |Precisa de uma entidade para executar. As entidades da fonte de dados dependem da ingestão. Entidades enriquecidas dependem de enriquecimentos. A entidade Cliente depende da fusão.  |
|Fontes de dados   |Não depende de nenhum outro processo. A correspondência depende da conclusão bem-sucedida desse processo.  |
|Enriquecimentos   |É executada manualmente (atualização única). Depende do processo de mesclagem. |
|Destinos de exportação |É executada manualmente (atualização única). Depende dos segmentos.  |
|Insights |É executada manualmente (atualização única). Depende dos segmentos.  |
|Inteligência   |Depende da mesclagem.   |
|Corresponder |Depende do processamento das fontes de dados usadas na definição de correspondência.      |
|Medidas  |É executada manualmente (atualização única). Depende do processo de mesclagem.  |
|Mesclagem   |Depende da conclusão do processo de correspondência. Segmentos, medidas, enriquecimento, pesquisa, atividades, previsões e preparação de dados dependem da conclusão bem-sucedida desse processo.   |
|Perfis   |É executada manualmente (atualização única). Depende do processo de mesclagem. |
|Pesquisa   |É executada manualmente (atualização única). Depende do processo de mesclagem. |
|Segmentos  |É executada manualmente (atualização única). Depende do processo de mesclagem. Os insights dependem do seu processamento.|
|Sistema   |Depende da conclusão do processo de correspondência. Segmentos, medidas, enriquecimento, pesquisa, atividades, previsões e preparação de dados dependem da conclusão bem-sucedida desse processo.   |
|Usuário  |É executada manualmente (atualização única). Depende das entidades.  |

Selecione o status de um processo para exibir os detalhes do andamento de todo o trabalho em que ele estava. Os processos de atualização acima podem ajudar a entender o que você pode fazer para tratar de uma tarefa ou de um processo **Ignorado** ou **Na Fila**.


[!INCLUDE [footer-include](includes/footer-banner.md)]
