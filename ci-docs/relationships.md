---
title: Relacionamentos entre entidades e caminhos de entidade
description: Crie e gerencie relacionamentos entre entidades de várias fontes de dados.
ms.date: 09/27/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- ci-entities
- ci-relationships
- ci-activities
- ci-activities-wizard
- ci-measures
- ci-segments
- ci-segment-builder
- ci-measure-builder
- ci-measure-template
- ci-permissions
- customerInsights
ms.openlocfilehash: e622e5fa0b5738e31db1c668d95312adbc4f7d36
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183534"
---
# <a name="relationships-between-entities-and-entity-paths"></a>Relacionamentos entre entidades e caminhos de entidade

Relacionamentos conectam entidades e definem um gráfico de seus dados quando as entidades compartilham um identificador comum, uma chave estrangeira. Essa chave estrangeira pode ser referenciada de uma entidade para outra. As entidades conectadas permitem a definição de segmentos e medidas com base em várias fontes de dados.

Existem três tipos de relacionamento: 
- As relações do sistema não editáveis são criadas pelo sistema como parte do processo de unificação dos dados
- As relações do sistema herdadas não editáveis são criadas manualmente a partir da ingestão de fontes de dados
- Os relacionamentos personalizados editáveis são criados e configurados pelos usuários

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

1. Vá para **Dados** > **Relacionamentos**.

2. Selecione **Novo relacionamento**.

3. No painel **Novo relacionamento**, forneça as seguintes informações:

   :::image type="content" source="media/relationship-add.png" alt-text="Novo painel lateral de relacionamento com campos de entrada vazios.":::

   - **Nome do relacionamento**: nome que reflete o propósito do relacionamento. Exemplo: CustomerToSupportCase.
   - **Descrição**: Descrição do relacionamento.
   - **Entidade de origem**: entidade que é usada como fonte no relacionamento. Exemplo: SupportCase.
   - **Entidade de destino**: entidade que é usada como destino no relacionamento. Exemplo: cliente.
   - **Cardinalidade da origem**: cardinalidade da entidade de origem. A cardinalidade descreve o número de elementos possíveis em um conjunto. Sempre está relacionado à cardinalidade de destino. Você pode escolher entre **Um** e **Muitos**. Somente relacionamentos muitos para um e um para um são suportados.  
     - Muitos para um: vários registros de origem podem se relacionar a um registro de destino. Exemplo: vários casos de suporte de um único cliente.
     - Um para um: um único registro de origem se relaciona a um registro de destino. Exemplo: uma ID de fidelidade para um único cliente.

     > [!NOTE]
     > Os relacionamentos muitos para muitos podem ser criados por meio de dois relacionamentos muitos para um e uma entidade de vinculação, que conecta a entidade de origem e a entidade de destino.

   - **Cardinalidade do destino**: cardinalidade dos registros da entidade de destino.
   - **Campo Chave de origem**: campo de chave estrangeira na entidade de origem. Exemplo: SupportCase usa **CaseID** como o campo de chave estrangeira.
   - **Campo Chave de destino**: campo de chave da entidade de destino. Exemplo: Cliente usa **CustomerID** como o campo de chave.

4. Selecione **Salvar** para criar o relacionamento personalizado.

## <a name="set-up-account-hierarchies"></a>Configure as hierarquias da conta

Ambientes que são configurados para usar contas comerciais como o público-alvo principal podem configurar hierarquias de conta para as contas comerciais relacionadas. Por exemplo, uma empresa que possui unidades de negócio separadas.

As organizações criam hierarquias de contas para gerenciar melhor as contas e seus relacionamentos entre si. O Customer Insights oferece suporte a hierarquias de contas pai-filho que já existem nos dados do cliente ingeridos. Por exemplo, contas do Dynamics 365 Sales. Essas hierarquias podem ser configuradas na página **Relacionamentos**.

1. Vá para **Dados** > **Relacionamentos**.
1. Selecione a guia **Hierarquia da conta**.
1. Selecione **Nova hierarquia da conta**.
1. No painel **Hierarquia da conta**, forneça um nome para a hierarquia. O sistema cria um nome para a entidade de saída, mas você pode alterá-lo.
1. Selecione a entidade que contém a hierarquia de sua conta. Geralmente está na mesma entidade que contém as contas.
1. Selecione o **UID da Conta** e o **UID Pai** da entidade selecionada.
1. Selecione **Salvar** para finalizar a hierarquia de contas.

## <a name="manage-existing-relationships"></a>Gerenciar relacionamentos existentes

Acesse a página **Relacionamentos** para exibir todos os relacionamentos que foram criados, sua entidade de origem, a entidade de destino e a cardinalidade.

:::image type="content" source="media/relationships-list.png" alt-text="Lista de relacionamentos e opções na barra de ação da página Relacionamentos.":::

Use as opções **Filtrar por** ou **Pesquisar relacionamentos** para localizar um relacionamento específico. Para ver um diagrama de rede dos relacionamentos existentes e sua cardinalidade, selecione [**Visualizador**](#explore-the-relationship-visualizer).

Selecione um relacionamento para exibir as ações disponíveis:
- **Editar**: atualize as propriedades de relacionamentos personalizados no painel de edição e salve as alterações.
- **Excluir**: exclua relacionamentos personalizados.
- **Exibir**: exiba relacionamentos criados pelo sistema e herdados.

### <a name="explore-the-relationship-visualizer"></a>Explorar o visualizador de relacionamento

O visualizador de relacionamento mostra um diagrama de rede dos relacionamentos existentes entre entidades conectadas e sua cardinalidade. Ele também visualiza o caminho do relacionamento.

:::image type="content" source="media/relationship-visualizer.png" alt-text="Captura de tela do diagrama de rede do visualizador de relacionamento com conexões entre entidades relacionadas.":::

Para personalizar a exibição, você pode alterar a posição das caixas arrastando-as na tela. Outras opções incluem: 
- **Exportar como imagem**: salve a exibição atual como um arquivo de imagem.
- **Alterar para layout horizontal/vertical**: altere o alinhamento das entidades e relacionamentos.
- **Editar**: atualize as propriedades de relacionamentos personalizados no painel de edição e salve as alterações.

## <a name="relationship-paths"></a>Caminhos de relacionamento

Um caminho de relacionamento descreve as entidades que estão conectadas com os relacionamentos entre uma entidade de origem e uma entidade de destino. Ele é usado ao criar um segmento ou uma medida que inclua entidades diferentes da entidade do perfil unificado e há várias opções para alcançar a entidade do perfil unificado. Caminhos de relacionamento diferentes podem produzir resultados diferentes.

Por exemplo, a entidade *eCommerce_eCommercePurchases* tem os seguintes relacionamentos com a entidade de perfil unificado *Cliente*:

- eCommerce_eCommercePurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > Cliente
- eCommerce_eCommercePurchases > eCommerce_eCommerceContacts > POS_posPurchases > loyaltyScheme_loyCustomers > Cliente

Um caminho de relacionamento determina quais entidades você pode usar ao criar regras para medidas ou segmentos. A escolha da opção com o caminho de relacionamento mais longo provavelmente produzirá menos resultados porque os registros correspondentes precisam fazer parte de todas as entidades. Neste exemplo, um cliente tem que ter adquirido mercadorias através de comércio eletrônico (eCommerce_eCommercePurchases) em um ponto de venda (POS_posPurchases) e participar de nosso programa de fidelidade (loyaltyScheme_loyCustomers). Ao escolher a primeira opção, você provavelmente obterá mais resultados porque os clientes só precisam existir em uma entidade adicional.

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

Um **relacionamento com saltos múltiplos** é um *relacionamento indireto* que permite que você se conecte a uma entidade de origem por meio de uma ou mais entidades intermediárias.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchasesWest* se conecta a uma entidade intermediária chamada *eCommerce_eCommercePurchasesEast* e então se conecta a uma entidade de destino chamada *eCommerce_eCommerceContacts*, isso é um relacionamento com saltos múltiplos.

:::image type="content" source="media/multi-hop_relationship.png" alt-text="A entidade de origem se conecta diretamente a uma entidade de destino com uma entidade intermediária.":::

### <a name="multi-hop-multi-path-relationship"></a>Relacionamento de múltiplos caminhos com saltos múltiplos

Os relacionamentos de múltiplos caminhos e com saltos múltiplos podem ser usados juntos para criar **relacionamentos de múltiplos caminhos com saltos múltiplos**. Esse tipo especial combina as funções de **relacionamentos com saltos múltiplos** e de **relacionamentos de múltiplos caminhos**. Ele permite que você se conecte a mais de uma entidade enquanto usa entidades intermediárias.

Por exemplo, se uma entidade de atividade chamada *eCommerce_eCommercePurchasesWest* se conecta a uma entidade intermediária chamada *eCommerce_eCommercePurchasesEast* e então se conecta a duas entidades de destino, *eCommerce_eCommerceContacts* e *loyaltyScheme_loyCustomers*, isso é um relacionamento de múltiplos caminhos e com saltos múltiplos.

:::image type="content" source="media/multi-hop_multi-path_relationship.png" alt-text="A entidade de origem se conecta diretamente a uma entidade de destino e se conecta a outra entidade de destino por meio de uma entidade intermediária.":::

## <a name="next-step"></a>Próxima etapa

Relacionamentos de sistema e personalizados são usados para [criar segmentos](segments.md) e [medidas](measures.md) com base em várias fontes de dados que não são mais isoladas.

[!INCLUDE [footer-include](includes/footer-banner.md)]
