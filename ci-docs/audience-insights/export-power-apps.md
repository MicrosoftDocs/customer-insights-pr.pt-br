---
title: Conector do Power Apps
description: Conecte-se com o Power Apps e o Power Automate.
ms.date: 01/19/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: fc0af656cd5b436d9efd65b2a2c75dde9c9deb9dbcdd56ffc6a960f5878a631f
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031735"
---
# <a name="microsoft-power-apps-connector-preview"></a>Conector do Microsoft Power Apps (versão prévia)

Importe perfis de cliente unificados para seus aplicativos personalizados com o Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectar o Power Apps e o Dynamics 365 Customer Insights

O Customer Insights é uma das muitas [fontes disponíveis para dados no Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte a documentação do Power Apps para saber como [adicionar uma conexão de dados a um aplicativo](/powerapps/maker/canvas-apps/add-data-connection). Recomendamos que você também analise [como o Power Apps usa a delegação para lidar com grandes conjuntos de dados em aplicativos de tela](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades disponíveis

Depois de adicionar o Customer Insights como uma conexão de dados, você pode escolher as seguintes entidades no Power Apps:

- Cliente: para usar dados do [perfil de cliente unificado](customer-profiles.md).
- UnifiedActivity: para exibir a [linha do tempo de atividade](activities.md) no aplicativo.

## <a name="limitations"></a>Limitações

### <a name="retrievable-entities"></a>Entidades recuperáveis

Você só pode recuperar as entidades **Cliente**, **UnifiedActivity** e **Segmentos** por meio do conector Power Apps. Outras entidades são mostradas porque o conector subjacente dá suporte a elas por meio de gatilhos no Power Automate.  

### <a name="delegation"></a>Delegação

A delegação funciona para as entidades Cliente e UnifiedActivity. 

- Delegação para a entidade **Cliente**: para usar a delegação para esta entidade, os campos precisam ser indexados em [Índice de filtro e pesquisa](search-filter-index.md).  

- Delegação para **UnifiedActivity** : a delegação para esta entidade só funciona para os campos **ActivityId** e **CustomerId**.  

- Para obter mais informações sobre delegação, consulte [Funções e operações delegáveis do Power Apps](/connectors/commondataservice/#power-apps-delegable-functions-and-operations-for-the-cds-for-apps). 

## <a name="example-gallery-control"></a>Exemplo de controle da galeria

Por exemplo, você adiciona perfis de clientes a um [controle de galeria](/powerapps/maker/canvas-apps/add-gallery).

1. Adicione um controle **Galeria** a um aplicativo que você está criando.

> [!div class="mx-imgBorder"]
> ![Adicione um elemento da galeria.](media/connector-powerapps9.png "Adicione um elemento da galeria")

1. Selecione **Cliente** como a fonte de dados dos itens.

    > [!div class="mx-imgBorder"]
    > ![Selecione uma fonte de dados.](media/choose-datasource-powerapps.png "Selecione uma fonte de dados")

1. Você pode alterar o painel de dados à direita para selecionar qual campo a entidade Cliente mostrará na galeria.

1. Se você quiser mostrar qualquer campo do cliente selecionado na galeria, preencha a propriedade Texto de um rótulo: **{Name_of_the_gallery}.Selecionado.{property_name}**

    Exemplo: Gallery1.Selected.address1_city

1. Para exibir a linha do tempo unificada para um cliente, adicione um elemento Galeria e adicione a propriedade Itens: **Filter('UnifiedActivity', CustomerId = {Customer_Id})**

    Exemplo: Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)


[!INCLUDE[footer-include](../includes/footer-banner.md)]