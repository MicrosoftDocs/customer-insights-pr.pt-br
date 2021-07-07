---
title: Configuração do sistema em insights do público
description: Saiba mais sobre as configurações do sistema na funcionalidade de insights de público-alvo do Dynamics 365 Customer Insights.
ms.date: 02/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 09d449e51a3a47ec916ab3d017419c9d9be1ffcf
ms.sourcegitcommit: 0b754d194d765afef70d1008db7b347dd1f0ee40
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305696"
---
# <a name="system-configuration"></a>Configuração do sistema

A página **Sistema** inclui as seguintes guias:
- [Status](#status-tab)
- [Agendar](#schedule-tab)
- [Uso da API](#api-usage-tab)
- [Sobre](#about-tab)
- [Geral](#general-tab)

> [!div class="mx-imgBorder"]
> ![Página do sistema](media/system-tabs.png "Página do sistema")

## <a name="status-tab"></a>Guia Status

A **guia Status** permite acompanhar o progresso da ingestão de dados, exportações de dados e vários outros processos importantes do produto. Revise as informações nesta guia para garantir a integridade dos processos ativos.

Esta guia inclui tabelas com status e informações de processamento para vários processos. Cada tabela rastreia o **Nome** da tarefa e sua entidade correspondente, o **Status** de sua execução mais recente e quando foi **Ultima atualização**.

Exiba os detalhes das últimas execuções das tarefas, selecionando seu nome.

### <a name="status-types"></a>Tipos de status

Existem seis tipos de status para tarefas. Os seguintes tipos de status também são exibidos na página *Corresponder*, *Mesclar*, *Fontes de dados*, *Segmentos*, *Medidas*, *Enriquecimento*, *Atividades* e *Previsões*:

- **Processamento:** a tarefa está em andamento. O status pode mudar para Bem-sucedido ou Falha.
- **Bem-sucedido:** tarefa concluída com sucesso.
- **Ignorada:** A tarefa foi ignorada. Um ou mais dos processos de downstream dos quais essa tarefa depende estão falhando ou foram ignorados.
- **Falha:** o processamento da tarefa falhou.
- **Cancelado:** o processamento foi cancelado pelo usuário antes de terminar.
- **Enfileirado:** O processamento está enfileirado e iniciará assim que todas as tarefas upstream forem concluídas. Para obter mais informações, consulte [Políticas de atualização](#refresh-policies).

### <a name="refresh-policies"></a>Políticas de atualização

Esta lista mostra as políticas de atualização para cada um dos processos principais:

- **Fontes de dados:** funciona de acordo com o [agendamento configurado](#schedule-tab). Não depende de nenhum outro processo. A correspondência depende da conclusão bem-sucedida desse processo.
- **Corresponder**: funciona de acordo com o [agendamento configurado](#schedule-tab). Depende do processamento das fontes de dados usadas na definição de correspondência. A mesclagem depende da conclusão bem-sucedida desse processo.
- **Mesclar**: funciona de acordo com o [agendamento configurado](#schedule-tab). Depende da conclusão do processo de correspondência. Segmentos, medidas, enriquecimento, pesquisa, atividades, previsões e preparação de dados dependem da conclusão bem-sucedida desse processo.
- **Segmentos**: executa manualmente (atualização única) e de acordo com o [agendamento configurado](#schedule-tab). Depende da mesclagem. Os insights dependem do seu processamento.
- **Medidas**: executa manualmente (atualização única) e de acordo com o [agendamento configurado](#schedule-tab). Depende da mesclagem.
- **Atividades**: executa manualmente (atualização única) e de acordo com o [agendamento configurado](#schedule-tab). Depende da mesclagem.
- **Enriquecimento**: executa manualmente (atualização única) e de acordo com o [agendamento configurado](#schedule-tab). Depende da mesclagem.
- **Pesquisar**: executa manualmente (atualização única) e de acordo com o [agendamento configurado](#schedule-tab). Depende da mesclagem.
- **Preparação de dados**: funciona de acordo com o [agendamento configurado](#schedule-tab). Depende da mesclagem.
- **Insights**: executa manualmente (atualização única) e de acordo com o [agendamento configurado](#schedule-tab). Depende dos segmentos.

Selecione o status de uma tarefa para ver os detalhes sobre o progresso de todo o trabalho em que ela estava. As políticas de atualização acima podem ajudar a entender o que você pode fazer para resolver uma tarefa **Ignorado** ou **Na fila**.

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

Existem duas opções na guia **Geral**: **Idioma** e **Formato de País/Região**.

A aplicação [suporta vários idiomas](supported-languages.md). Para alterar seu idioma preferido, escolha um **Idioma** no menu suspenso.

Para alterar sua formatação preferida para datas, hora e números, use o menu suspenso **Formato de País/Região**. Uma visualização de formatação é exibida nesse campo. O sistema irá sugerir automaticamente uma seleção quando você escolher um novo idioma.

Selecione **Salvar** para confirmar suas seleções.

## <a name="api-usage-tab"></a>Guia de uso da API

Encontre detalhes sobre o uso da API em tempo real e veja quais eventos aconteceram em um determinado período. Você pode escolher o período no menu suspenso **Selecionar um período**. 

O **Uso de API** contém três seções: 
- **Chamadas de API** - um gráfico que visualiza o número agregado de chamadas para a API no período selecionado.

- **Transferência de dados** - um gráfico que mostra o volume de dados que foram transferidos por meio da API no período selecionado.

-  **Operações** - uma tabela com linhas para cada operação de API disponível e detalhes sobre o uso das operações. Você pode selecionar um nome de operação para ir para [a referência da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

   Operações que usam [ingestão de dados em tempo real](real-time-data-ingestion.md) contêm um botão com um símbolo binocular para visualizar o uso da API em tempo real. Selecione o botão para abrir um painel lateral contendo detalhes de uso para o uso da API em tempo real no ambiente atual.   
   Use a caixa **Agrupar por** no painel **Uso da API em tempo real** para escolher a melhor forma de apresentar suas interações em tempo real. Você pode agrupar os dados pelo método API, nome qualificado da entidade (entidade ingerida), criado por (fonte do evento), resultado (êxito ou falha) ou códigos de erro. Os dados estão disponíveis como um gráfico de histórico e como uma tabela.


[!INCLUDE[footer-include](../includes/footer-banner.md)]