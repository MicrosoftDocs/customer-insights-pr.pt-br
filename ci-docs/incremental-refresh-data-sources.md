---
title: Atualização incremental para fontes de dados do Power Query e do Azure Data Lake
description: Atualize dados novos e atualizados para grandes fontes de dados com base em fontes de dados do Power Query ou do Azure Data Lake.
ms.date: 05/30/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: bff27bf7fec2bcb741846ae76bb1f616f459136c
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9012011"
---
# <a name="incremental-refresh-for-power-query-and-azure-data-lake-data-sources"></a>Atualização incremental para fontes de dados do Power Query e do Azure Data Lake

Este artigo discute como configurar a atualização incremental para fontes de dados baseadas no Power Query ou no Azure Data Lake.

A atualização incremental de fontes de dados oferece as seguintes vantagens:

- **Atualizações mais rápidas** - Apenas os dados que foram alterados são atualizados. Por exemplo, você pode atualizar apenas os últimos cinco dias de um conjunto de dados histórico.
- **Maior confiabilidade** - Com atualizações menores, você não precisa manter conexões com sistemas de fontes voláteis por tanto tempo, reduzindo o risco de problemas de conexão.
- **Consumo reduzido de recursos** - Atualizar apenas um subconjunto dos dados totais leva a um uso mais eficiente dos recursos de computação e diminui o volume ambiental.

## <a name="configure-incremental-refresh-for-data-sources-based-on-power-query"></a>Configurar a atualização incremental para fontes de dados baseadas no Power Query

O Customer Insights permite a atualização incremental de fontes de dados importadas por meio do Power Query que dão suporte à ingestão incremental. Por exemplo, bancos de dados SQL do Azure com campos de data e hora, que indicam quando os registros de dados foram atualizados pela última vez.

1. [Crie uma fonte de dados baseada no Power Query](connect-power-query.md).

1. Selecione uma fonte de dados que ofereça suporte à atualização incremental, como o [banco de dados SQL do Azure](/power-query/connectors/azuresqldatabase).

1. Selecione as entidades ou tabelas a serem ingeridas.

1. Conclua as etapas de transformação e selecione **Próximo**.

1. Na caixa de diálogo **Configurar atualização incremental**, selecione **Configurar** para abrir as **Configurações de atualização incremental**. Se você selecionar **Pular**, a fonte de dados atualizará todo o conjunto de dados.
   > [!TIP]
   > Você também pode aplicar a atualização incremental posteriormente editando uma fonte de dados existente.

1. Em **Configurações de atualização incremental**, você configurará a atualização incremental para todas as entidades selecionadas ao criar a fonte de dados.

   :::image type="content" source="media/incremental-refresh-settings.png" alt-text="Definir as configurações de atualização incremental.":::

1. Selecione uma entidade e forneça os seguintes detalhes:

   - **Definir a chave primária** : Selecione uma chave primária para a entidade ou tabela.
   - **Defina o campo "última atualização"** : Este campo exibirá apenas atributos do tipo de data ou hora. Selecione um atributo que indica quando os registros foram atualizados pela última vez. Ele será usado para identificar os registros que se enquadram no período de atualização incremental.
   - **Verificar se há atualizações a cada** : Especifique quanto tempo você deseja que dure o período de atualização incremental.

1. Selecione **Salvar** para concluir a criação da fonte de dados. A atualização inicial dos dados será uma atualização completa. Posteriormente, a atualização incremental de dados acontece conforme configurado na etapa anterior.

## <a name="configure-incremental-refresh-for-azure-data-lake-data-sources"></a>Configurar a atualização incremental para fontes de dados do Azure Data Lake

O Customer Insights permite a atualização incremental para fontes de dados conectadas ao Azure Data Lake Storage. Para usar a ingestão incremental e a atualização de uma entidade, configure essa entidade ao adicionar a fonte de dados do Azure Data Lake ou posterior ao editar a fonte de dados. A pasta de dados da entidade deve conter as seguintes pastas:

- **FullData**: pasta com arquivos de dados que contêm os registros iniciais
- **IncrementalData**: pasta com pastas da hierarquia de data/hora no formato **aaaa/mm/dd/hh** que contém as atualizações incrementais. **hh** representa a hora UTC das atualizações e contém as pastas **Upserts** e **Deletes**. **Upserts** contém arquivos de dados com atualizações de registros existentes ou novos. **Deletes** contém arquivos de dados com registros a serem removidos.

1. Ao adicionar ou editar uma fonte de dados, navegue até o painel **Atributos** para a entidade.

1. Renove os atributos. Certifique-se de que um atributo de data de criação ou última atualização esteja configurado com um **Formato de dados** *dateTime* e um **Tipo de semântica** *Calendar.Date*. Se necessário, edite o atributo e selecione **Concluído**.

1. No painel **Selecionar Entidades**, edite a entidade. A caixa de seleção **Ingestão incremental** está marcada.

   :::image type="content" source="media/ADLS_inc_refresh.png" alt-text="Configurar entidades em uma fonte de dados para atualização incremental.":::

   1. Navegue até a pasta raiz que contém os arquivos .csv ou .parquet para obter dados completos, upserts de dados incrementais e exclusões de dados incrementais.
   1. Insira a extensão para os dados completos e os dois arquivos incrementais (\.csv ou \.parquet).
   1. Selecione **Salvar**.

1. Para **Última atualização**, selecione o atributo timestamp de data.

1. Se a **Chave primária** não estiver selecionada, selecione-a. A chave primária é um atributo exclusivo da entidade. Para um atributo ser uma chave primária válida, ele não deve ter valores duplicados, valores ausentes ou valores nulos. Os atributos de tipo de dados de cadeia de caracteres, inteiro e GUID são compatíveis como chaves primárias.

1. Selecione **Fechar** para salvar e fechar o painel.

1. Continue adicionando ou editando a fonte de dados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
