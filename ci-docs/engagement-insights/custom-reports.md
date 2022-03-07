---
title: Sobre relatórios personalizados
description: Saiba como criar relatórios personalizados.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: e8cdfc07b67b78febc1d50b3b1fd44ab94448e64
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8232134"
---
# <a name="create-and-edit-custom-reports"></a>Criar e editar relatórios personalizados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Além de relatórios prontos para uso (OOB), você pode criar um relatório personalizado com visualizações de gráficos e tabelas para ajudá-lo a entender o comportamento do usuário. Este artigo explica como criar um relatório com os dados de que você precisa usando visualizações de tabela e gráfico. Para obter informações sobre relatórios OOB, consulte [Visualizar relatórios](view-reports.md).

## <a name="create-a-custom-report"></a>Criar um relatório personalizado

1. Vá para **Analisar** > **Personalizado** para acessar a lista de relatórios personalizados.

1. Selecione **Novo relatório** para começar a criar um relatório personalizado.

   :::image type="content" source="media/new-custom-report.png" alt-text="Novos relatórios personalizados.":::

1. Decida o tipo de relatório que deseja criar:

    - Selecione **Adicionar visual** na barra de comandos para criar uma visualização de tabela padrão.
    - Ou selecione uma visualização de coluna, barra, linha, área, pizza, rosca ou de tabela da página **Editor de relatório**.

1. Na seção **Dados** do painel **Editor de visualização**, escolha uma das opções disponíveis (por exemplo, visualizações de página) na lista suspensa **Métricas**. Você também pode adicionar **Dimensões** (por exemplo, país) para mostrar na visualização. Para mais informações, consulte [Visualize e crie métricas](metrics.md) e [Visualize e crie dimensões](dimensions.md).

   :::image type="content" source="media/page-views.png" alt-text="Escolha uma métrica para seu relatório.":::

1. Selecione a seção **Projeto** do painel **Editor de visualização** para adicionar **Texto do título** e alternar o **Título** como ligado e desligado.  Você também pode alterar o tipo de visualização selecionando outro gráfico, como **gráfico de pizza**.

1. Para alterar o tamanho e a posição de uma visualização:
   - Selecione a visualização e arraste um dos cantos ou bordas para ajustar seu tamanho.
   - Selecione a visualização e mova-a para uma nova posição. Você também pode usar as teclas de seta para alterar a posição.
1. Para adicionar outra visualização, selecione **Adicionar visualização** na barra de comandos.
1. Depois de adicionar as visualizações desejadas para o relatório, selecione **Salvar** na barra de comandos.

1. Forneça um nome para o relatório personalizado e selecione **Salvar** para criá-lo.
 
## <a name="filter-a-custom-report"></a>Filtrar um relatório personalizado

Você pode selecionar o período de tempo ou intervalo de datas em um relatório personalizado para focar em um valor ou período de tempo.

Para selecionar um período de tempo, no canto superior direito da visualização do relatório, selecione um valor na lista suspensa do relatório. Você também pode escolher um *Período fixo*.

:::image type="content" source="media/filter-time-date-range.png" alt-text="Filtrar por intervalo de data ou hora.":::

Para a maioria dos relatórios, selecione **+ Adicionar condição**, para escolher uma dimensão ou segmento para filtrar o relatório. Para obter mais informações, consulte [Visualizar e criar segmentos](segments.md).

## <a name="edit-a-custom-report"></a>Editar um relatório personalizado

1. Vá para **Analisar** > **Personalizado** para acessar a lista de relatórios personalizados.

1. Na lista de relatórios personalizados, selecione **Mais [...]** 

1. Escolha **Editar nome** para alterar o nome do relatório.

1. Selecione o nome do relatório e use as opções **+ Adicionar visualização** e **Editar** para adicionar, remover, reposicionar ou redimensionar as visualizações.

1. Para alterar as propriedades de uma visualização, selecione o visual, selecione **...** e então **Editar visual**.

   :::image type="content" source="media/edit-visual-control.png" alt-text="Editando propriedades de gráfico para relatórios personalizados.":::

1. Após a edição do relatório, selecione **Salvar** para aplicar suas alterações. 

## <a name="delete-a-custom-report"></a>Excluir um relatório personalizado

1. Vá para **Analisar** > **Personalizado** para acessar a lista de relatórios personalizados.

1. Na lista de relatórios personalizados, selecione **...**

1. Escolha **Excluir** para remover o relatório.

1. Confirme sua exclusão para remover o relatório permanentemente.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
