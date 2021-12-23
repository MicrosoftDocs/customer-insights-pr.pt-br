---
title: Gerenciar regras de consentimento padrão em segmentos
description: Com o recurso de gerenciamento de consentimento, você pode desabilitar ou alterar as regras de consentimento padrão se as substituições estiverem habilitadas.
ms.date: 12/01/2021
ms.service: customer-insights
mms.topic: how-to
author: smithy7
ms.author: smithc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 28c9ea49b1f3aebd3abd7d4de58fe61e6474158b
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7884156"
---
# <a name="disable-or-change-default-consent-rules"></a>Desativar ou alterar as regras de consentimento padrão

Se a sua organização usa o [recurso de gerenciamento de consentimento](../consent-management/overview.md) combinado com insights de público-alvo, [os administradores podem impor regras de consentimento](activate-consent.md) para os segmentos. 

Com as regras de consentimento aplicadas na área do segmento, cada segmento informa sobre o estado da verificação de consentimento e das regras. Se forem permitidas substituições, as regras de consentimento padrão serão desativadas para segmentos específicos. Cada criador de um segmento pode adicionar mais regras de consentimento sobre as regras padrão de um segmento. 

## <a name="for-administrators"></a>Para administradores

:::image type="content" source="../consent-management/media/consent-rules-segment.png" alt-text="Construtor de segmentos com opções de regra de consentimento.":::

**Para desativar as regras de consentimento padrão:**

1. Na notificação **Regras de consentimento**, selecione **Ver detalhes**. 

1. Defina a alternância **Regras de consentimento padrão** como **Desativado**.

**Para adicionar regras de consentimento:**

1. Na notificação **Regras de consentimento**, selecione **Ver detalhes**. 

1. Selecione **Adicionar regras de consentimento** e escolha uma regra de consentimento no menu suspenso **Selecionar tipo de dados de consentimento**.

1. Selecione **Salvar** para aplicar a nova regra ao segmento.

## <a name="for-contributors"></a>Para colaboradores

Para criar um segmento sem regras de consentimento aplicadas, você deve trabalhar com o seu administrador para desabilitá-las no seu segmento. No entanto, você pode adicionar suas próprias regras de consentimento aos segmentos que possui e gerencia.

É um processo de três etapas: 
1. [Criar o segmento](segments.md) nos insights de público-alvo e salvá-lo. 

1. Compartilhar o nome do segmento com o seu administrador e pedir a ele para [habilitar substituições para o seu segmento](activate-consent.md). 

1. Abrir seus segmentos novamente. Na notificação **Regras de consentimento**, selecione **Ver detalhes** e adicione as regras de consentimento que você deseja aplicar. Em seguida, **Salve** e **Execute** seu segmento.



[!INCLUDE[footer-include](../includes/footer-banner.md)] 
