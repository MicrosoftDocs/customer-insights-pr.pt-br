---
title: Relacionamentos entre entidades e caminhos de entidade
description: Crie e gerencie relacionamentos entre entidades de várias fontes de dados.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: c639cfca30cf1b57ada7d728311210b7210a37ac
ms.sourcegitcommit: f72d5b86dfdc7282c6c1918b1ab3962d7a1c9852
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7557338"
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

O visualizador de relacionamento mostra um diagrama de rede dos relacionamentos existentes entre entidades conectadas e sua cardinalidade. Ele também visualiza o caminho do relacionamento.

Para personalizar a exibição, você pode alterar a posição das caixas arrastando-as na tela.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de tela do diagrama de rede do visualizador de relacionamento com conexões entre entidades relacionadas.":::

Opções disponíveis: 
- **Exportar como imagem**: salve a exibição atual como um arquivo de imagem.
- **Alterar para layout horizontal/vertical**: altere o alinhamento das entidades e relacionamentos.
- **Editar**: atualize as propriedades de relacionamentos personalizados no painel de edição e salve as alterações.

## <a name="relationship-paths"></a>Caminhos de relacionamento

Um caminho de relacionamento descreve as entidades que estão conectadas com os relacionamentos entre uma entidade de origem e uma entidade de destino. Ele é usado ao criar um segmento ou medida que inclui outras entidades além da entidade de perfil unificado e há várias opções para alcançar a entidade de perfil unificado. 

Um caminho de relacionamento informa o sistema sobre os relacionamentos para acessar a entidade de perfil unificado. Caminhos de relacionamento diferentes podem produzir resultados diferentes.

Por exemplo, a entidade *eCommerce_eCommercePurchases* tem os seguintes relacionamentos com a entidade de perfil unificado *Cliente*:

- eCommerce_eCommercePurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente 

Um caminho de relacionamento determina quais entidades você pode usar ao criar regras para medidas ou segmentos. A escolha da opção com o caminho de relacionamento mais longo provavelmente produzirá menos resultados porque os registros correspondentes precisam fazer parte de todas as entidades. Neste exemplo, um cliente deve ter comprado mercadorias por meio de comércio eletrônico (eCommerce_eCommercePurchases), em um ponto de venda (POS_posPurchases) e participa de nosso programa de fidelidade (loyaltyScheme_loyCustomers). Ao escolher a primeira opção, você provavelmente obterá mais resultados porque os clientes só precisam existir em uma entidade adicional.

### <a name="direct-relationship"></a>Relacionamento direto

Um relacionamento é classificado como um **relacionamento direto** quando uma entidade de origem se relaciona a uma entidade de destino com somente um relacionamento.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchases* se conecta a uma entidade de destino *eCommerce_eCommerceContacts* por meio de uma *ContactId* somente, isso é um relacionamento direto.

:::image type="content" source="media/direct_Relationship.png" alt-text="A entidade de origem se conecta diretamente à entidade de destino.":::

#### <a name="multi-path-relationship"></a>Relacionamento de múltiplos caminhos

Um **relacionamento de múltiplos caminhos** é um tipo especial de relacionamento que conecta uma entidade de origem a mais de uma entidade de destino.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchases* se relaciona a duas entidades de destino *eCommerce_eCommerceContacts* e *loyaltyScheme_loyCustomers*, isso é um relacionamento de múltiplos caminhos.

:::image type="content" source="media/multi-path_relationship.png" alt-text="A entidade de origem se conecta diretamente a mais de uma entidade de destino por meio de um relacionamento com saltos múltiplos.":::

### <a name="indirect-relationship"></a>Relacionamento indireto

Um relacionamento é classificado como um **relacionamento indireto** quando uma entidade de origem se relaciona a uma ou mais entidades adicionais antes de se relacionar a uma entidade de destino.

#### <a name="multi-hop-relationship"></a>Relacionamento com saltos múltiplos

Um *relacionamento com saltos múltiplos* é um *relacionamento indireto* que permite que você se conecte a uma entidade de origem por meio de uma ou mais entidades intermediárias.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchasesWest* se conecta a uma entidade intermediária chamada *eCommerce_eCommercePurchasesEast* e então se conecta a uma entidade de destino chamada *eCommerce_eCommerceContacts*, isso é um relacionamento com saltos múltiplos.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="A entidade de origem se conecta diretamente a uma entidade de destino com uma entidade intermediária.":::

### <a name="multi-hop-multi-path-relationship"></a>Relacionamento de múltiplos caminhos com saltos múltiplos

Os relacionamentos de múltiplos caminhos e com saltos múltiplos podem ser usados juntos para criar **relacionamentos de múltiplos caminhos com saltos múltiplos**. Esse tipo especial combina as funções de **relacionamentos com saltos múltiplos** e de **relacionamentos de múltiplos caminhos**. Ele permite que você se conecte a mais de uma entidade enquanto usa entidades intermediárias.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchasesWest* se conecta a uma entidade intermediária chamada *eCommerce_eCommercePurchasesEast* e então se conecta a duas entidades de destino, *eCommerce_eCommerceContacts* e *loyaltyScheme_loyCustomers*, isso é um relacionamento de múltiplos caminhos e com saltos múltiplos.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="A entidade de origem se conecta diretamente a uma entidade de destino e se conecta a outra entidade de destino por meio de uma entidade intermediária.":::

## <a name="manage-existing-relationships"></a>Gerenciar relacionamentos existentes 

Na página Relacionamentos, cada relacionamento é representado por uma linha. 

Selecione um parentesco e escolha uma das seguintes opções: 
 
- **Editar**: atualize as propriedades de relacionamentos personalizados no painel de edição e salve as alterações.
- **Excluir**: exclua relacionamentos personalizados.
- **Exibir**: exiba relacionamentos criados pelo sistema e herdados. 

## <a name="next-step"></a>Próxima etapa

Relacionamentos de sistema e personalizados são usados para [criar segmentos](segments.md) e [medidas](measures.md) com base em várias fontes de dados que não são mais isoladas.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
