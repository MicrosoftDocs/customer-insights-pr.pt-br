---
title: Relacionamentos entre entidades e caminhos de entidade
description: Crie e gerencie relacionamentos entre entidades de várias fontes de dados.
ms.date: 04/14/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 292da986faa7f62d8aa73ed7214075612178e2e1
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269853"
---
# <a name="relationships-between-entities"></a>Relacionamentos entre entidades

Os relacionamentos ajudam a conectar entidades e gerar um gráfico de seus dados quando as entidades compartilham um identificador comum (chave estrangeira) que pode ser referenciado de uma entidade para outra. As entidades conectadas permitem definir segmentos e medidas com base em várias fontes de dados.

Há dois tipos de relacionamentos. Relacionamentos de sistema não editáveis, criados automaticamente, e relacionamentos personalizados, criados e configurados pelos usuários.

Durante os processos de correspondência e mesclagem, os relacionamentos do sistema são criados nos bastidores com base na correspondência inteligente. Esses relacionamentos ajudam a relacionar os registros do Perfil do Cliente com os registros de outras entidades correspondentes. O diagrama a seguir ilustra a criação de três relacionamentos do sistema quando a entidade do cliente é correspondida com outras entidades para produzir a entidade final do Perfil do Cliente.

> [!div class="mx-imgBorder"]
> ![Criação de relacionamento](media/relationships-entities-merge.png "Criação de relacionamento")

- **O Relacionamento *CustomerToContact*** foi criado entre a entidade Cliente e a entidade Contato. A entidade Cliente obtém o campo-chave **Contact_contactId** para relacionar-se com o campo-chave da entidade de Contato **contactId**.
- **O Relacionamento *CustomerToContact*** foi criado entre a entidade Cliente e a entidade Conta. A entidade Cliente obtém o campo-chave **Account_accountId** para relacionar-se com o campo-chave da entidade de Conta **accountId**.
- **O Relacionamento *CustomerToWebAccount*** foi criado entre a entidade Cliente e a entidade WebAccount. A entidade Customer obtém o campo-chave **WebAccount_webaccountId** para relacionar-se com o campo-chave da entidade de WebAccount **webaccountId**.

## <a name="create-a-relationship"></a>Criar um relacionamento

Defina relacionamentos personalizados na página **Relacionamentos**. Cada relacionamento consiste em uma entidade de Origem (a entidade que detém a chave estrangeira) e uma entidade de Destino (a entidade para a qual a chave estrangeira da entidade de origem aponta).

1. Nas informações de público-alvo, vá para **Dados** > **Relacionamentos**.

2. Selecione **Novo relacionamento**.

3. No painel **Adicionar relacionamento**, forneça as seguintes informações:

   > [!div class="mx-imgBorder"]
   > ![Digite os detalhes do relacionamento](media/relationships-add.png "Digite os detalhes do relacionamento")

   - **Nome do relacionamento** : Nome que reflete o objetivo do relacionamento (por exemplo, **AccountWebLogs**).
   - **Descrição**: Descrição do relacionamento.
   - **Entidade de origem**: Selecione a entidade que é usada como fonte no relacionamento (por exemplo, WebLog).
   - **Cardinalidade**: Selecione a cardinalidade dos registros da entidade de origem. Por exemplo, "muitos" significa que vários registros do Weblog estão relacionados a uma WebAccount.
   - **Campo da chave de origem**: Representa o campo de chave estrangeira na entidade de origem. Por exemplo, o WebLog tem o campo de chave estrangeira **accountId**.
   - **Entidade de destino**: Selecione a entidade que é usada como destino no relacionamento (por exemplo, WebAccount).
   - **Cardinalidade de destino**: Selecione a cardinalidade dos registros da entidade de destino. Por exemplo, "uma" significa que vários registros do Weblog estão relacionados a uma WebAccount.
   - **Campo-chave de destino**: Este campo representa o campo-chave da entidade de destino. Por exemplo, o WebAccount tem o campo de chave **accountId**.

> [!NOTE]
> Somente relacionamentos muitos para um e um para um são suportados. Os relacionamentos muitos-para-muitos podem ser criados usando dois relacionamentos muitos-para-um e uma entidade de link (uma entidade usada para conectar a entidade de origem e a entidade de destino).

## <a name="delete-a-relationship"></a>Excluir um relacionamento

1. Nas informações de público-alvo, vá para **Dados** > **Relacionamentos**.

2. Marque as caixas de seleção para os relacionamentos que você deseja excluir.

3. Selecione **Excluir** na parte superior da tabela **Relacionamentos**.

4. Confirme a exclusão.

## <a name="next-step"></a>Próxima etapa

Os relacionamentos do sistema e personalizados são usados para criar segmentos com base em várias fontes de dados que não são mais isoladas. Para obter mais informações, consulte [Segmentos](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]