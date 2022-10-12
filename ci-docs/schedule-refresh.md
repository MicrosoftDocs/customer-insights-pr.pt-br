---
title: Agendar a atualização do sistema
description: Agende o horário em que o sistema deve ser atualizado
ms.date: 09/27/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-system-schedule
- customerInsights
ms.openlocfilehash: 4aac02b570357d2086f7a9d7340b0e4837157a0b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610314"
---
# <a name="schedule-system-refresh"></a>Agendar a atualização do sistema

Agende atualizações automáticas de todos as suas [fontes de dados ingeridos](data-sources.md). As atualizações automática ajudam a garantir que as atualizações de suas fontes de dados sejam refletidas no seus perfis de cliente unificado.

> [!NOTE]
> As fontes de dados do Power Query gerenciadas por você são atualizadas de acordo com suas próprias agendas. Para agendar a atualização dessas fontes de dados do Power Query, defina as configurações de atualização nessa fonte de dados específica na página **Fontes de dados**. Alinhe o tempo com o agendamento de atualização de dados upstream para que as atualizações não ocorram todas de uma vez.
> :::image type="content" source="media/PPDF-edit-refresh.png" alt-text="Configurações de atualização de de fluxo de dados do Power Platform.":::

## <a name="set-system-refresh-schedule"></a>Definir a agenda de atualização do sistema

1. Vá para **Administrador** > **Sistema** e selecione a guia **Agendar**.

   :::image type="content" source="media/schedule_refresh.png" alt-text="Guia Agendar atualização na página Sistema.":::

1. O estado padrão para a atualização agendada é **Desativado**. Para ativar as atualizações agendadas, altere a alternância na parte superior da tela para **Ativado**.

1. Escolha entre atualizações **Semanal** (padrão) e **Diária**. Se você pretende agendar atualizações semanais, selecione um ou mais dias nos quais deseja executar a atualização.

1. Defina seu **Fuso horário**, em seguida, use a lista suspensa **Tempo** para definir seu tempo de atualização. Se você deseja agendar várias atualizações em um único dia, selecione **Adicionar outra hora**. Você pode adicionar até quatro atualizações.

1. Selecione **Salvar** para aplicar suas alterações.

[!INCLUDE [footer-include](includes/footer-banner.md)]
