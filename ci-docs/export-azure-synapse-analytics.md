---
title: Exportar para o Azure Synapse Analytics (versão preliminar)
description: Saiba como configurar a conexão ao Azure Synapse Analytics.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: f9c9ee55f2874ae1dcaf82f2ff17ed0fbbb7804d
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196380"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar para o Azure Synapse Analytics (versão preliminar)

O Azure Synapse é um serviço de análise que acelera o tempo de insight de armazéns de dados e sistemas de big data. Você pode ingerir e usar seus dados de Customer Insights em [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

> [!NOTE]
> Lembre-se de definir todas as **atribuições de função** conforme descrito.

- No Customer Insights, sua conta de usuário do Azure Active Directory (AD) deve ter uma [função Administrador](permissions.md#assign-roles-and-permissions).

No Azure:

- Uma assinatura ativa do Azure.

- Se você usar uma nova conta do Azure Data Lake Storage Gen2, a [entidade de serviço para o Customer Insights](connect-service-principal.md) deverá ter permissões de **Colaborador de Dados do Blob de Armazenamento**. O Data Lake Storage Gen2 **deve ter** [namespace hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos em que o Azure Synapse workspace está localizado, a *entidade de serviço* e o usuário do *Azure AD com permissões de administrador no Customer Insights* devem ter pelo menos as [permissões](/azure/role-based-access-control/role-assignments-portal) de **Leitor**.

- O usuário do *Azure AD com permissões de administrador no Customer Insights* tem permissões de **Colaborador de Dados do Blob de Armazenamento** na conta do Azure Data Lake Storage Gen2 em que os dados estão localizados e vinculados ao Azure Synapse workspace. Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A identidade gerenciada do *[Azure Synapse workspace](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* tem permissões de **Colaborador de Dados de Blobs de Armazenamento** na conta do Azure Data Lake Storage Gen2 em que os dados estão localizados e vinculados ao Azure Synapse workspace. Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse workspace, a *entidade de serviço para o Customer Insights* tem a [função **Administrador do Synapse** atribuída](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-connection-to-azure-synapse"></a>Configurar conexão com o Azure Synapse

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Azure Synapse Analytics**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione ou pesquise pela assinatura na qual deseja usar os dados do Customer Insights. Assim que uma assinatura for selecionada, você também pode selecionar **Espaço de trabalho**, **Conta de armazenamento** e **Recipiente**.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)] Para configurar a exportação com uma conexão compartilhada, você precisa de, pelo menos, permissões de **Colaborador** no Customer Insights.

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Azure Synapse Analytics. Contate um administrador se nenhuma conexão estiver disponível.

1. Fornece um **Nome de exibição** reconhecívelf para sua exportação e um **Nome do banco de dados**. A exportação criará um [banco de dados lake do Azure Synapse](/azure/synapse-analytics/database-designer/concepts-lake-database) no espaço de trabalho definido na conexão.

1. Selecione quais entidades você deseja exportar para o Azure Synapse Analytics.
   > [!NOTE]
   > Não há suporte a fontes de dados baseadas em uma [pasta do Common Data Model](connect-common-data-model.md).

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

Para consultar dados que foram exportados para o Synapse Analytics, você precisa de acesso **Leitor de Dados do Blob de Armazenamento** ao armazenamento de destino no espaço de trabalho de exportações.

## <a name="update-an-export"></a>Atualizar uma exportação

1. Vá para **Dados** > **Exportações**.

1. Selecione **Editar** na exportação que você deseja atualizar.

   - **Adicionar** ou **Remove** entidades da seleção. Se forem removidas da seleção, as entidades não serão excluídas do banco de dados do Synapse Analytics. Porém, futuras atualizações de dados não irão atualizar as entidades removidas desse banco de dados.

   - **Alterar o nome do banco de dados** cria um novo banco de dados do Synapse Analytics. O banco de dados cujo o nome já foi configurado não será atualizado em nenhuma atualização futura.

[!INCLUDE [footer-include](includes/footer-banner.md)]
