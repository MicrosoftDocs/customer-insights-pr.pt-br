---
title: Exportar dados do Customer Insights para um Armazenamento de Blobs do Azure
description: Aprenda a configurar a conexão e exportar para o Armazenamento de blobs.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d02c09a1869d0099db4861b65ac8ff006914873e
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7605824"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportar a lista de segmentos e outros dados para o Armazenamento de Blobs do Azure (versão preliminar)

Armazene seus dados do Customer Insights em um Armazenamento de blobs ou use-o para transferir seus dados para outros aplicativos.

## <a name="known-limitations"></a>Limitações conhecidas

1. Para Armazenamento de Blobs do Azure, você pode escolher entre [Desempenho padrão e nível de desempenho Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se você escolher o nível de desempenho Premium, selecione [blobs de blocos premium como tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-blob-storage"></a>Configurar a conexão com o Armazenamento de Blobs

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Armazenamento de Blobs do Azure** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira o **Nome da conta**, a **Chave de conta** e o **Contêiner** para a conta do Armazenamento de Blobs.
    - Para saber mais sobre como encontrar o nome e a chave da conta do Armazenamento de Blobs, consulte [Gerenciar configurações de conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
    - Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

> [!IMPORTANT]
> Se você ativou a configuração de exclusão temporária para a conta do Armazenamento de Blobs do Azure, haverá falha nas exportações. Desative a exclusão temporária para exportar dados para os blobs. Para obter mais informações, consulte [Habilitar exclusão temporária de blob](/azure/storage/blobs/soft-delete-blob-enable.md)

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Armazenamento de Blobs do Azure. Se você não vir este nome de seção, significa que não há conexões desse tipo disponíveis para você.

1. Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab).     

Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

Os dados exportados são armazenados no contêiner do Armazenamento de Blobs configurado. Os seguintes caminhos de pasta são criados automaticamente no seu contêiner:

- Para entidades de origem e entidades geradas pelo sistema:   
  `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`  
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
 
- O model.json das entidades exportadas estará no nível %ExportDestinationName%.  
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
