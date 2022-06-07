---
title: Segmentos no Customer Insights
description: Visão geral dos segmentos e como criá-los e gerenciá-los.
ms.date: 05/20/2022
ms.subservice: audience-insights
ms.topic: overview
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-customers-page
- ci-enrichment-details
- ci-segments
- ci-segment-details
- customerInsights
ms.openlocfilehash: d616ec8273115203dddb59334a348c66e72fa678
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800728"
---
# <a name="segments-overview"></a>Visão geral dos segmentos

Os segmentos permitem agrupar seus clientes com base em atributos demográficos, transacionais ou comportamentais. Você pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para atingir suas metas de negócios.

Os perfis de clientes que correspondem aos filtros de uma definição de segmento são chamados de *membros* de um segmento. Alguns [limites de serviço](/dynamics365/customer-insights/service-limits) se aplicam.

## <a name="create-a-new-segment"></a>Criar um novo segmento

Há várias maneiras de criar um novo segmento: 

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

- Segmento complexo com construtor de segmentos: [Construa o nosso próprio](segment-builder.md#create-a-new-segment) 
- Segmentos simples com um operador: [Segmento rápido](segment-builder.md#quick-segments) 
- Forma de encontrar clientes semelhantes com tecnologia de IA: [Clientes semelhantes](find-similar-customer-segments.md) 
- Sugestões com IA com base em medidas ou atributos [Segmentos sugeridos para melhorar as medidas](suggested-segments.md) 
- Sugestões baseadas em atividades: [Segmentos sugeridos com base na atividade do cliente](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

- Segmento complexo com construtor de segmentos: [Construa o nosso próprio](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Gerenciar segmentos existentes

Acesse a página **Segmentos** para exibir todos os seus segmentos salvos e gerenciá-los.

Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selecionado com a lista suspensa de opções e opções disponíveis." lightbox="media/segments-selected-segment.png":::

As seguintes ações estão disponíveis quando você seleciona um segmento:

- **Exibir** os detalhes do segmento, incluindo a tendência de contagem de membros, uma visualização dos membros do segmento.
- **Baixar** a lista de membros como um arquivo .CSV.
- **Editar** o segmento para alterar suas propriedades.
- **Criar duplicidade** de um segmento. Você pode editar suas propriedades imediatamente ou salvar a duplicata.
- **Atualizar** o segmento para incluir os dados mais recentes.
- **Ativar** ou **desativar** o segmento. Para segmentos inativos, a definição do segmento existe, mas ainda não contém nenhum cliente. Um segmento ativo procura clientes que correspondam à definição do segmento. Se uma [atualização programada](system.md#schedule-tab) estiver configurada, os segmentos inativos terão o **Status** listado como **Ignorado**, indicando que uma atualização nem mesmo foi tentada. Quando um segmento inativo for ativado, ele será atualizado e incluído nas atualizações agendadas.
  Como alternativa, você pode usar a funcionalidade **Agendar mais tarde** na lista suspensa **Ativar/desativar** para especificar data e hora futuras para a ativação e desativação de um segmento específico.
- **[Encontre clientes semelhantes](find-similar-customer-segments.md)** no segmento.
- **Renomear** o segmento.
- **Marcar** para [gerenciar as marcas](work-with-tags-columns.md#manage-tags) para o segmento.
- **Baixar** a lista de membros como um arquivo .CSV.
- **Gerenciar as exportações** para ver o segmento relacionado às exportações e gerenciá-las. [Saiba mais sobre as exportações.](export-destinations.md)
- **Excluir** o segmento.
- **Colunas** para [personalizar as colunas](work-with-tags-columns.md#customize-columns) que são exibidas.
- **Filtro** para [filtrar as marcas](work-with-tags-columns.md#filter-on-tags).
- **Pesquisar nome** para pesquisar pelo nome do segmento.

## <a name="refresh-segments"></a>Atualizar segmentos

Você pode atualizar todos os segmentos de uma vez, selecionando **Atualizar tudo** na página **Segmentos** ou você pode atualizar um ou vários segmentos ao selecioná-los e escolher **Atualizar** nas opções. Como alternativa, você pode configurar uma atualização recorrente em **Admin** > **Sistema** > **Agendar**. Quando uma atualização recorrente é configurada, as seguintes regras se aplicam:

- Todos os segmentos com o tipo **Dinâmico** ou **Expansão** serão atualizados automaticamente conforme a cadência definida. Quando a atualização estiver concluída, o **Status** indica se houve algum problema na atualização do segmento. A informação **Última atualização** mostra um carimbo de data/hora da última atualização bem-sucedida. Se ocorrer um erro, selecione-o para ver detalhes sobre o que aconteceu.
- Segmentos com o tipo **Estático** *não* serão atualizados automaticamente. A informação **Última atualização** mostra um carimbo de data/hora da última vez que os segmentos estáticos foram executados ou atualizados manualmente.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Você pode exportar um segmento da página de segmentos ou da [página de exportações](export-destinations.md). 

1. Vá para a página **Segmentos**.

1. Selecione as reticências verticais (&vellip;) do segmento que você deseja exportar.

1. Selecione **Gerenciar exportações** na lista suspensa de ações.

1. A página **Exportações (versão preliminar) para segmento** é aberta. Você pode ver todas as exportações configuradas agrupadas contendo o segmento atual ou não.

   1. Para adicionar o segmento selecionado a uma exportação, use a opção **Editar** a respectiva exportação para selecionar o segmento correspondente e, em seguida, salve. Em ambientes para clientes individuais, você pode selecionar a exportação na lista e selecionar **Adicionar segmento** para alcançar o mesmo resultado.

   1. Para criar uma exportação com o segmento selecionado, selecione **Adicionar exportação**. Para obter mais informações sobre a criação de exportações, consulte [Configurar uma nova exportação](export-destinations.md#set-up-a-new-export).

1. Selecione **Voltar** para retornar à página principal dos segmentos.

## <a name="track-usage-of-a-segment"></a>Acompanhar o uso de um segmento

Se você usa segmentos em aplicativos, que são baseados na mesma organização do Microsoft Dataverse que está conectada ao Customer Insights, você pode acompanhar o uso de um segmento. Para [Segmentos do Customer Insights usados nas jornadas do cliente do Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), o sistema informa sobre o uso desse segmento.

Ao editar um segmento que está sendo usado no ambiente do Customer Insights, ou em um jornada do cliente em Marketing, um banner no [criador de segmentos](segment-builder.md) informa sobre as dependências. Você pode inspecionar os detalhes da dependência diretamente do banner ou selecionando **Uso** no criador de segmentos.

O painel **Uso do segmento** mostra os detalhes sobre o uso deste segmento em aplicativos baseados no Dataverse. Para segmentos usados em jornadas do cliente, você encontrará um link para inspecionar a jornada no Marketing onde esse segmento é usado. Se você tiver permissões para acessar o aplicativo Marketing, poderá acessar mais detalhes lá.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Painel lateral com detalhes do uso do segmento no criador de segmentos.":::

O sistema informa sobre o uso de um segmento rastreado quando você tenta excluí-lo. Se o segmento que você está prestes a excluir for usado em um jornada do cliente no Marketing, essa jornada será interrompida para todos os usuários do segmento. Se a jornada fizer parte de uma campanha de marketing, a exclusão afetará a própria campanha. No entanto, você ainda pode excluir o segmento, apesar dos avisos.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Caixa de diálogo para confirmar a exclusão do segmento quando ele é usado em um aplicativo do Dataverse.":::

### <a name="supported-apps"></a>Aplicativos compatíveis

O uso é atualmente rastreado nos seguintes aplicativos baseados no Dataverse:

- [Jornadas dos clientes no Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

## <a name="view-processing-history-and-segment-members"></a>Exibir histórico de processamento e membros do segmento

Você pode ver dados consolidados sobre um segmento revisando seus detalhes.

Na página **Segmentos**, selecione o segmento que deseja revisar.

A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros. Passe o mouse sobre os pontos de dados para ver a contagem de membros em uma data específica.

Você pode atualizar o período da visualização.

> [!div class="mx-imgBorder"]
> ![Intervalo de tempo do segmento.](media/segment-time-range.png "Intervalo de tempo do segmento")

A parte inferior contém uma lista dos membros do segmento.

> [!NOTE]
> Os campos que aparecem nesta lista são baseados nos atributos das entidades do seu segmento.
>
>A lista é uma visualização dos membros do segmento correspondentes e mostra os 100 primeiros registros do seu segmento, para que você possa avaliá-lo rapidamente e revisar suas definições, se necessário. Para ver todos os registros correspondentes, você precisa [exportar o segmento](export-destinations.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
