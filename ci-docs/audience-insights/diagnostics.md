---
title: Auditar o Dynamics 365 Customer Insights com o Azure Monitor
description: Saiba como enviar logs para o Microsoft Azure Monitor.
ms.date: 12/14/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: article
author: brndkfr
ms.author: bkief
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 18fc072d129be6b4fc5470b1057f592dc2638216
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8523654"
---
# <a name="log-forwarding-in-dynamics-365-customer-insights-with-azure-monitor-preview"></a>Encaminhamento de logs no Dynamics 365 Customer Insights com o Azure Monitor (Versão preliminar)

O Dynamics 365 Customer Insights fornece uma integração direta com o Azure Monitor. Os logs de recursos do Azure Monitor permitem monitorar e enviar logs para o [Armazenamento do Azure](https://azure.microsoft.com/services/storage/), o [Azure Log Analytics](/azure/azure-monitor/logs/log-analytics-overview), ou transmiti-los para os [Hubs de Eventos do Azure](https://azure.microsoft.com/services/event-hubs/).

O Customer Insights envia os seguintes logs de eventos:

- **Eventos de Auditoria**
  - **APIEvent** - permite o controle de alterações feito por meio da interface de usuário do Dynamics 365 Customer Insights.
- **Eventos Operacionais**
  - **WorkflowEvent** - o Workflow permite configurar [Fontes de Dados](data-sources.md), [unificar](data-unification.md), [enriquecer](enrichment-hub.md) e, por fim, [exportar](export-destinations.md) dados para outros sistemas. Todas essas etapas podem ser executadas individualmente (por exemplo, acionar uma única exportação) ou orquestradas (por exemplo, atualização de dados de fontes de dados que acionam o processo de unificação que atrairá enriquecimentos adicionais e, após a conclusão, exportará os dados para outro sistema). Para obter mais detalhes, consulte o [Esquema WorkflowEvent](#workflow-event-schema).
  - **APIEvent** - todas as chamadas à API para a instância dos clientes no Dynamics 365 Customer Insights. Para obter mais detalhes, consulte o [Esquema APIEvent](#api-event-schema).

## <a name="set-up-the-diagnostic-settings"></a>Definir as configurações de diagnóstico

### <a name="prerequisites"></a>Pré-requisitos

Para configurar o diagnóstico no Customer Insights, os seguintes pré-requisitos devem ser atendidos:

- Você deve ter uma [Assinatura do Azure](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/) ativa.
- Você deve ter permissões de [Administrador](permissions.md#admin) no Customer Insights.
- Você deve ter as funções **Colaborador** e **Administrador de Acesso de Usuário** no recurso de destino no Azure. O recurso pode ser uma conta do Armazenamento do Azure, um Hub de Eventos do Azure ou um workspace do Azure Log Analytics. Para obter mais informações, consulte [Adicionar ou remover atribuições de função do Azure usando o portal do Azure](/azure/role-based-access-control/role-assignments-portal).
- Você deve atender aos [Requisitos de destino](/azure/azure-monitor/platform/diagnostic-settings#destination-requirements) para Armazenamento do Azure, Hub de Eventos do Azure ou Azure Log Analytics.
- Você deve ter pelo menos a função **Leitor** no grupo de recursos ao qual o recurso pertence.

### <a name="set-up-diagnostics-with-azure-monitor"></a>Configurar o diagnóstico com o Azure Monitor

1. No Customer Insights, selecione **Sistema** > **Diagnóstico** para ver os destinos de diagnóstico configurados nesta instância.

1. Selecione **Adicionar destino**.

   > [!div class="mx-imgBorder"]
   > ![Conexão de diagnóstico](media/diagnostics-pane.png "Conexão de diagnóstico")

1. Forneça um nome no campo **Nome do destino de diagnóstico**.

1. Escolha o **Locatário** da assinatura do Azure com o recurso de destino e selecione **Entrar**.

1. Selecione o **Tipo de recurso** (Conta de armazenamento, Hub de Eventos ou análise de logs).

1. Selecione a **Assinatura** do recurso de destino.

1. Selecione o **Grupo de recursos** do recurso de destino.

1. Selecione o **Recurso**.

1. Confirme a declaração **Conformidade e privacidade dos dados**.

1. Selecione **Conectar-se ao sistema** para se conectar ao recurso de destino. Os logs começam a aparecer no destino após 15 minutos, se a API estiver em uso e gerar eventos.

### <a name="remove-a-destination"></a>Remover um destino

1. Vá para **Sistema** > **Diagnóstico**.

1. Selecione o destino de diagnóstico na lista.

1. Na coluna **Ações**, selecione o ícone **Excluir**.

1. Confirme a exclusão para interromper o encaminhamento de logs. O recurso na assinatura do Azure não será excluído. Você pode selecionar o link na coluna **Ações** para abrir o portal do Azure para o recurso selecionado e excluí-lo lá.

## <a name="log-categories-and-event-schemas"></a>Categorias de logs e esquemas de eventos

Atualmente, há suporte para [eventos de API](apis.md) e eventos de fluxo de trabalho, e as seguintes categorias e esquemas se aplicam.
O esquema de log segue o [esquema comum do Azure Monitor](/azure/azure-monitor/platform/resource-logs-schema#top-level-common-schema).

### <a name="categories"></a>Categorias

O Customer Insights fornece duas categorias:

- **Eventos de auditoria**: [eventos de API](#api-event-schema) para rastrear as alterações de configuração no serviço. As operações `POST|PUT|DELETE|PATCH` entram nesta categoria.
- **Eventos operacionais**: [eventos de API](#api-event-schema) ou [eventos de fluxo de trabalho](#workflow-event-schema) gerados durante o uso do serviço.  Por exemplo, solicitações `GET` ou os eventos de execução de um fluxo de trabalho.

## <a name="configuration-on-the-destination-resource"></a>Configuração no recurso de destino

Com base na sua escolha no tipo de recurso, as seguintes etapas serão aplicadas automaticamente:

### <a name="storage-account"></a>Storage account

A entidade de serviço do Customer Insights obtém a permissão **Colaborador da Conta de Armazenamento** no recurso selecionado e cria dois contêineres no namespace selecionado:

- `insight-logs-audit` que contém **eventos de auditoria**
- `insight-logs-operational` que contém **eventos operacionais**

### <a name="event-hub"></a>Hub de Eventos

A entidade de serviço do Customer Insights obtém a permissão **Proprietário dos Dados dos Hubs de Eventos do Azure** no recurso e criará dois Hubs de Eventos no namespace selecionado:

- `insight-logs-audit` que contém **eventos de auditoria**
- `insight-logs-operational` que contém **eventos operacionais**

### <a name="log-analytics"></a>Log Analytics

A entidade de serviço do Customer Insights obtém a permissão **Colaborador do Log Analytics** no recurso. Os logs estarão disponíveis em **Logs** > **Tabelas** > **Gerenciamento de Log** no workspace do Log Analytics selecionado. Expanda a solução **Gerenciamento de Log** e localize as tabelas `CIEventsAudit` e `CIEventsOperational`.

- `CIEventsAudit` que contém **eventos de auditoria**
- `CIEventsOperational` que contém **eventos operacionais**

Na janela **Consultas**, expanda a solução **Auditoria** e localize as consultas de exemplo fornecidas ao pesquisar `CIEvents`.

## <a name="event-schemas"></a>Esquemas de eventos

Os eventos de API e os eventos de fluxo de trabalho têm uma estrutura comum e detalhes em que diferem, consulte [Esquema de eventos de API](#api-event-schema) ou [Esquema de eventos de fluxo de trabalho](#workflow-event-schema).

### <a name="api-event-schema"></a>Esquema de eventos de API

| Campo             | DataType  | Obrigatório/Opcional | Description       | Exemplo        |
| ----------------- | --------- | ----------------- | --------------------- | ------------------------ |
| `time`            | Carimbo de data/hora | Obrigatória          | Carimbo de data/hora do evento (UTC)       | `2020-09-08T09:48:14.8050869Z`         |
| `resourceId`      | String    | Obrigatória          | ResourceId da instância que emitiu o evento         | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX`  |
| `operationName`   | String    | Obrigatória          | Nome da operação representada por este evento.                                                                                                                | `Workflows.GetWorkFlowStatusAsync`                                                                                                                                       |
| `category`        | String    | Obrigatória          | Categoria de log do evento. Tanto `Operational` ou `Audit`. Todas as Solicitações HTTP POST/PUT/PATCH/DELETE são marcadas com `Audit`, todo o resto com `Operational` | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resultType`      | String    | Obrigatória          | Status do evento. `Success`, `ClientError`, `Failure`                                                                                                        |                                                                                                                                                                          |
| `resultSignature` | String    | Opcional          | Status do resultado do evento. Se a operação corresponder a uma chamada à API REST, é o código de status HTTP.        | `200`             |
| `durationMs`      | Longo      | Opcional          | Duração da operação em milissegundos.     | `133`     |
| `callerIpAddress` | String    | Opcional          | Endereço IP do chamador, se a operação corresponder a uma chamada à API proveniente de um endereço IP disponível publicamente.                                                 | `144.318.99.233`         |
| `identity`        | String    | Opcional          | Objeto JSON que descreve a identidade do usuário ou aplicativo que realizou a operação.       | Consulte a seção [Identidade](#identity-schema).     |  
| `properties`      | String    | Opcional          | Objeto JSON com mais propriedades para a categoria particular de eventos.      | Consulte a seção [Propriedades](#api-properties-schema).    |
| `level`           | String    | Obrigatória          | Nível de gravidade do evento.    | `Informational`, `Warning`, `Error` ou `Critical`.           |
| `uri`             | String    | Opcional          | URI de solicitação absoluto.    |               |

#### <a name="identity-schema"></a>Esquema de identidades

O objeto JSON `identity` tem a estrutura a seguir

```json
{
  "Authorization" : {
    "UserRole": "Admin",
    "RequiredRoles": [
      "Contributor",
      "Viewer"
      ]
    },
  "Claims" {
    "claimNameX" : "claimValueX",
    "claimNameY" : "claimValueY"
   }
}  
```

| Campo                         | Description                                                                                                                          |
| ----------------------------- | ------------------------------------------------------------------------------------------------------------------------------------ |
| `Authorization.UserRole`      | Função atribuída ao usuário ou aplicativo. Para obter mais informações, consulte [permissões de usuário](permissions.md).                                     |
| `Authorization.RequiredRoles` | Funções necessárias para realizar a operação. A função `Admin` tem permissão para realizar todas as operações.                                                    |
| `Claims`                      | Declarações do Token Web JSON (JWT) do usuário ou aplicativo. As propriedades de declaração variam de acordo com a organização e a configuração do Azure Active Directory. |

#### <a name="api-properties-schema"></a>Esquema de propriedades de API

Os [eventos de API](apis.md) têm as seguintes propriedades.

| Campo                        | Description                                                                                                            |
| ---------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `properties.eventType`       | Sempre `ApiEvent`, marcando o evento de log como evento de API.                                                                 |
| `properties.userAgent`       | Agente do navegador enviando a solicitação ou `unknown`.                                                                        |
| `properties.method`          | Método HTTP: `GET/POST/PUT/PATCH/HEAD`.                                                                                |
| `properties.path`            | Caminho relativo da solicitação.                                                                                          |
| `properties.origin`          | URI indicando de onde vem uma busca ou `unknown`.                                                                  |
| `properties.operationStatus` | `Success` para Código de status HTTP < 400 <br> `ClientError` para Código de status HTTP < 500 <br> `Error` para Status HTTP >= 500 |
| `properties.tenantId`        | ID da Organização                                                                                                        |
| `properties.tenantName`      | Nome da organização.                                                                                              |
| `properties.callerObjectId`  | ObjectId do Azure Active Directory do chamador.                                                                         |
| `properties.instanceId`      | `instanceId` do Customer Insights                                                                                         |

### <a name="workflow-event-schema"></a>Esquema de eventos de fluxo de trabalho

O fluxo de trabalho contém várias etapas. [Ingerir fontes de dados](data-sources.md), [unificar](data-unification.md), [enriquecer](enrichment-hub.md) e [exportar](export-destinations.md) dados. Todas essas etapas podem ser executadas individualmente ou orquestradas com os processos a seguir. 

#### <a name="operation-types"></a>Tipos de operação

| OperationType     | Agrupar                                     |
| ----------------- | ----------------------------------------- |
| Ingestão         | [Fontes de dados](data-sources.md)           |
| DataPreparation   | [Fontes de dados](data-sources.md)           |
| Mapear               | [Unificação de dados](data-unification.md)   |
| Corresponder             | [Unificação de dados](data-unification.md)   |
| Mesclagem             | [Unificação de dados](data-unification.md)   |
| ProfileStore      | [Perfis do cliente](customer-profiles.md) |
| Pesquisa            | [Perfis do cliente](customer-profiles.md) |
| Atividade          | [Atividades](activities.md)                  |
| AttributeMeasures | [Segmentos e Medidas](segments.md)      |
| EntityMeasures    | [Segmentos e Medidas](segments.md)      |
| Medidas          | [Segmentos e Medidas](segments.md)      |
| Segmentação      | [Segmentos e Medidas](segments.md)      |
| Enriquecimento        | [Enriquecimento](enrichment-hub.md)                                          |
| Inteligência      | [Previsões](predictions-overview.md)                                          |
| AiBuilder         | [Previsões](predictions-overview.md)                                          |
| Insights          | [Previsões](predictions-overview.md)                                          |
| Export            | [Exportações](export-destinations.md)                                          |
| ModelManagement   | [Previsões](custom-models.md)                                           |
| Relação      | [Unificação de dados](relationships.md)                                           |

#### <a name="field-description"></a>Descrição do campo

| Campo           | DataType  | Obrigatório/Opcional | Description                                                                                                                                                   | Exemplo                                                                                                                                                                  |
| --------------- | --------- | ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| `time`          | Carimbo de data/hora | Obrigatória          | Carimbo de data/hora do evento (UTC).                                                                                                                                 | `2020-09-08T09:48:14.8050869Z`                                                                                                                                           |
| `resourceId`    | String    | Obrigatória          | ResourceId da instância que emitiu o evento.                                                                                                            | `/SUBSCRIPTIONS/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX/RESOURCEGROUPS/<RESOURCEGROUPNAME>/`<br>`PROVIDERS/MICROSOFT.D365CUSTOMERINSIGHTS/`<br>`INSTANCES/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXX` |
| `operationName` | String    | Obrigatória          | Nome da operação representada por este evento. `{OperationType}.[WorkFlow|Task][Started|Completed]`. Consulte [Tipos de Operação](#operation-types) para referência. | `Segmentation.WorkflowStarted`,<br> `Segmentation.TaskStarted`, <br> `Segmentation.TaskCompleted`, <br> `Segmentation.WorkflowCompleted`                                 |
| `category`      | String    | Obrigatória          | Categoria de log do evento. Sempre `Operational` para eventos de fluxo de trabalho                                                                                           | `Operational`                                                                                                                                                            | 
| `resultType`    | String    | Obrigatória          | Status do evento. `Running`, `Skipped`, `Successful`, `Failure`                                                                                            |                                                                                                                                                                          |
| `durationMs`    | Longo      | Opcional          | Duração da operação em milissegundos.                                                                                                                    | `133`                                                                                                                                                                    |
| `properties`    | String    | Opcional          | Objeto JSON com mais propriedades para a categoria particular de eventos.                                                                                        | Consulte a subseção [Propriedades do Fluxo de Trabalho](#workflow-properties-schema)                                                                                                       |
| `level`         | String    | Obrigatória          | Nível de gravidade do evento.                                                                                                                                  | `Informational`, `Warning` ou `Error`                                                                                                                                   |
|                 |

#### <a name="workflow-properties-schema"></a>Esquema de propriedades do fluxo de trabalho

Os eventos de fluxo de trabalho têm as seguintes propriedades.

| Campo              | Workflow | Tarefa | Description            |
| ------------------------------- | -------- | ---- | ----------- |
| `properties.eventType`                       | Sim      | Sim  | Sempre `WorkflowEvent`, marcando o evento como evento de fluxo de trabalho.                                                                                                                                                                                                |
| `properties.workflowJobId`                   | Sim      | Sim  | Identificador da execução do fluxo de trabalho. Todos os eventos de fluxo de trabalho e tarefa na execução do fluxo de trabalho têm a mesma `workflowJobId`.                                                                                                                                   |
| `properties.operationType`                   | Sim      | Sim  | Identificador da operação, consulte [Tipos de operação](#operation-types).                                                                                                                                                                               |
| `properties.tasksCount`                      | Sim      | No   | Somente fluxo de trabalho. Número de tarefas acionadas pelo fluxo de trabalho.                                                                                                                                                                                                       |
| `properties.submittedBy`                     | Sim      | No   | Opcional. Somente eventos de fluxo de trabalho. A [objectId do usuário](/azure/marketplace/find-tenant-object-id#find-user-object-id) do Azure Active Directory que acionou o fluxo de trabalho, consulte também `properties.workflowSubmissionKind`.                                   |
| `properties.workflowType`                    | Sim      | No   | Atualização `full` ou `incremental`.                                                                                                                                                                                                                            |
| `properties.workflowSubmissionKind`          | Sim      | No   | `OnDemand` ou `Scheduled`.                                                                                                                                                                                                                                  |
| `properties.workflowStatus`                  | Sim      | No   | `Running` ou  `Successful`.                                                                                                                                                                                                                                 |
| `properties.startTimestamp`                  | Sim      | Sim  | Carimbo de data/hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.endTimestamp`                    | Sim      | Sim  | Carimbo de data/hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.submittedTimestamp`              | Sim      | Sim  | Carimbo de data/hora UTC`yyyy-MM-ddThh:mm:ss.SSSSSZ`                                                                                                                                                                                                                  |
| `properties.instanceId`                      | Sim      | Sim  | `instanceId` do Customer Insights                                                                                                                                                                                                                              |  
| `properties.identifier`                      | No       | Sim  | - Para OperationType = `Export`, o identificador é o guid da configuração de exportação. <br> - Para OperationType = `Enrichment`, é o guid do enriquecimento <br> - Para OperationType `Measures` e `Segmentation`, o identificador é o nome da entidade. |
| `properties.friendlyName`                    | No       | Sim  | Nome amigável da exportação ou entidade que é processada.                                                                                                                                                                                           |
| `properties.error`                           | No       | Sim  | Opcional. Mensagem de erro com mais detalhes.                                                                                                                                                                                                                  |
| `properties.additionalInfo.Kind`             | No       | Sim  | Opcional. Somente para OperationType `Export`. Identifica o tipo da exportação. Para obter mais informações, consulte [Visão geral dos destinos de exportação](export-destinations.md).                                                                                          |
| `properties.additionalInfo.AffectedEntities` | No       | Sim  | Opcional. Somente para OperationType `Export`. Contém uma lista de entidades configuradas na exportação.                                                                                                                                                            |
| `properties.additionalInfo.MessageCode`      | No       | Sim  | Opcional. Somente para OperationType `Export`. Mensagem detalhada da exportação.                                                                                                                                                                                 |
| `properties.additionalInfo.entityCount`      | No       | Sim  | Opcional. Somente para OperationType `Segmentation`. Indica o número total de membros do segmento.                                                                                                                                                    |
