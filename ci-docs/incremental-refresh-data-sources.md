---
title: Atualização incremental para fontes de dados baseadas no Power Query
description: Atualize dados novos e atualizados para grandes fontes de dados baseadas no Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 3d21baf9804f300802b066df0183fc8f01abba9a
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645678"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Atualização incremental para fontes de dados baseadas no Power Query

Este artigo discute como configurar a atualização incremental para fontes de dados baseadas no Power Query.

A atualização incremental de fontes de dados oferece as seguintes vantagens:

- **Atualizações mais rápidas** - Apenas os dados que foram alterados são atualizados. Por exemplo, você pode atualizar apenas os últimos cinco dias de um conjunto de dados histórico.
- **Maior confiabilidade** - Com atualizações menores, você não precisa manter conexões com sistemas de fontes voláteis por tanto tempo, reduzindo o risco de problemas de conexão.
- **Consumo reduzido de recursos** - Atualizar apenas um subconjunto dos dados totais leva a um uso mais eficiente dos recursos de computação e diminui o volume ambiental.

## <a name="configure-incremental-refresh"></a>Configurar atualização incremental

O Customer Insights permite a atualização incremental de fontes de dados importadas por meio do Power Query que dão suporte à ingestão incremental. Por exemplo, bancos de dados SQL do Azure com campos de data e hora, que indicam quando os registros de dados foram atualizados pela última vez.

1. [Crie uma fonte de dados baseada no Power Query](connect-power-query.md).

1. Forneça um **Nome** para a fonte de dados.

1. Selecione uma fonte de dados que ofereça suporte à atualização incremental, como o [banco de dados SQL do Azure](/power-query/connectors/azuresqldatabase).

1. Selecione as entidades ou tabelas a serem ingeridas.

1. Conclua as etapas de transformação e selecione **Próximo**.

1. Na caixa de diálogo **Configurar atualização incremental**, selecione **Configurar** para abrir as **Configurações de atualização incremental**. Se você selecionar **Pular**, a fonte de dados atualizará todo o conjunto de dados.
   > [!TIP]
   > Você também pode aplicar a atualização incremental posteriormente editando uma fonte de dados existente.

1. Em **Configurações de atualização incremental**, você configurará a atualização incremental para todas as entidades selecionadas ao criar a fonte de dados.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Configurar entidades em uma fonte de dados para atualização incremental.":::

1. Selecione uma entidade e forneça os seguintes detalhes:

   - **Definir a chave primária** : Selecione uma chave primária para a entidade ou tabela.
   - **Defina o campo "última atualização"** : Este campo exibirá apenas atributos do tipo de data ou hora. Selecione um atributo que indica quando os registros foram atualizados pela última vez. Ele será usado para identificar os registros que se enquadram no período de atualização incremental.
   - **Verificar se há atualizações a cada** : Especifique quanto tempo você deseja que dure o período de atualização incremental.

1. Selecione **Salvar** para concluir a criação da fonte de dados. A atualização inicial dos dados será uma atualização completa. Posteriormente, a atualização incremental de dados acontece conforme configurado na etapa anterior.


[!INCLUDE [footer-include](includes/footer-banner.md)]
