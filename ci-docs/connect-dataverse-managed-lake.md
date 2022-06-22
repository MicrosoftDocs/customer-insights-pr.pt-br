---
title: Conectar-se a tabelas no Microsoft Dataverse
description: Importar dados de um data lake gerenciado pelo Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: c470956b0453ac2558ed85acdeebba120a0ca55d
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011689"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conecte-se aos dados em um data lake gerenciado do Microsoft Dataverse

Os usuários do Microsoft Dataverse podem se conectar rapidamente a entidades analíticas em um lake gerenciado pelo Microsoft Dataverse.

> [!NOTE]
> Você deve ser um administrador na organização do Dataverse para prosseguir e exibir a lista de entidades disponíveis no lake gerenciado.

## <a name="important-considerations"></a>Considerações importantes

1. Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar ou se conectar aos dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center).
2. Apenas as entidades Dataverse com o [controle de alterações](/power-platform/admin/enable-change-tracking-control-data-synchronization) habilitado são visíveis. Essas entidades podem ser exportadas para o data lake gerenciado do Dataverse e usadas no Customer Insights. As tabelas do Dataverse prontas para uso têm o controle de alterações habilitado por padrão. Você precisa ativar o controle de alterações para tabelas personalizadas. Para verificar se uma tabela do Dataverse está com o controle de alterações habilitado, acesse [Power Apps](https://make.powerapps.com) > **Dados** > **Tabelas**. Encontre a tabela que você está procurando e selecione-a. Acesse **Configurações** > **Opções avançadas** e verifique a configuração **Controlar alterações**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectar-se a um data lake gerenciado do Dataverse

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Selecione **Microsoft Dataverse**.

1. Insira um **Nome** para a fonte de dados e uma **Descrição** opcional.

1. Forneça o **Endereço do servidor** para a organização do Dataverse e selecione **Entrar**.

1. Selecione as tabelas que você deseja ingerir como entidades no Customer Insights na lista disponível.

   > [!NOTE]
   > Se algumas tabelas já estiverem selecionadas, elas podem ser usadas por outros aplicativos do Dynamics 365 (como o Dynamics 365 Sales Insights ou o Customer Service Insights). Não é possível alterar a seleção. Essas tabelas estarão disponíveis como entidades assim que a fonte de dados for criada.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo mostrando uma lista de entidades no ambiente do Dataverse.":::

1. Salve sua seleção para começar a sincronizar as tabelas selecionadas do Dataverse. Você encontrará a conexão recém-adicionada na página **Fontes de dados**. Ela será enfileirada para atualização e mostrará a contagem de entidades como zero até que todas as tabelas selecionadas sejam sincronizadas.

Apenas uma fonte de dados de um ambiente pode usar simultaneamente o mesmo lake gerenciado pelo Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edite uma fonte de dados de lake gerenciado do Dataverse

Você só editará a seleção da entidade depois de criar a fonte de dados. Por exemplo, se entidades adicionais foram adicionadas ao Dataverse e você quiser importá-las também.
Para conectar-se a um data lake diferente do Dataverse, [crie uma nova fonte de dados](#connect-to-a-dataverse-managed-lake).

1. Acesse **Dados** > **Fontes de dados**.

1. Ao lado da fonte de dados que você deseja atualizar, selecione **Editar**

1. Selecione entidades adicionais na lista de entidades disponíveis e selecione **Salvar**.
