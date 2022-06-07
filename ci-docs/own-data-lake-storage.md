---
title: Use sua própria conta do Azure Data Lake Storage Gen2
author: mukeshpo
description: Saiba mais sobre os requisitos para usar sua própria conta do Azure Data Lake Storage para armazenar dados do Customer Insights.
ms.author: mukeshpo
ms.date: 05/30/2022
ms.topic: conceptual
ms.manager: shellyha
ms.custom: intro-internal
ms.reviewer: mhart
ms.openlocfilehash: 9fcd7645e34bf310ac3a1b98a0dd9a60598b19dc
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833913"
---
# <a name="use-your-own-azure-data-lake-storage-gen2-account"></a>Use sua própria conta do Azure Data Lake Storage Gen2

O Dynamics 365 Customer Insights permite armazenar todos os seus dados no [Azure Data Lake Storage Gen2](/azure/storage/blobs/data-lake-storage-introduction).

Salvando dados no Data Lake Storage, você concorda que os dados serão transferidos e armazenados no local geográfico apropriado para essa conta de armazenamento do Azure. Para obter mais informações, consulte o [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Os administradores no Customer Insights podem [criar ambientes](create-environment.md) e [especifique a opção de armazenamento de dados](create-environment.md#step-2-configure-data-storage) no processo.

## <a name="prerequisites-to-use-your-storage-account"></a>Pré-requisitos para usar sua conta de armazenamento

- As contas do Azure Data Lake Storage devem estar na mesma região do Azure que você selecionou ao criar o ambiente do Customer Insights. Você pode verificar a região do ambiente do Customer Insights em **Administrador** > **Sistema** > **Sobre**.
- O Data Lake Storage deve ser Gen2 e ter o recurso [namespace hierárquico habilitado](/azure/storage/blobs/create-data-lake-storage-account). As contas de armazenamento Gen1 não são compatíveis.
- Precisa existir um contêiner chamado `customerinsights` na conta de armazenamento. Você precisa criá-las antes de usar seu próprio Data Lake Storage no Customer Insights. O administrador que configura o ambiente do Customer Insights precisa da função de Colaborador de Dados do Blob de Armazenamento ou de Proprietário de Dados do Blob de Armazenamento na conta de armazenamento ou no contêiner do `customerinsights`. Para obter mais informações sobre como atribuir permissão em uma conta de armazenamento, leia [Criar uma conta de armazenamento](/azure/storage/common/storage-account-create?toc=%2Fazure%2Fstorage%2Fblobs%2Ftoc.json&tabs=azure-portal).

## <a name="connect-customer-insights-with-your-storage-account"></a>Conecte o Customer Insights à sua conta de armazenamento

Ao criar um novo ambiente, verifique se a conta do Data Lake Storage existe e se todos os pré-requisitos são atendidos.

1. Na etapa de **Armazenamento de dados** durante a criação do ambiente, defina **Salvar dados de saída** como **Azure Data Lake Storage Gen2**.
1. Escolha como **Conectar seu armazenamento**. Você pode escolher entre uma opção baseada em recursos e outra baseada em assinatura para autenticação. Para obter mais informações, consulte [Conectar-se a uma conta do  Azure Data Lake Storage usando uma entidade de serviço do Azure](connect-service-principal.md).
   - Para **Assinatura do Azure**, escolha a **Inscrição**, o **Grupo de recursos** e a **Conta de armazenamento** que contém o contêiner `customerinsights`.
   - Para a **Chave da conta**, forneça o **Nome da conta** e a **Chave da conta** do Data Lake Storage. O uso desse método de autenticação implica que você seja informado se sua organização alternar as chaves. Você deve [atualizar a configuração do ambiente](manage-environments.md#edit-an-existing-environment) com a nova chave quando ela é girada.

Quando os processos do sistema, como a ingestão de dados, estão concluídos, o sistema cria pastas correspondentes na conta de armazenamento. Os arquivos de dados e os arquivos *model.json* são criados e adicionados às pastas com base no nome do processo.

Se você criar vários ambientes de Customer Insights e optar por salvar as entidades de saída desses ambientes em sua conta de armazenamento, o Customer Insights cria pastas separadas para cada ambiente com `ci_environmentID` no container.
