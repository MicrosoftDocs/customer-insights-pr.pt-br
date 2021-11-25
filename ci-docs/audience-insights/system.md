---
title: Configuração do sistema em insights do público
description: Saiba mais sobre as configurações do sistema na funcionalidade de insights de público-alvo do Dynamics 365 Customer Insights.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1b790106f8b9617d0c1f244e1d15a74c7ef9a82b
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732347"
---
# <a name="system-configuration"></a>Configuração do sistema

Para acessar as configurações do sistema nos insights de público-alvo, na barra de navegação à esquerda, selecione **Administração** > **Sistema** para exibir uma lista de tarefas e processos do sistema.

A página **Sistema** inclui as seguintes guias:
- [Status](#status-tab)
- [Agendar](#schedule-tab)
- [Uso da API](#api-usage-tab)
- [Sobre](#about-tab)
- [Geral](#general-tab)
- [Segurança](#security-tab)

:::image type="content" source="media/system-tabs.png" alt-text="Guias de configurações na página do sistema.":::

## <a name="status-tab"></a>Guia Status

A guia **Status** permite que você acompanhe o andamento das tarefas, a ingestão de dados, a exportação de dados e vários outros processos importantes do produto. Examine as informações nesta guia para garantir a conclusão de suas tarefas e processos ativos.

Esta guia inclui tabelas com status e informações de processamento para vários processos. Cada tabela rastreia o **Nome** da tarefa e sua entidade correspondente, o **Status** de sua execução mais recente e quando foi **Ultima atualização**. Você pode exibir os detalhes das várias últimas execuções selecionando a tarefa ou o nome do processo. 

Selecione o status ao lado da tarefa ou do processo na coluna **Status** para abrir o painel **Detalhes do progresso**.

   :::image type="content" source="media/system-progress-details.png" alt-text="Painel de detalhes do progresso do sistema":::

### <a name="status-definitions"></a>Definições de status

O sistema usa os seguintes status para as tarefas e os processos:

|Status  |Definição  |
|---------|---------|
|Cancelada |O processamento foi cancelado pelo usuário antes de ser concluído.   |
|Falhou   |A ingestão de dados encontrou erros.         |
|Falha  |Houve falha no processamento.  |
|Não Iniciado   |A fonte de dados ainda não recebeu dados ou ainda está no modo de rascunho.         |
|Processamento  |Tarefa ou processo em andamento.  |
|Atualizando    |A ingestão de dados está em andamento. Você pode cancelar esta operação selecionando **Interromper atualização** na coluna **Ações**. Parar a atualização de uma fonte de dados a reverterá para seu estado da última atualização.       |
|Ignorado  |A tarefa ou o processo foi ignorado. Um ou mais dos processos de downstream dos quais essa tarefa depende estão falhando ou foram ignorados.|
|Êxito  |A tarefa ou o processo foi concluído com êxito. Para fontes de dados, indica que os dados foram ingeridos com êxito se um horário for mencionado na coluna **Atualizado**.|
|Na Fila | O processamento está na fila e será iniciado assim que todas as tarefas e processos upstream forem concluídos. Para obter mais informações, consulte [Atualizar processos](#refresh-processes).|

### <a name="refresh-processes"></a>Processos de atualização

A atualização de tarefas e processos é executada de acordo com a [agenda configurada](#schedule-tab). 

|Process  |Descrição  |
|---------|---------|
|Atividade  |É executada manualmente (atualização única). Depende do processo de mesclagem. Os insights dependem do seu processamento.|
|Vinculação de análise |É executada manualmente (atualização única). Depende dos segmentos.  |
|Preparação da análise |É executada manualmente (atualização única). Depende dos segmentos.  |
|Preparação de dados   |Depende da mesclagem.   |
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

## <a name="schedule-tab"></a>Guia Agendamento

Use a guia **Agendar** para agendar atualizações automáticas de todos as suas [fontes de dados ingeridos](data-sources.md). As atualizações automática ajudam a garantir que as atualizações de suas fontes de dados sejam refletidas no seus perfis de cliente unificado.

1. Nos insights de público-alvo, vá para **Admin** > **Sistema** e selecione a guia **Agendar**.

2. O estado padrão para a atualização agendada é **Desativado**. Para ativar as atualizações agendadas, altere a alternância na parte superior da tela para **Ativado**.

3. Escolha entre atualizações **Semanal** (padrão) e **Diária**. Se você pretende agendar atualizações semanais, selecione um ou mais dias nos quais deseja executar a atualização.

4. Defina seu **Fuso horário**, em seguida, use a lista suspensa **Tempo** para definir seu tempo de atualização. Ao concluir, selecione **Definir**. Se você deseja agendar várias atualizações em um único dia, selecione **Adicionar outra hora**.

5. Selecione **Salvar** para aplicar suas alterações.

## <a name="about-tab"></a>Guia Sobre

A guia **Sobre** contém o **Nome de exibição** de sua organização, o **ID do Ambiente** ativo, a **Região** e seu **ID da Sessão**. Se você tiver mais de um ambiente de trabalho, deverá fornecer a cada um deles um nome de exibição facilmente identificável.

## <a name="general-tab"></a>Guia Geral

Você pode alterar o idioma e o formato do país/região na aba **Geral**.

O Customer Insights [oferece suporte a vários idiomas](/dynamics365/get-started/availability). O aplicativo usa sua preferência de idioma para exibir elementos como menu, texto de rótulo e mensagens do painel em seu idioma de preferência.

Os dados importados e as informações inseridas manualmente não são traduzidas.

### <a name="update-the-settings"></a>Atualizar as configurações

Para alterar seu idioma preferido, escolha um **Idioma** no menu suspenso.

Para alterar sua formatação preferida para datas, hora e números, use o menu suspenso **Formato de País/Região**. Uma visualização de formatação é exibida nesse campo. O sistema irá sugerir automaticamente uma seleção quando você escolher um novo idioma.

Selecione **Salvar** para confirmar suas seleções.

## <a name="api-usage-tab"></a>Guia de uso da API

Encontre detalhes sobre o uso da API em tempo real e veja quais eventos aconteceram em um determinado período. Você pode escolher o período no menu suspenso **Selecionar um período**. 

O **Uso de API** contém três seções: 
- **Chamadas de API** - um gráfico que visualiza o número agregado de chamadas para a API no período selecionado.

- **Transferência de dados** - um gráfico que mostra o volume de dados que foram transferidos por meio da API no período selecionado.

-  **Operações** - uma tabela com linhas para cada operação de API disponível e detalhes sobre o uso das operações. Você pode selecionar um nome de operação para ir para [a referência da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operações que usam a [ingestão de dados em tempo real](real-time-data-ingestion.md) contém um botão com um símbolo de binóculos para exibir o uso da API em tempo real. Selecione o botão para abrir um painel lateral contendo detalhes de uso para o uso da API em tempo real no ambiente atual.   
   Use a caixa **Agrupar por** no painel **Uso da API em tempo real** para escolher a melhor forma de apresentar suas interações em tempo real. Você pode agrupar os dados pelo método API, nome qualificado da entidade (entidade ingerida), criado por (fonte do evento), resultado (êxito ou falha) ou códigos de erro. Os dados estão disponíveis como um gráfico de histórico e como uma tabela.

## <a name="security-tab"></a>Guia Segurança 

A guia **Segurança** permite que você vincule e gerencie seu próprio [Azure Key Vault](/azure/key-vault/general/basic-concepts) no ambiente.
O cofre de chaves dedicado pode ser usado para preparar e usar segredos nos limites de conformidade de uma organização. As percepções do público-alvo podem usar os segredos do Azure Key Vault para [configurar conexões](connections.md) para sistemas de terceiros.

Para obter mais informações, consulte [Trazer seu próprio Azure Key Vault](use-azure-key-vault.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
