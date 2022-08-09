---
title: Criar segmentos complexos com o construtor de segmentos
description: Use o construtor de segmentos para criar segmentos complexos de clientes agrupando-os com base em vários atributos.
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
ms.openlocfilehash: cde373cd65e296675e1b3c92f3024e1093853842
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170621"
---
# <a name="create-complex-segments-with-segment-builder"></a>Criar segmentos complexos com o construtor de segmentos

Defina filtros complexos em torno da entidade unificada do cliente e suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registros do cliente que você pode exportar e executar.

> [!TIP]
> Segmentos baseados em **clientes individuais** incluem automaticamente as informações de contato disponíveis para os membros do segmento. Em ambientes para **contas comerciais**, os segmentos são baseados em contas (empresas ou subsidiárias). Para incluir informações de contato em um segmento, use a funcionalidade **Atributos do projeto** no construtor de segmento. Certifique-se de que as fontes de dados de contato são [mapeadas semanticamente para a entidade ContactProfile](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).

## <a name="segment-builder"></a>Construtor de segmentos

A imagem a seguir ilustra os vários aspectos do construtor de segmentos. Ela mostra um segmento que resulta em um grupo de clientes. Os clientes encomendaram mercadorias em um período de tempo específico e ganharam pontos de recompensa ou gastaram uma certa quantia de dinheiro.

:::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do construtor de segmento." lightbox="media/segment-builder-overview.png":::

1. Organize seu segmento com regras e sub-regras. Cada regra ou sub-regra consiste em condições. Combinar as condições com operadores lógicos

1. Escolha o [caminho de relacionamento](relationships.md) entre entidades que se aplicam a uma regra. O caminho do relacionamento determina quais atributos podem ser usados em uma condição.

1. Gerencie regras e sub-regras. Altere a posição de uma regra ou exclua-a.

1. Adicione condições e crie o nível certo de aninhamento usando sub-regras.

1. Aplique operações definidas às regras conectadas.

1. Use o painel de atributos para adicionar atributos de entidade disponíveis ou criar condições baseadas em atributos. O painel mostra a lista de entidades e atributos, com base no caminho de relacionamento selecionado, que estão disponíveis para a regra selecionada.

1. Adicione condições com base em atributos às regras e sub-regras existentes ou adicione-as a uma nova regra.

1. Desfaça e refaça alterações durante a criação do segmento.

O exemplo acima ilustra a capacidade de segmentação. Definimos um segmento para clientes que compraram pelo menos $500 de mercadorias online *e* têm interesse em desenvolvimento de software.

## <a name="create-a-new-segment-with-segment-builder"></a>Criar um segmento com o construtor de segmentos

1. Vá para **Segmentos**.

1. Selecione **Novo** > **Criar seu próprio**. Na página do construtor de segmento, você define ou compõe regras. Uma regra consiste em uma ou mais condições que definem um conjunto de clientes.

1. Selecione **Editar detalhes** ao lado de Segmento sem título. Forneça um nome para o seu segmento e atualize o **Nome da entidade de saída** sugerido para o segmento. Opcionalmente, adicione uma descrição e [marcas](work-with-tags-columns.md#manage-tags) ao segmento.

   :::image type="content" source="media/segments_edit_details.png" alt-text="Editar caixa de diálogo de detalhes":::

1. Na seção **Regra 1**, escolha um atributo de uma entidade pela qual você deseja filtrar os clientes. Há duas maneiras de escolher atributos:
   - Revise a lista de entidades e atributos disponíveis no painel **Adicionar à Regra** e selecione o ícone **+** ao lado do atributo a ser adicionado. Escolha se deseja adicionar o atributo a uma regra existente ou use-o para criar uma nova regra.
   - Digite o nome do atributo na seção de regra para ver as sugestões correspondentes.

1. Escolha os operadores para especificar os valores correspondentes da condição. O atributo pode ter um dos quatro tipos de dados como valor: numérico, cadeia de caracteres, data ou booliano. Dependendo do tipo de dados do atributo, diferentes operadores estão disponíveis para especificar a condição. Para segmentos com contas comerciais, dois operadores especiais estão disponíveis para incluir hierarquias potenciais entre as contas ingeridas. Use os operadores *child of (filho de)* e *parent of (pai de)* para incluir contas relacionadas.

1. Selecione **Adicionar condição** para adicionar mais condições a uma regra. Para criar uma regra sob a regra atual, selecione **Adicionar sub-regra**.

1. Se uma regra usar entidades diferentes da entidade *Cliente*, selecione **Definir o caminho do relacionamento** para mapear a entidade selecionada para a entidade de cliente unificada. Se houver somente um caminho de relacionamento possível, o sistema o selecionará automaticamente. Diferentes [caminhos de relacionamento](relationships.md#relationship-paths) podem gerar diferentes resultados. Cada regra pode ter seu próprio caminho de relacionamento.

   :::image type="content" source="media/relationship-path.png" alt-text="Caminho de relacionamento potencial ao criar uma regra com base em uma entidade mapeada para a entidade de cliente unificada.":::

1. Se você tiver várias condições em uma regra, escolha qual operador lógico as conecta.  
   - Operador **AND**: todas as condições devem ser atendidas para incluir um registro no segmento. Use essa opção ao definir condições nas diferentes entidades.
   - Operador **OR**: uma das condições deve ser atendida para incluir um registro no segmento. Use essa opção ao definir várias condições para a mesma entidade.

   :::image type="content" source="media/segmentation-either-condition.png" alt-text="Regra com duas condições AND":::

   Ao usar o operador OR, todas as condições devem se basear em entidades incluídas no caminho de relacionamento.

1. Para criar conjuntos diferentes de registros de clientes, crie várias regras. Para incluir os clientes necessários para seu caso de uso, combine grupos. Especificamente, se você não puder incluir uma entidade em uma regra porque o caminho do relacionamento especificado, crie uma regra para escolher atributos dela.

      :::image type="content" source="media/segment-rule-grouping.png" alt-text="Adicione uma nova regra a um segmento e escolha o operador definido.":::

   1. Selecione **Adicionar regra**.
   1. Selecione um dos operadores de conjunto: **União**, **Interseção** ou **Exceto**.

      - **União** une os dois grupos.
      - **Interseção** sobrepõe os dois grupos. Somente os dados que *são comuns* aos dois grupos são mantidos no grupo unificado.
      - **Exceto** combina os dois grupos. Somente os dados no grupo A que *não são comuns* aos dados do grupo B são mantidos.

1. Por padrão, a entidade de saída conterá automaticamente todos os atributos dos perfis de cliente que corresponderem aos filtros definidos. Se um a segmento for baseado em entidades diferentes da entidade *Cliente*, selecione **Atributos do projeto** para adicionar mais atributos dessas entidades à entidade de saída.

   > [!IMPORTANT]
   > Para segmentos baseados em contas comerciais, detalhes de um ou mais contratos de cada conta da entidade *ContactProfile* devem ser incluídos no segmento para permitir que o segmento seja ativado ou exportado para destinos que exigem as informações de contato. Para obter mais informações sobre a entidade *ContactProfile*, consulte [Mapeamentos semânticos](semantic-mappings.md).
   > Um exemplo de saída para um segmento com base em contas comerciais com atributos projetados de contatos poderia ser assim:
   >
   > |ID  |Nome da conta  |Receita  |Nome do contato  | Função do contato|
   > |---------|---------|---------|---------|---|
   > |10021     | Contoso | 100 mil | [Abbie Moss, Ruth Soto]  | [CEO, gerente de compras]

   :::image type="content" source="media/segments-project-attributes.png" alt-text="Exemplo de atributos projetados selecionados no painel lateral a serem adicionados à entidade de saída.":::
  
   Por exemplo: Um segmento é baseado em uma entidade que contém dados de compra, que estão relacionados à entidade *Cliente*. O segmento busca todos os clientes da Espanha que compraram mercadorias no ano atual. Você pode optar por anexar atributos como o preço das mercadorias ou a data de compra para todos os registros de cliente correspondentes na entidade de saída. Essas informações podem ser úteis para analisar as correlações sazonais com o gasto total.

   > [!NOTE]
   > - **Atributos do projeto** só funciona para entidades que têm um relacionamento um-para-muitos com a entidade cliente. Por exemplo, um cliente pode ter várias assinaturas.
   > - Se o atributo que você deseja projetar está a mais de um salto de distância da entidade *Cliente*, conforme definido pelo relacionamento, esse atributo deve ser usado em todas as regras da consulta de segmento que você está construindo.
   > - Se o atributo que você deseja projetar está a mais de um salto de distância da entidade *Cliente*, esse atributo não precisa estar presente em todas as regras da consulta do segmento que você está construindo.
   > - **Atributos projetados** são fatorados com o uso de operadores de conjunto.

1. Selecione **Executar** para criar o segmento. Selecione **Salvar** se quiser manter a configuração atual e executar a segmento posteriormente. A página **Segmentos** será exibida.

### <a name="segment-builder-tips"></a>Dicas do construtor de segmentos

Ao criar um segmento usando o construtor de segmentos, lembre-se das seguintes dicas:

- O construtor de segmentos não sugere valores válidos de entidades ao definir os operadores para as condições. Você pode acessar **Dados** > **Entidades** e baixar os dados da entidade para ver os valores disponíveis.
- Condições baseadas em datas permitem que você alterne entre datas fixas e um intervalo de datas flutuantes.
- Se você tiver várias regras para o seu segmento, a regra que você está editando terá uma linha azul vertical ao lado dela.
- Você pode mover regras e condições para outros locais na definição do segmento. Selecione as reticências verticais (&vellip;) ao lado de uma regra ou condição e escolha como e para onde movê-la.
- Os controles **Desfazer** e **Refazer** na barra de comando permitem reverter as alterações.
- Após a criação, alguns segmentos permitem que você [acompanhe o uso do segmento](segments.md#track-usage-of-a-segment).

## <a name="next-steps"></a>Próximas etapas

[Exportar um segmento](export-destinations.md) e explorar a [Integração do cartão do cliente](customer-card-add-in.md) para usar segmentos em outros aplicativos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
