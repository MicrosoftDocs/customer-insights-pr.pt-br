---
title: Conectar-se a tabelas no Microsoft Dataverse
description: Importar dados de um data lake gerenciado pelo Microsoft Dataverse.
ms.date: 07/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: f92d64723e6a4d2fcebdbb3758519d4bfd4aeaf4
ms.sourcegitcommit: 8cc70f30baaae13dfb9c4c201a79691f311634f5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2021
ms.locfileid: "6692560"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conecte-se aos dados em um data lake gerenciado do Microsoft Dataverse

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artigo fornece informações sobre como os usuários do Dataverse podem se conectar rapidamente às suas entidades analíticas em um lake gerenciado do Dataverse. Você deve ser um administrador na organização do Dataverse para prosseguir e ver a lista de entidades disponíveis no lake gerenciado.

## <a name="important-considerations"></a>Considerações importantes

Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar ou se conectar a dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectar-se a um data lake gerenciado do Dataverse

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Selecione **Adicionar fonte de dados**.

3. Selecione **Conectar-se ao lake gerenciado do Microsoft Dataverse** e selecione **Avançar**.

4. Insira um **Nome** para a fonte de dados e selecione **Avançar**. Nomear diretrizes: 
   - Comece com uma letra.
   - Use somente letras e números. Caracteres especiais e espaços não são permitidos.
   - Use entre 3 e 64 caracteres.

5. Forneça o **Endereço do servidor** para a organização do Dataverse e selecione **Entrar**.

   :::image type="content" source="media/ingest-dataverse-server-address.png" alt-text="Tela na etapa de ingestão de dados em que um usuário pode inserir a URL do ambiente do Dataverse.":::

6. Selecione as tabelas que deseja ingerir como entidades para insights de público-alvo na lista disponível.    

   > [!NOTE]
   > Se algumas tabelas já estiverem selecionadas, elas podem ser usadas por outros aplicativos do Dynamics 365 (como o Dynamics 365 Sales Insights ou o Customer Service Insights). Não é possível alterar a seleção. Essas tabelas estarão disponíveis como entidades assim que a fonte de dados for criada.

   :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo mostrando uma lista de entidades no ambiente do Dataverse.":::

7. Salve sua seleção para começar a sincronizar as tabelas selecionadas do Dataverse. Você encontrará a conexão recém-adicionada na página **Fontes de dados**. Ela será enfileirada para atualização e mostrará a contagem de entidades como zero até que todas as tabelas selecionadas sejam sincronizadas.

Apenas uma fonte de dados de um ambiente pode usar simultaneamente o mesmo lake gerenciado pelo Dataverse.

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edite uma fonte de dados de lake gerenciado do Dataverse

Você só editará a seleção da entidade depois de criar a fonte de dados. Por exemplo, se entidades adicionais foram adicionadas ao Dataverse e você quiser importá-las também.    
Para conectar-se a um data lake diferente do Dataverse, [crie uma nova fonte de dados](#connect-to-a-dataverse-managed-lake).

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Ao lado da fonte de dados que você deseja atualizar, selecione as reticências.

3. Selecione uma opção **Editar** na lista.

4. Selecione entidades adicionais na lista de entidades disponíveis e selecione **Salvar**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]