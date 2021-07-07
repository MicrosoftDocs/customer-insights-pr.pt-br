---
title: Integrar dados da web de insights de participação com insights de público-alvo
description: Use informações da web sobre clientes, desde de insights de participação até insights de público-alvo.
ms.date: 06/24/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 76a53a897e90152707a7c1255ed5ed93a5f3b5a0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305004"
---
# <a name="integrate-web-data-from-engagement-insights-with-audience-insights"></a>Integrar dados da web de insights de participação com insights de público-alvo

Os clientes costumam fazer suas transações diárias online usando sites. O recurso de insights de engajamento (versão preliminar) no Dynamics 365 Customer Insights é uma solução prática para integrar dados da Web como uma fonte. Além de dados transacionais, demográficos ou comportamentais, é possível ver atividades na web em perfis de clientes unificados. Podemos usar esses perfis para obter mais insights, como segmentos, medidas ou previsões para ativação de público-alvo.

Este artigo descreve as etapas para trazer os dados de atividade da web de seus clientes de insights de participação para o ambiente de insights de público-alvo existente.

Neste exemplo, usamos um ambiente que contém perfis de clientes unificados. Os perfis foram unificados com fontes de pesquisas, vendas de varejo e um sistema de tíquetes. As atividades relacionadas dos clientes também são mostradas. 

Agora queremos saber se um cliente acessa nossas propriedades da web e entende suas atividades. As atividades incluem, por exemplo, sites acessados ou páginas de produto exibidas por meio de um link recebido por email.

## <a name="prerequisites"></a>Pré-requisitos

Para integrar dados de insights de participação, alguns pré-requisitos precisam ser atendidos: 

- Integre o SDK de insights de participação ao site. Para obter mais informações, consulte [Visão geral dos recursos de desenvolvedor](../engagement-insights/developer-resources.md).
- Para exportar eventos Web dos insights de engajamento, é necessário ter acesso a uma conta do Azure Data Lake Storage que será usada para ingerir os dados dos eventos Web nos insights sobre público-alvo. Para obter mais informações, consulte [Exportar eventos](../engagement-insights/export-events.md).

## <a name="configure-refined-events-in-engagement-insights"></a>Configurar eventos refinados em insights de participação

Após um administrador instrumentar um site com o SDK de insights sobre engajamento, os *eventos base* são coletados quando um usuário visualiza um site ou clica em algum lugar. Os eventos base tendem a conter vários detalhes. Dependendo do caso de uso, você precisa somente de um subconjunto dos dados em um evento de base. Os insights de participação permitem criar *Eventos refinados* que contêm somente as propriedades de um evento base selecionado.     

Para obter mais informações, consulte [Criar e modificar eventos refinados](../engagement-insights/refined-events.md).

Considerações ao criar eventos refinados: 

- Forneça um nome significativo para o evento refinado. Ele será usado como o nome de uma atividade nos insights sobre público-alvo.
- Selecione pelo menos as seguintes propriedades para criar uma atividade em insights de público-alvo: 
    - Signal.Action.Name – Indica os detalhes da atividade.
    - Signal.User.Id – Usado para mapear com o ID do cliente.
    - Signal.View.Uri – Usado como endereço da Web como base para segmentos ou medidas.
    - Signal.Export.Id – Usado como chave primária para eventos.
    - Signal.Timestamp - Determina a data e a hora da atividade.

Selecione os filtros para focar nos eventos e nas páginas importantes para o caso de uso. Neste exemplo, usaremos o nome da ação "Promoção de email".

## <a name="export-the-refined-web-events"></a>Exportar os eventos da Web refinados 

Após definir o evento refinado, você precisa configurar a exportação dos dados do evento para o Azure Data Lake Storage, o que pode ser definido como uma fonte de dados para ingestão nos insights sobre público-alvo. As exportações acontecem constantemente à medida que os eventos fluem da propriedade da web.

Para obter mais informações, consulte [Exportar eventos](../engagement-insights/export-events.md).

## <a name="ingest-event-data-to-audience-insights"></a>Ingerir dados de evento para insights de público-alvo

Agora que você definiu o evento refinado e configurou a exportação, prosseguiremos para a ingestão de dados para insights de público-alvo. É necessário criar uma fonte de dados baseada em uma pasta do Common Data Model. Insira os detalhes da conta de armazenamento para a qual exporta os eventos. No arquivo *default.cdm.json*, selecione o evento refinado a ser ingerido e crie a entidade nos insights de público-alvo.

Para mais informações, [Conectar a uma pasta do Common Data Model usando uma conta do Azure Data Lake](connect-common-data-model.md).


## <a name="relate-refined-event-data-as-an-activity-of-a-customer-profile"></a>Relacionar dados de eventos refinados como atividade de um perfil de cliente

Depois de concluir a ingestão da entidade, você pode configurar a atividade para o perfil do cliente.

Para obter mais informações, consulte [Atividades do cliente](activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Página Atividades com painel Editar atividade e campos preenchidos.":::

Configurar a nova atividade com o seguinte mapeamento: 

- **Chave primária**: Signal.Export.Id, um ID exclusivo disponível para cada registro de evento nos insights sobre engajamento. Esta propriedade é gerada automaticamente.

- **Timestamp**: Signal.Timestamp na propriedade do evento.

- **Event**: Signal.Name, o nome do evento que você deseja acompanhar.

- **Endereço da Web**: Signal.View.Uri referente ao URI da página que criou o evento.

- **Detalhes**: Signal.Action.Name para representar as informações para associar ao evento. A propriedade selecionada neste caso indica que o evento é para promoção de email.

- **Tipo de atividade**: neste exemplo, escolhemos o tipo de atividade existente WebLog. Esta seleção é uma opção de filtro útil para executar modelos de previsão ou criar segmentos baseados neste tipo de atividade.

- **Configurar relacionamento**: esta configuração importante vincula a atividade aos perfis de cliente existentes. **Signal.User.Id** é o identificador configurado no SDK a ser coletado e que se relaciona à ID de usuário em outras fontes de dados configuradas nos insights de público-alvo. Neste exemplo, configuramos o relacionamento entre Signal.User.Id e RetailCustomers:CustomerRetailId, que é a chave primária que foi identificada na etapa de mapeamento do processo de unificação de dados.

Depois de processar as atividades, você pode revisar os registros do cliente e abrir um cartão do cliente para ver as atividades de insights de participação na linha do tempo. 

> [!TIP]
> Para encontrar um ID de cliente que tem uma atividade de insights sobre engajamento, acesse **Entidades** e visualize os dados da entidade UnifiedActivity. ActivityTypeDisplay = WebLog contém a atividade de insights sobre engajamento configurada no exemplo acima. Copie a ID do cliente para um desses registros e para essa ID na página **Clientes**.

## <a name="next-steps"></a>Próximas etapas

Agora é possível criar [segmentos](segments.md), [medidas](measures.md) e [previsões](predictions.md) para criar uma conexão significativa com seus clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
