---
title: Configuração do sistema em insights do público
description: Saiba mais sobre as configurações do sistema na funcionalidade de insights de público-alvo do Dynamics 365 Customer Insights.
ms.date: 06/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: nimagen
manager: shellyha
ms.openlocfilehash: 7dd72e6512cd87ac70235d21667399298408db21
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405053"
---
# <a name="system-configuration"></a>Configuração do sistema

A página **Sistema** inclui quatro guias: **Status**, **Agenda**, **Sobre** e **Geral**.

> [!div class="mx-imgBorder"]
> ![Página do sistema](media/system-tabs.png "Página do sistema")

## <a name="status-tab"></a>Guia Status

A guia **Status** permite acompanhar o progresso da ingestão de dados, exportações de dados e vários processos importantes do produto. Revise as informações nesta guia para garantir a integridade dos processos ativos.

Essa guia inclui tabelas de status para **Fontes de dados**, **Processos do sistema** e **Preparação de dados**. Cada tabela rastreia o **Nome** da tarefa e sua entidade correspondente, o **Status** de sua execução mais recente e quando foi **Ultima atualização**.

Exiba os detalhes das últimas execuções das tarefas, selecionando seu nome.

### <a name="status-types"></a>Tipos de status

Existem seis tipos de status para tarefas. Os seguintes tipos de status também são exibidos na página *Corresponder*, *Mesclar*, *Fontes de dados*, *Segmentos*, *Medidas*, *Enriquecimento*, *Atividades* e *Previsões*:

- **Processamento:** a tarefa está em andamento. O status pode mudar para Bem-sucedido ou Falha.
- **Bem-sucedido:** tarefa concluída com sucesso.
- **Ignorada:** A tarefa foi ignorada. Um ou mais dos processos de downstream dos quais essa tarefa depende estão falhando ou foram ignorados.
- **Falha:** o processamento da tarefa falhou.
- **Cancelado:** o processamento foi cancelado pelo usuário antes de terminar.
- **Na fila:** o processamento está na fila e será iniciado assim que todas as tarefas posteriores forem concluídas. Para obter mais informações, consulte [Políticas de atualização](#refresh-policies).

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

Encontre detalhes sobre o uso da API em tempo real e veja quais eventos ocorreram em um determinado período. Para obter mais informações, consulte [Ingestão de dados em tempo real](real-time-data-ingestion.md).
