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
ms.openlocfilehash: eeabd889f7b694f8d809894169a3cdc068acc340
ms.sourcegitcommit: 9ef2cf99b847e7bd8f890f83d84b3a4045aaf8cc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2022
ms.locfileid: "8529387"
---
# <a name="use-a-template-to-build-a-measure"></a>Usar um modelo para criar uma medida

Você pode usar modelos predefinidos de [medidas](measures.md) comumente usadas para criá-las. Descrições detalhadas dos modelos e uma experiência guiada ajudam na criação de medidas eficientes. Os modelos se baseiam em dados mapeados da entidade *Atividade Unificada*. Portanto, verifique se você configurou as [atividades de clientes](activities.md) antes de criar uma medida com base em um modelo.

Para criar medidas personalizadas, consulte [Usar o construtor de medidas para criar medidas a partir do zero](measure-builder.md).

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

Modelos de medidas disponíveis: 
- Valor médio da transação (ATV)
- Valor total da transação
- Receita média diária
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

1. Na seção **Definir período**, defina o período dos dados a serem usados. Para escolher se você deseja que a nova medida aborde todo o conjunto de dados, selecione **O tempo todo**, ou que a medida se concentre em um **Período específico**.

   :::image type="content" source="media/measure-set-time-period.png" alt-text="Captura de tela mostrando a seção do período ao configurar uma medida com base em um modelo.":::

1. Na próxima seção, selecione **Adicionar dados** para escolher as atividades e mapear os dados correspondentes da sua entidade *Atividade Unificada*.

    1. Etapa 1 de 2: em **Tipo de atividade**, escolha o tipo da entidade que deseja usar. Para **Atividades**, selecione as entidades que deseja mapear.
    1. Etapa 2 de 2: escolha o atributo da entidade *Atividade Unificada* do componente exigido pela fórmula. Por exemplo, para Valor médio da transação, é o atributo que representa o Valor da transação. Para **Carimbo de data/hora da atividade**, escolha o atributo da entidade Atividade Unificada que representa a data e hora da atividade.
   
1. Depois que o mapeamento de dados for bem-sucedido, você poderá ver o status como **Concluído** e o nome das atividades e atributos mapeados.

1. Agora você pode selecionar **Executar** para calcular os resultados da medida. Para refiná-los mais tarde, selecione **Salvar rascunho**.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

Este recurso está disponível apenas para medidas criadas em ambientes com clientes individuais como público-alvo primário.

---
