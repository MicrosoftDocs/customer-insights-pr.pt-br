---
title: Ativar regras de consentimento para segmentos
description: Siga estas etapas para vincular dados de consentimento e ativar verificações de consentimento no Dynamics 365 Customer Insights. Um administrador também pode desativar as verificações de consentimento.
ms.date: 04/27/2022
ms.topic: how-to
author: anubhav-t
ms.author: antando
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f82e3a4031fee8bcaa88575cbd68b37385a7fffb
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755156"
---
# <a name="activate-consent-rules"></a>Ativar regras de consentimento

O [Centro de Consentimento (versão preliminar)](consent-management/overview.md) ajuda você a harmonizar os dados de consentimento de várias fontes. Use a entidade unificada *Consentimento* para aplicar verificações padrão de consentimento. Depois de importar dados de consentimento e configurar regras de mapa, a entidade *Consentimento* é automaticamente sincronizada com o Dynamics 365 Customer Insights.

## <a name="enable-consent-checks"></a>Habilitar verificações de consentimento

Com os dados de consentimento importados para o Centro de Consentimento (versão preliminar) e as regras configuradas, é possível habilitar as verificações de consentimento. 

:::image type="content" source="consent-management/media/enable-consent-checks.png" alt-text="Guia Consentimento em configurações do Customer Insights com dados de consentimento ativados.":::

1. No Customer Insights, acesse **Administrador** > **Sistema**.

1. Escolha a guia **Consentimento (versão preliminar)**.

1. Na seção **Habilitar verificações de consentimento**, defina a alternância para todas as área que deseja habilitar como **Ativado**.

1. Marque a caixa de seleção **Permitir substituição das regras de consentimento padrão** para remover as verificações padrão de consentimento aplicadas em um segmento específico. 

1. No menu suspenso, selecione onde deseja permitir substituições.     

1. Na seção **Vincular consentimento a perfis de clientes**, escolha o atributo que é usado como um identificador para vincular os dados de consentimento aos dados do cliente. Isso provavelmente é um número de telefone ou endereço de email. 

1. Selecione **Salvar** para aplicar as configurações.

## <a name="disable-consent-checks"></a>Desabilitar verificações de consentimento

Para parar de usar dados de consentimento no Customer Insights, um administrador deve atualizar as configurações do sistema de acordo.

1. No Customer Insights, acesse **Administrador** > **Sistema**.

1. Escolha a guia **Consentimento (versão preliminar)**.

1. Na seção **Habilitar verificações de consentimento**, defina a alternância como **Desativado**.

> [!TIP]
> Para parar de usar o recurso de gerenciamento de consentimento, consulte [Configurações do sistema no Centro de Consentimento (versão preliminar)](consent-management/system-settings.md).
