---
title: Tarefas compartilhadas para cenários previsão
description: Saiba como gerenciar, solucionar problemas e refinar as previsões.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c4d269e1b542e84ade8c6e63c1dadace51ddde32
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645698"
---
# <a name="manage-predictions"></a>Gerenciar previsões

Este artigo discute algumas tarefas que a maioria dos cenários de previsão compartilham.

## <a name="troubleshoot-a-failed-prediction"></a>Solucionar uma previsão com falha

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione as reticências verticais ao lado da previsão para a qual deseja exibir os logs de erros.

1. Selecione **Logs**.

1. Revise todos os erros. Há vários tipos de erros que podem ocorrer e eles descrevem qual condição causou o erro. Por exemplo, um erro causado por dados insuficientes para gerar uma previsão de forma precisa é geralmente resolvido ao carregar dados adicionais no Customer Insights.

## <a name="input-data-usability-report"></a>Relatório de usabilidade de dados de entrada

O relatório de usabilidade de dados de entrada fornece uma visão consolidada dos erros e avisos que suas previsões predefinidas podem estar gerando. Ele também fornece recomendações sobre como melhorar o desempenho do modelo.

O relatório é disponibilizado depois que um modelo conclui seu processo de treinamento. Ele é criado para cada modelo separadamente, independentemente de ter sido concluído com sucesso ou não.

### <a name="view-the-input-data-usability-report"></a>Exibir o relatório de usabilidade de dados de entrada

Depois que um modelo pronto para uso tiver concluído sua etapa de treinamento, exiba o relatório:
- Selecione as reticências ao lado do nome do modelo e escolha **Relatório de usabilidade de dados de entrada**.
- Selecione o status de um modelo em **Ver Relatório de usabilidade de dados de entrada** no painel lateral.
- Selecione um dos modelos na lista e, em seguida, selecione **Relatório de usabilidade de dados de entrada** na barra de comando.
- Abra a página de resultados do modelo e selecione **Relatório de usabilidade de dados de entrada** na barra de comando.

### <a name="information-in-the-input-data-usability-report"></a>Informações no relatório de usabilidade de dados de entrada

As colunas a seguir no relatório contêm informações úteis para aprimorar os dados do modelo.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo de um relatório de usabilidade de dados de entrada mostrando uma tabela com erros, avisos e recomendações.":::

- **Nome:** nome descritivo do erro, aviso ou recomendação.
- **Etapa:** fase de modelagem, treinamento ou pontuação, a que se referem as informações.
- **Estado:** gravidade das informações (erro, aviso, recomendação).
- **Nome da coluna:** coluna em uma entidade que deve ser modificada para melhorar o desempenho do modelo.
- **Nome da entidade:** nome da entidade que deve ser modificada para melhorar o desempenho do modelo.
- **Detalhes:** detalhes sobre o erro, aviso ou recomendação.

## <a name="refresh-a-prediction"></a>Atualizar uma previsão

As previsões serão atualizadas automaticamente no mesmo [cronograma de atualização dos dados](system.md#schedule-tab) conforme definido nas configurações. Você também pode atualizá-las manualmente.

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione os três pontos verticais ao lado da previsão que deseja atualizar.

1. Selecione **Atualizar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="delete-a-prediction"></a>Excluir uma previsão

A exclusão de uma previsão também remove sua entidade de saída.

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione os três pontos verticais ao lado da previsão que deseja excluir.

1. Selecione **Excluir**.
