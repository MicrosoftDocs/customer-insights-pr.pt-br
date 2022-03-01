---
title: Relacionamentos entre entidades e caminhos de entidade
description: Crie e gerencie relacionamentos entre entidades de várias fontes de dados.
ms.date: 06/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.openlocfilehash: d5b9566ec88096fec31d8e164a51598159ec26d4
ms.sourcegitcommit: ece48f80a7b470fb33cd36e3096b4f1e9190433a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/03/2021
ms.locfileid: "6171150"
---
# <a name="relationships-between-entities"></a>Relacionamentos entre entidades

Relacionamentos conectam entidades e definem um gráfico de seus dados quando as entidades compartilham um identificador comum, uma chave estrangeira. Essa chave estrangeira pode ser referenciada de uma entidade para outra. As entidades conectadas permitem a definição de segmentos e medidas com base em várias fontes de dados.

Existem três tipos de relacionamento: 
- Relacionamentos de sistema não editáveis, criados pelo sistema como parte do processo de unificação de dados
- Relacionamentos herdados não editáveis, que são criados automaticamente por meio da ingestão de fontes de dados 
- Relacionamentos personalizados editáveis, criados e configurados por usuários

## <a name="non-editable-system-relationships"></a>Relações de sistema não editáveis

Durante a unificação de dados, os relacionamentos do sistema são criados automaticamente com base na correspondência inteligente. Esses relacionamentos ajudam a relacionar os registros do perfil do cliente com os registros correspondentes. O diagrama a seguir ilustra a criação de três relacionamentos baseados no sistema. A entidade do cliente é combinada com outras entidades para produzir a entidade unificada *Cliente*.

:::image type="content" source="media/relationships-entities-merge.png" alt-text="Diagrama com caminhos de relacionamento para a entidade do cliente com três relacionamentos 1:N.":::

- O **Relacionamento *CustomerToContact*** foi criado entre a entidade *Cliente* e a entidade *Contato*. A entidade *Cliente* obtém o campo-chave **Contact_contactID** para relacionar-se com o campo-chave da entidade de *Contato* **contactID**.
- O **Relacionamento *CustomerToContact*** foi criado entre a entidade *Cliente* e a entidade *Conta*. A entidade *Cliente* obtém o campo-chave **Account_accountID** para relacionar-se com o campo-chave da entidade de *Conta* **accountID**.
- O **Relacionamento *CustomerToWebAccount*** foi criado entre a entidade *Cliente* e a entidade *WebAccount*. A entidade *Customer* obtém o campo-chave **WebAccount_webaccountID** para relacionar-se com o campo-chave da entidade de *WebAccount* **webaccountID**.

## <a name="non-editable-inherited-relationships"></a>Relações herdadas não editáveis

Durante o processo de ingestão de dados, o sistema verifica as fontes de dados para relacionamentos existentes. Se não houver relacionamentos, o sistema os criará automaticamente. Esses relacionamentos também são usados em processos downstream.

## <a name="create-a-custom-relationship"></a>Criar um relacionamento personalizado

O relacionamento consiste em uma *entidade de origem* contendo a chave estrangeira e uma *entidade de destino* para a qual a chave estrangeira da entidade de origem aponta. 

1. Nas informações de público-alvo, vá para **Dados** > **Relacionamentos**.

2. Selecione **Novo relacionamento**.

3. No painel **Novo relacionamento**, forneça as seguintes informações:

   :::image type="content" source="media/relationship-add.png" alt-text="Novo painel lateral de relacionamento com campos de entrada vazios.":::

   - **Nome do relacionamento**: nome que reflete o propósito do relacionamento. Exemplo: CustomerToSupportCase.
   - **Descrição**: Descrição do relacionamento.
   - **Entidade de origem**: entidade que é usada como fonte no relacionamento. Exemplo: SupportCase.
   - **Entidade de destino**: entidade que é usada como destino no relacionamento. Exemplo: cliente.
   - **Cardinalidade de origem**: especifique a cardinalidade da entidade de origem. A cardinalidade descreve o número de elementos possíveis em um conjunto. Sempre está relacionado à cardinalidade de destino. Você pode escolher entre **Um** e **Muitos**. Somente relacionamentos muitos para um e um para um são suportados.  
     - Muitos para um: vários registros de origem podem se relacionar a um registro de destino. Exemplo: vários casos de suporte de um único cliente.
     - Um para um: um único registro de origem se relaciona a um registro de destino. Exemplo: uma ID de fidelidade para um único cliente.

     > [!NOTE]
     > Os relacionamentos muitos para muitos podem ser criados por meio de dois relacionamentos muitos para um e uma entidade de vinculação, que conecta a entidade de origem e a entidade de destino.

   - **Cardinalidade de destino**: Selecione a cardinalidade dos registros da entidade de destino. 
   - **Campo-chave de fonte**: o campo de chave estrangeira na entidade de origem. Exemplo: o SupportCase pode usar CaseID como um campo de chave estrangeira.
   - **Campo-chave de destino**: o campo-chave da entidade de destino. Exemplo: o cliente pode usar o campo-chave **CustomerID**.

4. Selecione **Salvar** para criar o relacionamento personalizado.

## <a name="view-relationships"></a>Exibir relacionamentos

A página Relacionamentos lista todos os relacionamentos que foram criados. Cada linha representa um relacionamento, que também inclui detalhes sobre a entidade de origem, a entidade de destino e a cardinalidade. 

:::image type="content" source="media/relationships-list.png" alt-text="Lista de relacionamentos e opções na barra de ação da página Relacionamentos.":::

Esta página oferece um conjunto de opções para relacionamentos novos e existentes: 
- **Novo relacionamento**: [Criar um relacionamento personalizado](#create-a-custom-relationship).
- **Visualizador**: [explore o visualizador de relacionamento](#explore-the-relationship-visualizer) para ver um diagrama de rede dos relacionamentos existentes e sua cardinalidade.
- **Filtrar por**: escolha o tipo de relacionamento a ser mostrado na lista.
- **Pesquisar relacionamentos**: use uma pesquisa baseada em texto nas propriedades dos relacionamentos.

### <a name="explore-the-relationship-visualizer"></a>Explorar o visualizador de relacionamento

O visualizador de relacionamento mostra um diagrama de rede dos relacionamentos existentes entre entidades conectadas e sua cardinalidade.

Para personalizar a exibição, você pode alterar a posição das caixas arrastando-as na tela.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de tela do diagrama de rede do visualizador de relacionamento com conexões entre entidades relacionadas.":::

Opções disponíveis: 
- **Exportar como imagem**: salve a exibição atual como um arquivo de imagem.
- **Alterar para layout horizontal/vertical**: altere o alinhamento das entidades e relacionamentos.
- **Editar**: atualize as propriedades de relacionamentos personalizados no painel de edição e salve as alterações.

## <a name="manage-existing-relationships"></a>Gerenciar relacionamentos existentes 

Na página Relacionamentos, cada relacionamento é representado por uma linha. 

Selecione um parentesco e escolha uma das seguintes opções: 
 
- **Editar**: atualize as propriedades de relacionamentos personalizados no painel de edição e salve as alterações.
- **Excluir**: exclua relacionamentos personalizados.
- **Exibir**: exiba relacionamentos criados pelo sistema e herdados. 

## <a name="next-step"></a>Próxima etapa

Os relacionamentos do sistema e personalizados são usados para [criar segmentos](segments.md) com base em várias fontes de dados que não são mais isoladas.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
