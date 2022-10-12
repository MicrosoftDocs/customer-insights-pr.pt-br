---
title: Entidades no Customer Insights
description: Exiba os dados na página Entidades.
ms.date: 08/04/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: e365945b27e7c985ca5371c6b72619610b6f3af1
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610084"
---
# <a name="entities-in-customer-insights"></a>Entidades no Customer Insights

Após [configurar suas fontes de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos. As entidades são consideradas conjuntos de dados. Vários recursos do Dynamics 365 Customer Insights são criados com base nessas entidades. Analisá-los de perto pode ajudá-lo a validar a saída desses recursos.

À medida que você trabalha no Customer Insights enriquecendo dados ou criando segmentos, medidas e atividades, as entidades criadas a partir dessas ações são exibidas na página **Entidades**.

## <a name="view-a-list-of-entities"></a>Exibir uma lista de entidades

Vá para **Dados** > **Entidades** para ver uma lista de entidades. As informações a seguir de cada entidade são exibidas.

- **Nome**: nome da entidade de dados. Se você vir um símbolo de aviso próximo ao nome de uma entidade, significa que os dados dessa entidade não foram carregados com êxito.
- **Fonte**: tipo da fonte de dados que ingeriu a entidade.
- **Atualização**: hora da última atualização da entidade.
- **Status**: detalhes sobre a última atualização da entidade.

## <a name="explore-a-specific-entitys-data"></a>Explorar dados de uma entidade específica

1. Vá para **Dados** > **Entidades**.
1. Selecione uma entidade para abrir a página de detalhes.  
1. Explore os diferentes campos e registros incluídos nessa entidade.

- A guia **Atributos** vem selecionada por padrão e mostra os detalhes da entidade selecionada, como nomes de campo, tipos de dados e tipos. A coluna **Tipo** mostra os tipos associados de Common Data Model que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos usuários. Esses tipos são tipos semânticos que podem ser diferentes dos tipos de dados dos atributos. Por exemplo, o campo *Email* abaixo tem o tipo de dados *Cadeia de caracteres*, mas seu tipo Common Data Model (semântico) pode ser *Email*, *EmailAddress* ou *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabela de campos.":::

   > [!NOTE]
   > Esta página mostra apenas um exemplo dos dados da sua entidade. Para exibir o conjunto de dados completo, acesse a página **Fontes de dados**, selecione uma entidade, selecione **Editar** e exiba os dados dessa entidade com o editor do Power Query, conforme explicado em [Fontes de dados](data-sources.md).

   Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características de dados importantes, como nulos, valores ausentes, valores exclusivos, contagens e distribuições, conforme aplicável a seus dados. Selecione o ícone do gráfico para ver o resumo dos dados.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabela de resumo de dados.":::

- A guia **Dados** mostra detalhes sobre registros individuais da entidade. Os detalhes listados dependem do tipo de dados da entidade.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Selecione uma entidade.":::

- A guia **Relatórios** (disponível para algumas entidades) permite visualizar dados criando um relatório que inclui estas colunas:

  - **Nome do relatório**: nome do relatório.
  - **Criação de**: nome da pessoa que criou a entidade.
  - **Criação**: data e hora da criação da entidade.
  - **Edição de**: nome da pessoa que modificou a entidade.
  - **Edição**: data e hora da modificação da entidade.

[!INCLUDE [footer-include](includes/footer-banner.md)]
