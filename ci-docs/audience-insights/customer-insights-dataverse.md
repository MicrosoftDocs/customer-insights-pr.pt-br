---
title: Dados do Customer Insights no Microsoft Dataverse
description: Use entidades Customer Insights como tabelas no Microsoft Dataverse.
ms.date: 11/25/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 9f730f5856221592cddf34b714beeaca24c52130
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8355415"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabalhar com dados do Customer Insights no Microsoft Dataverse

O Customer Insights oferece a opção de disponibilizar entidades de saída no [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro.md). Essa integração permite o fácil compartilhamento de dados e o desenvolvimento personalizado por meio de uma abordagem de pouco código/nenhum código. As entidades de saída estarão disponíveis como tabelas no Dataverse. Essas tabelas permitem cenários como [fluxos de trabalho automatizados pelo Power Automate](/power-automate/getting-started), [aplicativos baseados em modelo](/powerapps/maker/model-driven-apps/) e [aplicativos de tela](/powerapps/maker/canvas-apps/) pelo Power Apps. Você pode usar os dados para qualquer outro aplicativo baseado em tabelas do Dataverse. A implementação atual oferece suporte principalmente a pesquisas em que os dados das entidades de insights de público-alvo disponíveis podem ser obtidos para uma determinada ID de cliente.

## <a name="attach-a-dataverse-environment-to-customer-insights"></a>Anexar um ambiente do Dataverse ao Customer Insights

**Organizações com ambientes existentes do Dataverse**

Organizações que já usam o Dataverse podem [usar um dos ambientes existentes do Dataverse](create-environment.md) quando um administrador configura insights de público-alvo. Ao fornecer a URL para o ambiente do Dataverse, ele estará vinculado ao seu novo ambiente de insights de público-alvo. Para garantir o melhor desempenho possível, os ambientes do Customer Insights e do Dataverse devem estar hospedados na mesma região.

**Nova organização**

Se criar uma nova organização ao configurar o Customer Insights, você obterá automaticamente um novo ambiente do Dataverse.

> [!NOTE]
> Se a organização já usa o Dataverse em seu locatário, é importante lembrar que a [criação do ambiente do Dataverse é controlada por um administrador](/power-platform/admin/control-environment-creation.md). Por exemplo, se você estiver configurando um novo ambiente de insights de público-alvo com sua conta organizacional e o administrador tiver desativado a criação de ambientes de avaliação do Dataverse para todos, exceto administradores, você não poderá criar um ambiente de avaliação.
> 
> Os ambientes de avaliação do Dataverse criados no Customer Insights têm 3 GB de armazenamento, que não contam na capacidade geral à qual o locatário tem direito. As assinaturas pagas têm no direito a 15 GB para banco de dados e 20 GB para armazenamento de arquivos Dataverse.

## <a name="output-entities"></a>Entidades de saída

Algumas entidades de saída de insights de público-alvo estão disponíveis como tabelas no Dataverse. As seções abaixo descrevem o esquema esperado dessas tabelas.

- [Perfil do Cliente](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecimento](#enrichment)
- [Previsão](#prediction)
- [Associação ao segmento](#segment-membership)


### <a name="customerprofile"></a>Perfil do Cliente

Esta tabela contém o perfil de cliente unificado do Customer Insights. O esquema para um perfil de cliente unificado depende das entidades e atributos usados no processo de mesclagem. Um esquema de perfil de cliente geralmente contém um subconjunto dos atributos da [Definição do Common Data Model do Perfil do Cliente](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

A tabela AlternateKey contém as chaves das entidades que participaram do processo de unificação.

|Column  |Digitar  |Descrição  |
|---------|---------|---------|
|DataSourceName    |Cadeia de Caracteres         | Nome da fonte de dados. Por exemplo: `datasource5`        |
|EntityName        | Cadeia de Caracteres        | Nome da entidade nos insights de público-alvo. Por exemplo: `contact1`        |
|AlternateValue    |Cadeia de Caracteres         |ID alternativa que é mapeada para a ID do cliente. Exemplo: `cntid_1078`         |
|KeyRing           | Texto com várias linhas        | Valor JSON  </br> Exemplo: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Cadeia de Caracteres        | ID do perfil de cliente unificado.         |
|AlternateKeyId     | GUID         |  GUID determinístico AlternateKey baseado em msdynci_identifier       |
|msdynci_identifier |   Cadeia de Caracteres      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta tabela contém atividades de usuários que estão disponíveis no Customer Insights.

| Column            | Digitar        | Descrição                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | Cadeia de Caracteres      | ID do Perfil do Cliente                                                                      |
| ActivityId        | Cadeia de Caracteres      | ID interna da atividade do cliente (chave primária)                                       |
| SourceEntityName  | Cadeia de Caracteres      | Nome da entidade de origem                                                                |
| SourceActivityId  | Cadeia de Caracteres      | Chave primária da entidade de origem                                                       |
| ActivityType      | Cadeia de Caracteres      | Tipo de atividade semântica ou nome da atividade personalizada                                        |
| ActivityTimeStamp | DATETIME    | Carimbo de data/hora da atividade                                                                      |
| Tratamento             | Cadeia de Caracteres      | Título ou nome da atividade                                                               |
| Descrição       | Cadeia de Caracteres      | Descrição da atividade                                                                     |
| URL               | Cadeia de Caracteres      | Link para uma URL externa específica à atividade                                         |
| SemanticData      | Cadeia de caracteres JSON | Inclui uma lista de pares de chave/valor para os campos de mapeamento semântico específicos ao tipo de atividade |
| RangeIndex        | Cadeia de Caracteres      | Carimbo de data/hora Unix usado para classificar a linha do tempo de atividades e as consultas de intervalo em vigor |
| mydynci_unifiedactivityid   | GUID | ID interna da atividade do cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta tabela contém os dados de saída de medidas baseadas em atributos do cliente.

| Column             | Digitar             | Descrição                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Cadeia de Caracteres           | ID do Perfil do cliente        |
| Medidas           | Cadeia de caracteres JSON      | Inclui uma lista de pares de chave/valor para o nome da medida e valores para o cliente fornecido | 
| msdynci_identifier | Cadeia de Caracteres           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID do Perfil do cliente |


### <a name="enrichment"></a>Enriquecimento

Esta tabela contém a saída do processo de enriquecimento.

| Column               | Digitar             |  Descrição                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Cadeia de Caracteres           | ID do Perfil do cliente                                 |
| EnrichmentProvider   | Cadeia de Caracteres           | Nome do provedor para o enriquecimento                                  |
| EnrichmentType       | Cadeia de Caracteres           | Tipo de enriquecimento                                      |
| Valores               | Cadeia de caracteres JSON      | Lista de atributos produzidos pelo processo de enriquecimento |
| msdynci_enrichmentid | GUID             | GUID determinístico gerado a partir de msdynci_identifier |
| msdynci_identifier   | Cadeia de Caracteres           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Previsão

Esta tabela contém a saída das previsões do modelo.

| Column               | Digitar        | Descrição                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | Cadeia de Caracteres      | ID do Perfil do Cliente                                  |
| ModelProvider        | Cadeia de Caracteres      | Nome do provedor do modelo                                      |
| Modelo                | Cadeia de Caracteres      | Nome do modelo                                                |
| Valores               | Cadeia de caracteres JSON | Lista de atributos produzidos pelo modelo |
| msdynci_predictionid | GUID        | GUID determinístico gerado a partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Associação ao segmento

Esta tabela contém informações de associação ao segmento de perfis do cliente.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID do Perfil do Cliente        |
| SegmentProvider      | String       | Aplicativo que publica os segmentos. Padrão: Insights de público-alvo         |
| SegmentMembershipType | String       | Tipo de cliente registrado por esta associação ao segmento. Oferece suporte a vários tipos, como Cliente, Contato ou Conta. Padrão: Cliente  |
| Segmentos       | Cadeia de caracteres JSON  | Lista de segmentos exclusivos dos quais o perfil do cliente é membro      |
| msdynci_identifier  | String   | Identificador exclusivo do registro da associação ao segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinístico gerado de `msdynci_identifier`          |
