---
title: Atividades do cliente
description: Defina atividades do cliente e exiba-as em uma linha do tempo em perfis de clientes.
ms.date: 11/01/2021
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
ms.openlocfilehash: 6c0a1bc5d9a42806b458142804199c733ff530ec
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755484"
---
# <a name="customer-activities"></a>Atividades do cliente

Combine as atividades do cliente de [várias fontes de dados](data-sources.md) no Dynamics 365 Customer Insights. Crie uma linha do tempo que liste as atividades cronologicamente. Inclua a linha do tempo nos aplicativos do Dynamics 365 com a solução [Suplemento do Cartão do Cliente](customer-card-add-in.md).

## <a name="define-an-activity"></a>Definir uma atividade

Suas fontes de dados podem incluir entidades com dados transacionais e de atividades de várias fontes de dados. Identifique essas entidades e selecione as atividades que deseja visualizar na linha do tempo do cliente. Escolha a entidade que inclui sua atividade ou atividades de destino.

Uma entidade deve ter pelo menos um atributo do tipo **Data** para ser incluído na linha do tempo do cliente e você não pode adicionar entidades sem os campos de **Data**. O controle **Adicionar atividade** é desativado, se nenhuma entidade for encontrada.

1. Vá para **Dados** > **Atividades**.

1. Selecione **Adicionar atividade** para iniciar a experiência guiada para o processo de configuração da atividade.

1. Na etapa **Dados da atividade**, defina os valores para os seguintes campos:

   - **Nome da atividade**: selecione um nome para sua atividade.
   - **Entidade**: Selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Seleciona o campo que identifica exclusivamente um registro. Não deve conter valores duplicados, valores vazios ou valores ausentes.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure os dados da atividade com nome, entidade e chave primária.":::

1. Selecione **Avançar** para ir para a próxima etapa.

1. Na etapa **Relacionamento**, configure os detalhes para conectar seus dados de atividade ao registro de cliente correspondente. Esta etapa visualiza a conexão entre as entidades.  

   - **Primeiro**: o campo estrangeiro em sua entidade de atividade que será utilizado para estabelecer um relacionamento com outra entidade.
   - **Segundo**: a entidade cliente de origem correspondente com qual sua entidade de atividade se relacionará. Você só pode se relacionar com entidades de origem do cliente que são usadas no processo de unificação dos dados.
   - **Terceiro**: se já existir um relacionamento entre esta entidade de atividade e a entidade do cliente de origem selecionada, o nome do relacionamento estará no modo somente leitura. Se o relacionamento não existir, um relacionamento será criado com o nome que você forneceu nesta caixa.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina o relacionamento da entidade.":::

   > [!TIP]
   > Em ambientes B2B, você pode selecionar entre entidades de conta e outras entidades. Se você selecionar uma entidade de conta, o caminho de relacionamento será definido automaticamente. Para outras entidades, é necessário definir o caminho do relacionamento sobre uma ou mais entidades intermediárias até chegar a uma entidade de conta.

1. Selecione **Avançar** para ir para a próxima etapa. 

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

1. Selecione **Avançar** para passar para a próxima etapa. Você pode selecionar **Concluir e revisar** para salvar a atividade agora com o tipo de atividade definido como **Outro**. 

1. Na etapa **Tipo de Atividade**, escolha o tipo de atividade e, opcionalmente, selecione se deseja mapear semanticamente alguns dos tipos de atividade para uso em outras áreas do Customer Insights. No momento, os tipos de atividade *Comentários*, *Fidelidade*, *SalesOrder*, *SalesOrderLine* e *Assinatura* oferecem suporte à semântica após concordar em mapear os campos. Se um tipo de atividade não for relevante para a nova atividade, você pode escolher *Outro* ou *Criar* para um tipo de atividade personalizada.

1. Selecione **Avançar** para passar para a próxima etapa. 

1. Na etapa **Revisar**, verifique suas seleções. Volte para qualquer uma das etapas anteriores e atualize as informações, se necessário.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Revise os campos especificados para uma atividade.":::
   
1. Selecione **Salvar atividade** para aplicar suas alterações e selecione **Concluído** para retornar a **Dados** > **Atividades**. Aqui você verá quais atividades estão definidas para serem exibidas na linha do tempo. 

1. Na página **Atividades**, selecione **Executar** para processar a atividade. 

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-activities"></a>Gerenciar atividades existentes

Em **Dados** > **Atividades**, você pode ver todas as suas atividades salvas e gerenciá-las. Cada atividade é representada por uma linha que também inclui detalhes sobre a origem, a entidade e o tipo de atividade.

As seguintes ações estão disponíveis quando você seleciona uma atividade. 

- **Editar**: abre a configuração da atividade na etapa de revisão. Você pode alterar qualquer uma ou todas as configurações atuais desta etapa. Depois que alterar a configuração, selecione **Salvar atividade** e, em seguida, selecione **Executar** para processar as alterações.

- **Renomear**: abre uma caixa de diálogo onde você pode inserir um nome diferente para a atividade selecionada. Selecione **Salvar** para aplicar suas alterações.

- **Excluir**: abre uma caixa de diálogo para confirmar a exclusão da atividade selecionada. Você também pode excluir mais de uma atividade de uma vez, selecionando as atividades e, em seguida, selecionando o ícone de exclusão. Selecione **Excluir** para confirmar a exclusão.

## <a name="view-activity-timelines-on-customer-profiles"></a>Visualizar cronogramas de atividades em perfis de clientes

Depois de configurar as atividades do cliente, selecione **Exibir na linha do tempo da atividade** na configuração de atividades para encontrar todas as atividades do seu cliente em seu perfil de cliente.

Para abrir a linha do tempo para um cliente, vá para **Clientes** e escolha o perfil do cliente que deseja visualizar.

Se um cliente participou de uma atividade configurada, você a encontrará na seção **Linha do tempo da atividade**.

:::image type="content" source="media/Activity_Timeline1.PNG" alt-text="Visualize atividades configuradas em Perfis de Clientes.":::

Existem várias maneiras de filtrar atividades na linha do tempo da atividade:

- Você pode selecionar um ou vários dos ícones de atividade para refinar seus resultados para incluir apenas os tipos selecionados.

  :::image type="content" source="media/Activity_Timeline2.PNG" alt-text="Filtre as atividades por tipo usando os ícones.":::

- Você pode selecionar **Filtro** para abrir um painel de filtro para configurar seus filtros de linha do tempo.

   1. Você pode filtrar por *Tipo de atividade* e *Data*
   1. Selecione **Aplicar** para usar os filtros na linha do tempo da atividade.

   :::image type="content" source="media/Activity_Timeline3.PNG" alt-text="Use o painel de filtro para configurar as condições do filtro.":::

Para remover filtros, selecione o **x** ao lado de cada filtro aplicado à linha do tempo ou selecione **Limpar filtros**.


> [!NOTE]
> Os filtros de atividade são removidos quando você sai de um perfil de cliente. Você deve aplicá-los cada vez que abrir um perfil de cliente.

[!INCLUDE [footer-include](includes/footer-banner.md)]