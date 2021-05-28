---
title: Entidades e conjuntos de dados
description: Exiba os dados na página Entidades.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: f81128183b6e20e1078ad38c42c771d343909270
ms.sourcegitcommit: c1841ab91fbef9ead9db0f63fbc669cc3af80c12
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/17/2021
ms.locfileid: "6049380"
---
# <a name="entities-in-audience-insights"></a>Entidades em insights de público-alvo

Após [configurar suas fontes de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos. As entidades são consideradas conjuntos de dados. Vários recursos do Dynamics 365 Customer Insights são criados com base nessas entidades. Analisá-los de perto pode ajudá-lo a validar a saída desses recursos.

A página **Entidades** lista as entidades e tem várias colunas:

- **Nome** : O nome da sua entidade de dados. Se você vir um símbolo de aviso próximo ao nome de uma entidade, significa que os dados dessa entidade não foram carregados com êxito.
- **Fonte**: O tipo de fontes de dados que ingeriu a entidade
- **Criada por**: Nome da pessoa que criou a entidade
- **Criada**: Data e hora de criação da entidade
- **Atualizada por**: Nome da pessoa que atualizou a entidade
- **Ultima atualização**: Data e hora da última atualização da entidade
- **Última atualização**: Data e hora da última atualização de dados

## <a name="exploring-a-specific-entitys-data"></a>Explorando dados de uma entidade específica

Selecione uma entidade para explorar os diferentes campos e registros incluídos nessa entidade.

> [!div class="mx-imgBorder"]
> ![Selecionar uma entidade](media/data-manager-entities-data.png "Selecionar uma entidade")

- A guia **Dados** mostra uma tabela que lista detalhes sobre registros individuais da entidade.

> [!div class="mx-imgBorder"]
> ![Tabela de campos](media/data-manager-entities-fields.PNG "Tabela de campos")

- A guia **Atributos** vem selecionada por padrão e mostra uma tabela para revisar os detalhes da entidade selecionada, como nomes de campo, tipos de dados e tipos. A coluna **Tipo** mostra os tipos associados de Common Data Model que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos usuários. Esses são tipos semânticos que podem diferir dos tipos de dados dos atributos - por exemplo, o campo *Email* abaixo tem um tipo de dados *Texto*, mas seu tipo de Common Data Model (semântico) pode ser *Email* ou *Endereço de E-mail*.

> [!NOTE]
> Ambas as tabelas mostram apenas uma amostra dos dados da sua entidade. Para visualizar o conjunto completo de dados, vá para a página **Fontes de dados**, selecione uma entidade, selecione **Editar** e, em seguida, visualize os dados dessa entidade com o editor Power Query, conforme explicado em [Fontes de dados](data-sources.md).

Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características importantes dos dados, como nulos, valores ausentes, valores exclusivos, contagens e distribuições, conforme aplicável a seus dados.

Selecione o ícone do gráfico para ver o resumo dos dados.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumo](media/data-manager-entities-summary.png "Tabela de resumo de dados")

### <a name="next-step"></a>Próxima etapa

Veja o tópico [Unificar](data-unification.md) para saber como *mapear*, *corresponder* e *mesclar* os dados ingeridos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
