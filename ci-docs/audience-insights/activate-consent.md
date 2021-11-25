---
title: Ativar regras de consentimento para segmentos em insights de público-alvo
description: Etapas para vincular dados de consentimento e ativar verificações de consentimento em insights de público-alvo.
ms.date: 11/03/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 33ec3a684c2ca47badb4e5461f069d1b2e4a4f3d
ms.sourcegitcommit: 2a0947cffb52eaf885aa2e50c95b3693f7e4c589
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "7753047"
---
# <a name="activate-consent-rules"></a>Ativar regras de consentimento

[O Centro de Consentimento (versão preliminar)](../consent-management/overview.md) ajuda você a harmonizar os dados de consentimento de várias fontes. Use a entidade unificada *Consentimento* para aplicar verificações padrão de consentimento. Depois de importar dados de consentimento na Centro de Consentimento e configurar as regras para os dados de consentimento importados, a entidade *Consentimento* será sincronizada automaticamente com os insights de público-alvo.

## <a name="enable-consent-checks"></a>Habilitar verificações de consentimento

Com os dados de consentimento importados para o Centro de Consentimento (versão preliminar) e as regras configuradas, é possível ativar as verificações de consentimento nos insights de público-alvo. 

:::image type="content" source="../consent-management/media/enable-consent-checks-audience-insights.png" alt-text="Guia Consentimento nas configurações de insights de público-alvo com dados de consentimento ativados.":::

1. Nos insights de público-alvo, vá para **Administrador** > **Sistema**.

1. Escolha a guia **Consentimento (versão preliminar)**.

1. Na seção **Habilitar verificações de consentimento**, defina a alternância para a área que deseja habilitar como **Ativado**.

1. Marque a caixa de seleção **Permitir substituição das regras de consentimento padrão** para remover as verificações padrão de consentimento aplicadas em um segmento específico. 

1. No menu suspenso, selecione onde deseja permitir substituições.     

1. Na seção **Vincular consentimento a perfis de clientes**, escolha o atributo que é usado como um identificador para vincular os dados de consentimento aos dados do cliente. Isso provavelmente é um número de telefone ou endereço de email. 

1. Selecione **Salvar** para aplicar as configurações.

## <a name="disable-consent-checks"></a>Desabilitar verificações de consentimento

Para parar de usar dados de consentimento em insights de público-alvo, um administrador deve atualizar as configurações do sistema de acordo.

1. Nos insights de público-alvo, vá para **Administrador** > **Sistema**.

1. Escolha a guia **Consentimento (versão preliminar)**.

1. Na seção **Habilitar verificações de consentimento**, defina a alternância como **Desativado**.
