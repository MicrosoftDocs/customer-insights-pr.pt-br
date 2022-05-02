---
title: Entender e gerenciar medidas
description: Saiba como as medidas ajudam a analisar e refletir o desempenho do seu negócio.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 84a3a10a2517258c1f895800882b9c67391ec3de
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645638"
---
# <a name="measures-overview"></a>Visão geral de medidas

As medidas ajudam você a entender melhor os comportamentos dos clientes e o desempenho dos negócios. Elas analisam para valores relevantes de [perfis unificados](data-unification.md). Por exemplo, uma empresa deseja ver o *gasto total por cliente* para entender o histórico ou a medida de um cliente específico ou medir as *vendas totais da empresa* para entender a receita de nível agregado em toda a empresa.  

As medidas são criadas [usando-se o construtor de medidas](measure-builder.md), uma plataforma de consulta de dados com vários operadores e opções de mapeamento simples. Ele permite filtrar dados, agrupar resultados, detectar [caminhos de relacionamento de entidades](relationships.md) e exibir a saída. Você pode [usar modelos predefinidos](measure-templates.md) para configurar de modo eficiente medidas comumente usadas.

Use o construtor de medidas para extrair insights e planejar atividades comerciais por meio da consulta de dados do cliente. Por exemplo, criar uma medida de *gasto total por cliente* e *retorno total por cliente* ajuda a identificar um grupo de clientes com alto gasto, mas alto retorno. Você pode [criar um segmento](segments.md) com base nessas medidas para impulsionar as próximas ações recomendadas.

## <a name="manage-your-measures"></a>Gerenciar suas medidas

Você pode encontrar a lista de medidas na página **Medidas**.

Você encontrará informações sobre o tipo de medida, o criador, a data de criação, o status e o estado. Ao selecionar uma nova medida, na lista, você pode visualizar a saída e baixar um arquivo CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Ações para gerenciar medidas únicas."lightbox="media/measures-actions.png":::

As seguintes ações estão disponíveis quando você seleciona uma medida:

- **Editar** a configuração da medida.
- **Duplicar** uma medida. Você pode optar por editar suas propriedades imediatamente ou simplesmente salvar a duplicidade.
- **Atualizar** a medida com base nos dados mais recentes. Para atualizar todas as suas medidas ao mesmo tempo, selecione todas as medidas e, em seguida, **Atualizar**.
- **Renomear** a medida.
- **Ativar** ou **Desativar**. Medidas inativas não serão atualizadas durante uma [atualização agendada](system.md#schedule-tab).
- **Marcar** para [gerenciar as marcas](work-with-tags-columns.md#manage-tags) para o segmento.
- **Excluir** a medida.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="next-step"></a>Próxima etapa

Você pode usar medidas existentes para criar [um segmento de cliente](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
