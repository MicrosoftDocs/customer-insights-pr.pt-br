---
title: Exportar dados do Customer Insights para a InMobi
description: Saiba como configurar a conexão e exportar para a InMobi.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ef486ad6786ef01be977f3d6bda69ce8a2b081c7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195874"
---
# <a name="export-customer-insights-data-to-inmobi-preview"></a>Exportar dados do Customer Insights para InMobi (versão preliminar)

Exporte listas de segmentos ou outros dados de sua instância do Customer Insights para a [InMobi](https://www.inmobi.com/).

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta da InMobi](https://www.inmobi.com/) e credenciais de administrador.
- O nome de uma [conta do Armazenamento de Blobs do Azure](/azure/storage/blobs/create-data-lake-storage-account) e a chave de conta. Para encontrar o nome e a chave, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
- Um [contêiner do Armazenamento de Blobs do Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container) para o qual exportar dados da InMobi.
- A InMobi criará uma conexão direta com seu Armazenamento de Blobs e configurará uma importação automática de seus dados para a InMobi. Entre em contato com seu representante da InMobi para iniciar o processo.

## <a name="known-limitations"></a>Limitações conhecidas

- Para o Armazenamento de Blobs do Azure, você pode escolher entre os [níveis de desempenho Padrão e de desempenho Premium](/azure/storage/blobs/storage-blob-performance-tiers). Se você escolher o nível de desempenho Premium, selecione [blobs de blocos premium como tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-blob-storage"></a>Configurar a conexão com o Armazenamento de Blobs do Azure

[Configure a conexão com o Armazenamento de Blobs do Azure](export-azure-blob-storage.md).

## <a name="configure-an-export"></a>Configurar uma exportação

[Configure uma exportação](export-azure-blob-storage.md#configure-an-export).

[!INCLUDE [footer-include](includes/footer-banner.md)]
