---
title: Visão geral de fontes de dados
description: Saiba como importar ou ingerir dados de várias fontes.
ms.date: 09/29/2022
ms.subservice: audience-insights
ms.topic: overview
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: f89da3cf5b56e367bd673740f80cd82ec0907b28
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610038"
---
# <a name="data-sources-overview"></a>Visão geral de fontes de dados

O Dynamics 365 Customer Insights fornece conexões para trazer dados de um amplo conjunto de fontes. A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*. Após a ingestão dos dados, você pode [unificar](data-unification.md), gerar insights e ativar os dados para criar experiências personalizadas.

## <a name="add-or-edit-data-sources"></a>Adicionar ou editar fontes de dados

Você pode anexar ou importar fontes de dados para o Customer Insights. Os links abaixo fornecem instruções sobre como adicionar e editar fontes de dados.

**Anexar uma fonte de dados**

Se você tiver dados preparados em um dos serviços de dados do Azure da Microsoft, o Customer Insights poderá se conectar facilmente ao fonte de dados sem precisar ingerir novamente os dados. Selecione uma das opções a seguir:
- [Azure Data Lake Storage (arquivos csv ou parquet em uma pasta do Common Data Model)](connect-common-data-model.md)
- [Azure Synapse Analytics (bancos de dados do Lake)](connect-synapse.md)
- [Data lake do Microsoft Dataverse](connect-dataverse-managed-lake.md)

**Importar e transformar**

Se você usar fontes de dados locais, dados da Microsoft ou de terceiros, importe e transforme os dados usando conectores do Power Query.
- [Conectores do Power Query](connect-power-query.md)

## <a name="review-data-sources"></a>Revisar fontes de dados

Se o seu ambiente tiver sido configurado para usar o armazenamento do Customer Insights e se usa fontes de dados locais, você usa fluxos de dados do Power Platform. Com fluxos de dados do Power Platform, você poderá exibir fontes de dados compartilhadas e fontes de dados gerenciadas por outras pessoas. A página **Fontes de Dados** lista as fontes de dados em três seções:
- **Compartilhado**: as fontes de dados que podem ser gerenciadas por todos os administradores do Customer Insights. Alguns exemplos de fontes de dados compartilhadas incluem os fluxos de dados do Power Platform, sua própria conta de armazenamento e anexar a um data lake gerenciado do Dataverse.
- **Gerenciado por mim**: os fluxos de dados do Power Platform criados e gerenciados somente por você. Outros administradores do Customer Insights só podem visualizar esses fluxos de dados, mas não podem editar, atualizar ou excluir.
- **Gerenciado por outros**: os fluxos de dados do Power Platform criados por outros administradores. Você só pode visualizar. Aqui, é indicado o proprietário do fluxo de dados que você precisa contatar caso precise de qualquer ajuda.
> [!NOTE]
> Todas as entidades podem ser visualizadas e usadas por outros usuários. Embora as fontes de dados sejam propriedade do usuário que as criou, as entidades resultantes da ingestão de dados podem ser usadas por todos os usuários do Customer Insights.

Se o seu ambiente não usa fluxos de dados do Power Platform, a página **Fontes de Dados** contém apenas uma lista de todas as fontes de dados. Nenhuma seção é exibida.

## <a name="manage-existing-data-sources"></a>Gerenciar fontes de dados existentes

Acesse **Dados** > **Fontes de dados** para exibir o nome de cada fonte de dados ingerida, seu status e a última vez que os dados foram atualizados para essa fonte. Você pode classificar a lista de fontes de dados por qualquer coluna ou usar a caixa de pesquisa para encontrar a fonte de dados que deseja gerenciar.

Selecione uma fonte de dados para exibir as ações disponíveis.

:::image type="content" source="media/data_sources_showmore.png" alt-text="Fonte de dados adicionada.":::

- [**Editar**](#add-or-edit-data-sources) a fonte de dados para alterar suas propriedades.
- [**Atualizar**](#refresh-data-sources) a fonte de dados para incluir os dados mais recentes.
- [**Enriquecer**](data-sources-enrichment.md) a fonte de dados antes da unificação.
- **Excluir** a fonte de dados. Um fonte de dados só poderá ser excluída se os dados não forem usados em nenhum processamento, como unificação, insights, ativações ou exportações.

## <a name="refresh-data-sources"></a>Atualizar fontes de dados

As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda. As [fontes de dados locais](connect-power-query.md#add-data-from-on-premises-data-sources) são atualizadas em suas próprias agendas, que são configuradas durante a ingestão de dados. Para obter dicas de solução de problemas, consulte [Solucionar problemas de atualização da fonte de dados baseada no PPDF Power Query](connect-power-query.md#troubleshoot-ppdf-power-query-based-data-source-refresh-issues).

Para fontes de dados anexadas, a ingestão de dados consome os dados mais recentes disponíveis desse fonte de dados.

Acesse **Administrador** > **Sistema** > [**Agenda**](schedule-refresh.md) para configurar atualizações agendadas pelo sistema de suas fontes de dados ingeridas.

Para atualizar uma fonte de dados por demanda:

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione a fonte de dados que você deseja atualizar e selecione **Atualizar**. A fonte de dados agora é acionada para uma atualização manual. Atualizar um fonte de dados atualizará o esquema da entidade e os dados de todas as entidades especificadas na fonte de dados.

1. Selecione o status para abrir o painel **Detalhes de progresso** e exibir o progresso. Para cancelar o trabalho, selecione **Cancelar trabalho** na parte inferior do painel.

## <a name="corrupt-data-sources"></a>Fontes de dados corrompidas

Os dados inseridos podem ter registros corrompidos, o que pode fazer com que o processo de ingestão de dados seja concluído com erros ou avisos.

> [!NOTE]
> Se a ingestão de dados for concluída com erros, o processamento subsequente (como unificação ou criação de atividade) que aproveita essa fonte de dados será ignorado. Se a ingestão for concluída com avisos, o processamento subsequente continua, mas alguns dos registros podem não ser incluídos.

Esses erros podem ser vistos nos detalhes da tarefa.

:::image type="content" source="media/corrupt-task-error.png" alt-text="Detalhe da tarefa mostrando erro de dados corrompidos.":::

Registros corrompidos são mostrados em entidades criadas pelo sistema.

### <a name="fix-corrupt-data"></a>Corrigir dados corrompidos

1. Para exibir os dados corrompidos, acesse **Dados** > **Entidades** e procure as entidades corrompidas na seção **Sistema**. O esquema de nomenclatura de entidades corrompidas: 'DataSourceName_EntityName_corrupt'.

1. Selecione uma entidade corrompida e depois a guia **Dados**.

1. Identifique os campos corrompidos em um registro e o motivo.

   :::image type="content" source="media/corruption-reason.png" alt-text="Motivo da corrupção." lightbox="media/corruption-reason.png":::

   > [!NOTE]
   > **Dados** > **Entidades** mostram apenas uma parte dos registros corrompidos. Para exibir todos os registros corrompidos, exporte os arquivos para um contêiner na conta de armazenamento usando o [processo de exportação do Customer Insights](export-destinations.md). Se você usou sua própria conta de armazenamento, também poderá consultar a pasta do Customer Insights em sua conta de armazenamento.

1. Corrija os dados corrompidos. Por exemplo, para fontes de dados do Azure Data Lake, [corrija os dados no Data Lake Storage ou atualize os tipos de dados no arquivo manifest/model.json](connect-common-data-model.md#common-reasons-for-ingestion-errors-or-corrupt-data). Para fontes de dados do Power Query, corrija os dados no arquivo de origem e [corrija o tipo de dados na etapa de transformação](connect-power-query.md#data-type-does-not-match-data) na página **Power Query - Editar consultas**.

Após a próxima atualização da fonte de dados, os registros corrigidos são ingeridos no Customer Insights e passados para os processos downstream.

Por exemplo, uma coluna 'aniversário' tem o tipo de dados definido como 'data'. Um registro de cliente tem sua data de aniversário inserida como '01/01/19777'. O sistema sinaliza este registro como corrompido. Altere o aniversário no sistema de origem para "1977". Após uma atualização automática das fontes de dados, o campo agora tem um formato válido e o registro será removido da entidade corrompida.

[!INCLUDE [footer-include](includes/footer-banner.md)]
