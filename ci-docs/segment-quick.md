---
title: Criar segmentos simples com segmentos rápidos
description: Crie segmentos simples de clientes para agrupá-los com base em vários atributos.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: 98260371a17ff8a05912cc1bc08c67fbe9755727
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9171125"
---
# <a name="create-simple-segments-with-quick-segments"></a>Criar segmentos simples com segmentos rápidos

Segmentos rápidos lhe permitem construir segmentos simples com um único operador rapidamente para insights mais rápidos. Segmentos rápidos são suportados apenas em ambientes para **clientes individuais**.

## <a name="create-a-new-segment-with-quick-segments"></a>Criar um segmento com segmentos rápidos

1. Vá para **Segmentos**.

1. Selecione **Novo** > **Criar a partir de**.
   - Selecione a opção **Perfis** para criar um segmento baseado na entidade *unificada do cliente*.
   - Selecione a opção **Medidas** para construir um segmento em torno das medidas que você já criou.
   - Selecione a opção **Inteligência** para criar um segmento em torno de uma das entidades de saída que você gerou usando os recursos **Previsões** ou **Modelos personalizados**.

1. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo no menu suspenso **Campo**. Com base na sua seleção, o sistema fornece valores diferentes.
   - Para campos de categoria, a contagem dos 10 principais clientes será exibida. Escolha um **Valor** e selecione **Revisar**.
   - Para um atributo numérico, o sistema exibirá quais valores de atributo caem em cada percentil do cliente. Escolha um **Operador** e um **Valor** e selecione **Revisar**.

1. O sistema fornece um **Tamanho estimado do segmento**. Escolha se deseja gerar o segmento que você definiu ou voltar e escolher um campo diferente.

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nome e estimativa de um segmento rápido.":::

1. Forneça um **Nome** e um **Nome da entidade de saída** para seu segmento. Opcionalmente, adicione [marcas](work-with-tags-columns.md#manage-tags).

1. Selecione **Salvar** para criar seu segmento. A página **Segmentos** será exibida.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-steps"></a>Próximas etapas

[Exportar um segmento](export-destinations.md) e explorar a [Integração do cartão do cliente](customer-card-add-in.md) para usar segmentos em outros aplicativos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
