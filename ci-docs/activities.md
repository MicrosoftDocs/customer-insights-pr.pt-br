---
title: Atividades do cliente
description: Defina atividades do cliente e exiba-as em uma linha do tempo em perfis de clientes.
ms.date: 07/22/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsight
ms.openlocfilehash: cc21b0eeb368156437e60d851c2d144f3974c066
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9188125"
---
# <a name="customer-activities"></a>Atividades do cliente

Atividades do cliente são ações ou eventos realizados por clientes. Por exemplo, transações, duração de chamadas de suporte, avaliações de site, compras ou devoluções. Essas atividades estão contidas em uma ou mais fontes de dados. Com o Customers Insights, consolide as atividades dos clientes dessas [fontes de dados](data-sources.md) e as associe a perfis de cliente. Essas atividades são exibidas em ordem cronológica em uma linha do tempo no perfil do cliente. Inclua a linha do tempo nos aplicativos do Dynamics 365 com a solução [Suplemento do Cartão do Cliente](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definir uma atividade

Uma entidade deve ter pelo menos um atributo do tipo **Data** a ser incluído na linha do tempo de um cliente. O controle **Adicionar atividade** é desativado, se nenhuma entidade for encontrada.

1. Vá para **Dados** > **Atividades**.

1. Selecione **Adicionar atividade** para iniciar a experiência guiada.

1. Na etapa **Dados da atividade**, insira as seguintes informações:

   - **Nome da atividade**: o nome da atividade.
   - **Entidade atividade**: a entidade que inclui dados transacionais ou de atividade.
   - **Chave primária**: campo que identifica exclusivamente um registro. Não deve conter valores duplicados, valores vazios ou valores ausentes.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure os dados da atividade com nome, entidade e chave primária.":::

1. Selecione **Avançar**

1. Na etapa **Relacionamento**, selecione **Adicionar relacionamento** para conectar dados da atividade ao registro de cliente correspondente. Esta etapa visualiza a conexão entre as entidades.  

   - **Chave estrangeira da entidade**: campo da entidade atividade que será usado para estabelecer um relacionamento com outra entidade.
   - **Nome da entidade de destino**: entidade do cliente de origem correspondente com a qual a entidade atividade se relacionará. Você só pode se relacionar com entidades de origem do cliente que são usadas no processo de unificação dos dados.
   - **Nome do relacionamento**: o nome que identifica o relacionamento entre entidades. Se já existir um relacionamento entre essa entidade atividade e a entidade do cliente de origem selecionada, o nome do relacionamento será somente leitura.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina o relacionamento da entidade.":::

   > [!TIP]
   > Em ambientes B2B, você pode selecionar entre entidades de conta e outras entidades. Se você selecionar uma entidade de conta, o caminho de relacionamento será definido automaticamente. Para outras entidades, é necessário definir o caminho do relacionamento sobre uma ou mais entidades intermediárias até chegar a uma entidade de conta.

1. Selecione **Aplicar** para criar o relacionamento.

1. Selecione **Avançar**

1. Na etapa **Unificação de atividades**, escolha o evento de atividade e a hora de início de sua atividade.
   - **Campos obrigatórios**
      - **Atividade do evento**: o campo que é o evento para esta atividade.
      - **Carimbo de data/hora**: o campo que representa a hora de início da sua atividade.

   - **Campos opcionais**
      - **Detalhes adicionais**: o campo com informações relevantes desta atividade.
      - **Ícone**: o ícone que melhor representa este tipo de atividade.
      - **Endereço Web**: o campo contendo uma URL com informações sobre esta atividade. Por exemplo, o sistema transacional que origina essa atividade. Essa URL pode ser qualquer campo da fonte de dados ou pode ser criada como um novo campo usando uma transformação do Power Query. Os dados da URL serão armazenados na entidade *Atividade Unificada*, que pode ser consumida posteriormente com o uso de [APIs](apis.md).

   - **Mostrar na linha do tempo**
      - Escolha se você deseja mostrar esta atividade na exibição da linha do tempo em seus perfis de cliente. Selecione **Sim** para mostrar a atividade na linha do tempo ou **Não** para ocultá-la.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifique os dados da atividade do cliente em uma entidade Atividade Unificada.":::

1. Selecione **Avançar** para escolher o tipo de atividade ou selecione **Concluir e revisar** para salvar a atividade com o tipo de atividade definido como **Outro**.

1. Na etapa **Tipo de Atividade**, escolha o tipo de atividade e, opcionalmente, selecione se deseja mapear semanticamente alguns dos tipos de atividade para uso em outras áreas do Customer Insights. No momento, os tipos de atividade *Comentários*, *Fidelidade*, *SalesOrder*, *SalesOrderLine* e *Assinatura* oferecem suporte à semântica após concordar em mapear os campos. Se um tipo de atividade não for relevante para a nova atividade, você pode escolher *Outro* ou *Criar* para um tipo de atividade personalizada.

1. Selecione **Avançar**

1. Na etapa **Revisar**, verifique suas seleções. Volte para qualquer uma das etapas anteriores e atualize as informações, se necessário.

1. Selecione **Salvar atividade** para aplicar suas alterações e selecione **Concluído** para retornar a **Dados** > **Atividades**. A atividade criada é exibida.

1. Depois de criar todas as atividade, selecione **Executar** para processá-las.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Gerenciar atividades existentes

Vá para **Dados** > **Atividades** para visualizar as atividades salvas, a entidade de origem, o tipo de atividade e se elas estão incluídas na linha do tempo do cliente. Você pode classificar a lista de atividades por qualquer coluna ou usar a caixa de pesquisa para encontrar a atividade que deseja gerenciar.

Selecione uma atividade para exibir as ações disponíveis.

- **Edite** a atividade para alterar sua configuração. A configuração é aberta na etapa de revisão. Depois que alterar a configuração, selecione **Salvar atividade** e, em seguida, selecione **Executar** para processar as alterações.
- **Renomeie** a atividade. Selecione **Salvar** para aplicar suas alterações.
- **Exclua** a atividade. Para excluir mais de uma atividade ao mesmo tempo, selecione as atividades e, depois, selecione **Excluir**. Confirme a exclusão.

## <a name="view-activity-timelines-on-customer-profiles"></a>Visualizar cronogramas de atividades em perfis de clientes

1. Se você selecionou **Exibir na linha do tempo da atividade** na configuração da atividade, vá para **Clientes** e selecione um perfil de cliente para visualizar as atividades do cliente na seção **Linha do tempo de atividade**.

   :::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Visualize atividades configuradas em Perfis de Clientes.":::

1. Para filtrar as atividades na linha do tempo de atividade:

   - Selecione um ou mais ícones de atividade para refinar os resultados e incluir apenas os tipos selecionados.

     :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtre as atividades por tipo usando os ícones.":::

   - Selecione **Filtro** para abrir um painel de filtros e configurar filtros de linha do tempo. Filtre por *ActivityType* e/ou *Data*. Selecione **Aplicar**.

     :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Use o painel de filtro para configurar as condições do filtro.":::

1. Para remover filtros, selecione **Limpar filtros** ou **Filtro** e desmarque a caixa de seleção do filtro.

> [!NOTE]
> Os filtros de atividade são removidos quando você sai de um perfil de cliente. Você deverá aplicá-los cada vez que abrir um perfil de cliente.

[!INCLUDE [footer-include](includes/footer-banner.md)]
