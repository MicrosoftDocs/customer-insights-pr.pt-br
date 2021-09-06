---
title: Solicitações de Direitos do Titular dos Dados (DSR) no RGPD | Microsoft Docs
description: Responda a Solicitações do Titular dos Dados para o recurso de insights de público-alvo do Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 891794321f20954533ec0374b397eaf6b30445c2b0c95f601009912b3c3950a7
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034484"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitações de Direitos do Titular dos Dados (DSR) no GDPR

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Responder a solicitações de exclusão do titular dos dados de RGPD para o recurso de insights de público-alvo do Dynamics 365 Customer Insights

O "direito de apagar" através de remoção de dados pessoais dos dados do cliente de uma organização é uma proteção chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e os logs gerados pelo sistema, exceto informações de log de auditoria.

### <a name="manage-data-subject-delete-requests"></a>Gerenciar solicitações de exclusão do titular dos dados

Os insights de público-alvo oferecem as seguintes experiências no produto para excluir dados pessoais de um cliente ou usuário específico:

- **Gerenciar solicitações de exclusão de dados do cliente** : Os dados do cliente no Customer Insights são ingeridos de fontes de dados originais externas ao Customer Insights. Todas as solicitações de exclusão de RGPD devem ser executadas no fonte de dados original.
- **Gerenciar solicitações de exclusão de dados do usuário do Customer Insights**: dados para usuários são criados pelo Customer Insights. Todas as solicitações de exclusão de RGPD devem ser executadas no Customer Insights.

#### <a name="manage-delete-requests-for-customer-data"></a>Gerenciar solicitações de exclusão de dados do cliente

Um administrador do Customer Insights pode seguir estas etapas para remover dados do cliente que foram excluídos no fonte de dados:

1. Entre no Dynamics 365 Customer Insights.
2. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.
3. Para cada fonte de dados na lista que contém dados excluídos do cliente:
   1. Selecione (...) e depois selecione **Atualizar**.
   2. Verifique o status da fonte de dados em **Status**. Uma marca de seleção significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo deu errado. Se um triângulo de aviso for exibido, entre em contato com D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Tratar solicitações de exclusão de RGPD de dados do cliente.](media/gdpr-data-sources.png "Tratar solicitações de exclusão de RGPD de dados do cliente")

#### <a name="manage-delete-requests-for-user-data"></a>Gerenciar solicitações de exclusão de dados do usuário

Um administrador do Customer Insights pode seguir estas etapas para excluir os dados do usuário do Customer Insights:

1. Entre no Dynamics 365 Customer Insights.
2. Nos insights de público-alvo, vá para **Administrador** > **Permissões**.
3. Marque a caixa de seleção do usuário que você deseja excluir.
4. Selecione **Remover**.

> [!div class="mx-imgBorder"]
> ![Tratar solicitações de exclusão de RGPD de dados do usuário.](media/gdpr-permissions.png "Tratar solicitações de exclusão de RGPD de dados do usuário")

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitações de exportação do titular dos dados de RGPD

Como parte de nosso compromisso de fazer parceria com você em sua jornada para o Regulamento Geral sobre a Proteção de Dados (GDPR), desenvolvemos uma documentação para ajudá-lo a se preparar. Essa documentação descreve as etapas que você pode seguir hoje para oferecer suporte à conformidade com o RGPD ao usar insights de público-alvo.

### <a name="manage-export-and-view-requests"></a>Gerenciar solicitações de exportação e exibição

O direito de portabilidade de dados permite que um titular dos dados solicite uma cópia de seus dados pessoais em um formato eletrônico (definido como “formato estruturado, comumente usado, legível por máquina e interoperável”) que pode ser transmitido para outro controlador de dados.

#### <a name="export-customer-data-tenant-admin"></a>Exportar dados do cliente (administrador do locatário)

Um administrador do locatário pode seguir estas etapas para exportar dados:

1. Enviar um email para D365CI@microsoft.com especificando o endereço de email do cliente na solicitação. A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.
2. Reconheça a confirmação para exportar os dados para o cliente solicitado.
3. Receba os dados exportados através do endereço de e-mail do administrador do locatário.

#### <a name="export-user-data-tenant-admin"></a>Exportar dados do usuário (administrador do locatário)

1. Enviar um email para D365CI@microsoft.com especificando o endereço de email do usuário na solicitação. A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.
2. Reconheça a confirmação para exportar os dados para o usuário solicitado.
3. Receba os dados exportados através do endereço de e-mail do administrador do locatário.


[!INCLUDE[footer-include](../includes/footer-banner.md)]