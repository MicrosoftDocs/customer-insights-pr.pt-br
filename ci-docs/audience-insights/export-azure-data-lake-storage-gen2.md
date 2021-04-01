---
title: Exportar dados do Customer Insights para o Azure Data Lake Storage Gen2
description: Saiba como configurar a conexão do Azure Data Lake Storage Gen2.
ms.date: 02/04/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 7c0eef575f745efa6312d7141a6dd96607f9797e
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596623"
---
# <a name="connector-for-azure-data-lake-storage-gen2-preview"></a>Conector para Azure Data Lake Storage Gen2 (versão preliminar)

Armazene seus dados do Customer Insights no Azure Data Lake Storage Gen2 ou use-o para transferir seus dados para outros aplicativos.

## <a name="configure-the-connector-for-azure-data-lake-storage-gen2"></a>Configurar o conector do Azure Data Lake Storage Gen2

1. Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.

1. Em **Azure Data Lake Storage Gen2**, selecione **Configurar**.

1. Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.

1. Insira **Nome da conta**, **Chave da conta** e **Contêiner** do Azure Data Lake Storage Gen2.
    - Para aprender a criar a conta de armazenamento a ser usada com o Azure Data Lake Storage Gen2, consulte [Criar conta de armazenamento](/azure/storage/blobs/create-data-lake-storage-account). 
    - Para saber mais sobre como localizar o nome e a chave da conta de armazenamento do Azure Data Lake Gen2, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

1. Selecione **Avançar**.

1. Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md#export-data-on-demand). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).