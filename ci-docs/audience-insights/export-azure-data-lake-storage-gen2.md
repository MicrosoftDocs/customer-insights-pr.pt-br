---
title: Exportar dados do Customer Insights para o Azure Data Lake Storage Gen2
description: Saiba como configurar a conexão do Azure Data Lake Storage Gen2.
ms.date: 10/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: cc0b3aac11a33facc366e9c57071d1fb8be4ecc4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8231655"
---
# <a name="export-segment-list-and-other-data-to-azure-data-lake-storage-gen2-preview"></a>Exporte a lista de segmentos e outros dados para o Azure Data Lake Storage Gen2 (versão preliminar)

Armazene seus dados do Customer Insights na conta do Azure Data Lake Storage Gen2 ou use para transferir os dados para outros aplicativos.

## <a name="known-limitations"></a>Limitações conhecidas

1. Para Azure Data Lake Storage Gen2, você pode escolher entre [Desempenho padrão e nível de desempenho Premium](/azure/storage/blobs/create-data-lake-storage-account) ao criar uma conta de armazenamento para seu data lake. Se você escolher o nível de desempenho Premium, selecione blobs de blocos premium como tipo de conta. 


## <a name="set-up-the-connection-to-azure-data-lake-storage-gen2"></a>Configure a conexão com o Azure Data Lake Storage Gen2 


1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Azure Data Lake Gen 2** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira **Nome da conta**, **Chave da conta** e **Contêiner** do Azure Data Lake Storage Gen2.
    - Para aprender a criar a conta de armazenamento a ser usada com o Azure Data Lake Storage Gen2, consulte [Criar conta de armazenamento](/azure/storage/blobs/create-data-lake-storage-account). 
    - Para saber mais sobre como encontrar o nome do Azure Data Lake Gen2 e a chave de conta, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma exportação, selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do **Azure Data Lake**. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Marque a caixa ao lado de cada uma das entidades que você deseja exportar para este destino.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

Os dados exportados são armazenados no Azure Data Lake Gen 2 configurado. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
