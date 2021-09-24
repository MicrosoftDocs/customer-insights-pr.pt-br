---
title: Atividades do cliente
description: Defina atividades do cliente e exiba-as em uma linha do tempo em perfis de clientes.
ms.date: 09/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c5697df8a7d011c70384c8bc5e4773d7fcc25a62
ms.sourcegitcommit: fecdee73e26816c42d39d160d4d5cfb6c8a91596
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/15/2021
ms.locfileid: "7494397"
---
# <a name="customer-activities"></a>Atividades do cliente

Combine as atividades do cliente de [várias fontes de dados](data-sources.md) no Dynamics 365 Customer Insights para criar uma linha do tempo que lista as atividades de forma cronológica. Inclua a linha do tempo em aplicativos do Dynamics 365 com a solução [Suplemento do Cartão do Cliente](customer-card-add-in.md) ou em um painel do Power BI.

## <a name="define-an-activity"></a>Definir uma atividade

Suas fontes de dados podem incluir entidades com dados transacionais e de atividades de várias fontes de dados. Identifique essas entidades e selecione as atividades que deseja visualizar na linha do tempo do cliente. Escolha a entidade que inclui sua atividade ou atividades de destino.

> [!NOTE]
> Uma entidade deve ter pelo menos um atributo do tipo **Data** para ser incluído na linha do tempo do cliente e você não pode adicionar entidades sem os campos de **Data**. O controle **Adicionar atividade** é desativado, se nenhuma entidade for encontrada.

1. Nos insights de público-alvo, vá para **Dados** > **Atividades**.

1. Selecione **Adicionar atividade** para iniciar a experiência guiada para o processo de configuração da atividade.

1. Na etapa **Dados da atividade**, defina os valores para os seguintes campos:

   - **Nome da atividade**: selecione um nome para sua atividade.
   - **Entidade**: Selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Seleciona o campo que identifica exclusivamente um registro. Não deve conter valores duplicados, valores vazios ou valores ausentes.

   :::image type="content" source="media/Activity_Wizard1.PNG" alt-text="Configure os dados da atividade com nome, entidade e chave primária.":::

1. Selecione **Avançar** para ir para a próxima etapa.

1. Na etapa **Relacionamento**, configure os detalhes para conectar os dados de sua atividade ao cliente correspondente. Esta etapa visualiza a conexão entre as entidades.  

   - **Primeiro**: o campo estrangeiro em sua entidade de atividade que será utilizado para estabelecer um relacionamento com outra entidade.
   - **Segundo**: a entidade cliente de origem correspondente com qual sua entidade de atividade se relacionará. Você só pode se relacionar com entidades de origem do cliente que são usadas no processo de unificação dos dados.
   - **Terceiro**: se já existir um relacionamento entre esta entidade de atividade e a entidade do cliente de origem selecionada, o nome do relacionamento estará no modo somente leitura. Se o relacionamento não existir, um relacionamento será criado com o nome que você forneceu nesta caixa.

   :::image type="content" source="media/Activity_Wizard2.PNG" alt-text="Defina o relacionamento da entidade.":::

1. Selecione **Avançar** para ir para a próxima etapa. 

1. Na etapa **Unificação de atividades**, escolha o evento de atividade e a hora de início de sua atividade. 
   - **Campos obrigatórios**
      - **Atividade do evento**: o campo que é o evento para esta atividade.
      - **Carimbo de data/hora**: o campo que representa a hora de início da sua atividade.

   - **Campos opcionais**
      - **Detalhes adicionais**: o campo com informações relevantes desta atividade.
      - **Ícone**: o ícone que melhor representa este tipo de atividade.
      - **Endereço Web**: o campo contendo uma URL com informações sobre esta atividade. Por exemplo, o sistema transacional que origina essa atividade. Esse URL pode ser qualquer campo da fonte de dados ou pode ser construído como um novo campo usando uma transformação do Power Query. Os dados da URL serão armazenados na entidade *Atividade Unificada*, que pode ser consumida posteriormente com o uso de [APIs](apis.md).

   - **Mostrar na linha do tempo**
      - Escolha se você deseja mostrar esta atividade na exibição da linha do tempo em seus perfis de cliente. Selecione **Sim** para mostrar a atividade na linha do tempo ou **Não** para ocultá-la.

      :::image type="content" source="media/Activity_Wizard3.PNG" alt-text="Especifique os dados da atividade do cliente em uma entidade Atividade Unificada.":::

1. Selecione **Avançar** para passar para a próxima etapa. Você pode selecionar **Concluir e revisar** para salvar a atividade agora com o tipo de atividade definido como **Outro**. 

1. Na etapa **Tipo de Atividade**, escolha o tipo de atividade e, opcionalmente, selecione se deseja mapear semanticamente alguns dos tipos de atividade para uso em outras áreas do Customer Insights. No momento, os tipos de atividade *Comentários*, *Fidelidade*, *SalesOrder*, *SalesOrderLine* e *Assinatura* podem ser mapeados semanticamente depois que concordar em mapear os campos. Se um tipo de atividade não for relevante para a nova atividade, você pode escolher *Outro* ou *Criar* para um tipo de atividade personalizada.

1. Selecione **Avançar** para passar para a próxima etapa. 

1. Na etapa **Revisar**, verifique suas seleções. Volte para qualquer uma das etapas anteriores e atualize as informações, se necessário.

   :::image type="content" source="media/Activity_Wizard5.PNG" alt-text="Revise os campos especificados para uma atividade.":::
   
1. Selecione **Salvar atividade** para aplicar suas alterações e selecione **Concluído** para retornar a **Dados** > **Atividades**. Aqui você verá quais atividades estão definidas para serem exibidas na linha do tempo. 

1. Na página **Atividades**, selecione **Executar** para processar a atividade. 

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.


## <a name="manage-existing-activities"></a>Gerenciar atividades existentes

Em **Dados** > **Atividades**, você pode ver todas as suas atividades salvas e gerenciá-las. Cada atividade é representada por uma linha que também inclui detalhes sobre a origem, a entidade e o tipo de atividade.

As seguintes ações estão disponíveis quando você seleciona uma atividade. 

- **Editar**: abre a configuração da atividade na etapa de revisão. Você pode alterar qualquer uma ou todas as configurações atuais desta etapa. Depois que alterar a configuração, selecione **Salvar atividade** e, em seguida, selecione **Executar** para processar as alterações.

- **Renomear**: abre uma caixa de diálogo onde você pode inserir um nome diferente para a atividade selecionada. Selecione **Salvar** para aplicar suas alterações.

- **Excluir**: abre uma caixa de diálogo para confirmar a exclusão da atividade selecionada. Você também pode excluir mais de uma atividade de uma vez, selecionando as atividades e, em seguida, selecionando o ícone de exclusão. Selecione **Excluir** para confirmar a exclusão.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
