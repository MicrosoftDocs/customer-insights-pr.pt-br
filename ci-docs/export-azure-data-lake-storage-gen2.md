---
title: Exportar para o Azure Data Lake Storage Gen2 (versão preliminar)
description: Saiba como configurar a conexão do Azure Data Lake Storage Gen2.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 55a61e4d9166df7809a64aeb1168a730402aaed6
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196426"
---
# <a name="export-data-to-azure-data-lake-storage-gen2-preview"></a>Exportar para o Azure Data Lake Storage Gen2 (versão preliminar)

Armazene seus dados do Customer Insights na conta do Azure Data Lake Storage Gen2 ou use para transferir os dados para outros aplicativos.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta de armazenamento a ser usada com o Azure Data Lake Gen2](/azure/storage/blobs/create-data-lake-storage-account). Para encontrar o nome e a chave da conta de armazenamento, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
- Um [contêiner do Armazenamento de Blobs do Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="known-limitations"></a>Limitações conhecidas

- Para o Azure Data Lake Storage Gen2, escolha entre os [níveis de desempenho Padrão e desempenho Premium](/azure/storage/blobs/create-data-lake-storage-account). Se você escolher o nível de desempenho Premium, selecione [blobs de blocos premium como tipo de conta](/azure/storage/common/storage-account-overview#types-of-storage-accounts).

## <a name="set-up-connection-to-azure-data-lake-storage-gen2"></a>Configurar a conexão com o Azure Data Lake Storage Gen2

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Azure Data Lake Gen 2**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira **Nome da conta**, **Chave da conta** e **Contêiner** do Azure Data Lake Storage Gen2.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Azure Data Lake. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Insira o nome da pasta para o armazenamento do Azure Data Lake Storage Gen2.

1. Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Os dados exportados são armazenados no Azure Data Lake Gen 2 configurado.

> [!TIP]
> A exportação de entidades que contêm uma grande quantidade de dados pode levar a vários arquivos CSV na mesma pasta para cada exportação. A divisão de exportações ocorre por motivos de desempenho para minimizar o tempo necessário para a conclusão de uma exportação.

[!INCLUDE [footer-include](includes/footer-banner.md)]
