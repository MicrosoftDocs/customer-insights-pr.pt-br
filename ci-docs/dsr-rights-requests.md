---
title: Solicitações de Direitos do Titular dos Dados (DSR) no RGPD | Microsoft Docs
description: Responder a Solicitações do Titular dos Dados do Dynamics 365 Customer Insights.
ms.date: 08/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 49251fb46957c4d7ec205b93c9547a3cd380eb11
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387097"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitações de Direitos do Titular dos Dados (DSR) no GDPR

O Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia está em vigor desde 25 de maio de 2018. Ele concede direitos significativos aos indivíduos em relação aos seus dados. O RGPD refere-se à proteção e à viabilização dos direitos de privacidade dos usuários. Leia mais sobre o compromisso da Microsoft com a segurança e a conformidade no [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Temos o compromisso de ajudar nossos clientes a atender aos requisitos do RGPD. Isso inclui o direito de excluir ou exportar dados que contenham informações pessoais, como IDs de usuário, números de telefone e endereços de email. Os administradores podem implementar solicitações do usuário para excluir ou exportar dados pessoais.

## <a name="responding-to-gdpr-data-subject-delete-requests-for-customer-insights"></a>Responder a solicitações de exclusão do titular dos dados do RGPD para o Customer Insights

O "direito de apagar" através de remoção de dados pessoais dos dados do cliente de uma organização é uma proteção chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e os logs gerados pelo sistema, exceto informações de log de auditoria.

### <a name="manage-data-subject-delete-requests"></a>Gerenciar solicitações de exclusão do titular dos dados

O Customer Insights oferece as seguintes experiências no produto para excluir dados pessoais de um cliente específico ou usuário do Customer Insights:

- **Gerenciar solicitações de exclusão de dados do cliente** : Os dados do cliente no Customer Insights são ingeridos de fontes de dados originais externas ao Customer Insights. Primeiro, execute as solicitações de exclusão do RGPD na fonte de dados original.
- **Gerenciar solicitações de exclusão de dados do usuário do Customer Insights**: dados para usuários são criados pelo Customer Insights. Execute todas as solicitações de exclusão do RGPD no Customer Insights.

#### <a name="manage-requests-to-delete-customer-data"></a>Gerenciar solicitações para excluir dados do cliente

Como administrador do Customer Insights, remova dados do cliente que foram excluídos na fonte de dados. Verifique se as solicitações de exclusão do RGPD foram executadas na fonte de dados original.

1. Entre no Dynamics 365 Customer Insights.

1. Acesse **Dados** > **Fontes de dados**.

1. Para cada fonte de dados na lista que contém dados excluídos do cliente:
   1. Selecione a fonte de dados e, em seguida, selecione **Atualizar**.
   1. Verifique o status da fonte de dados em **Status**. Uma marca de seleção significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo deu errado. Se um triângulo de aviso for exibido, entre em contato com D365CI@microsoft.com.

   :::image type="content" source="media/gdpr-data-sources.png" alt-text="Tratar solicitações de exclusão de RGPD de dados do cliente.":::

1. Após uma atualização bem-sucedida das fontes de dados, execute também as atualizações downstream. Principalmente se você não tiver uma atualização completa recorrente do Customer Insights agendada.

   > [!IMPORTANT]
   > Os segmentos estáticos não são incluídos em uma atualização completa ou em atualizações de downstream após uma solicitação de exclusão. Para garantir que os dados do cliente também sejam removidos de segmentos estáticos, recrie esses segmentos com os dados de origem atualizados.

#### <a name="manage-delete-requests-for-user-data"></a>Gerenciar solicitações de exclusão de dados do usuário

Como administrador do Customer Insights, exclua os dados do usuário do Customer Insights.

1. Entre no Dynamics 365 Customer Insights.

1. Acesse **Administrador** > **Segurança** > e selecione a guia **Usuários**.

1. Marque a caixa de seleção dos usuários que você deseja excluir.

1. Selecione **Remover**.

1. Confirme a exclusão.

## <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitações de exportação do titular dos dados de RGPD

O direito de portabilidade de dados permite que um titular dos dados solicite uma cópia de seus dados pessoais em um formato eletrônico (definido como “formato estruturado, comumente usado, legível por máquina e interoperável”) que pode ser transmitido para outro controlador de dados.

### <a name="manage-export-and-view-requests"></a>Gerenciar solicitações de exportação e exibição

Gerencie solicitações para exportar dados do cliente ou do usuário.

#### <a name="export-customer-data-tenant-admin"></a>Exportar dados do cliente (administrador do locatário)

Como administrador de locatários, exporte os dados do cliente.

1. Enviar um email para D365CI@microsoft.com especificando o endereço de email do cliente na solicitação. A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.
2. Reconheça a confirmação para exportar os dados para o cliente solicitado.
3. Receba os dados exportados através do endereço de e-mail do administrador do locatário.

#### <a name="export-user-data-tenant-admin"></a>Exportar dados do usuário (administrador do locatário)

Como administrador de locatários, exporte os dados do usuário.

1. Enviar um email para D365CI@microsoft.com especificando o endereço de email do usuário na solicitação. A equipe do Customer Insights envia um email para o endereço de email do administrador de locatários registrado, pedindo confirmação para exportar dados.
1. Reconheça a confirmação para exportar os dados para o usuário solicitado.
1. Receba os dados exportados através do endereço de e-mail do administrador do locatário.

## <a name="data-deletion-handling-in-dynamics-365-customer-insights"></a>Tratamento de exclusão de dados no Dynamics 365 Customer Insights

Os dados serão excluídos (partições de dados e instantâneos de dados) se as partições e os instantâneos de dados ficarem inativos por mais de 30 dias, o que significa que eles foram substituídos por novas partições e instantâneos por meio de uma atualização das fontes de dados.

Nem todos os dados e instantâneos são excluídos. A partição de dados e o instantâneo de dados mais recentes estão ativos porque são usados no Customer Insights. Em relação aos dados mais recentes, não importa se as fontes de dados não foram atualizadas nos últimos 30 dias.

[!INCLUDE [footer-include](includes/footer-banner.md)]
