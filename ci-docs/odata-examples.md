---
title: Exemplos de consulta OData para APIs do Customer Insights
description: Exemplos comumente usados do Protocolo Open Data (OData) para consultar as APIs do Customer Insights a fim de revisar dados.
ms.date: 05/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 8843fc04e4e6eaba0019d932c54f62561ffbdb92
ms.sourcegitcommit: f3c12ad445d5f91a88f91a7bbc40790ebcfaa826
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2022
ms.locfileid: "9121548"
---
# <a name="odata-query-examples-for-customer-insights-apis"></a>Exemplos de consulta OData para APIs do Customer Insights

O Protocolo Open Data (OData) é um protocolo de acesso a dados baseado em protocolos importantes como HTTP. Ele usa metodologias comumente aceitas como REST para a Web. Há vários tipos de bibliotecas e ferramentas que podem ser usadas para consumir serviços OData.

Este artigo lista algumas consultas de exemplo solicitadas com frequência para ajudá-lo a criar suas próprias implementações com base nas [APIs do Customer Insights](apis.md).

Você precisa modificar os exemplos de consulta para fazê-los funcionar nos ambientes de destino: 

- {serviceRoot}: `https://api.ci.ai.dynamics.com/v1/instances/{instanceId}/data` onde a {instanceId} é o GUID do ambiente do Customer Insights que você deseja consultar. A [operação ListAllInstances](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) permite que você encontre a {InstanceId} à qual tem acesso.
- {CID}: GUID de um registro de cliente unificado. Exemplo: `ce759201f786d590bf2134bff576c369`.
- {AlternateKey}: identificador da chave primária de um registro de cliente em uma fonte de dados. Exemplo: `CNTID_1002`
- {DSname}: cadeia de caracteres com o nome da entidade de uma fonte de dados que é ingerida no Customer Insights. Exemplo: `Website_contacts`.
- {SegmentName}: cadeia de caracteres com o nome da entidade de saída de um segmento no Customer Insights. Exemplo: `Male_under_40`.

## <a name="customer"></a>Customer

A tabela a seguir contém um conjunto de consultas de exemplo para a entidade *Cliente*.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|ID de cliente única     | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'`          |  |
|Chave alternativa    | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} eq '{AlternateKey}'`         |  As chaves alternativas persistem na entidade de cliente unificado       |
|Select   | `{serviceRoot}/Customer?$select=CustomerId,FullName&$filter=customerid eq '1'`        |         |
|Em    | `{serviceRoot}/Customer?$filter=CustomerId in ('{CID1}',’{CID2}’)`        |         |
|Chave Alternativa + In   | `{serviceRoot}/Customer?$filter={DSname_EntityName_PrimaryKeyColumnName} in ('{AlternateKey}','{AlternateKey}')`         |         |
|Pesquisa  | `{serviceRoot}/Customer?$top=10&$skip=0&$search="string"`        |   Retorna os 10 principais resultados de uma cadeia de caracteres de pesquisa      |
|Associação ao segmento  | `{serviceRoot}/Customer?select=*&$filter=IsMemberOfSegment('{SegmentName}')&$top=10`     | Retorna um número predefinido de linhas da entidade de segmentação.      |
|Associação ao segmento para um cliente | `{serviceRoot}/Customer?$filter=CustomerId eq '{CID}'&IsMemberOfSegment('{SegmentName}')`     | Retorna o perfil do cliente se ele for um membro do determinado segmento     |

## <a name="unified-activity"></a>Atividade unificada

A tabela a seguir contém um conjunto de consultas de exemplo para a entidade *UnifiedActivity*.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Atividade de CID     | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}'`          | Lista as atividades de um perfil de cliente específico |
|Período da atividade    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityTime gt 2017-01-01T00:00:00.000Z and ActivityTime lt 2020-01-01T00:00:00.000Z`     |  Atividades de um perfil de cliente em um período       |
|Tipo de atividade    |   `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq '{CID}' and ActivityType eq '{ActivityName}'`        |         |
|Atividade por nome de exibição     | `{serviceRoot}/UnifiedActivity$filter=CustomerId eq ‘{CID}’ and ActivityTypeDisplay eq ‘{ActivityDisplayName}’`        | |
|Classificação de atividades    | `{serviceRoot}/UnifiedActivity?$filter=CustomerId eq ‘{CID}’ & $orderby=ActivityTime asc`     |  Classificar atividades em ordem crescente ou decrescente       |
|Atividade expandida da associação ao segmento  |   `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId eq '{CID}'`     |         |

## <a name="other-examples"></a>Outros exemplos

A tabela a seguir contém um conjunto de consultas de exemplo para outras entidades.

|Tipo de consulta |Exemplo  | Nota  |
|---------|---------|---------|
|Medidas de CID    | `{serviceRoot}/Customer_Measure?$filter=CustomerId eq '{CID}'`          |  |
|Marcas enriquecidas de CID    | `{serviceRoot}/BrandShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`  |       |
|Interesses enriquecidos de CID    |   `{serviceRoot}/InterestShareOfVoiceFromMicrosoft?$filter=CustomerId eq '{CID}'`       |         |
|Na Cláusula + Expandir     | `{serviceRoot}/Customer?$expand=UnifiedActivity,Customer_Measure&$filter=CustomerId in ('{CID}', '{CID}')`         | |

## <a name="not-supported-odata-queries"></a>Consultas OData não compatíveis

As seguintes consultas não são compatíveis com o Customer Insights:

- `$filter` em entidades de origem ingeridas. Você só pode executar consultas $filter em entidades do sistema criadas pelo Customer Insights.
- `$expand` a partir de uma consulta `$search`. Exemplo: `Customer?$expand=UnifiedActivity$top=10&$skip=0&$search="corey"`
- `$expand` a partir de `$select` se apenas um subconjunto de atributos for selecionado. Exemplo: `Customer?$select=CustomerId,FullName&$expand=UnifiedActivity&$filter=CustomerId eq '{CID}'`
- `$expand` marca enriquecida ou afinidades de interesse para um determinado cliente. Exemplo: `Customer?$expand=BrandShareOfVoiceFromMicrosoft&$filter=CustomerId eq '518291faaa12f6d853c417835d40eb10'`
- Consulte entidades de saída do modelo de previsão por meio de chave alternativa. Exemplo: `OOBModelOutputEntity?$filter=HotelCustomerID eq '{AK}'`
