---
title: Atividades do cliente ou do contato comercial
description: Defina as atividades do cliente ou do contato comercial e exiba-as em uma linha do tempo nos perfis dos clientes.
ms.date: 10/26/2022
ms.subservice: audience-insights
ms.reviewer: v-wendysmith
ms.topic: conceptual
author: srivas15
ms.author: shsri
manager: shellyha
searchScope:
- ci-entities
- ci-customer-card
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: d8caa477278f04c3a0a95ced15f4bea2a22aa8cd
ms.sourcegitcommit: da6a2d189edacc8f2c0f2abedcb28245f26fe74c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9723767"
---
# <a name="customer-or-business-contact-activities"></a>Atividades do cliente ou do contato comercial

As atividades do cliente são ações ou eventos realizados por clientes ou contatos comerciais. Por exemplo, transações, duração de chamadas de suporte, avaliações de site, compras ou devoluções. Essas atividades estão contidas em uma ou mais fontes de dados. Com o Customers Insights, consolide as atividades dos clientes dessas [fontes de dados](data-sources.md) e as associe a perfis de cliente. Essas atividades são exibidas em ordem cronológica em uma linha do tempo no perfil do cliente. Inclua a linha do tempo nos aplicativos do Dynamics 365 com a solução [Suplemento do Cartão do Cliente](customer-card-add-in.md).

## <a name="define-a-customer-activity"></a>Definir uma atividade do cliente

Uma entidade deve ter pelo menos um atributo do tipo **Data** a ser incluído na linha do tempo de um cliente. O controle **Adicionar atividade** é desativado, se nenhuma entidade for encontrada.

1. Vá para **Dados** > **Atividades**.

1. Selecione **Adicionar atividade** para iniciar a experiência guiada.

1. Na etapa **Dados da atividade**, insira as seguintes informações:

   - **Nome da atividade**: selecione um nome para sua atividade.
   - **Entidade de atividade**: selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Seleciona o campo que identifica exclusivamente um registro. Não deve conter valores duplicados, valores vazios ou valores ausentes.

     > [!NOTE]
     > A chave primária de cada linha deve permanecer consistente em atualizações da fonte de dados. Se a chave primária de uma linha for atualizada em uma atualização de fonte de dados, ela criará duplicatas na entidade Atividade de saída. 

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure os dados da atividade com nome, entidade e chave primária.":::

1. Selecione **Avançar**

1. Na etapa **Relacionamento**, selecione **Adicionar relacionamento** para conectar dados da atividade ao registro de cliente correspondente. Esta etapa visualiza a conexão entre as entidades.  

   - **Chave estrangeira**: o campo estrangeiro em sua entidade de atividade que será utilizado para estabelecer um relacionamento com outra entidade.
   - **Nome da entidade de destino**: entidade do cliente de origem correspondente com a qual a entidade atividade se relacionará. Você só pode se relacionar com entidades de origem do cliente que são usadas no processo de unificação dos dados.
   - **Nome do relacionamento**: se já existir um relacionamento entre esta entidade de atividade e a entidade cliente de origem selecionada, o nome do relacionamento estará no modo somente leitura. Se o relacionamento não existir, um relacionamento será criado com o nome que você forneceu nesta caixa.

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

## <a name="manage-existing-customer-activities"></a>Gerenciar atividades de clientes existentes

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

> [!NOTE]
> Os filtros de atividade são removidos quando você sai de um perfil de cliente. Você deverá aplicá-los cada vez que abrir um perfil de cliente.

## <a name="define-a-contact-activity"></a>Definir uma atividade de contato

Para contas comerciais (B-to-B), use uma entidade *ContactProfile* para capturar atividades de contatos. É possível ver na linha do tempo de atividades de uma conta qual contato foi responsável por cada atividade. A maioria das etapas segue a configuração do mapeamento de atividades do cliente.

   > [!NOTE]
   > Para definir uma atividade em nível de contato, uma entidade *ContactProfile* deve ser criada, como um [perfil de contato unificado](data-unification-contacts.md) ou por meio de [mapeamento semântico](semantic-mappings.md#define-a-contactprofile-semantic-entity-mapping).
   >
   > Você deve ter os atributos **AccountID** e **ContactID** para cada registro nos seus dados de atividade.
  
1. Vá para **Dados** > **Atividades**.

1. Selecione **Adicionar atividade**.

1. Na etapa **Dados da atividade**, insira as seguintes informações:

   - **Nome da atividade**: selecione um nome para sua atividade.
   - **Entidade de atividade**: selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Seleciona o campo que identifica exclusivamente um registro. Não deve conter valores duplicados, valores vazios ou valores ausentes.

     > [!NOTE]
     > A chave primária de cada linha deve permanecer consistente em atualizações da fonte de dados. Se a chave primária de uma linha for atualizada em uma atualização de fonte de dados, ela criará duplicatas na entidade Atividade de saída. 


1. Na etapa **Relacionamentos**, crie um relacionamento indireto entre seus dados de origem de atividade e contas, usando seus dados de contato como uma entidade intermediária. Para obter mais informações, consulte [caminhos de relacionamento direto e indireto](relationships.md#relationship-paths).
   - Relacionamento de exemplo para uma atividade chamada *Compras*:
      - **Dados da Atividade de Origem de Compras** > **Dados de Contato** no atributo **ContactID**
      - **Dados de Contato** > **Dados de Conta** no atributo **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Configuração do relacionamento de exemplo.":::

1. Depois de configurar os relacionamentos, selecione **Avançar** e conclua a configuração do seu mapeamento de atividades. Para obter etapas detalhadas sobre a criação de atividades, consulte [definir uma atividade do cliente](#define-a-customer-activity).

1. Execute seus mapeamentos de atividades.

1. Suas atividades no nível do contato agora estarão visíveis na linha do tempo do cliente.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultado final após a configuração das atividades de contato":::

## <a name="contact-level-activity-timeline-filtering"></a>Filtragem da linha do tempo de atividades no nível do contato

Depois de configurar um mapeamento de atividades no nível do contato e executá-lo, a linha do tempo de atividades dos seus clientes será atualizada. Ela inclui as IDs ou nomes, dependendo da sua configuração *ContactProfile*, das atividades em que atuaram. Você pode filtrar atividades por contatos na linha do tempo para ver contatos específicos de seu interesse. Além disso, você pode ver todas as atividades que não estão atribuídas a um contato específico, selecionando **Atividades não mapeadas para um Contato**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opções de filtragem disponíveis para atividades no nível do contato.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
