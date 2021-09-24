---
title: Criar segmentos usando o construtor de segmentos
description: Criar segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 09/07/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7f7bd0e7e581305836287bd503ef273a2d556bff
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494477"
---
# <a name="create-segments"></a>Criar segmentos

Defina filtros complexos em torno da entidade unificada do cliente e suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registros do cliente que você pode exportar e executar. Os segmentos são gerenciados na página **Segmentos**. Você pode [criar novos segmentos](#create-a-new-segment) usando o [construtor de segmentos](#segment-builder) ou [criar segmentos rápidos](#quick-segments) de outras áreas do aplicativo.

## <a name="segment-builder"></a>Construtor de segmentos

A imagem a seguir ilustra os vários aspectos do construtor de segmentos. Ela mostra um segmento que resulta em um grupo de clientes. Os clientes solicitaram mercadorias em um período específico e reuniram uma série de pontos de recompensa ou gastaram certa quantia em dinheiro. 

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do construtor de segmento." lightbox="media/segment-builder-overview.png":::

1 - Organize seu segmento com regras e sub-regras. Cada regra ou sub-regra consiste em condições. Combine as condições com operadores lógicos

2 - Escolha o [caminho de relacionamento](relationships.md) entre entidades que se aplicam a uma regra. O caminho do relacionamento determina quais atributos podem ser usados em uma condição.

3 - Gerencie regras e sub-regras. Altere a posição de uma regra ou exclua-a.

4 - Adicione condições e crie o nível certo de aninhamento usando sub-regras.

5 - Aplique operações definidas às regras conectadas.

6 - Use o painel de atributos para adicionar atributos de entidade disponíveis ou criar condições baseadas em atributos. O painel mostra a lista de entidades e atributos, com base no caminho de relacionamento selecionado, que estão disponíveis para a regra selecionada.

7 - Adicione condições com base em atributos às regras e sub-regras existentes ou adicione-as a uma nova regra.

8 - Desfaça e refaça alterações durante a criação do segmento.

O exemplo acima ilustra a capacidade de segmentação. Definimos um segmento para clientes que compraram pelo menos $500 de mercadorias online *e* têm interesse em desenvolvimento de software.

## <a name="create-a-new-segment"></a>Criar um novo segmento

Há várias maneiras de criar um novo segmento. Esta seção descreve como criar seu próprio segmento do zero. Você também pode criar um *segmento rápido* com base em entidades existentes ou usar modelos de Aprendizado de Máquina para ter *segmentos sugeridos*. Mais informações: [Visão geral de segmentos](segments.md).

Ao criar um segmento, você pode salvar um rascunho. Ele será salvo como um segmento inativo, e não pode ser ativado se for finalizado com uma configuração válida.

1. Vá para a página **Segmentos**.

1. Selecione **Novo** > **Criar seu próprio**.

1. Na página do construtor de segmentos, você define a primeira regra. Uma regra consiste em uma ou mais condições e define um conjunto de clientes.

1. Na seção **Regra 1**, escolha um atributo de uma entidade pela qual deseja filtrar clientes. Há duas maneiras de escolher atributos: 
   - Revise a lista de entidades e atributos disponíveis no painel **Adicionar à Regra** e selecione o ícone **+** ao lado do atributo a ser adicionado. Escolha se deseja adicionar o atributo a uma regra existente ou use-o para criar uma nova regra.
   - Digite o nome do atributo na seção de regra para ver as sugestões correspondentes.

1. Escolha os operadores para especificar os valores correspondentes da condição. O atributo pode ter um dos quatro tipos de dados como valor: numérico, cadeia de caracteres, data ou booliano. Dependendo do tipo de dados do atributo, diferentes operadores estão disponíveis para especificar a condição. 

1. Selecione **Adicionar condição** para adicionar mais condições a uma regra. Para criar uma regra sob a regra atual, selecione **Adicionar sub-regra**.

1. Se uma regra usar outras entidades além da entidade *Cliente*, você deverá definir o caminho do relacionamento. O caminho de relacionamento é necessário para informar ao sistema os relacionamentos em que você deseja acessar a entidade de cliente unificada. Selecione **Definir caminho de relacionamento** para mapear a entidade selecionada para a entidade de cliente unificada. Se houver apenas um caminho de relacionamento possível, o sistema o selecionará automaticamente. Caminhos de relacionamento diferentes podem produzir resultados diferentes. Cada regra pode ter seu próprio caminho de relacionamento.

   :::image type="content" source="media/relationship-path.png" alt-text="Caminho de relacionamento potencial ao criar uma regra com base em uma entidade mapeada para a entidade de cliente unificada.":::

   Por exemplo, a entidade *eCommerce_eCommercePurchases* na captura de tela tem quatro opções de mapeamento para a entidade *Cliente*: 
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Cliente
   - eCommerce_eCommercePurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente. Ao escolher a última opção, podemos incluir atributos de todas as entidades listadas nas condições da regra. Provavelmente obteremos menos resultados porque os registros de clientes correspondentes precisam fazer parte de todas as entidades. Neste exemplo, eles compraram mercadorias por meio de comércio eletrônico (*eCommerce_eCommercePurchases*), em um ponto de venda (*POS_posPurchases*) e participam de nosso programa de fidelidade (*loyaltyScheme_loyCustomers*). Ao escolher a segunda opção, só podemos escolher atributos das entidades *eCommerce_eCommercePurchases* e *Cliente*. Isso provavelmente resulta em mais perfis de clientes.

1. Se você tiver várias condições em uma regra, poderá escolher qual operador lógico as conectará.

   - Operador **AND**: todas as condições devem ser atendidas para incluir um registro no segmento. Esta opção é mais útil quando você define condições em diferentes entidades.

   - Operador **OR**: uma das condições deve ser atendida para incluir um registro no segmento. Esta opção é mais útil quando você define várias condições para a mesma entidade.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regra com duas condições AND":::

   Ao usar o operador OR, todas as condições devem se basear em entidades incluídas no caminho de relacionamento.

   1. Você pode criar várias regras para criar diferentes conjuntos de registros de clientes. Você pode combinar grupos para incluir os clientes que são necessários para o seu caso de negócios. Para criar uma nova regra, selecione **Adicionar regra**. Especificamente, se você não puder incluir uma entidade em uma regra devido ao caminho de relacionamento especificado, deverá criar uma nova regra para escolher os atributos dela.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Adicione uma nova regra a um segmento e escolha o operador definido.":::

   1. Selecione um dos operadores de conjunto: **União**, **Interseção** ou **Exceto**.

   - **União** une os dois grupos.

   - **Interseção** sobrepõe os dois grupos. Apenas dados que são *comuns* para ambos os grupos é retido no grupo unificado.

   - **Exceto** combina os dois grupos. Apenas dados no grupo A que *não são comuns* a dados no grupo B são retidos.

1. Por padrão, os segmentos geram a entidade de saída contendo todos os atributos de perfis de clientes que correspondem aos filtros definidos. Se um segmento for baseado em entidades diferentes da entidade *Cliente*, você poderá adicionar mais atributos dessas entidades à entidade de saída. Selecione **Atributos do projeto** para escolher os atributos que serão anexados à entidade de saída.  

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplo de atributos projetados selecionados no painel lateral a serem adicionados à entidade de saída.":::
  
   Exemplo: um segmento é baseado em uma entidade contendo dados de compra, que estão relacionados à entidade *Cliente*. O segmento busca todos os clientes da Espanha que compraram mercadorias no ano atual. Você pode optar por anexar atributos como o preço das mercadorias ou a data de compra a todos os registros de cliente correspondentes na entidade de saída. Essas informações podem ser úteis para analisar as correlações sazonais com o gasto total.

   > [!NOTE]
   > - Os atributos projetados funcionam somente para entidades que tenham um relacionamento um-para-muitos com a entidade do cliente. Por exemplo, um cliente pode ter várias assinaturas.
   > - Você só poderá projetar atributos de uma entidade que é usada em todas as regras de consulta de segmento estiver criando.
   > - Os atributos projetados são fatorados com o uso de operadores de conjunto.

1. Antes de salvar e executar o segmento, selecione **Editar detalhes** ao lado do nome do segmento. Forneça um nome para o seu segmento e atualize o **Nome da entidade de saída** sugerido para o segmento. Você também pode adicionar uma descrição ao segmento.

1. Selecione **Executar** para salvar e processar o segmento se todos os requisitos estiverem validados. Caso contrário, ele será salvo como um rascunho de segmento inativo.

1. Selecione **Voltar aos segmentos** voltar para a página **Segmentos**.

> [!TIP]
> - O construtor de segmentos não sugere valores válidos de entidades ao definir os operadores para as condições. Você pode acessar **Dados** > **Entidades** e baixar os dados da entidade para ver os valores disponíveis.
> - As condições baseadas nas datas permitem alternar entre datas fixas e um intervalo de datas flutuante.
> - Se você tiver várias regras para seu segmento, encontrará uma barra azul ao redor da regra que estiver editando.
> - Você pode mover regras e condições para outros locais na definição do segmento. Selecione [...] ao lado de uma regra ou condição e escolha como e para onde movê-la.
> - Os controles **Desfazer** e **Refazer** na barra de comandos permitem reverter as alterações.

## <a name="quick-segments"></a>Segmentos rápidos

Segmentos rápidos lhe permitem construir segmentos simples com um único operador rapidamente para insights mais rápidos.

1. Na página **Segmentos**, selecione **Novo** > **Criar a partir de**.

   - Selecione a opção **Perfis** para criar um segmento baseado na entidade *unificada do cliente*.
   - Selecione a opção **Medidas** para construir um segmento em torno das medidas que você já criou.
   - Selecione a opção **Inteligência** para criar um segmento em torno de uma das entidades de saída que você gerou usando os recursos **Previsões** ou **Modelos personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo no menu suspenso **Campo**.

3. O sistema fornecerá mais insights que o ajudarão a criar melhores segmentos de clientes.
   - Para campos categóricos, mostraremos as 10 principais contagens de clientes. Escolha um **Valor** e selecione **Revisar**.

   - Para um atributo numérico, o sistema mostrará qual valor de atributo se enquadra no percentil de cada cliente. Escolha um **Operador** e um **Valor** e selecione **Revisar**.

4. O sistema fornecerá a você um **Tamanho estimado do segmento**. Você pode optar por gerar o segmento definido ou primeiro revisitá-lo para obter um tamanho de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nome e estimativa de um segmento rápido.](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")

5. Forneça um **Nome** para seu segmento. Se preferir, forneça um **Nome para exibição**.

6. Selecione **Salvar** para criar seu segmento.

7. Depois que o segmento terminar o processamento, você poderá vê-lo como qualquer outro segmento criado.

## <a name="next-steps"></a>Próximas etapas

[Exportar um segmento](export-destinations.md) e explorar a [Integração do cartão do cliente](customer-card-add-in.md) para usar segmentos em outros aplicativos.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
