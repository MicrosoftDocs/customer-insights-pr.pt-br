---
ms.openlocfilehash: 1d79987893986148421c316193b27d268cfe0a0b
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755530"
---
Depois de ingerir os dados, inicie o processo de unificação de dados para criar um perfil de cliente unificado. Para obter mais informações, consulte [Unificação de dados](../data-unification.md).

### <a name="select-source-fields"></a>Selecionar campos de origem

1. Depois de ingerir os dados, mapeie os contatos dos dados de comércio eletrônico e de fidelidade para tipos de dados comuns. Acesse **Dados** > **Unificar**.

1. Selecione as entidades que representam o perfil do cliente – **eCommerceContacts** e **loyCustomers**.

   ![unifique as fontes de dados de comércio eletrônico e fidelidade.](../media/unify-ecommerce-loyalty.png)

1. Selecione **ContactId** como a chave primária para **eCommerceContacts** e **LoyaltyID** como a chave primária para **loyCustomers**.

1. Selecione **Avançar** Ignore registros duplicados e selecione **Avançar**.

### <a name="match-conditions"></a>Condições de correspondência

1. Escolha **eCommerceContacts : eCommerce** como a entidade principal e inclua todos os registros.

1. Escolha **loyCustomers : LoyaltyScheme** e inclua todos os registros.

1. Adicionar uma regra:
   - Selecione **FullName** para eCommerceContacts e loyCustomers.
   - Selecione **Tipo (telefone, nome, endereço, ...)** para **Normalizar**.
   - Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.
   - Insira **FullName, Email** para o nome.

1. Adicionar uma segunda condição para o endereço de email:
   - Selecione **Email** para eCommerceContacts e loyCustomers.
   - Deixe o campo Normalizar em branco.
   - Defina **Nível de precisão**: **Básico** e **Valor**: **Alto**.

   ![Regra de correspondência unificada para nome e email.](../media/unify-match-rule.png)

1. Selecione **Concluído**.

1. Selecione **Avançar**

### <a name="unify-fields"></a>Unificar campos

1. Renomeie a **ContactId** para a entidade **loyCustomers** como **ContactIdLOYALTY** para diferenciá-la das outras IDs ingeridas.

1. Selecione **Avançar** para revisar e, em seguida, selecione **Criar perfis de cliente**.
