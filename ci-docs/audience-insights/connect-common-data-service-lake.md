---
title: Conectar-se a entidades no lake gerenciado pelo Common Data Service
description: Importar dados de um data lake gerenciado pelo Common Data Service.
ms.date: 09/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: mhart
ms.openlocfilehash: b1cfab40c1edb32f4a7f359e1195cfb1e879a0d5
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596945"
---
# <a name="connect-to-data-in-a-common-data-service-managed-data-lake"></a>Conecte-se aos dados em um data lake gerenciado do Common Data Service

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artigo fornece informações sobre como os clientes existentes do Dynamics 365 podem se conectar rapidamente às suas entidades analíticas no lake gerenciado pelo Common Data Service. Você deve ser um administrador na organização do Common Data Service para prosseguir e ver a lista de entidades disponíveis no lake gerenciado.

## <a name="important-considerations"></a>Considerações importantes

Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar ou se conectar a dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-service-managed-lake"></a>Conectar-se a um data lake gerenciado do Common Data Service

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Selecione **Adicionar fonte de dados**.

3. Selecione **Conecte-se ao Common Data Service** e selecione **Avançar**.

4. Insira um **Nome** para a fonte de dados e selecione **Avançar**. Nomear diretrizes: 
   - Comece com uma letra.
   - Use somente letras e números. Caracteres especiais e espaços não são permitidos.
   - Use entre 3 e 64 caracteres.

5. Forneça o **Endereço do servidor** para sua organização do Common Data Service e selecione **Conectar-se**.

   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo para inserir o endereço de servidor do Common Data Service](media/enter-CDS-org-details.png)

6. Selecione as entidades que você deseja receber da lista disponível.    

   > [!NOTE]
   > Se algumas entidades já estiverem selecionadas, elas poderão ser usadas por outros aplicativos do Dynamics 365 (como o Dynamics 365 Sales Insights ou o Customer Service Insights). Não é possível alterar a seleção. Essas entidades estarão disponíveis assim que fonte de dados for criada.

   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo mostrando uma lista de entidades na organização do Common Data Service](media/select-analytical-entities.png)

7. Salve sua seleção para começar a sincronizar as entidades selecionadas com o lake gerenciado do Common Data Service. Você encontrará a conexão recém-adicionada na página **Fontes de dados**. Será colocado na fila para atualização e mostrará que as entidades contam como 0 até que todas as entidades sejam sincronizadas.

Apenas uma fonte de dados de um ambiente pode usar simultaneamente o mesmo lake gerenciado pelo Common Data Service.

## <a name="edit-a-common-data-service-managed-lake-data-source"></a>Edite uma fonte de dados de lake gerenciado do Common Data Service

Você só editará a seleção da entidade depois de criar a fonte de dados. Por exemplo, se entidades adicionais foram adicionadas ao Common Data Service e você quiser importá-las também.    
Para conectar-se a um Common Data Service diferente, [crie uma nova fonte de dados](#connect-to-a-common-data-service-managed-lake).

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Ao lado da fonte de dados que você deseja atualizar, selecione as reticências.

3. Selecione uma opção **Editar** na lista.

4. Selecione entidades adicionais na lista de entidades disponíveis e selecione **Salvar**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]