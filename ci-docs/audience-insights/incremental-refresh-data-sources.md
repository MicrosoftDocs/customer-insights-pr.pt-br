---
title: Atualização incremental de fontes de dados baseadas no Power Query
description: Atualize dados novos e atualizados de grandes fontes de dados baseadas no Power Query.
ms.date: 09/28/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 1af2e4c42dc5890556c90bb3e5ef1aeb0621fda0
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6554145"
---
# <a name="incremental-refresh-for-data-sources-based-on-power-query"></a>Atualização incremental de fontes de dados baseadas no Power Query

A atualização incremental de fontes de dados oferece as seguintes vantagens:

- **Atualizações mais rápidas** - Apenas os dados que foram alterados são atualizados. Por exemplo, você pode atualizar apenas os últimos cinco dias de um conjunto de dados histórico.
- **Maior confiabilidade** - Com atualizações menores, você não precisa manter conexões com sistemas de fontes voláteis por tanto tempo, reduzindo o risco de problemas de conexão.
- **Consumo reduzido de recursos** - Atualizar apenas um subconjunto dos dados totais leva a um uso mais eficiente dos recursos de computação e diminui o volume ambiental.

## <a name="configure-incremental-refresh"></a>Configurar atualização incremental

Os insights de público-alvo permitem a atualização incremental de fontes de dados importadas por meio do Power Query que oferecem suporte à ingestão incremental. Por exemplo, bancos de dados SQL do Azure com campos de data e hora, que indicam quando os registros de dados foram atualizados pela última vez.

1. [Criar uma nova fonte de dados baseada no Power Query](connect-power-query.md).

1. Forneça um nome para a fonte de dados.

1. Selecione uma fonte de dados que ofereça suporte à atualização incremental, como o banco de dados SQL do Azure.

1. Selecione as entidades ou tabelas a serem ingeridas.

1. Conclua as etapas de transformação e selecione **Próximo**.

1. Na caixa de diálogo **Configurar atualização incremental**, selecione **Configurar** para abrir as **Configurações de atualização incremental**. Se você selecionar **Pular**, a fonte de dados atualizará todo o conjunto de dados.
   > [!TIP]
   > Você também pode aplicar a atualização incremental posteriormente editando uma fonte de dados existente.

1. Em **Configurações de atualização incremental**, você configurará a atualização incremental para todas as entidades selecionadas ao criar a fonte de dados.

   > [!div class="mx-imgBorder"]
   > ![Configurar entidades em uma fonte de dados para atualização incremental.](media/incremental-refresh-settings.png "Configurar entidades em uma fonte de dados para atualização incremental")

1. Selecione uma entidade e forneça os seguintes detalhes:

   - **Definir a chave primária** : Selecione uma chave primária para a entidade ou tabela.
   - **Defina o campo "última atualização"** : Este campo exibirá apenas atributos do tipo de data ou hora. Selecione um atributo que indica quando os registros foram atualizados pela última vez. Ele será usado para identificar os registros que se enquadram no período de atualização incremental.
   - **Verificar se há atualizações a cada** : Especifique quanto tempo você deseja que dure o período de atualização incremental.

1. Selecione **Salvar** para concluir a criação da fonte de dados. A atualização inicial dos dados será uma atualização completa. Posteriormente, a atualização incremental de dados acontece conforme configurado na etapa anterior.


[!INCLUDE[footer-include](../includes/footer-banner.md)]