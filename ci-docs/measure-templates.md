---
title: Criar medidas usando modelos
description: Defina medidas usando modelos para casos de uso comuns.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measure-template
- customerInsights
ms.openlocfilehash: 6dc7fce78d10ba91de4b2abf54c6c6ab1c919d3a
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170759"
---
# <a name="create-measures-from-templates"></a>Criar medidas usando modelos

Use modelos predefinidos de [medidas](measures.md) comumente usadas para criá-las. Os modelos se baseiam em dados mapeados da entidade *Atividade Unificada*. Portanto, verifique se você configurou as [atividades de clientes](activities.md) antes de criar uma medida com base em um modelo.

Os modelos de medida têm suporte somente em ambientes para **clientes individuais**. Para criar medidas personalizadas ou criar medidas para B2B, consulte [Usar o construtor de medidas](measure-builder.md).

Modelos de medidas disponíveis:
- Valor médio da transação (ATV)
- Valor total da transação
- Receita média diária
- Receita média mensal
- Receita média anual
- Contagem de transações
- Pontos de fidelidade ganhos
- Pontos de fidelidade resgatados
- Saldo de pontos de fidelidade
- Período ativo do cliente
- Duração da associação ao programa de fidelidade
- Tempo desde a última compra

## <a name="build-a-new-measure-using-a-template"></a>Criar uma medida usando um modelo

1. Acesse **Medidas**.

1. Selecione **Novo** e, em seguida, selecione **Escolher um modelo**.

   :::image type="content" source="media/measure-use-template.png" alt-text="Captura de tela do menu suspenso ao criar uma nova medida com destaque no modelo.":::

1. Encontre o modelo que se adapta às suas necessidades e selecione **Escolher modelo**.

1. Revise os dados necessários e selecione **Começar** se você tiver todos os dados no local.

1. Selecione **Editar detalhes** ao lado do Nome da medida. Forneça um nome para a medida. Opcionalmente, adicione [marcas](work-with-tags-columns.md#manage-tags) à medida.

   :::image type="content" source="media/measures_edit_details.png" alt-text="Editar caixa de diálogo de detalhes":::

1. Selecione **Concluído**.

1. Na seção **Definir período**, defina o período dos dados. Para escolher se você deseja que a nova medida aborde todo o conjunto de dados, selecione **O tempo todo**, ou que a medida se concentre em um **Período específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de tela mostrando a seção do período ao configurar uma medida com base em um modelo.":::

1. Na próxima seção, selecione **Adicionar dados** para escolher as atividades e mapear os dados correspondentes da sua entidade *Atividade Unificada*.

    1. Etapa 1 de 2: em **Tipo de atividade**, escolha o tipo da entidade que deseja usar. Em **Atividades**, selecione as entidades que deseja mapear e selecione **Avançar**.
    1. Etapa 2 de 2: escolha o atributo da entidade *Atividade Unificada* do componente exigido pela fórmula. Por exemplo, para Valor médio da transação, é o atributo que representa o Valor da transação. Em **Carimbo de data/hora da atividade**, escolha o atributo na entidade *Atividade Unificada* que representa a data e a hora da atividade.
    1. Selecione **Salvar**.

    Quando há êxito no mapeamento de dados, o status **Concluído** é exibido e o nome das atividades e atributos mapeados é exibido.

1. Selecione **Executar** para calcular os resultados da medida. Selecione **Salvar rascunho** se quiser manter a configuração atual e executar a medida posteriormente. A página **Medidas** será exibida.

## <a name="next-step"></a>Próxima etapa

Use medidas existentes para criar [um segmento do cliente](segments.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
