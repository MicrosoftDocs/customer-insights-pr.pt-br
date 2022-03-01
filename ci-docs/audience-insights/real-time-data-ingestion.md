---
title: Ingestão de dados em tempo real e limitações
description: Informações gerais sobre recursos em tempo real em percepções de público.
ms.date: 10/27/2020
ms.reviewer: nikeller
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: b00a72e6a67e33c8e70ccc6139c5e62020f9d3e1
ms.sourcegitcommit: b50c754481d0af6d0cf4b550775d7b31d95846ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/06/2020
ms.locfileid: "4689161"
---
# <a name="real-time-data-ingestion-preview"></a>Ingestão de dados em tempo real (versão preliminar)

A funcionalidade quase em tempo real permite ver, em segundos, as últimas interações que seus clientes tiveram com seus produtos ou serviços.

[Atualizações programadas](system.md#schedule-tab) incluem um grande número de registros e várias operações complexas. Primeiro, os dados são extraídos de fonte de dados. Em seguida, os dados são unificados e depois enriquecidos com informações adicionais. Cada execução desse processo pode levar de minutos a horas.

A funcionalidade em tempo real fornece dados imediatamente para consumo, até que a atualização programada subsequente extraia esses dados de fonte de dados.

As atualizações em tempo real têm um horário de expiração após o qual não substituem mais o valor da fonte de dados:

- As atualizações de perfil serão mantidas por 4 horas
- As atividades serão mantidas por 30 dias

Esses valores são parâmetros de chamada à API que você pode alterar. Eles visam garantir que seus dados de origem continuem sendo sua fonte de referência. Se você deseja que as atualizações em tempo real sejam incluídas por mais tempo, você precisa adicioná-las a um fonte de dados para que sejam retiradas durante a próxima atualização programada.

## <a name="real-time-update-of-the-unified-customer-profile-fields"></a>Atualização em tempo real dos campos do perfil de cliente unificado

Os perfis atualizados serão exibidos na visualização do cartão do cliente ou em qualquer outra visualização em alguns segundos.

Como as operações em tempo real ocorrem após a unificação de dados, elas se aplicam apenas aos perfis de cliente unificados. Consequentemente, as alterações de perfil em tempo real não atualizarão medidas, associação de segmentos ou aprimoramentos.

### <a name="limitations"></a>Limitações

- Perfis de clientes podem ser atualizados, mas não criados ou excluídos.
- Exportar atualizações em tempo real para sistemas externos, como o Power BI, não é possível no momento.

## <a name="real-time-creation-of-activities"></a>Criação de atividades em tempo real

A API em tempo real permite publicar uma nova atividade de seu sistema de origem (um registro de origem individual) para um perfil de cliente unificado. A nova atividade estará disponível como uma atividade unificada na linha do tempo desse perfil de cliente unificado em segundos. Você pode ver a linha do tempo na visualização do cartão do cliente ou qualquer outra integração de linha do tempo que você configurou.

> [!NOTE]
>
> - Atividades são imutáveis. Elas não mudam depois de criadas.
> - Atualmente, segmentos e medidas não são atualizados com base na nova atividade.
> - As atividades adicionadas apenas por meio da API em tempo real não fazem parte das exportações e não serão exibidas no Power BI.

Existem duas maneiras de se conectar à API em tempo real:

- [indiretamente](#connect-via-the-dynamics-365-customer-insights-connector), usando o [conector do Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/)
- [diretamente](#connect-directly-to-the-real-time-api), com código

As duas maneiras compartilham os seguintes pré-requisitos:

- Um ambiente do Customer Insights
- Perfis de cliente unificados
- Atividades configuradas e executadas
- Permissões de Colaborador ou Administrador para autenticar sua conta

## <a name="connect-via-the-dynamics-365-customer-insights-connector"></a>Conectar-se por meio do conector do Dynamics 365 Customer Insights

A API em tempo real pode ingerir dados de um conector dedicado do Power Platform, o [conector do Dynamics 365 Customer Insights](https://docs.microsoft.com/connectors/customerinsights/), sem a necessidade de escrever e implantar nenhum código.    
O conector pode executar as mesmas ações em tempo real que a API. Você precisa de uma licença válida para conectores premium. Para obter mais informações, consulte [Perguntas frequentes sobre licenciamento do Power Apps e do Power Automate](https://docs.microsoft.com/power-platform/admin/powerapps-flow-licensing-faq).

- Power Platform [Power Apps e/ou Power Automate](https://docs.microsoft.com/connectors/)
- [Aplicativos Lógicos](https://docs.microsoft.com/azure/connectors/apis-list) do Azure

Para obter detalhes sobre a criação de fluxos, consulte a [documentação do Power Automate](https://docs.microsoft.com/power-automate/).

## <a name="connect-directly-to-the-real-time-api"></a>Conectar-se diretamente à API em tempo real

Você pode usar os recursos em tempo real criando seu próprio pipeline e conectando-se diretamente à API em tempo real.    
Você pode postar uma atividade no formato do seu sistema de origem ou no formato UnifiedActivity. Obtenha o formato fazendo uma chamada à API para /api/instances/{instanceId}/manage/entities/UnifiedActivity.

Os detalhes desta API, incluindo parâmetros e respostas, podem ser encontrados na seção **EntityData** na referência [APIs do Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Para obter mais informações, consulte [Trabalhar com APIs do Customer Insights](apis.md).

## <a name="understand-your-real-time-usage-with-telemetry"></a>Entenda seu uso em tempo real com telemetria

Obtenha uma visão geral do volume de solicitações para a API em tempo real e informações sobre os problemas que o sistema pode encontrar. Você pode [acessar a telemetria em tempo real](system.md#api-usage-tab) indo para **Admin** > **Sistema** > **Uso da API**. Na tabela **Operações**, as linhas para operações da API que usam os métodos em tempo real contêm um botão para visualizar o uso da API em tempo real. O botão é visualizado com um símbolo binocular. Selecione o botão para abrir um painel lateral contendo detalhes de uso para o uso da API em tempo real no ambiente atual.

Use o seletor **Agrupar por** para escolher a melhor forma de apresentar suas interações em tempo real em uma linha do tempo que varia das últimas 24 horas aos últimos 30 dias. Você pode agrupar os dados pelo método API, nome qualificado da entidade (entidade ingerida), criado por (fonte do evento), resultado (êxito ou falha) ou códigos de erro. Os dados estão disponíveis como um gráfico de histórico e como uma tabela.
