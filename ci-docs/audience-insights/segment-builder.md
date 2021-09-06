---
title: Criar e gerenciar segmentos
description: Criar segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 07/18/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: e759872643cc7387cf732d73c7a320ae8901e5a9
ms.sourcegitcommit: 42692a815695b9fdc93b9358eae09f2c3e97293c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7377774"
---
# <a name="create-and-manage-segments"></a>Criar e gerenciar segmentos

> [!IMPORTANT]
> Várias alterações serão implementadas na experiência de criação de segmentos em setembro de 2021: 
> - O construtor de segmentos terá uma aparência diferente com elementos reestilizados e um fluxo de usuário aprimorado.
> - Novos operadores datetime e um seletor de datas aprimorado estão habilitados no construtor de segmentos.
> - Você poderá adicionar ou remover condições e regras de segmentos. 
> - Regras aninhadas que começarem com uma condição OR estarão disponíveis. Você não precisa mais de uma condição AND na camada mais externa.
> - Um painel lateral para selecionar atributos estará constantemente disponível.
> - Uma opção para selecionar caminhos de relacionamento de entidade.
> Para experimentar o novo construtor de segmentos, envie um email com o assunto "Solicitação para habilitar o novo construtor de segmentos" a cihelp [at] microsoft.com. Inclua o nome de sua organização e a ID de seu ambiente de área restrita.
> :::image type="content" source="media/segment-builder-overview.png" alt-text="Elementos do construtor de segmento." lightbox="media/segment-builder-overview.png":::
>
> 1 - Organize seu segmento com regras e sub-regras. Cada regra ou sub-regra consiste em condições. Combine as condições com operadores lógicos
>
> 2 - Escolha o [caminho de relacionamento](relationships.md) entre entidades que se aplicam a uma regra. O caminho do relacionamento determina quais atributos podem ser usados em uma condição.
>
> 3 - Gerencie regras e sub-regras. Altere a posição de uma regra ou exclua-a.
>
> 4 - Adicione condições e crie o nível certo de aninhamento usando sub-regras.
>
> 5 - Aplique operações definidas às regras conectadas.
>
> 6 - Use o painel de atributos para adicionar atributos de entidade disponíveis ou criar condições baseadas em atributos. O painel mostra a lista de entidades e atributos, com base no caminho de relacionamento selecionado, que estão disponíveis para a regra selecionada.
>
> 7 - Adicione condições com base em atributos às regras e sub-regras existentes ou adicione-as a uma nova regra.
>
> 8 - Desfaça e refaça alterações durante a criação do segmento.

Defina filtros complexos em torno da entidade unificada do cliente e suas entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registros do cliente que você pode exportar e executar. Os segmentos são gerenciados na página **Segmentos**. 

O exemplo a seguir ilustra a capacidade de segmentação. Definimos um segmento para clientes que fizeram pedidos de pelo menos US$ 500 em mercadorias nos últimos 90 dias *e* que estão envolvidos em uma chamada de atendimento ao cliente escalonada.

:::image type="content" source="media/segmentation-group1-2.png" alt-text="Captura de tela da interface do usuário do construtor de segmentos com dois grupos que especificam um segmento de cliente.":::

## <a name="create-a-new-segment"></a>Criar um novo segmento

Há várias maneiras de criar um novo segmento. Esta seção descreve como criar um *segmento em branco* do zero. Você também pode criar um *segmento rápido* com base em entidades existentes ou usar modelos de Aprendizado de Máquina para ter *segmentos sugeridos*. Mais informações: [Visão geral de segmentos](segments.md).

Ao criar um segmento, você pode salvar um rascunho. Ele será salvo como um segmento inativo, e não pode ser ativado se for finalizado com uma configuração válida.

1. Vá para a página **Segmentos**.

1. Selecione **Novo** > **Segmento em branco**.

1. No painel **Novo segmento**, escolha um tipo de segmento:

   - **Segmentos dinâmicos** [atualizar](segments.md#refresh-segments) em uma agenda recorrente.
   - Os **Segmentos estáticos** são executados depois da criação.

1. Forneça um **Nome da entidade de saída** para o segmento. Se preferir, forneça um nome para exibição e uma descrição que ajude a identificar o segmento.

1. Selecione **Próximo** para ir até a página **Construtor de segmentos** onde você define um grupo. Um grupo é um conjunto de clientes.

1. Escolha a entidade que tem o atributo pelo qual você deseja segmentar.

1. Escolha o atributo pelo qual você fará a segmentação. Este atributo pode ter um dos quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.

1. Escolha um operador e um valor para o atributo selecionado.

   > [!div class="mx-imgBorder"]
   > ![Filtro do grupo personalizado.](media/customer-group-numbers.png "Filtro do grupo do cliente")

   |Número |Definição  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atributo          |
   |3    |Operador         |
   |4    |Valor         |

   1. Para adicionar mais condições a um grupo, você pode usar dois operadores lógicos:

      - Operador **E**: Ambas as condições devem ser atendidas como parte do processo de segmentação. Esta opção é mais útil quando você define condições em diferentes entidades.

      - Operador **OU**: Qualquer uma das condições precisa ser atendida como parte do processo de segmentação. Esta opção é mais útil quando você define várias condições para a mesma entidade.

      > [!div class="mx-imgBorder"]
      > ![Operador OU em que uma das condições precisa ser atendida.](media/segmentation-either-condition.png "Operador OU em que uma das condições precisa ser atendida")

      Atualmente é possível aninhar um operador **OU** sob um operador **E**, mas não o contrário.

   1. Cada grupo corresponde a um conjunto de clientes. Você pode combinar grupos para incluir os clientes que são necessários para o seu caso de negócios.    
   Selecione **Adicionar Grupo**.

      > [!div class="mx-imgBorder"]
      > ![Adicionar grupo do grupo de clientes.](media/customer-group-add-group.png "Grupo de clientes adicionar grupo")

   1. Selecione um dos operadores de conjunto: **União**, **Interseção** ou **Exceto**.

   > [!div class="mx-imgBorder"]
   > ![Adicionar união do grupo de clientes.](media/customer-group-union.png "Grupo de clientes adicionar união")

   - **União** une os dois grupos.

   - **Interseção** sobrepõe os dois grupos. Apenas dados que são *comuns* para ambos os grupos é retido no grupo unificado.

   - **Exceto** combina os dois grupos. Apenas dados no grupo A que *não são comuns* a dados no grupo B são retidos.

1. Se a entidade estiver conectada à entidade unificada do cliente por meio de [relacionamentos](relationships.md), você precisará definir o caminho do relacionamento para criar um segmento válido. Adicione as entidades do caminho do relacionamento até poder selecionar a entidade **Cliente: CustomerInsights** no menu suspenso. Depois, escolha **Todos os registros** para cada etapa.

   > [!div class="mx-imgBorder"]
   > ![Caminho do relacionamento durante a criação do segmento.](media/segments-multiple-relationships.png "Caminho do relacionamento durante a criação do segmento")

1. Por padrão, os segmentos geram uma entidade de saída que contém todos os atributos dos perfis de clientes que correspondem aos filtros definidos. Se um segmento for baseado em entidades diferentes da entidade *Cliente*, você poderá adicionar mais atributos dessas entidades à entidade de saída. Selecione **Atributos do projeto** para escolher os atributos que serão anexados à entidade de saída.  
  
   Exemplo: um segmento é baseado em uma entidade que contém dados da atividade do cliente que estão relacionados à entidade *Cliente*. O segmento busca todos os clientes que ligaram para o suporte técnico nos últimos 60 dias. Você pode optar por anexar a duração da chamada e o número de chamadas a todos os registros do cliente correspondentes na entidade de saída. Essas informações podem ser úteis para enviar um email com links úteis para artigos de ajuda online e perguntas frequentes para clientes que ligam com frequência.

   > [!NOTE]
   > - Os atributos projetados funcionam somente para entidades que tenham um relacionamento um-para-muitos com a entidade do cliente. Por exemplo, um cliente pode ter várias assinaturas.
   > - Você só pode projetar atributos a partir de uma entidade que seja usada em cada grupo de consulta de segmento que você está construindo.
   > - Os atributos projetados são fatorados com o uso de operadores de conjunto.

1. Selecione **Salvar** para salvar seu segmento. Seu segmento será salvo e processado, se todos os requisitos forem validados. Caso contrário, ele será salvo como rascunho.

1. Selecione **Voltar aos segmentos** voltar para a página **Segmentos**.



## <a name="quick-segments"></a>Segmentos rápidos

Segmentos rápidos lhe permitem construir segmentos simples com um único operador rapidamente para insights mais rápidos.

1. Na página **Segmentos**, selecione **Novo** > **Criar a partir de**.

   - Selecione a opção **Perfis** para criar um segmento baseado na entidade *unificada do cliente*.
   - Selecione a opção **Medidas** para construir um segmento em torno das medidas que você já criou.
   - Selecione a opção **Inteligência** para criar um segmento em torno de uma das entidades de saída que você gerou usando os recursos **Previsões** ou **Modelos personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo no menu suspenso **Campo**.

3. O sistema fornecerá algumas informações adicionais que ajudarão a criar melhores segmentos de seus clientes.
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
