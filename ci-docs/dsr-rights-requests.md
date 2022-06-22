---
title: Solicitações de Direitos do Titular dos Dados (DSR) no RGPD | Microsoft Docs
description: Responder a Solicitações do Titular dos Dados do Dynamics 365 Customer Insights.
ms.date: 05/23/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c71305ab835b0f4f75adcce716e795959f898e47
ms.sourcegitcommit: 8e9f0a9693fd8d91ad0227735ff03688fef5406f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2022
ms.locfileid: "8947354"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitações de Direitos do Titular dos Dados (DSR) no GDPR

O Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia está em vigor desde 25 de maio de 2018. Ele concede direitos significativos aos indivíduos em relação aos seus dados. O RGPD refere-se à proteção e à viabilização dos direitos de privacidade dos usuários. Você pode ler mais sobre o compromisso da Microsoft com a segurança e conformidade no [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Temos o compromisso de ajudar nossos clientes a atender aos requisitos do RGPD. Inclui o direito de excluir e exportar dados que incluem informações pessoais, como IDs de usuário, números de telefone e endereços de email. Os administradores podem implementar solicitações do usuário para excluir ou exportar dados pessoais.

## <a name="dynamics-365-customer-insights"></a>Dynamics 365 Customer Insights

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights"></a>Responder a solicitações de exclusão do titular dos dados do RGPD para Dynamics 365 Customer Insights

O "direito de apagar" através de remoção de dados pessoais dos dados do cliente de uma organização é uma proteção chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e os logs gerados pelo sistema, exceto informações de log de auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Gerenciar solicitações de exclusão do titular dos dados

O Customer Insights oferece as seguintes experiências no produto para excluir dados pessoais de um cliente específico ou usuário do Customer Insights:

- **Gerenciar solicitações de exclusão de dados do cliente** : Os dados do cliente no Customer Insights são ingeridos de fontes de dados originais externas ao Customer Insights. Todas as solicitações de exclusão de RGPD devem ser executadas no fonte de dados original.
- **Gerenciar solicitações de exclusão de dados do usuário do Customer Insights**: dados para usuários são criados pelo Customer Insights. Todas as solicitações de exclusão de RGPD devem ser executadas no Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gerenciar solicitações para excluir dados do cliente

Um administrador do Customer Insights pode seguir estas etapas para remover dados do cliente que foram excluídos no fonte de dados:

1. Entre no Dynamics 365 Customer Insights.
2. Acesse **Dados** > **Fontes de dados**
3. Para cada fonte de dados na lista que contém dados excluídos do cliente:
   1. Selecione as reticências verticais (&vellip;) e, depois, **Atualizar**.
   2. Verifique o status da fonte de dados em **Status**. Uma marca de seleção significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo deu errado. Se um triângulo de aviso for exibido, entre em contato com D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Tratar solicitações de exclusão de RGPD de dados do cliente.](media/gdpr-data-sources.png "Tratar solicitações de exclusão de RGPD de dados do cliente")

##### <a name="manage-delete-requests-for-user-data"></a>Gerenciar solicitações de exclusão de dados do usuário

Um administrador do Customer Insights pode seguir estas etapas para excluir os dados do usuário do Customer Insights:

1. Entre no Dynamics 365 Customer Insights.
2. Acesse **Administrador** > **Segurança** > **Permissões**.
3. Marque a caixa de seleção do usuário que você deseja excluir.
4. Selecione **Remover**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitações de exportação do titular dos dados de RGPD

Como parte de nosso compromisso de parceria com você na jornada para o Regulamento Geral sobre a Proteção de Dados (RGPD), desenvolvemos uma documentação para ajudá-lo a responder a solicitações de titulares de dados.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]