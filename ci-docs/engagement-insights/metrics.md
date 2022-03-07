---
title: Exibir e criar métricas
description: Como criar, editar e excluir métricas.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7e8c96f38af74f25080a40fd92e73f05c71320a8
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229802"
---
# <a name="view-and-create-metrics"></a>Exibir e criar métricas

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

As métricas ajudam a entender o comportamento de seus visitantes. Elas agregam propriedades de eventos e medem estatísticas e desempenho de suas propriedades da Web.  

Suponha que você esteja realizando uma promoção de marketing em seu site. Você pode usar métricas para rastrear o número de visitantes únicos ou usuários que vieram ao seu site durante a promoção. Analisar as métricas ajuda você a entender melhor o público-alvo do seu site. Combinar métricas com [dimensões](dimensions.md) em um [relatório personalizado](custom-reports.md) permite medir o comportamento para entender seus usuários. Por exemplo, você pode separar os visitantes em categorias novas e recorrentes para identificar as diferenças de interesse e intenção entre os grupos.

## <a name="view-metrics"></a>Exibir métricas

Os insights de participação incluem agregações comumente usadas de propriedades de eventos como métricas do sistema: 

- Visitantes
- Visitas
- Exibições de página
- Cliques

Essas métricas do sistema são baseadas em propriedades de eventos existentes em eventos de base.

1. Acesse **Dados** no painel de navegação esquerdo. 
1. Selecione a guia **Métricas** para ver uma lista de todas as métricas no espaço de trabalho. 
   > [!NOTE]
   > As métricas geradas pelo sistema são somente leitura. Você não pode editá-los ou exclui-los. Só é possível criar e editar métricas personalizadas.

## <a name="create-a-metric"></a>Criar uma métrica

Os administradores de ambiente e espaço de trabalho podem criar métricas. As propriedades do evento devem ser enviadas ao espaço de trabalho antes de você criar uma métrica. Você pode criar métricas com base nas propriedades do evento que são enviadas por eventos de base ou usar o SDK da Web para [enviar propriedades personalizadas do evento](advanced-SDK-implementation.md).

1. Acesse **Dados** > **Métricas**.
1. Selecione **Nova métrica** para abrir a caixa de diálogo **Biblioteca de Recursos** e **Nova métrica sem título**.

   :::image type="content" source="media/new-metric.png" alt-text="Adicionar uma métrica a um evento.":::

1. Na caixa de diálogo **Nova métrica sem título**, selecione o **Formato** na lista suspensa e escolha o tipo de dados **Inteiro** ou **Dobro**. O inteiro é um número inteiro. Para Dobro, você pode escolher uma e três casas decimais.

   :::image type="content" source="media/create-new-metric.png" alt-text="Criar uma nova métrica.":::
   
5. No painel **Biblioteca de Recursos**, encontre a propriedade do evento na qual basear a métrica.
6. Selecione o **sinal de adição (+)** próximo à propriedade para usá-lo na fórmula. Você só pode criar uma fórmula com base em uma propriedade. 
7. Escolha uma das seguintes funções de agregação. 

   - Soma: o total aritmético de todos os valores 
   - Média: a média de todos os valores
   - Contagem: o número total de valores
   - Contagem distinta: o número total de valores distintos

   Depois de definir a métrica, você verá uma versão preliminar da atividade da métrica na última hora.

1. Selecione **Salvar**. 
1. Insira um nome para a métrica e selecione **Salvar**.

Pode levar até um minuto para a métrica antes que você possa usá-la para [criar relatórios personalizados](custom-reports.md).

## <a name="edit-a-metric"></a>Editar uma métrica

Você só pode editar métricas personalizadas.

1. Acesse **Dados** > **Métricas**.
1. Selecione a métrica na lista.
1. Alterar a definição da métrica
1. Selecione **Salvar**.

## <a name="change-the-name-of-a-metric"></a>Alterar o nome de uma métrica

Você só pode alterar o nome de métricas personalizadas.

1. Acesse **Dados** > **Métricas**.
1. Selecione **Mais [...]** para uma métrica e escolha **Editar nome**.
1. Alterar o nome. 
1. Selecione **Renomear**.

## <a name="delete-a-metric"></a>Excluir uma métrica

Você só pode excluir métricas personalizadas.

1. Acesse **Dados** > **Métricas**.
1. Selecione **Mais [...]** para uma métrica e escolha **Excluir**.

   :::image type="content" source="media/delete-metric.png" alt-text="Excluir uma métrica de um evento.":::

1. Selecione **Excluir** para confirmar a exclusão.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
