---
title: Criar um link entre insights do público-alvo e insights de participação
description: Crie um link ativo entre insights do público-alvo e insights de participação para permitir o compartilhamento bidirecional de dados.
ms.date: 09/08/2021
ms.service: customer-insights
ms.topic: conceptual
author: mkisel
ms.author: mkisel
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 6aadd6b5018f63362f86c0e3e3ce085e94c47391
ms.sourcegitcommit: 5dd32dc2b18027cf2aa954356dded4bc6aab9801
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2022
ms.locfileid: "8116000"
---
# <a name="create-a-link-between-audience-insights-and-engagement-insights"></a>Criar um link entre insights do público-alvo e insights de participação

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

A integração entre insights de participação e insights do público-alvo vincula ambientes de ambas as funcionalidades e permite que dados sejam compartilhados de forma bidirecional entre si.

Use perfis e segmentos unificados de insights do público-alvo para obter mais opções de análise em insights de participação. Exporte eventos com um alto valor comercial a partir de insights de participação. Use esses eventos para adicionar dados a perfis unificados em insights do público-alvo.

## <a name="prerequisites"></a>Pré-requisitos

- Os perfis de insights do público-alvo devem ser armazenados em uma conta do Azure Data Lake Storage que você possui, ou em um data lake do [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro)&ndash; gerenciado. 
- Seu ambiente de insights do público-alvo deve ter um ambiente do Dataverse associado. Se esse ambiente também estiver usando o Dataverse para armazenamento de dados, certifique-se de verificar a opção **Habilitar compartilhamento de dados** em insights do público-alvo. Para mais informações, consulte [Crie e configure um ambiente em insights do público-alvo](../audience-insights/create-environment.md).
- Você precisa de permissões de administrador para os ambientes de insights de participação e do público-alvo.
- Os ambientes vinculados devem estar na mesma região geográfica.

> [!NOTE]
> - Se sua assinatura de insights do público-alvo for uma avaliação que usa um data lake gerenciado internamente por insights do público-alvo, fale com [pirequest@microsoft.com](mailto:pirequest@microsoft.com) para obter assistência. 
> - Se o ambiente de insights do público-alvo usar o seu próprio Azure Data Lake Storage para armazenar dados, você precisará adicionar uma entidade de serviço do Azure de insights de participação à sua conta de armazenamento. Para obter detalhes, acesse [Conecte-se a uma conta do Azure Data Lake Storage com uma entidade de serviço do Azure para insights do público-alvo](../audience-insights/connect-service-principal.md). 


## <a name="create-an-environment-link"></a>Criar um link do ambiente

Você pode criar um link do ambiente atualizando as configurações de **Administrador** > **Ambiente** em insights de participação.

**Para estabelecer um link ativo entre insights do público-alvo e insights de participação**

1. Na página **Administrador de ambiente**, selecione a guia **Vincular ambientes**.

    :::image type="content" source="media/integrate1.png" alt-text="Configurar um ambiente.":::

1. Selecione **Configurar ambiente** no canto superior esquerdo ou na parte inferior da tela.

     :::image type="content" source="media/integrate2.png" alt-text="Selecione um ambiente de insights do público-alvo.":::

1. Selecione um ambiente de insights do público-alvo e, depois, selecione **Avançar** para terminar. Agora você pode selecionar recursos opcionais para os ambientes vinculados.
 
## <a name="enable-audience-insights-unified-profiles-attributes-and-segments"></a>Habilite atributos e segmentos de perfis unificados de insights do público-alvo

Após vincular ambientes, você pode selecionar recursos opcionais para os ambientes vinculados. Esses recursos permitem atributos e segmentos de perfis unificados a partir de insights do público-alvo para análise interativa dos dados do cliente.

> [!IMPORTANT]
> Para que segmentos de insights do público-alvo apareçam em insights de participação, você deve primeiro [executar processos de mesclagem e downstream](../audience-insights/merge-entities.md). Os processos de downstream são importantes porque geram uma tabela única que prepara segmentos de insights do público-alvo a serem compartilhados com insights de participação. (Se uma atualização do sistema for agendada, ela incluirá automaticamente processos de downstream.)

**Para analisar dados da Web em insights de participação**

1. Na página **Administrador de ambiente**, ative a alternância **Compartilhe dados de insights do público-alvo com insights de participação** e selecione **Avançar**.

    :::image type="content" source="media/integrate4.png" alt-text="Selecionar recursos.":::

1. Selecione os atributos dos perfis unificados que se tornarão dimensões em insights de participação. (Nem todos os atributos são dimensões úteis. Por exemplo, não é provável que você precise de **Nome** ou **Sobrenome** como um atributo para análise de eventos do site.)

    :::image type="content" source="media/integrate5.png" alt-text="Coletar dimensões.":::

   >[!NOTE]
   > Todos os atributos de perfis de insights do público-alvo que representam identificadores (como **ID** e **ID alternativa**) são filtrados entre os atributos disponíveis e se tornam dimensões em insights de participação.

1. Ao terminar de selecionar os atributos, selecione **Avançar**.
1. Adicione usuários que podem exibir as dimensões e segmentos do perfil de insights do público-alvo em insights de participação.

    :::image type="content" source="media/integrate6.png" alt-text="Gerenciar o acesso a dados do cliente.":::

   > [!IMPORTANT]
   > Se você não adicionar usuários explicitamente nesta etapa, os dados serão ocultados de usuários em insights de participação.
   > Para que segmentos de insights do público-alvo apareçam em insights de participação, você deve primeiro [executar processos de mesclagem e downstream](../audience-insights/merge-entities.md). Os processos de downstream são importantes porque geram uma tabela única que prepara segmentos de insights do público-alvo a serem compartilhados com insights de participação. (Se uma atualização do sistema for agendada, ela incluirá automaticamente processos de downstream.)

1. Revise sua seleção e, depois, selecione **Concluir**.

    :::image type="content" source="media/integrate7.png" alt-text="Analisar configurações de dados do cliente.":::

## <a name="export-refined-events-to-audience-insights"></a>Exportar eventos refinados para insights do público-alvo

Depois de criar um link entre ambientes, você poderá exportar eventos refinados de insights de participação para insights do público-alvo e ingeri-los como uma nova fonte de dados. 

Para obter mais informações, acesse [Integrar dados da Web de insights de participação com insights do público-alvo](../audience-insights/integrate-engagement-insights.md).

<!--
## Share engagement insights refined events with audience insights

After you create a link between environments, a new option becomes available for you to share [refined events](refined-events.md) with audience insights.

Consider the following when creating refined events for audience insights: 

- Provide a meaningful name for the refined event. It will be used as an activity name in audience insights.
- Select at least the following properties to create an activity in audience insights: 
    - Signal.Action.Name indicates the activity details.
    - Signal.User.Id maps with the customer ID.
    - Signal.View.Uri is a web address as a basis for segments or measures.
    - Signal.Export.Id is a primary key for events.
    - Signal.Timestamp determines the date and time for the activity.

To share refined events:

1. From the engagement insights menu, select **Data** and then select the **Events** tab.
2. On the **Action** menu, select **Share as activity**.

    :::image type="content" source="media/integrate8.png" alt-text="Data shared events settings.":::

3. You can view and stop actively shared events on the **Export and Sharing** tab.
4. -- per Michael K, we need a mock here (Mukesh needs to update to reflect what happens in AUI once a user shares a refined event (i.e. no longer AUI, data wrangler needs to go discover data in the storage, the shared event is available as a DS and entity, correct?)

### Attach refined events shared as activities to unified profiles in audience insights

You can bring customer web activity data from engagement insights into audience insights. In addition to transactional, demographic, or behavioral data, you can view activities on the web in unified customer profiles. You can then use these profiles to get insights such as segments, measures, and predictions for audience activation.

Follow the steps in [data unification](../audience-insights/data-unification.md) to map, match, and merge website authentication information to unified profiles in audience insights.

You can also share refined events that are now available in audience insights, identified as data sources and entities. 

Next, you can relate event data from engagement insights as unified activities in customer profiles.

### Relate refined event data as an activity of a customer profile

After unifying the data, you can configure the activity for the customer profile. For more information, go to [Customer activities](../audience-insights/activities.md).

:::image type="content" source="media/web-event-activity.png" alt-text="Activities page with expanded Edit activity pane.":::

Next, configure the new activity by using mapping elements: 

- **Primary Key**: Signal.Export.Id, a unique ID that is available for every event record in engagement insights. This property is automatically generated.

- **Timestamp**: Signal.Timestamp in the event property.

- **Event**: Signal.Name, the event name that you want to track.

- **Web address**: Signal.View.Uri that refers to the URI of the page that created the event.

- **Details**: Signal.Action.Name to represent the information to associate with the event. The selected property in this case indicates that the event is for email promotion.

- **Activity type**: In this example, we choose the existing activity type WebLog. This selection is a useful filter option to run prediction models or create segments based on this activity type.

- **Set up relationship**: This important setting ties the activity to existing customer profiles. **Signal.User.Id** is the identifier configured in the SDK to be collected. It relates to the user ID in other data sources that are configured in audience insights. 

This example configures the relationship between Signal.User.Id and RetailCustomers:CustomerRetailId, which is the primary key that was identified in the map step of the data unification process.

After processing the activities, you can review customer records and open a customer card to see activities from engagement insights in the timeline. 

> [!TIP]
> To find a customer ID that has an engagement insights activity, go to **Entities** and preview the data for the UnifiedActivity entity. **ActivityTypeDisplay = WebLog** contains the engagement insights activity configured in the preceding example. Copy the customer ID for one of those records and search<!--note from editor: Edit okay? I couldn't quite follow this.-- > for that ID on the **Customers** page.

--> 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
