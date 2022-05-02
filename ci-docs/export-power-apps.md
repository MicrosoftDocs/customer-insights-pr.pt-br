---
title: Conector do Power Apps
description: Conecte-se com o Power Apps e o Power Automate.
ms.date: 10/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: e99d7d4f231eb2ade67f27c9e52c61af3a21b99d
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645706"
---
# <a name="microsoft-power-apps-connector-preview"></a>Conector do Microsoft Power Apps (versão prévia)

Importe perfis de cliente unificados para seus aplicativos personalizados com o Power Apps.

## <a name="connect-power-apps-and-dynamics-365-customer-insights"></a>Conectar o Power Apps e o Dynamics 365 Customer Insights

O Customer Insights é uma das muitas [fontes disponíveis para dados no Power Apps](/powerapps/maker/canvas-apps/working-with-data-sources).

Consulte a documentação do Power Apps para saber como [adicionar uma conexão de dados a um aplicativo](/powerapps/maker/canvas-apps/add-data-connection). Recomendamos que você também analise [como o Power Apps usa a delegação para lidar com grandes conjuntos de dados em aplicativos de tela](/powerapps/maker/canvas-apps/delegation-overview).

## <a name="available-entities"></a>Entidades disponíveis

Depois de adicionar o Customer Insights como uma conexão de dados, você pode escolher as seguintes entidades no Power Apps:

- **Customer**: para usar dados do [perfil de cliente unificado](customer-profiles.md).
- **UnifiedActivity**: para exibir a [linha do tempo de atividades](activities.md) no aplicativo.
- **ContactProfile**: para exibir os contatos de um cliente. Essa entidade só está disponível em ambientes do Customer Insights para contas de negócios.

## <a name="limitations"></a>Limitações

### <a name="retrievable-entities"></a>Entidades recuperáveis

Você só pode recuperar as entidades **Cliente**, **UnifiedActivity**, **Segmentos** e **ContactProfile** através do conector Power Apps. O ContactProfile só está disponível na instância do Customer Insights para contas comerciais. Outras entidades são mostradas porque o conector subjacente dá suporte a elas por meio de gatilhos no Power Automate.

Você pode fazer no máximo 100 chamadas por 60 segundos. Você pode fazer uma chamada para o ponto de extremidade da API várias vezes usando o parâmetro $skip. [Saiba mais sobre o parâmetro $skip](/connectors/customerinsights/#get-items-from-an-entity).

### <a name="delegation"></a>Delegação

A delegação funciona para as entidades **Cliente** e **UnifiedActivity**. 

- Delegação para a entidade **Cliente**: para usar a delegação para esta entidade, os campos precisam ser indexados em [Índice de filtro e pesquisa](search-filter-index.md).  
- Delegação para **UnifiedActivity** : a delegação para esta entidade só funciona para os campos **ActivityId** e **CustomerId**.  
- Delegação para **ContactProfile**: A delegação para esta entidade só funciona para os campos **ContactId** e **CustomerId**. O ContactProfile só está disponível em ambientes do Customer Insights para contas comerciais.

Para obter mais informações sobre delegação, vá para [funções e operações delegáveis do Power Apps](/powerapps/maker/canvas-apps/delegation-overview). 

## <a name="example-gallery-control"></a>Exemplo de controle da galeria

Você pode adicionar perfis de clientes a um [controle de galeria](/powerapps/maker/canvas-apps/add-gallery).

1. Adicione um controle de **galeria** a um aplicativo que você está criando.

    > [!div class="mx-imgBorder"]
    > ![Adicione um elemento da galeria.](media/connector-powerapps9.png "Adicione um elemento da galeria.")

2. Selecione **Cliente** como a fonte de dados dos itens.

    > [!div class="mx-imgBorder"]
    > ![Selecione uma fonte de dados.](media/choose-datasource-powerapps.png "Selecione uma fonte de dados.")

3. Você pode alterar o painel de dados à direita para selecionar qual campo a entidade Cliente mostrará na galeria.

4. Se você quiser mostrar qualquer campo do cliente selecionado na galeria, preencha a propriedade **Texto** de um rótulo usando **{Name_of_the_gallery}.Selected.{property_name}**  
    - Por exemplo: _Gallery1.Selected.address1_city_

5. Para exibir a linha do tempo unificada para um cliente, adicione um elemento de galeria e acrescente a propriedade **Itens** usando **Filter('UnifiedActivity', CustomerId = {Customer_Id})**  
    - Por exemplo: _Filter('UnifiedActivity', CustomerId = Gallery1.Selected.CustomerId)_


[!INCLUDE [footer-include](includes/footer-banner.md)]
