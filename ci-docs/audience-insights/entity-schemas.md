---
title: Esquemas de entidade do Customer Insights no Common Data Model
description: Trabalhe com entidades no Common Data Model.
ms.date: 04/17/2020
ms.reviewer: mukeshpo
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 9e7a6e944d37d25f4c25846644278b39b3ddd08e
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269270"
---
# <a name="entity-schemas-in-common-data-model"></a>Esquemas de entidades no Common Data Model

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

O [Common Data Model](https://docs.microsoft.com/common-data-model/) é uma especificação declarativa e uma definição de entidades padrão que representam os conceitos e atividades comumente usados em uma variedade de aplicações de negócios e de produtividade. Este modelo está sendo estendido aos dados observacionais e analíticos. O Common Data Service oferece entidades de negócios bem definidas, modulares e extensíveis, como Conta, Unidade de Negócios, Ocorrência, Contato, Cliente Potencial, Oportunidade e Produto, bem como interações e relações entre fornecedores, trabalhadores e clientes, como atividades e contratos de nível de serviço. Qualquer pessoa pode desenvolver e estender definições do Common Data Model para capturar ideias adicionais específicas de negócios.

Esse é um modelo de dados compartilhado que permite que aplicativos e integradores de dados colaborem mais facilmente, fornecendo uma definição unificada de dados. O Common Data Model inclui um rico sistema de metadados com entidades, relacionamentos, hierarquias, características e muito mais. Ele tem sua origem nos aplicativos do Dynamics 365 e é um software livre no GitHub com mais de 260 entidades padrão. Um grande sistema de parceiros internos e externos contribui com conceitos específicos do setor para o Common Data Model.

Vários sistemas e plataformas implementam o Common Data Model hoje, incluindo fluxos de dados do Power BI e Serviços de Dados do Azure. Já tem suporte no Common Data Service, no Dynamics 365, no Power Apps, no Power BI e nos próximos serviços de dados do Azure, agregando valor diretamente ao [Open Data Initiative](https://www.microsoft.com/open-data-initiative).

## <a name="customer-insights-entity-schemas"></a>Esquemas de entidades do Customer Insights

Para estabelecer uma visão de 360 graus do cliente e disponibilizar modelos do Customer Insights no Common Data Model para extensibilidade, publicamos os seguintes esquemas de entidade:

| Entidade | Descrição |
|---------|---------|
|[Atividade do Cliente](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customeractivity) | Uma atividade executada por um usuário que tem valor observacional para os negócios. |
|[Perfil do Cliente](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile) | Uma pessoa ou organização que executou ou tem potencial para se envolver em atividades comerciais. |
|[Definição de Medida](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/measuredefinition) | Definição de KPIs particionados por zero ou mais dimensões (como Usuários Ativos Mensais, Gasto Total por Cliente, Custo Médio de Aquisição de Clientes) |
|[Segmento ](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segment) | Define um grupo de membros com características em comum. |
|[Membros dos Segmentos](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/segmentmembership) | Membros participantes de um determinado segmento. |

Para obter mais informações, consulte a documentação sobre os [Esquemas de entidades do Customer Insights no Common Data Model](https://docs.microsoft.com/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/overview).

## <a name="view-entities-using-the-common-data-model-entity-navigator"></a>Exibir entidades usando o Navegador de Entidades do Common Data Model

Você pode exibir entidades no [Navegador de Entidades do Common Data Model](https://microsoft.github.io/CDM/). Selecione o botão **Carregar do GitHub!** e vá até **foundationCommon** > **crmCommon** > **solutions** > **customerInsights**, onde você encontrará a lista de entidades do Customer Insights e suas definições.
> [!div class="mx-imgBorder"]
> ![Navegador de Entidades do CDM mostrando a entidade Atividade do Cliente](media/CDM-entity-navigator.png "Navegador de Entidades do CDM mostrando a entidade Atividade do Cliente")


[!INCLUDE[footer-include](../includes/footer-banner.md)]