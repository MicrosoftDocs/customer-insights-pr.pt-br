---
title: Exportar dados do Customer Insights para um Armazenamento de Blobs do Azure
description: Aprenda a configurar a conexão e exportar para o Armazenamento de blobs.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c19dc6d4956a33a5bd3cea706f8a154198d487f
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976120"
---
# <a name="export-segment-list-and-other-data-to-azure-blob-storage-preview"></a>Exportar a lista de segmentos e outros dados para o Armazenamento de Blobs do Azure (versão preliminar)

Armazene seus dados do Customer Insights em um Armazenamento de blobs ou use-o para transferir seus dados para outros aplicativos.

## <a name="set-up-the-connection-to-blob-storage"></a>Configurar a conexão com o Armazenamento de blobs

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Armazenamento de Blobs do Azure** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira **Nome da conta**, **Chave de conta** e **Contêiner** para a Conta de armazenamento de blobs.
    - Para saber mais sobre como encontrar o nome da Conta de armazenamento de blobs e a chave de conta, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
    - Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Armazenamento de Blobs do Azure. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab).     
Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

Os dados exportados são armazenados no contêiner de Armazenamento de blobs configurado. Os seguintes caminhos de pasta são criados automaticamente no seu contêiner:

- Para entidades de origem e entidades geradas pelo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- O model.json das entidades exportadas estará no nível %ExportDestinationName%
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

[!INCLUDE[footer-include](../includes/footer-banner.md)]
