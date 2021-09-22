---
title: Use dimensões demográficas para dividir dados comportamentais (dimensões coletadas)
description: Use dimensões coletadas do perfil unificado para habilitar propriedades do perfil do cliente para insights do público-alvo.
ms.date: 07/27/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 50bb800c9e097d03cc6f26f79819c741ab5e8baf
ms.sourcegitcommit: 1c396394470df8e68c2fafe3106567536ff87194
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "7461089"
---
# <a name="use-demographic-dimensions-for-splitting-behavioral-data"></a>Use dimensões demográficas para dividir dados comportamentais

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Ao usar dimensões demográficas do perfil unificado, os usuários de insights de participação podem acessar propriedades de perfil de insights do público-alvo. Você pode usar essas propriedades em análises interativas de dados comportamentais, incluindo dados capturados por insights de participação no site ou aplicativo móvel.

>[!NOTE]
> Os insights de participação incluem dimensões predefinidas para propriedades de eventos. Mais informações: [Exibir e criar dimensões](dimensions.md)

## <a name="prerequisite"></a>Pré-requisito

- Um ambiente de insights de participação no qual você tem dados de perfil do cliente vinculados ao ambiente de insights do público-alvo em que os perfis de cliente são criados. Mais informações: [Criar um link entre insights do público-alvo e insights de participação](integrate-audience-insights-engagement-insights.md)

> [!NOTE]
> Depois de criar um link entre os ambientes de insights do público-alvo e de insights de participação, talvez você deseje apenas dados específicos para propriedades de perfil do cliente, que podem ser úteis como dimensões em insights de participação. Para obter mais informações acesse [Habilite atributos e segmentos de perfis unificados de insights do público-alvo](integrate-audience-insights-engagement-insights.md#enable-audience-insights-unified-profiles-attributes-and-segments).<!--note from editor: Suggested. -->

## <a name="create-a-new-custom-report"></a>Criar um novo relatório personalizado

1. No painel esquerdo, selecione **Personalizado** > **Novo relatório** e selecione a métrica desejada. (Para este exemplo, escolhemos **Exibições de página por Hora**.)

    :::image type="content" source="media/curated-dimensions1.png" alt-text="Selecionar uma métrica.":::

2. No editor de visualização, selecione **Dimensões** e, depois, selecione **Demográfico** no menu suspenso **Tipo de Dimensão**.

    :::image type="content" source="media/curated-dimensions2.png" alt-text="Selecione demográfico.":::

3. Selecione uma dimensão **Signal.Customer.*xxx***. (Este exemplo mostra Signal.Customer.Country.)

    :::image type="content" source="media/curated-dimensions3.png" alt-text="Selecione uma dimensão.":::
  
## <a name="limitations"></a>Limitações

No momento, você só pode usar dimensões demográficas para dividir dados comportamentais.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
