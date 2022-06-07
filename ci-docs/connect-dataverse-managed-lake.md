---
title: Conectar-se a tabelas no Microsoft Dataverse
description: Importar dados de um data lake gerenciado pelo Microsoft Dataverse.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 7140e9254108bc6f0d518b3ccf4b10fc33cde115
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800149"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conecte-se aos dados em um data lake gerenciado do Microsoft Dataverse

Este artigo fornece informações sobre como os usuários do Dataverse podem se conectar rapidamente a entidades analíticas em um lake gerenciado pelo Microsoft Dataverse. 

> [!NOTE]
> Você deve ser um administrador na organização do Dataverse para prosseguir e exibir a lista de entidades disponíveis no lake gerenciado.

## <a name="important-considerations"></a>Considerações importantes

1. Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar ou se conectar aos dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center).
2. Apenas as entidades Dataverse com o [controle de alterações](/power-platform/admin/enable-change-tracking-control-data-synchronization) habilitado são visíveis. Essas entidades podem ser exportadas para o data lake gerenciado do Dataverse e usadas no Customer Insights. As tabelas do Dataverse prontas para uso têm o controle de alterações habilitado por padrão. Você precisa ativar o controle de alterações para tabelas personalizadas. Para verificar se uma tabela do Dataverse está com o controle de alterações habilitado, acesse [Power Apps](https://make.powerapps.com) > **Dados** > **Tabelas**. Encontre a tabela que você está procurando e selecione-a. Acesse **Configurações** > **Opções avançadas** e verifique a configuração **Controlar alterações**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectar-se a um data lake gerenciado do Dataverse

1. No Customer Insights, acesse **Dados** > **Fontes de dados**.

2. Selecione **Adicionar fonte de dados**.

3. Selecione **Microsoft Dataverse** e, em seguida, selecione **Avançar**.

4. Insira um **Nome** para a fonte de dados e selecione **Avançar**. 

5. Forneça o **Endereço do servidor** para a organização do Dataverse e selecione **Entrar**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Tela na etapa de ingestão de dados em que um usuário pode inserir a URL do ambiente do Dataverse.":::

6. Selecione as tabelas que você deseja ingerir como entidades no Customer Insights na lista disponível.    

   > [!NOTE]
   > Se algumas tabelas já estiverem selecionadas, elas podem ser usadas por outros aplicativos do Dynamics 365 (como o Dynamics 365 Sales Insights ou o Customer Service Insights). Não é possível alterar a seleção. Essas tabelas estarão disponíveis como entidades assim que a fonte de dados for criada.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo mostrando uma lista de entidades no ambiente do Dataverse.":::

7. Salve sua seleção para começar a sincronizar as tabelas selecionadas do Dataverse. Você encontrará a conexão recém-adicionada na página **Fontes de dados**. Ela será enfileirada para atualização e mostrará a contagem de entidades como zero até que todas as tabelas selecionadas sejam sincronizadas.

Apenas uma fonte de dados de um ambiente pode usar simultaneamente o mesmo lake gerenciado pelo Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edite uma fonte de dados de lake gerenciado do Dataverse

Você só editará a seleção da entidade depois de criar a fonte de dados. Por exemplo, se entidades adicionais foram adicionadas ao Dataverse e você quiser importá-las também.    
Para conectar-se a um data lake diferente do Dataverse, [crie uma nova fonte de dados](#connect-to-a-dataverse-managed-lake).

1. Acesse **Dados** > **Fontes de dados**.

2. Ao lado da fonte de dados que você deseja atualizar, selecione as reticências verticais (&vellip;).

3. Selecione uma opção **Editar** na lista.

4. Selecione entidades adicionais na lista de entidades disponíveis e selecione **Salvar**.

[!INCLUDE [footer-include](includes/footer-banner.md)]