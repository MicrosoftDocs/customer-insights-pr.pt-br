---
title: Criar e gerenciar segmentos
description: Criar segmentos de clientes para agrupá-los com base em vários atributos.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: jimsonc
manager: shellyha
ms.openlocfilehash: 6931110c2ae93cd2792d319aa5a34f0df3088552
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405061"
---
# <a name="create-and-manage-segments"></a>Criar e gerenciar segmentos

Os segmentos permitem agrupar seus clientes com base em atributos demográficos, transacionais ou comportamentais. Você pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para atingir suas metas de negócios.

Você pode definir filtros complexos em torno da entidade Perfil do Cliente e de entidades relacionadas. Cada segmento, após o processamento, cria um conjunto de registros do cliente que você pode exportar e executar. Alguns [limites de serviço](service-limits.md) se aplicam.

Salvo indicação em contrário, todos os segmentos são **Segmentos dinâmicos**, que são atualizados em uma programação recorrente.

O exemplo a seguir ilustra a capacidade de segmentação. Definimos um segmento para clientes que fizeram pedidos de pelo menos US$ 500 em mercadorias nos últimos 90 dias *e* que estão envolvidos em uma chamada de atendimento ao cliente escalonada.

> [!div class="mx-imgBorder"]
> ![Vários grupos](media/segmentation-group1-2.png "Vários grupos")

## <a name="create-a-new-segment"></a>Criar um novo segmento

Os segmentos são gerenciados na página **Segmentos**.

1. Nas informações de público-alvo, vá para a página **Segmentos**.

2. Selecione **Novo** > **Segmento em branco**.

3. No painel **Novo segmento**, escolha um tipo de segmento e forneça um **Nome**.

   Se preferir, forneça um nome para exibição e uma descrição que ajude a identificar o segmento.

4. Selecione **Próximo** para ir até a página **Construtor de segmentos** onde você define um grupo. Um grupo é um conjunto de clientes.

5. Escolha a entidade que tem o atributo pelo qual você deseja segmentar.

6. Escolha o atributo pelo qual você fará a segmentação. Este atributo pode ter um dos quatro tipos de valor: numérico, cadeia de caracteres, data ou booleano.

7. Escolha um operador e um valor para o atributo selecionado.

   > [!div class="mx-imgBorder"]
   > ![Filtro do grupo personalizado](media/customer-group-numbers.png "Filtro do grupo do cliente")

   |Número |Definição  |
   |---------|---------|
   |1     |Entity          |
   |2     |Atributo          |
   |3    |Operador         |
   |4    |Valor         |

8. Se a entidade estiver conectada à entidade unificada do cliente por meio de [relacionamentos](relationships.md), você precisará definir o caminho do relacionamento para criar um segmento válido. Adicione as entidades do caminho do relacionamento até poder selecionar a entidade **Cliente: CustomerInsights** no menu suspenso. Em seguida, escolha **Todos os registros** de cada condição.

   > [!div class="mx-imgBorder"]
   > ![Caminho do relacionamento durante a criação do segmento](media/segments-multiple-relationships.png "Caminho do relacionamento durante a criação do segmento")

9. Selecione **Salvar** para salvar seu segmento. Seu segmento será salvo e processado, se todos os requisitos forem validados. Caso contrário, ele será salvo como rascunho.

10. Selecione **Voltar aos segmentos** voltar para a página **Segmentos**.

## <a name="manage-existing-segments"></a>Gerenciar segmentos existentes

Na página **Segmentos**, você pode visualizar todos os seus segmentos salvos e gerenciá-los.

Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.

Você pode classificar os segmentos em uma coluna selecionando o cabeçalho da coluna.

Use a caixa **Pesquisar** no canto superior direito para filtrar os segmentos.

> [!div class="mx-imgBorder"]
> ![Opções para gerenciar um segmento existente](media/segments-selected-segment.png "Opções para gerenciar um segmento existente")

As seguintes ações estão disponíveis quando você seleciona um segmento:

- **Exiba** os detalhes do segmento, incluindo a tendência de contagem de membros, uma visualização dos membros do segmento.
- **Edite** o segmento para alterar suas propriedades.
- **Atualize** o segmento para incluir os dados mais recentes.
- **Ative** ou **desative** o segmento. Os segmentos têm dois estados possíveis: ativo ou inativo. Esses estados são úteis ao editar um segmento. Para segmentos inativos, a definição do segmento existe, mas ainda não contém nenhum cliente. Quando você ativa um segmento, o estado dele muda de "inativo" para "ativo" e ele começa a procurar clientes que correspondam à definição do segmento. Se uma [atualização programada](system.md#schedule-tab) estiver configurada, os segmentos inativos terão o **Status** listado como **Ignorado**, indicando que uma atualização nem mesmo foi tentada. Quando um segmento inativo for ativado, ele será atualizado e incluído nas atualizações agendadas.
  Como alternativa, você pode usar a funcionalidade **Agendar mais tarde** na lista suspensa **Ativar/desativar** para especificar data e hora futuras para a ativação e desativação de um segmento específico.
- **Renomeie** o segmento.
- **Baixe** a lista de membros como um arquivo .CSV.
- A opção **Adicionar a** envia a lista de IDs do cliente no segmento para processamento em outro aplicativo.
- **Exclua** o segmento.

## <a name="refresh-segments"></a>Atualizar segmentos

Você pode atualizar todos os segmentos de uma vez, selecionando **Atualizar tudo** na página **Segmentos** ou você pode atualizar um ou vários segmentos ao selecioná-los e escolher **Atualizar** nas opções. Como alternativa, você pode configurar uma atualização recorrente em **Admin** > **Sistema** > **Agendar**.

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="download-and-export-segments"></a>Baixar e exportar segmentos

Você pode baixar seus segmentos para um arquivo CSV ou exportá-los para o Dynamics 365 Sales.

### <a name="download-segments-to-a-csv-file"></a>Baixar segmentos para um arquivo CSV

1. Nas informações de público-alvo, vá para a página **Segmentos**.

2. Selecione as reticências no bloco de um segmento específico.

3. Selecione **Baixar como CSV** da lista suspensa de ações.

### <a name="export-segments-to-dynamics-365-sales"></a>Exportar segmentos para o Dynamics 365 Sales

Antes de exportar segmentos para o Dynamics 365 Sales, um administrador precisa [criar o destino de exportação](export-destinations.md) para o Dynamics 365 Sales.

1. Nas informações de público-alvo, vá para a página **Segmentos**.

2. Selecione as reticências no bloco de um segmento específico.

3. Selecione **Adicionar a** na lista suspensa de ações e selecione o destino de exportação para o qual deseja enviar os dados.

## <a name="draft-mode-for-segments"></a>Modo de rascunho para segmentos

Se nem todos os requisitos para processar um segmento forem atendidos, você poderá salvar o segmento como rascunho e acessá-lo na página **Segmentos**.

Ele será salvo como um segmento inativo e não poderá ser ativado até que seja válido.

## <a name="add-more-conditions-to-a-group"></a>Adicionar mais condições a um grupo

Para adicionar mais condições a um grupo, você pode usar dois operadores lógicos:

- Operador **E**: Ambas as condições devem ser atendidas como parte do processo de segmentação. Esta opção é mais útil quando você define condições em diferentes entidades.

- Operador **OU**: Qualquer uma das condições precisa ser atendida como parte do processo de segmentação. Esta opção é mais útil quando você define várias condições para a mesma entidade.

   > [!div class="mx-imgBorder"]
   > ![Operador OU em que uma das condições precisa ser atendida](media/segmentation-either-condition.png "Operador OU em que uma das condições precisa ser atendida")

Atualmente é possível aninhar um operador **OU** sob um operador **E**, mas não o contrário.

## <a name="combine-multiple-groups"></a>Combinar vários grupos

Cada grupo produz um conjunto específico de clientes. Você pode combinar esses grupos para incluir os clientes necessários para o seu caso de negócios.

1. Nos insights de público-alvo, vá para a página **Segmentos** e selecione um segmento.

2. Selecione **Adicionar Grupo**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de clientes adicionar grupo](media/customer-group-add-group.png "Grupo de clientes adicionar grupo")

3. Selecione um dos seguintes operadores definidos: **União**, **Interseção** ou **Exceto**.

   > [!div class="mx-imgBorder"]
   > ![Grupo de clientes adicionar união](media/customer-group-union.png "Grupo de clientes adicionar união")

   Selecione um operador definido para definir um novo grupo. Salve grupos diferentes para determinar quais dados são mantidos:

   - **União** une os dois grupos.

   - **Interseção** sobrepõe os dois grupos. Apenas dados que são *comuns* para ambos os grupos é retido no grupo unificado.

   - **Exceto** combina os dois grupos. Apenas dados no grupo A que *não são comuns* a dados no grupo B são retidos.

## <a name="view-processing-history-and-segment-members"></a>Exibir histórico de processamento e membros do segmento

Você pode ver dados consolidados sobre um segmento revisando seus detalhes.

Na página **Segmentos**, selecione o segmento que deseja revisar.

A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros. Passe o mouse sobre os pontos de dados para ver a contagem de membros em uma data específica.

Você pode atualizar o período da visualização.

> [!div class="mx-imgBorder"]
> ![Intervalo de tempo do segmento](media/segment-time-range.png "Intervalo de tempo do segmento")

A parte inferior contém uma lista dos membros do segmento.

> [!NOTE]
> Os campos que aparecem nesta lista são baseados nos atributos das entidades do seu segmento.
>
>A lista é uma visualização dos membros do segmento correspondentes e mostra os 100 primeiros registros do seu segmento, para que você possa avaliá-lo rapidamente e revisar suas definições, se necessário. Para ver todos os registros correspondentes, você precisa [exportar o segmento](export-destinations.md).

## <a name="quick-segments"></a>Segmentos rápidos

Além do construtor de segmento, há outro caminho para a criação de segmentos. Os segmentos rápidos permitem criar rapidamente segmentos simples com um único operador e com insights instantâneos.

1. Na página **Segmentos**, selecione **Novo** > **Crie rapidamente a partir de**.

   - Selecione a opção **Perfis** para criar um segmento baseado na entidade unificada do Cliente.
   - Selecione a opção **Medidas** para criar um segmento em cada um dos tipos de medidas de Atributo do Cliente que você criou anteriormente na página **Medidas**.
   - Selecione a opção **Inteligência** para criar um segmento em torno de uma das entidades de saída que você gerou usando os recursos **Previsões** ou **Modelos personalizados**.

2. Na caixa de diálogo **Novo segmento rápido**, selecione um atributo no menu suspenso **Campo**.

3. O sistema fornecerá algumas informações adicionais que ajudarão a criar melhores segmentos de seus clientes.
   - Para campos categóricos, mostraremos as 10 principais contagens de clientes. Escolha um **Valor** e selecione **Revisar**.

   - Para um atributo numérico, o sistema mostrará qual valor de atributo se enquadra no percentil de cada cliente. Escolha um **Operador** e um **Valor** e selecione **Revisar**.

4. O sistema fornecerá a você um **Tamanho estimado do segmento**. Você pode optar por gerar o segmento definido ou primeiro revisitá-lo para obter um tamanho de segmento diferente.

    > [!div class="mx-imgBorder"]
    > ![Nome e estimativa para um segmento rápido](media/quick-segment-name.png "Nome e estimativa para um segmento rápido")

5. Forneça um **Nome** para seu segmento. Se preferir, forneça um **Nome para exibição**.

6. Selecione **Salvar** para criar seu segmento.

7. Depois que o segmento terminar o processamento, você poderá vê-lo como qualquer outro segmento criado.

Para os seguintes cenários, recomendamos o uso do construtor de segmentos, em vez do recursos de segmentos recomendados:

- Criando segmentos com filtros em campos categóricos nos quais o operador é diferente do operador **É**
- Criando segmentos com filtros em campos numéricos em que o operador é diferente dos operadores **Entre**, **Maior que** e **Menor que**
- Criação de segmentos com filtros nos campos de tipo de data

## <a name="next-steps"></a>Próximas etapas

[Exportar um segmento](export-destinations.md) e explorar o [Cartão de Cliente](customer-card-add-in.md) e os [Conectores](export-power-bi.md) para obter insights no nível do cliente.
