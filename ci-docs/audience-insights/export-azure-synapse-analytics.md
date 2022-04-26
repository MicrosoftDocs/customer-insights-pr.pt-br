---
title: Exportar dados do Customer Insights para a Azure Synapse Analytics
description: Saiba como configurar a conexão ao Azure Synapse Analytics.
ms.date: 04/11/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 8ace9fbee4fbd8822629a39d5902e176f8511cb5
ms.sourcegitcommit: 9f6733b2f2c273748c1e7b77f871e9b4e5a8666e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/11/2022
ms.locfileid: "8560373"
---
# <a name="export-data-to-azure-synapse-analytics-preview"></a>Exportar para o Azure Synapse Analytics (versão preliminar)

O Azure Synapse é um serviço de análise que acelera o tempo de insight de armazéns de dados e sistemas de big data. Você pode ingerir e usar seus dados de Customer Insights em [Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

Os seguintes pré-requisitos devem ser cumpridos para configurar a conexão do Customer Insights para o Azure Synapse.

> [!NOTE]
> Lembre-se de definir todas as **atribuições de função** conforme descrito.  

## <a name="prerequisites-in-customer-insights"></a>Pré-requisitos no Customer Insights

* Sua conta de usuário do Azure Active Directory (AD) tem uma função de **Administrador** no Customer Insights. Saiba mais sobre [como definir permissões do usuário em insights de público-alvo](permissions.md#assign-roles-and-permissions)

No Azure: 

- Uma assinatura ativa do Azure.

- Se estiver usando uma nova conta do Azure Data Lake Storage Gen2, a *entidade de serviço para o Customer Insights* precisará da permissão **Colaborador de Dados do Blob de Armazenamento**. Saiba mais sobre [como conectar-se a uma conta do Azure Data Lake Storage Gen2 com a entidade de serviço para insights do público-alvo](connect-service-principal.md). O Data Lake Storage Gen2 **deve ter** [namespace hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos em que o Azure Synapse workspace está localizado, a *entidade de serviço* e o *usuário do Azure AD com permissões de administração no Customer Insights* devem ter, pelo menos, a permissão de **Leitor**. Para mais informações, veja [Atribuir funções do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

- O *usuário do Azure AD com permissões de administração no Customer Insights* precisa da permissão de **Colaborador de Dados do Blob de Armazenamento** no Azure Data Lake Storage Gen2 em que os dados estão localizados e vinculados ao Azure Synapse workspace. Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A identidade gerenciada do espaço de trabalho do *[Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões do **Colaborador de Dados do Storage Blob** na conta do Azure Data Lake Storage Gen2 onde os dados estão localizados e vinculados ao espaço de trabalho do Azure Synapse. Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse workspace, a *entidade de serviço para o Customer Insights* deve ter a função de **Administrador do Synapse** atribuída. Para mais informações, veja [Como configurar o controle de acesso para o seu espaço de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="set-up-the-connection-and-export-to-azure-synapse"></a>Configurar a conexão e exportar para o Azure Synapse

### <a name="configure-a-connection"></a>Configurar uma conexão

Para criar uma conexão, a entidade de serviço e a conta de usuário no Customer Insights precisam de permissões de **Leitor** no *grupo de recursos* em que o espaço de trabalho do Synapse Analytics está localizado. Além disso, a entidade de serviço e o usuário no espaço de trabalho do Synapse Analytics precisam de permissões de **Administrador do Synapse**. 

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Azure Synapse Analytics** ou selecione a **Configuração** no bloco **Azure Synapse Analytics** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo Nome de exibição. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione ou pesquise pela assinatura na qual deseja usar os dados do Customer Insights. Assim que uma assinatura for selecionada, você também pode selecionar **Espaço de trabalho**, **Conta de armazenamento** e **Recipiente**.

1. Selecione **Salvar** para salvar a conexão.

### <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para configurar a exportação com uma conexão compartilhada, você precisa de, pelo menos, permissões de **Colaborador** no Customer Insights. Para obter mais informações, veja [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma exportação, selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do **Azure Synapse Analytics**. Se não vir este nome de seção, não há [conexões](connections.md) deste tipo disponíveis para você.

1. Fornece um **Nome de exibição** reconhecívelf para sua exportação e um **Nome do banco de dados**.

1. Selecione quais entidades você deseja exportar para o Azure Synapse Analytics.
   > [!NOTE]
   > Não há suporte a fontes de dados baseadas em uma [pasta do Common Data Model](connect-common-data-model.md).

2. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).

Para consultar dados que foram exportados para o Synapse Analytics, você precisa de acesso **Leitor de Dados do Blob de Armazenamento** ao armazenamento de destino no espaço de trabalho de exportações. 

### <a name="update-an-export"></a>Atualizar uma exportação

1. Vá para **Dados** > **Exportações**.

1. Selecione **Editar** na exportação que você deseja atualizar.

   - **Adicionar** ou **Remove** entidades da seleção. Se forem removidas da seleção, as entidades não serão excluídas do banco de dados do Synapse Analytics. Porém, futuras atualizações de dados não irão atualizar as entidades removidas desse banco de dados.

   - **Alterar o nome do banco de dados** cria um novo banco de dados do Synapse Analytics. O banco de dados cujo o nome já foi configurado não será atualizado em nenhuma atualização futura.
