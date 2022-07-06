---
title: Exportar dados do Customer Insights para a InMobi
description: Saiba como configurar a conexão e exportar para a InMobi.
ms.date: 06/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8261c8adfe231792e70fc85432237cf73d5cd5a7
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9056533"
---
# <a name="export-segment-list-and-other-data-to-inmobi-preview"></a>Exportar a lista de segmentos e outros dados para a InMobi (versão preliminar)

Exporte listas de segmentos ou outros dados de sua instância do Customer Insights para a [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Pré-requisitos

1. Você ter uma [conta da InMobi](https://www.inmobi.com/) e credenciais de administrador.
1. Você ter um nome de conta de Armazenamento de Blobs do Azure e a chave de conta correspondente. Para obter mais informações, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage). Há um contêiner na conta de armazenamento para o qual exportar dados da inMobi. Para obter mais informações, consulte [Criar um contêiner](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).
1. A InMobi criará uma conexão direta com seu Armazenamento de Blobs e configurará uma importação automática de seus dados para a InMobi. Entre em contato com seu representante da InMobi para iniciar o processo.

## <a name="known-limitations"></a>Limitações conhecidas

1. Para o Armazenamento de Blobs do Azure, você pode escolher entre [nível de desempenho Padrão e de desempenho Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se você escolher o nível de desempenho Premium, selecione [blobs de blocos premium como tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-the-connection-to-azure-blob-storage-and-configure-an-export"></a>Configurar a conexão com o Armazenamento de Blobs do Azure e configurar uma exportação

1. Siga as instruções para [configurar uma conexão com seu Armazenamento de Blobs do Azure](export-azure-blob-storage.md).
2. Siga as instruções para [configurar uma exportação](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
