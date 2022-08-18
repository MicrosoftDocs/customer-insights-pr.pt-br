---
title: Conectar-se a uma fonte de dados do Azure Synapse (versão preliminar)
description: Use um banco de dados no Azure Synapse como um fonte de dados no Dynamics 365 Customer Insights.
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 7bc0c3614e6dd39fbd65ae098ed679d95d09de9d
ms.sourcegitcommit: 086f75136132d561cd78a4c2cb1e1933e2301f32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/11/2022
ms.locfileid: "9259784"
---
# <a name="connect-an-azure-synapse-analytics-data-source-preview"></a>Conectar-se a uma fonte de dados do Azure Synapse Analytics (versão preliminar)

Azure Synapse Analytics é um serviço de análise empresarial que acelera o tempo para a obtenção de insights em data warehouses e sistemas de big data. O Azure Synapse Analytics reúne o melhor das tecnologias SQL usadas no armazenamento de dados corporativos, tecnologias Spark usadas para big data, Data Explorer para análise de logs e séries temporais, Pipelines para integração de dados e ETL/ELT e integração profunda com outros serviços do Azure, como o Power BI, o Cosmos DB e o AzureML.

Para obter mais informações, consulte [Visão geral do Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

> [!NOTE]
> No momento, não há suporte a Synapse Workspaces que têm o [firewall habilitado](/azure/synapse-analytics/security/synapse-workspace-ip-firewall).
> [!IMPORTANT]
> Lembre-se de definir todas as **atribuições de função** conforme descrito.  

**No Customer Insights**:

* Você deve ter uma permissão de **Administrador** no Customer Insights. Saiba mais sobre [permissões do usuário no Customer Insights](permissions.md#add-users).

**No Azure**:

- Uma assinatura ativa do Azure.

- Se estiver usando uma nova conta do Azure Data Lake Storage Gen2, a *entidade de serviço para o Customer Insights*, que é "Dynamics 365 AI for Customer Insights", precisará da permissão **Colaborador de Dados do Storage Blob**. Saiba mais sobre [como conectar-se a um Azure Data Lake Storage com uma entidade de serviço para o Customer Insights](connect-service-principal.md). O Data Lake Storage Gen2 **deve ter** [namespace hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos em que o Azure Synapse workspace está localizado, a *entidade de serviço*, que é "Dynamics 365 AI for Customer Insights" e o *usuário do Customer Insights* precisam ter pelo menos permissões de **Leitor**. Para mais informações, veja [Atribuir funções do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

- O *usuário* precisa de permissões do **Colaborador de Dados do Storage Blob** na conta do Azure Data Lake Storage Gen2 onde os dados estão localizados e vinculados ao espaço de trabalho do Azure Synapse. Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A identidade gerenciada do espaço de trabalho do *[Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões do **Colaborador de Dados do Storage Blob** na conta do Azure Data Lake Storage Gen2 onde os dados estão localizados e vinculados ao espaço de trabalho do Azure Synapse. Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No Azure Synapse workspace, a *entidade de serviço para o Customer Insights* que é "Dynamics 365 AI for Customer Insights" deve ter a função de **Administrador do Synapse** atribuída. Para mais informações, veja [Como configurar o controle de acesso para o seu espaço de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

- Se o ambiente do Customer Insights armazena dados em seu [próprio Azure Data Lake Storage](own-data-lake-storage.md), o usuário que configurar a conexão com o Azure Synapse Analytics deve ter, pelo menos, a função interna **Leitor** na conta do Data Lake Storage. Para mais informações, veja [Atribuir funções do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

## <a name="connect-to-the-data-lake-database-in-azure-synapse-analytics"></a>Conectar-se ao banco de dados de data lake no Azure Synapse Analytics

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Escolha o método **Azure Synapse Analytics (Versão Preliminar)**.

   :::image type="content" source="media/data_sources_synapse.png" alt-text="Caixa de diálogo para conexão aos dados do Synapse Analytics":::
  
1. Insira um **Nome** para a fonte de dados e uma **Descrição** opcional.

1. Escolha uma [conexão disponível](connections.md) ao Azure Synapse Analytics ou [crie uma](export-azure-synapse-analytics.md#set-up-connection-to-azure-synapse).

1. Escolha um **Banco de Dados** do espaço de trabalho conectado na conexão do Azure Synapse Analytics selecionada e escolha **Avançar**. No momento, oferecemos suporte somente ao tipo de banco de dados *Banco de dados lake*.

1. Selecione as entidades a serem ingeridas do banco de dados conectado e selecione **Avançar**.

1. Opcionalmente, escolha as entidades de dados na qual permitir a criação de perfil de dados.

1. Selecione **Salvar** para aplicar sua seleção e iniciar a ingestão dos dados da fonte de dados recém-criada vinculado às tabelas do banco de dados Lake no Azure Synapse Analytics. A página **Fontes de dados** abre mostrando a nova fonte de dados no status **Atualizando**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página [**Entidades**](entities.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
