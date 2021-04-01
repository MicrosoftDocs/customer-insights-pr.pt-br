---
title: Exportar dados do Customer Insights para um Armazenamento de Blobs do Azure
description: Saiba como configurar a conexão com o Armazenamento de Blobs do Azure.
ms.date: 09/18/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 0986ee5caf5fa079994ca584fb2c4d9294ddb80b
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596163"
---
# <a name="connector-for-azure-blob-storage-preview"></a>Conector para Armazenamento de Blobs do Azure (versão preliminar)

Armazene seus dados do Customer Insights em um Armazenamento de Blobs do Azure ou use-o para transferir seus dados para outros aplicativos.

## <a name="configure-the-connector-for-azure-blob-storage"></a>Configurar o conector para o Armazenamento de Blobs do Azure

1. Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.

1. Em **Armazenamento de Blobs do Azure**, selecione **Configurar**.

1. Insira **Nome da conta**, **Chave da conta** e **Contêiner** para sua conta de Armazenamento de Blobs do Azure.
    - Para saber mais sobre como encontrar o nome e a chave da conta do Azure Blob Storage, consulte [Gerenciar as configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
    - Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.

1. Selecione **Avançar**.

1. Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.

1. Selecione **Salvar**.

Os dados exportados são armazenados no contêiner do Armazenamento de Blobs do Azure que você configurou. Os seguintes caminhos de pasta são criados automaticamente no seu contêiner:

- Para entidades de origem e entidades geradas pelo sistema: `%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv`
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/HighValueSegment/2020/08/24/1433/HighValueSegment_1.csv`
- O model.json para as entidades exportadas residirá no nível do %ExportDestinationName%
  - Exemplo: `Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/model.json`

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md#export-data-on-demand). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]