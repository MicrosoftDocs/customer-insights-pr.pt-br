---
title: Solicitações de Direitos do Titular dos Dados (DSR) no RGPD | Microsoft Docs
description: Responda a Solicitações do Titular dos Dados para o recurso de insights de público-alvo do Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: e095eb4f8e194f314d7d6baf6fa6a7a319319d2a
ms.sourcegitcommit: 1946d7af0bd2ca216885bec3c5c95009996d9a28
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8350255"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitações de Direitos do Titular dos Dados (DSR) no GDPR

O Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia está em vigor desde 25 de maio de 2018. Ele concede direitos significativos aos indivíduos em relação aos seus dados. O RGPD refere-se à proteção e à viabilização dos direitos de privacidade dos usuários. Você pode ler mais sobre o compromisso da Microsoft com a segurança e conformidade no [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Temos o compromisso de ajudar nossos clientes a atender aos requisitos do RGPD. Inclui o direito de excluir e exportar dados que incluem informações pessoais, como IDs de usuário, números de telefone e endereços de email. Os administradores podem implementar solicitações do usuário para excluir ou exportar dados pessoais.

## <a name="audience-insights"></a>Insights do público-alvo

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Responder a solicitações de exclusão do titular dos dados de RGPD para o recurso de insights de público-alvo do Dynamics 365 Customer Insights

O "direito de apagar" através de remoção de dados pessoais dos dados do cliente de uma organização é uma proteção chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e os logs gerados pelo sistema, exceto informações de log de auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Gerenciar solicitações de exclusão do titular dos dados

Os insights de público-alvo oferecem as seguintes experiências no produto para excluir dados pessoais de um cliente ou usuário específico:

- **Gerenciar solicitações de exclusão de dados do cliente** : Os dados do cliente no Customer Insights são ingeridos de fontes de dados originais externas ao Customer Insights. Todas as solicitações de exclusão de RGPD devem ser executadas no fonte de dados original.
- **Gerenciar solicitações de exclusão de dados do usuário do Customer Insights**: dados para usuários são criados pelo Customer Insights. Todas as solicitações de exclusão de RGPD devem ser executadas no Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gerenciar solicitações para excluir dados do cliente

Um administrador do Customer Insights pode seguir estas etapas para remover dados do cliente que foram excluídos no fonte de dados:

1. Entre no Dynamics 365 Customer Insights.
2. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.
3. Para cada fonte de dados na lista que contém dados excluídos do cliente:
   1. Selecione (...) e depois selecione **Atualizar**.
   2. Verifique o status da fonte de dados em **Status**. Uma marca de seleção significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo deu errado. Se um triângulo de aviso for exibido, entre em contato com D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Tratar solicitações de exclusão de RGPD de dados do cliente.](audience-insights/media/gdpr-data-sources.png "Tratar solicitações de exclusão de RGPD de dados do cliente")

##### <a name="manage-delete-requests-for-user-data"></a>Gerenciar solicitações de exclusão de dados do usuário

Um administrador do Customer Insights pode seguir estas etapas para excluir os dados do usuário do Customer Insights:

1. Entre no Dynamics 365 Customer Insights.
2. Nos insights de público-alvo, vá para **Administrador** > **Permissões**.
3. Marque a caixa de seleção do usuário que você deseja excluir.
4. Selecione **Remover**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitações de exportação do titular dos dados de RGPD

Como parte de nosso compromisso de fazer parceria com você em sua jornada para o Regulamento Geral sobre a Proteção de Dados (GDPR), desenvolvemos uma documentação para ajudá-lo a se preparar. Essa documentação descreve as etapas que você pode seguir hoje para oferecer suporte à conformidade com o RGPD ao usar insights de público-alvo.

#### <a name="manage-export-and-view-requests"></a>Gerenciar solicitações de exportação e exibição

O direito de portabilidade de dados permite que um titular dos dados solicite uma cópia de seus dados pessoais em um formato eletrônico (definido como “formato estruturado, comumente usado, legível por máquina e interoperável”) que pode ser transmitido para outro controlador de dados.

##### <a name="export-customer-data-tenant-admin"></a>Exportar dados do cliente (administrador do locatário)

Um administrador do locatário pode seguir estas etapas para exportar dados:

1. Enviar um email para D365CI@microsoft.com especificando o endereço de email do cliente na solicitação. A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.
2. Reconheça a confirmação para exportar os dados para o cliente solicitado.
3. Receba os dados exportados através do endereço de e-mail do administrador do locatário.

##### <a name="export-user-data-tenant-admin"></a>Exportar dados do usuário (administrador do locatário)

1. Enviar um email para D365CI@microsoft.com especificando o endereço de email do usuário na solicitação. A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.
2. Reconheça a confirmação para exportar os dados para o usuário solicitado.
3. Receba os dados exportados através do endereço de e-mail do administrador do locatário.

## <a name="consent-management-preview"></a>Gerenciamento de consentimento (versão preliminar)

O recurso de gerenciamento de consentimento não coleta dados do usuário diretamente. Ele apenas importa e processa os dados de consentimento fornecidos por usuários em outros aplicativos.

Para remover os dados de consentimento sobre usuários específicos, remova-os das fontes de dados ingeridas para o recurso de gerenciamento de consentimento. Depois de atualizar a fonte de dados, os dados removidos também serão excluídos do Centro de Consentimento. Os aplicativos que usam a entidade de consentimento também excluirão os dados que foram removidos da fonte após uma [atualização](audience-insights/system.md#refresh-processes). Recomendamos atualizar as fontes de dados rapidamente depois de responder a uma solicitação do titular dos dados para remover os dados do usuário de todos os outros processos e aplicativos.


<!-- ## Engagement insights (preview)

### Deleting and exporting event data containing end user identifiable information

The following sections describe how to delete and export event data that might contain personal data.

To delete or export data:

1. Tag event properties that contain data with personal information.
2. Delete or export data associated with specific values (for example: a specified user ID).

#### Tag and update event properties

Personal data is tagged on an event property level. First, tag the properties being considered for deletion or export.

To tag an event property as containing personal information, follow these steps:

1. Open the workspace containing the event.

1. Go to **Data** > **Events** to see the list of events in the selected workspace.
  
1. Select the event you want to tag.

1. Select **Edit properties** to open the pane listing all properties of the selected event.
     
1. Select **...** and then choose **Edit** to reach the **Update property** dialog.

   ![Edit event.](engagement-insights/media/edit-event.png "Edit event")

1. In the **Update Property** window, choose **...** in the upper right corner, and then choose the **Contains EUII** box. Choose **Update** to save your changes.

   ![Save your changes.](engagement-insights/media/update-property.png "Save your changes")

   > [!NOTE]
   > Every time the event schema changes or you create a new event, it's recommended that you evaluate the associated event properties and tag or untag them as containing personal data, if necessary.

#### Delete or export tagged event data

If all event properties have been tagged appropriately as described in the previous step, an environment admin can issue a deletion request against the tagged event data.

To manage EUII deletion or export requests

1. Go to **Admin** > **Environment** > **Settings**.

1. In the **Manage end user identifiable information (EUII)** section, select **Manage EUII**.

##### Deletion

For deletion, you can enter a list of comma-separated user IDs in the **Delete end user identifiable information (EUII)** section. These IDs will then be compared with all tagged event properties of all projects in the current environment via exact string matching. 

If a property value matches one of the provided IDs, the associated event will be permanently deleted. Due to the irreversibility of this action, you must confirm the deletion after selecting **Delete**.

##### Export

The export process is identical to the deletion process when it comes to defining event property values in the **Export end user identifiable information (EUII)** section. Additionally, you'll need to provide an **Azure blob storage URL** to specify the export destination. The Azure Blob URL must include a [Shared Access Signature (SAS)](/azure/storage/common/storage-sas-overview).

After selecting **Export**, all events of the current team that contain matching tagged properties will be exported in CSV format to the export destination.

### Good practices

* Try to avoid sending any events that contain personal data.
* If you need to send events containing EUII data, limit the number of events and event properties that contain EUII data. Ideally, limit yourself to one such event.
* Make sure that as few people as possible have access to the sent personal data.
* For events containing personal data, make sure that you set one property to emit a unique identifier that can easily be linked to a specific user (for example, a user ID). This makes it easier to segregate data and to export or delete the right data.
* Only tag one property per event as containing personal data. Ideally one that only contains a unique identifier.
* Do not tag properties containing verbose values (for example, an entire request body). Engagement insights capability uses exact string matching when deciding which events to delete or export. -->

[!INCLUDE[footer-include](includes/footer-banner.md)]