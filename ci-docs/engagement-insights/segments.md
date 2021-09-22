---
title: Exibir e criar segmentos
description: Como criar, editar e excluir segmentos e onde usá-los.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 06/09/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: cedcd58373428dd35ba29ce8fdd00007257f8fa59b0d25bc584b4e832df13604
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036134"
---
# <a name="view-and-create-segments"></a>Exibir e criar segmentos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Os segmentos permitem que você identifique subconjuntos de visitantes com base nas características ou interações do site. Os segmentos permitem aplicar filtros e analisar esses subconjuntos. A análise pode ajudar a examinar e responder às tendências em seu negócio. 

:::image type="content" source="media/segments-page.png" alt-text="Captura de tela do aplicativo de insights de participação que mostra a lista de segmentos existentes em um espaço de trabalho.":::

## <a name="view-segments"></a>Exibir segmentos

1. Acesse **Dados** no painel de navegação esquerdo. 

1. Selecione a guia **Segmentos** para ver uma lista de todos os segmentos na área de trabalho. 

## <a name="create-a-segment"></a>Criar um segmento

Os segmentos consistem em regras e condições que são conectadas a operadores lógicos. As condições aplicam filtros a uma dimensão selecionada. Cada segmento pode usar até cinco dimensões.

O exemplo a seguir mostra um segmento com duas condições em uma regra. Ele filtra todos os eventos do site em que o navegador é o Chrome e os sistemas operacionais são iOS ou Android.

:::image type="content" source="media/segment-sample.png" alt-text="Segmentos de exemplo com duas condições em uma regra para filtrar eventos do site.":::

Esta seção descreve como criar um *segmento em branco* do zero.

1. Acesse **Dados** > **Segmentos**.

1. Selecione **Novo segmento**.

1. Na **Biblioteca de Recursos**, escolha o atributo pelo qual deseja filtrar. Atualmente, você só pode criar segmentos com base em dimensões.

1. Escolha um operador e um valor para o atributo selecionado. As seguintes operações são compatíveis:
   - **é**: requer uma correspondência exata para incluir valores. Usa **igual a** para um único valor ou **qualquer um** para incluir vários valores.
   - **não é**: requer uma correspondência exata para excluir valores. Usa **igual a** para um único valor ou **qualquer um** para incluir vários valores.
   - **começa com**: uma cadeia de caracteres com a qual os valores correspondentes começam.
   - **termina com**: uma cadeia de caracteres com a qual os valores correspondentes terminam.
   - **contém**: uma cadeia de caracteres contida em valores correspondentes.

1. Para adicionar mais condições a um grupo, você pode usar dois operadores lógicos. Os atributos projetados são fatorados com o uso de operadores de conjunto.
   - Operador **E**: Ambas as condições devem ser atendidas como parte do processo de segmentação. Esta opção é mais útil quando você define condições em diferentes entidades.
   - Operador **OU**: Qualquer uma das condições precisa ser atendida como parte do processo de segmentação. Esta opção é mais útil quando você define várias condições para a mesma entidade.

1. Selecione **Salvar** e nomeie o segmento. 

O segmento será listado na página Segmentos e você pode aplicá-lo a todos os relatórios e funis na área de trabalho.

## <a name="use-a-segment-in-a-report-or-funnel"></a>Usar um segmento em um relatório ou funil

Você pode aplicar segmentos a um relatório ou funil para filtrá-los com base nas condições do segmento. No entanto, você não pode aplicar segmentos ao relatório de uso em tempo real.

:::image type="content" source="media/segment-reports-filter.png" alt-text="Um relatório de visualizações de página com uma lista suspensa expandida para escolher quais segmentos aplicar.":::

Para aplicar um segmento, abra o relatório ou funil. Selecione **Adicionar condição** e escolha **Filtrar por segmento**. Escolha o segmento da lista que você deseja aplicar. O segmento pode ser aplicado ao relatório. Se um gráfico não oferece suporte ao segmento, ele mostra um erro.
 
Você pode aplicar *até três segmentos* a um relatório ou funil.

## <a name="edit-a-segment"></a>Editar um segmento

1. Acesse **Dados** > **Segmentos**.
1. Selecione o segmento na lista para abri-lo. 
1. Altere ou adicione valores conforme necessário.
1. Selecione **Salvar** para aplicar suas alterações.

## <a name="change-the-name-of-a-segment"></a>Alterar o nome de um segmento

1. Acesse **Dados** > **Segmentos**.
1. Na lista de segmentos, selecione **Mais [...]**. 
1. Na lista suspensa, selecione **Editar nome**.
1. Digite o novo nome e selecione **Renomear**.

## <a name="delete-a-segment"></a>Excluir um segmento

1. Acesse **Dados** > **Segmentos**.
1. Na lista de segmentos, selecione **Mais [...]**. 
1. Na lista suspensa, selecione **Excluir**.
1. Selecione **Excluir** para confirmar.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
