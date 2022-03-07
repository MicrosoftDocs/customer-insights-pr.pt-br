---
title: Use segmentos de insights do público-alvo para filtrar relatórios de insights de participação
description: Use segmentos de insights do público-alvo em análises interativas de dados comportamentais capturados por insights de participação no site de um cliente.
ms.date: 07/27/2021
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 9c8c7a1a9216e04ebee100c548afbc745af396ec
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8230472"
---
# <a name="use-audience-insights-segments-to-filter-engagement-insights-reports"></a>Use segmentos de insights do público-alvo para filtrar relatórios de insights de participação

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Com insights de participação, você pode usar segmentos de insights do público-alvo em análises interativas de dados comportamentais capturados por insights de participação em seus sites.

## <a name="prerequisite"></a>Pré-requisito

- Um ambiente de insights de participação no qual você tem dados de segmentos de insights do público-alvo vinculados ao ambiente de insights do público-alvo em que os segmentos e perfis de cliente são criados. Mais informações: [Criar um link entre insights do público-alvo e insights de participação](integrate-audience-insights-engagement-insights.md)

## <a name="create-audience-insights-segments"></a>Criar segmentos de insights do público-alvo 

> [!IMPORTANT]
> Para que segmentos de insights do público-alvo apareçam em insights de participação, você deve primeiro [executar processos de mesclagem e downstream](../audience-insights/merge-entities.md). Os processos de downstream são importantes porque geram uma tabela única que prepara segmentos de insights do público-alvo a serem compartilhados com insights de participação. (Se uma atualização do sistema for agendada, ela incluirá automaticamente processos de downstream.)

Você pode usar segmentos de insights do público-alvo em relatórios prontos para uso de insights de participação ou em relatórios personalizados que você criou. Para obter mais informações, acesse [Relatórios de perfil prontos para uso](profile-reports.md) e [Crie e edite relatórios personalizados](custom-reports.md).

**Para usar segmentos de insights do público-alvo em relatórios de insights de participação**

1. Na página **Espaço de trabalho**, selecione **Dados** e, depois, selecione a guia **Segmentos**.

    :::image type="content" source="media/integrate-audience-insights-segments1.png" alt-text="Selecione a guia Segmentos.":::

   >[!NOTE]
   > Selecionar um segmento de insights do público-alvo leva você a insights do público-alvo, onde é possível descobrir como esse segmento foi criado em termos de regras e lógica. Para obter mais informações sobre segmentos de insights do público-alvo, acesse [Exibir e criar segmentos](../audience-insights/segments.md).

2. Selecione um relatório pronto para uso ou [crie um relatório personalizado](custom-reports.md) e, depois, selecione **Adicionar condição**. (Para este exemplo, escolhemos o relatório **Exibições de página**.)

    :::image type="content" source="media/integrate-audience-insights-segments2.png" alt-text="Adicionar uma condição.":::

3. Selecione **Filtrar por segmento**, expanda a lista **Tipo de segmento** e, depois, selecione **Demográfico**.

    :::image type="content" source="media/integrate-audience-insights-segments3.png" alt-text="Selecione o tipo de segmento Demográfico.":::

4. Expanda a lista **Nome do segmento** e, depois, escolha um segmento de insights do público-alvo.

    :::image type="content" source="media/integrate-audience-insights-segments4.png" alt-text="Escolha um segmento.":::

5. Você pode aplicar um ou mais segmentos, incluindo segmentos comportamentais (insights de participação) e demográficos (insights do público-alvo). 

    :::image type="content" source="media/integrate-audience-insights-segments6.png" alt-text="Relatório Exibições de página restrito a clientes dos EUA e segmentos da página inicial.":::

Na imagem anterior, os segmentos **Clientes dos EUA** e **Pagina inicial** foram selecionados, o que restringe o relatório **Exibições de página** para exibir apenas esses dois segmentos. 


>[!NOTE]
> Você pode usar segmentos de insights do público-alvo para filtrar relatórios prontos para uso e funis em insights de participação. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]