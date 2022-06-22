---
title: Usar fontes de dados para ingerir dados
description: Saiba como importar dados de várias fontes.
ms.date: 05/31/2022
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
ms.openlocfilehash: e22977107565a0b28b74f41576a1c7ccc74f6dc1
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011735"
---
# <a name="data-sources-overview"></a>Visão geral de fontes de dados

O Dynamics 365 Customer Insights fornece conexões para trazer dados de um amplo conjunto de fontes. A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*. Após a ingestão dos dados, você pode [unificar](data-unification.md), gerar insights e ativar os dados para criar experiências personalizadas.

## <a name="add-data-sources"></a>Adicionar fontes de dados

Você pode anexar ou importar fontes de dados para o Customer Insights. Os links abaixo fornecem instruções sobre como adicionar fontes de dados.

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

Acesse **Dados** > **Fontes de dados** para exibir o nome de cada fonte de dados ingerida, seu status e a última vez que os dados foram atualizados para essa fonte. Você pode classificar a lista de fontes de dados por cada coluna.

:::image type="content" source="media/configure-data-datasource-added.png" alt-text="Fonte de dados adicionada.":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página **Entidades**. Para obter mais informações, consulte [Entidades](entities.md).

## <a name="refresh-data-sources"></a>Atualizar fontes de dados

As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda. As [fontes de dados locais](connect-power-query.md#add-data-from-on-premises-data-sources) são atualizadas em suas próprias agendas, que são configuradas durante a ingestão de dados. Para fontes de dados anexadas, a ingestão de dados consome os dados mais recentes disponíveis desse fonte de dados.

Acesse **Administrador** > **Sistema** > [**Agenda**](system.md#schedule-tab) para configurar atualizações agendadas pelo sistema de suas fontes de dados ingeridas.

Para atualizar uma fonte de dados sob demanda, siga estas etapas:

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione as reticências verticais (&vellip;) ao lado da fonte de dados que você deseja atualizar e selecione **Atualizar** na lista suspensa. A fonte de dados agora é acionada para uma atualização manual. Atualizar um fonte de dados atualizará o esquema da entidade e os dados de todas as entidades especificadas na fonte de dados.

1. Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e que a fonte de dados seja revertida para seu último status de atualização.

## <a name="delete-a-data-source"></a>Excluir uma fonte de dados

Um fonte de dados só poderá ser excluída se os dados não forem usados em nenhum processamento, como unificação, insights, ativações ou exportações.

1. Acesse **Dados** > **Fontes de dados**.

2. Selecione as reticências verticais (&vellip;) ao lado da fonte de dados que você deseja remover e selecione **Excluir** no menu suspenso.

3. Confirme a exclusão.


[!INCLUDE [footer-include](includes/footer-banner.md)]
