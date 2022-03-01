---
title: Criar e editar medidas
description: Defina medidas relacionadas ao cliente para analisar e refletir o desempenho de determinadas áreas de negócios.
ms.date: 10/15/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: wameng
manager: shellyha
ms.openlocfilehash: 0e214a6eb66abd27f7292db3ce2c2a6e16a8ff33
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405052"
---
# <a name="define-and-manage-measures"></a>Definir e gerenciar medidas

As **Medidas** representam indicadores chave de desempenho (KPIs) que refletem o desempenho e a integridade de áreas de negócios específicas. Os insights de público-alvo fornecem uma experiência intuitiva para criar diferentes tipos de medidas, usando um construtor de consultas que não exige a codificação nem a validação manual das suas medidas. Você pode acompanhar suas medidas de negócios na **Home page**, consultar medidas para clientes específicos no **Cartão de Cliente** e usar medidas para definir segmentos do cliente na página **Segmentos**.

## <a name="create-a-measure"></a>Criar uma medida

Esta seção orienta você na criação de uma medida do zero. Você pode criar medidas com dados de várias fontes de dados conectadas através da entidade Cliente. Alguns [limites de serviço](service-limits.md) se aplicam.

1. Nos insights de público-alvo, vá para **Medidas**.

2. Selecione **Nova medida**.

3. Escolha a medida **Tipo**:

   - **Atributo do cliente**: Um único campo por cliente que reflete uma pontuação, valor ou estado para o cliente. Os atributos do cliente são criados como atributos em uma nova entidade gerada pelo sistema chamada **Customer_Measure**.

   - **Medida do cliente**: Informações sobre o comportamento do cliente com detalhamento por dimensões selecionadas. Uma nova entidade é gerada para cada medida, com vários registros por cliente.

   - **Medida de negócios**: Acompanha o desempenho e a integridade dos negócios. As medidas de negócios podem ter duas saídas diferentes: uma saída numérica exibida na **Home page** ou uma nova entidade que você encontra na página **Entidades**.

4. Forneça um **Nome** e um **Nome de exibição** opcional, depois selecione **Próximo**.

5. Na seção **Entidades**, selecione a primeira entidade da lista suspensa. Nesse ponto, você deve decidir se são necessárias entidades adicionais como parte da sua definição de medida.

   > [!div class="mx-imgBorder"]
   > ![Definição de medida](media/measure-definition.png "Definição de medida")

   Para adicionar mais entidades, selecione **Adicionar entidade** e selecione as entidades que você deseja usar para a medida.

   > [!NOTE]
   > Você pode selecionar somente as entidades que tenham um relacionamento com a entidade inicial. Para obter mais informações sobre como definir relacionamentos, consulte [Relacionamentos](relationships.md).

6. Se preferir, você pode configurar variáveis. Na seção **Variáveis**, selecione **Nova variável**.

   Variáveis são cálculos feitos em cada um dos registros selecionados. Por exemplo, somando ponto de venda (POS) e vendas on-line para cada um dos registros de seus clientes.

7. Forneça um **Nome** para a variável.

8. Na área **Expressão**, escolha um campo no qual será iniciado o cálculo.

9. Digite uma expressão na área **Expressão** ao escolher mais campos a serem incluídos no seu cálculo.

   > [!NOTE]
   > No momento, só há suporte para expressões aritméticas. Além disso, o cálculo de variáveis não é suportado para entidades de diferentes [caminhos da entidade](relationships.md).

10. Escolha **Concluído**.

11. Na seção **Definição de medição**, você definirá como suas entidades escolhidas e variáveis calculadas são agregadas em uma nova entidade de medição ou atributo.

12. Selecione **Nova dimensão**. Você pode pensar em uma dimensão como uma função *agrupar por*. A saída de dados da sua entidade ou atributo de Medida será agrupada por todas as suas dimensões definidas.

    > [!div class="mx-imgBorder"]
    > ![Escolha ciclo agregado](media/measures-businessreport-measure-definition2.png "Escolha ciclo agregado")

    Selecione ou insira as seguintes informações como parte da definição da sua dimensão:

    - **Entidade**: Se você definir uma entidade de Medida, ela deverá incluir pelo menos um atributo. Se você definir um atributo Medida, ele incluirá apenas um atributo por padrão. Esta seleção é sobre como escolher a entidade que inclui esse atributo.
    - **Campo**: Escolha o atributo específico a ser incluído na sua entidade ou atributo de Medida.
    - **Bucket**: Escolha se você deseja agregar dados diariamente, mensalmente ou anualmente. É uma seleção obrigatória apenas se você tiver selecionado um atributo de tipo Data.
    - **Como**: Define o nome do seu novo campo.
    - **Nome para exibição**: Define o nome para exibição de seu campo.

    > [!NOTE]
    > Sua medida comercial será salva como uma entidade de número único e aparecerá na **Home page**, a menos que você adicione mais dimensões à sua medida. Depois de adicionar mais dimensões, a medida *não* aparecerá na **Home page**.

13. Opcionalmente, adicione funções de agregação. Qualquer agregação que você cria resulta em um novo valor dentro da sua entidade ou atributo de Medidas. As funções de agregação suportadas são: **Mín.**, **Máx.**, **Média**, **Mediano**, **Soma**, **Contagem Exclusiva**, **Primeira** (pega o primeiro registro de um valor de dimensão) e **Último** (pega o último registro adicionado a um valor de dimensão).

14. Selecione **Salvar** para salvar suas alterações na medida.

## <a name="manage-your-measures"></a>Gerenciar suas medidas

Depois de criar pelo menos uma medida, você verá uma lista de medidas na página **Medidas**.

Você encontrará informações sobre o tipo de medida, o criador, data e hora da criação, data e hora da última edição, status (se a medida está ativa, inativa ou com falha) e a data e hora da última atualização. Ao selecionar uma medida da lista, você poderá visualizar sua saída.

Para atualizar todas as suas medidas ao mesmo tempo, selecione **Atualizar tudo** sem selecionar uma medida específica.

> [!div class="mx-imgBorder"]
> ![Ações para gerenciar medidas únicas](media/measure-actions.png "Ações para gerenciar medidas únicas")

Como alternativa, selecione uma medida na lista e execute uma das seguintes ações:

- Selecione o nome da medida para ver seus detalhes.
- **Edite** a configuração da medida.
- **Renomeie** a medida.
- **Exclua** a medida.
- Selecione as reticências (...) e, em seguida, **Atualizar** para iniciar o processo de atualização da medida.
- Selecione as reticências (...) e, em seguida, use **Baixar** para obter um arquivo .CSV da medida.

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="next-step"></a>Próxima etapa

Você pode usar medidas existentes para criar seu primeiro segmento de cliente na página **Segmentos**. Para obter mais informações, consulte [Segmentos](segments.md).
