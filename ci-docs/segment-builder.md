---
title: Criar segmentos
description: Crie segmentos de clientes para agrupá-los com base em vários atributos usando o construtor de segmentos ou segmentos rápidos.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segments
- ci-segment-builder
- ci-segment-details
- customerInsights
ms.openlocfilehash: b99d9575d3b6af91758d80eb04170773b08cc9ab
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9053958"
---
# <a name="create-segments"></a>Criar segmentos

Defina filtros complexos em torno da entidade unificada do cliente e suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registros do cliente que você pode exportar e executar. Os segmentos são gerenciados na página **Segmentos**. Você pode [criar novos segmentos](#create-a-new-segment) usando o construtor de segmentos ou [criar segmentos rápidos](#quick-segments) de outras áreas do aplicativo.

> [!TIP]
> - Segmentos rápidos são suportados apenas em ambientes para **clientes individuais**.
> - Segmentos baseados em **clientes individuais** incluem automaticamente as informações de contato disponíveis para os membros do segmento. Em ambientes para **contas comerciais**, os segmentos são baseados em contas (empresas ou subsidiárias). Para incluir informações de contato em um segmento, use a funcionalidade **Atributos do projeto** no construtor de segmento. Certifique-se de que as fontes de dados de contato são [mapeadas semanticamente para a entidade ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Construtor de segmentos

A imagem a seguir ilustra os vários aspectos do construtor de segmentos. Ela mostra um segmento que resulta em um grupo de clientes. Os clientes encomendaram mercadorias em um período de tempo específico e ganharam pontos de recompensa ou gastaram uma certa quantia de dinheiro.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do construtor de segmento." lightbox="media/segment-builder-overview.png":::

1. Organize seu segmento com regras e sub-regras. Cada regra ou sub-regra consiste em condições. Combine as condições com operadores lógicos

1. Escolha o [caminho de relacionamento](relationships.md) entre entidades que se aplicam a uma regra. O caminho do relacionamento determina quais atributos podem ser usados em uma condição.

1. Gerencie regras e sub-regras. Altere a posição de uma regra ou exclua-a.

1. Adicione condições e crie o nível certo de aninhamento usando sub-regras.

1. Aplique operações definidas às regras conectadas.

1. Use o painel de atributos para adicionar atributos de entidade disponíveis ou criar condições baseadas em atributos. O painel mostra a lista de entidades e atributos, com base no caminho de relacionamento selecionado, que estão disponíveis para a regra selecionada.

1. Adicione condições com base em atributos às regras e sub-regras existentes ou adicione-as a uma nova regra.

1. Desfaça e refaça alterações durante a criação do segmento.

O exemplo acima ilustra a capacidade de segmentação. Definimos um segmento para clientes que compraram pelo menos $500 de mercadorias online *e* têm interesse em desenvolvimento de software.

## <a name="create-a-new-segment"></a>Criar um novo segmento

Há várias maneiras de criar um novo segmento. Esta seção descreve como criar seu próprio segmento do zero. Você também pode criar um *segmento rápido* com base em entidades existentes ou usar modelos de Aprendizado de Máquina para ter *segmentos sugeridos*. Para obter mais informações, vá para [Visão geral de segmentos](segments.md).

Ao criar um segmento, você pode salvar um rascunho. No estágio de rascunho, um segmento é salvo como um segmento inativo. Ao concluir a configuração do segmento, execute-o para ativar o segmento. Você também pode **Ativar** um segmento na página **Todos os segmentos**.

1. Vá para a página **Segmentos**.

1. Selecione **Novo** > **Criar seu próprio**.

1. Na página do construtor de segmento, você define ou compõe regras. Uma regra consiste em uma ou mais condições que definem um conjunto de clientes.

1. Na seção **Regra 1**, escolha um atributo de uma entidade pela qual você deseja filtrar os clientes. Há duas maneiras de escolher atributos:
   - Revise a lista de entidades e atributos disponíveis no painel **Adicionar à Regra** e selecione o ícone **+** ao lado do atributo a ser adicionado. Escolha se deseja adicionar o atributo a uma regra existente ou use-o para criar uma nova regra.
   - Digite o nome do atributo na seção de regra para ver as sugestões correspondentes.

1. Escolha os operadores para especificar os valores correspondentes da condição. O atributo pode ter um dos quatro tipos de dados como valor: numérico, cadeia de caracteres, data ou booliano. Dependendo do tipo de dados do atributo, diferentes operadores estão disponíveis para especificar a condição. Para segmentos com contas comerciais, dois operadores especiais estão disponíveis para incluir hierarquias potenciais entre as contas ingeridas. Use os operadores *child of (filho de)* e *parent of (pai de)* para incluir contas relacionadas.

1. Selecione **Adicionar condição** para adicionar mais condições a uma regra. Para criar uma regra sob a regra atual, selecione **Adicionar sub-regra**.

1. Se uma regra usar outras entidades além da entidade *Cliente*, você deverá definir o caminho do relacionamento. O caminho de relacionamento é necessário para informar ao sistema os relacionamentos em que você deseja acessar a entidade de cliente unificada. Selecione **Definir caminho de relacionamento** para mapear a entidade selecionada para a entidade de cliente unificada. Se houver apenas um caminho de relacionamento possível, o sistema o selecionará automaticamente. Caminhos de relacionamento diferentes podem produzir resultados diferentes. Cada regra pode ter seu próprio caminho de relacionamento.

   :::image type="content" source="media/relationship-path.png" alt-text="Caminho de relacionamento potencial ao criar uma regra com base em uma entidade mapeada para a entidade de cliente unificada.":::

   Por exemplo, a entidade *eCommerce_eCommercePurchases* na captura de tela tem quatro opções de mapeamento para a entidade *Cliente*:
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > Cliente
   - eCommerce_eCommercePurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
   - eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente. Ao escolher a última opção, podemos incluir atributos de todas as entidades listadas nas condições da regra. Provavelmente obteremos menos resultados porque os registros correspondentes dos clientes precisam fazer parte de todas as entidades. Neste exemplo, eles adquiriram mercadorias através do programa de comércio eletrônico(*eCommerce_eCommercePurchases*) no ponto de venda(*POS_posPurchases*) e participam do nosso programa de fidelidade (*loyaltyScheme_loyCustomers*). Ao escolher a segunda opção, só podemos escolher atributos das entidades *eCommerce_eCommercePurchases* e *Cliente*. Isso provavelmente resulta em mais perfis de clientes.

1. Se você tiver várias condições em uma regra, poderá escolher qual operador lógico as conectará.  
   - Operador **AND**: todas as condições devem ser atendidas para incluir um registro no segmento. Esta opção é mais útil quando você define condições em diferentes entidades.
   - Operador **OR**: uma das condições deve ser atendida para incluir um registro no segmento. Esta opção é mais útil quando você define várias condições para a mesma entidade.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regra com duas condições AND":::

   Ao usar o operador OR, todas as condições devem se basear em entidades incluídas no caminho de relacionamento.

   - Você pode criar várias regras para criar diferentes conjuntos de registros de clientes. Você pode combinar grupos para incluir os clientes que são necessários para o seu caso de negócios. Para criar uma nova regra, selecione **Adicionar regra**. Especificamente, se não puder incluir uma entidade em uma regra devido ao caminho de relacionamento especificado, você deve criar uma regra para escolher o formulário de atributos dela.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Adicione uma nova regra a um segmento e escolha o operador definido.":::

   - Selecione um dos operadores de conjunto: **União**, **Interseção** ou **Exceto**.

      - **União** une os dois grupos.
      - **Interseção** sobrepõe os dois grupos. Somente os dados que *são comuns* aos dois grupos são mantidos no grupo unificado.
      - **Exceto** combina os dois grupos. Somente os dados no grupo A que *não são comuns* aos dados do grupo B são mantidos.

1. Por padrão, os segmentos geram a entidade de saída contendo todos os atributos de perfis de clientes que correspondem aos filtros definidos. Se um segmento for baseado em entidades diferentes da entidade *Cliente*, você poderá adicionar mais atributos dessas entidades à entidade de saída. Selecione **Atributos do projeto** para escolher os atributos que serão anexados à entidade de saída.

   > [!IMPORTANT]
   > Para segmentos baseados em contas comerciais, os detalhes de um ou mais contatos de cada conta da entidade *ContactProfile* precisam ser incluídos no segmento para permitir que esse segmento seja ativado ou exportado para destinos que exijam informações de contato. Para obter mais informações sobre a entidade *ContactProfile*, consulte [Mapeamentos semânticos](semantic-mappings.md).
   > Um exemplo de saída para um segmento com base em contas comerciais com atributos projetados de contatos poderia ser assim:
   >
   > |ID  |Nome da conta  |Receita  |Nome do contato  | Função do contato|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 mil | [Abbie Moss, Ruth Soto]  | [CEO, gerente de compras]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplo de atributos projetados selecionados no painel lateral a serem adicionados à entidade de saída.":::
  
   Por exemplo: Um segmento é baseado em uma entidade que contém dados de compra, que estão relacionados à entidade *Cliente*. O segmento busca todos os clientes da Espanha que compraram mercadorias no ano atual. Você pode optar por anexar atributos como o preço das mercadorias ou a data de compra a todos os registros de cliente correspondentes na entidade de saída. Essas informações podem ser úteis para analisar as correlações sazonais com o gasto total.

   > [!NOTE]
   > - **Atributos do projeto** só funciona para entidades que têm um relacionamento um-para-muitos com a entidade cliente. Por exemplo, um cliente pode ter várias assinaturas.
   > - Se o atributo que você deseja projetar está a mais de um salto de distância da entidade *Cliente*, conforme definido pelo relacionamento, esse atributo deve ser usado em todas as regras da consulta de segmento que você está construindo.
   > - Se o atributo que você deseja projetar está a mais de um salto de distância da entidade *Cliente*, esse atributo não precisa estar presente em todas as regras da consulta do segmento que você está construindo.
   > - **Atributos projetados** são fatorados com o uso de operadores de conjunto.

1. Selecione **Editar detalhes** ao lado de Segmento sem título. Forneça um nome para o seu segmento e atualize o **Nome da entidade de saída** sugerido para o segmento. Opcionalmente, adicione uma descrição e [marcas](work-with-tags-columns.md#manage-tags) ao segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Editar caixa de diálogo de detalhes":::

1. Selecione **Executar** para salvar o segmento, ative-o e comece a processar seu segmento com base em todas as regras e condições. Caso contrário, ele será salvo como um segmento inativo.

1. Selecione **Voltar aos segmentos** voltar para a página **Segmentos**.

1. Por padrão, o segmento é criado como um segmento dinâmico. Isso significa que o segmento é atualizado durante as atualizações do sistema. Para [interromper a atualização automática](segments.md#manage-existing-segments), selecione o segmento, escolha a opção **Tornar estático**. Os segmentos estáticos podem ser [atualizados manualmente](segments.md#refresh-segments) a qualquer momento.

> [!TIP]
> - O construtor de segmentos não sugere valores válidos de entidades ao definir os operadores para as condições. Você pode acessar **Dados** > **Entidades** e baixar os dados da entidade para ver os valores disponíveis.
> - As condições baseadas nas datas permitem alternar entre datas fixas e um intervalo de datas flutuante.
> - Se você tiver várias regras para o seu segmento, a regra que você está editando terá uma linha azul vertical ao lado dela.
> - Você pode mover regras e condições para outros locais na definição do segmento. Selecione as reticências verticais (&vellip;) ao lado de uma regra ou condição e escolha como e para onde movê-la.
> - Os controles **Desfazer** e **Refazer** na barra de comando permitem reverter as alterações.
> - Após a criação, alguns segmentos permitem que você [acompanhe o uso do segmento](segments.md#track-usage-of-a-segment).

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

   :::image type="content" source="media/quick-segment-name.png" alt-text="Nome e estimativa de um segmento rápido.":::

5. Forneça um **Nome** e um **Nome da entidade de saída** para seu segmento. Opcionalmente, adicione [marcas](work-with-tags-columns.md#manage-tags).

6. Selecione **Salvar** para criar seu segmento.

7. Depois que o segmento terminar o processamento, você poderá vê-lo como qualquer outro segmento criado.

## <a name="next-steps"></a>Próximas etapas

[Exportar um segmento](export-destinations.md) e explorar a [Integração do cartão do cliente](customer-card-add-in.md) para usar segmentos em outros aplicativos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
