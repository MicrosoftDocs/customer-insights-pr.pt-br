---
title: Ingerir dados do Azure Synapse Analytics
description: Use um banco de dados no Azure Synapse como um fonte de dados no Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: v-wendysmith
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: 163bef897880f0497bf00e90fd095621a2d14378
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8356013"
---
# <a name="connect-an-azure-synapse-data-source-preview"></a>Conectar-se a uma fonte de dados do Azure Synapse (versão preliminar)

Azure Synapse Analytics é um serviço de análise empresarial que acelera o tempo para a obtenção de insights em data warehouses e sistemas de big data. O Azure Synapse Analytics reúne o melhor das tecnologias SQL usadas no armazenamento de dados corporativos, tecnologias Spark usadas para big data, Data Explorer para análise de logs e séries temporais, Pipelines para integração de dados e ETL/ELT e integração profunda com outros serviços do Azure, como o Power BI, o Cosmos DB e o AzureML.

Para obter mais informações, consulte [Visão geral do Azure Synapse](/azure/synapse-analytics/overview-what-is).

## <a name="prerequisites"></a>Pré-requisitos

Os seguintes pré-requisitos devem ser cumpridos para configurar a conexão do Customer Insights para o Azure Synapse.

> [!IMPORTANT]
> Lembre-se de definir todas as **atribuições de função** conforme descrito.  

## <a name="prerequisites-in-customer-insights"></a>Pré-requisitos no Customer Insights

* Você deve ter uma permissão de **Administrador** no Customer Insights. Saiba mais sobre [permissões do usuário em insights do público-alvo](permissions.md#assign-roles-and-permissions).

No Azure: 

- Uma assinatura ativa do Azure.

- Se estiver usando uma nova conta do Azure Data Lake Storage Gen2, a *entidade de serviço para insights do público-alvo* precisa de permissões do **Colaborador de Dados do Storage Blob**. Saiba mais sobre [como conectar-se a um Azure Data Lake Storage com uma entidade de serviço para obter insights de público-alvo](connect-service-principal.md). O Data Lake Storage Gen2 **deve ter** [namespace hierárquico](/azure/storage/blobs/data-lake-storage-namespace) ativado.

- No grupo de recursos onde o espaço de trabalho do Azure Synapse está localizado, a *entidade de serviço* e o *usuário para insights do público-alvo* precisa receber, pelo menos, permissões de **Leitor**. Para mais informações, veja [Atribuir funções do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).

- O *usuário* precisa de permissões do **Colaborador de Dados do Storage Blob** na conta do Azure Data Lake Storage Gen2 onde os dados estão localizados e vinculados ao espaço de trabalho do Azure Synapse. Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- A identidade gerenciada do espaço de trabalho do *[Azure Synapse](/azure/synapse-analytics/security/synapse-workspace-managed-identity)* precisa de permissões do **Colaborador de Dados do Storage Blob** na conta do Azure Data Lake Storage Gen2 onde os dados estão localizados e vinculados ao espaço de trabalho do Azure Synapse. Saiba mais sobre [como usar o portal do Azure para atribuir uma função do Azure para acesso aos dados de blob e fila](/azure/storage/common/storage-auth-aad-rbac-portal) e [permissões do Colaborador de Dados do Storage Blob](/azure/role-based-access-control/built-in-roles#storage-blob-data-contributor).

- No espaço de trabalho do Azure Synapse, a *entidade de serviço para insights do público-alvo* precisa da função de **Administrador do Synapse** atribuída. Para mais informações, veja [Como configurar o controle de acesso para o seu espaço de trabalho do Synapse](/azure/synapse-analytics/security/how-to-set-up-access-control).

## <a name="connect-to-data-lake-databases-in-azure-synapse-analytics"></a>Conectar-se a bancos de dados de data lake no Azure Synapse Analytics

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Escolha o método **Azure Synapse Analytics (Versão Preliminar)**.

1. Forneça um **Nome** para a fonte de dados e selecione **Avançar** para criar a fonte de dados. 

1. Escolha uma [conexão disponível](connections.md) ao Azure Synapse Analytics ou crie uma nova.

1. Escolha um **Banco de Dados Lake** do espaço de trabalho conectado na conexão selecionada do Azure Synapse Analytics e selecione **Avançar**.

1. Selecione as entidades a serem ingeridas do banco de dados conectado. 

1. Opcionalmente, escolha as entidades de dados na qual permitir a criação de perfil de dados. 

1. Selecione **Salvar** para aplicar sua seleção e iniciar a ingestão dos dados da fonte de dados recém-criada vinculado às tabelas do banco de dados Lake no Azure Synapse Analytics.
