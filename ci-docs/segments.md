---
title: Visão geral dos segmentos
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
ms.openlocfilehash: 4bcfbb50b893ca7e6ec4607d3c156a3c6979f775
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170667"
---
# <a name="segments-overview"></a>Visão geral dos segmentos

Os segmentos permitem agrupar seus clientes com base em atributos demográficos, transacionais ou comportamentais. Você pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para atingir suas metas de negócios.

Os perfis de cliente que corresponderem aos filtros de uma definição de segmento são chamados de *membros* de um segmento. Alguns [limites de serviço](/dynamics365/customer-insights/service-limits) se aplicam.

## <a name="create-a-segment"></a>Criar um segmento

Escolha como criar um segmento com base em seu público-alvo.

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

- Segmentos complexos com o construtor de segmentos: [Criar seu próprio](segment-builder.md)
- Segmentos simples com um operador: [Segmento rápido](segment-quick.md)
- Maneira com tecnologia de IA de encontrar clientes semelhantes: [Clientes semelhantes](find-similar-customer-segments.md)
- Sugestões com tecnologia de IA baseadas em medidas ou atributos: [Segmentos sugeridos baseados em medidas](suggested-segments.md)
- Sugestões baseadas em atividades: [Segmentos sugeridos com base na atividade do cliente](suggested-segments-activity.md)

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

- Segmentos simples ou complexos com o construtor de segmentos: [Criar seu próprio](segment-builder.md)

---

## <a name="manage-existing-segments"></a>Gerenciar segmentos existentes

Acesse a página **Segmentos** para exibir os segmentos que criou, seus status e estado, o número de membros e a última vez em que os dados foram atualizados. Você pode classificar os segmentos por qualquer coluna ou usar a caixa de pesquisa para encontrar o segmento que deseja gerenciar.

Selecione um segmento para exibir as ações disponíveis.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selecionado com a lista suspensa de opções e opções disponíveis." lightbox="media/segments-selected-segment.png":::

- [**Exibir**](#view-segment-details) os detalhes do segmento, incluindo a tendência de contagem de membros e uma visualização dos membros do segmento.
- **Baixar** a lista de membros como um arquivo .CSV.
- **Editar** o segmento para alterar suas propriedades.
- **Criar duplicidade** de um segmento. Você pode editar suas propriedades imediatamente ou salvar a duplicata.
- [**Atualizar**](#refresh-segments) o segmento para incluir os dados mais recentes.
- **Ativar** ou **desativar** o segmento. Os segmentos inativos não serão atualizados durante uma [atualização agendada](system.md#schedule-tab) e terão o **Status** listado como **Ignorado**, indicando que nem mesmo houve tentativa de atualização. Os segmentos ativos serão atualizados com base em seu tipo: estático ou dinâmico.
- **Torne estático** ou **Torne dinâmico** o tipo de segmento. Os segmentos estáticos devem ser atualizados manualmente. Os segmentos dinâmicos são atualizados automaticamente durante as atualizações do sistema.
- [**Encontre clientes semelhantes**](find-similar-customer-segments.md) no segmento.
- **Renomear** o segmento.
- **Marcar** para [gerenciar as marcas](work-with-tags-columns.md#manage-tags) para o segmento.
- [**Gerenciar exportações**](#export-segments) para ver os segmentos relacionados a exportações e gerenciá-los. [Saiba mais sobre as exportações.](export-destinations.md)
- **Excluir** o segmento.
- **Colunas** para [personalizar as colunas](work-with-tags-columns.md#customize-columns) que são exibidas.
- **Filtro** para [filtrar as marcas](work-with-tags-columns.md#filter-on-tags).
- **Pesquisar nome** para pesquisar pelo nome do segmento.

## <a name="view-segment-details"></a>Exibir detalhes do segmento

Na página **Segmentos**, selecione um segmento para exibir o histórico de processamento e seus membros.

A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros. Passe o mouse sobre os pontos de dados para ver a contagem de membros em uma data específica. Altere o período da visualização.

:::image type="content" source="media/segment-time-range.png" alt-text="Intervalo de tempo do segmento.":::

A parte inferior contém uma lista dos membros do segmento.

> [!NOTE]
> Os campos que aparecem nesta lista são baseados nos atributos das entidades do seu segmento.
>
>A lista é uma visualização dos membros do segmento correspondentes e mostra os 100 primeiros registros do seu segmento, para que você possa avaliá-lo rapidamente e revisar suas definições, se necessário. Para ver todos os registros correspondentes, [exporte o segmento](export-destinations.md).

## <a name="refresh-segments"></a>Atualizar segmentos

Os segmentos podem ser atualizados em uma agenda automática ou ser atualizados manualmente sob demanda. Para atualizar manualmente um ou mais segmentos, selecione-os e escolha **Atualizar**.

Para [agendar uma atualização automática](system.md#schedule-tab), acesse **Administrador** > **Sistema** > **Agenda**. As regras abaixo se aplicam:

- Todos os segmentos com o tipo **Dinâmico** ou **Expansão** serão atualizados automaticamente conforme a cadência definida. Após a conclusão da atualização, o **Status** indicará se houve algum problema na atualização do segmento. A informação **Última atualização** mostra um carimbo de data/hora da última atualização bem-sucedida. Se ocorrer um erro, selecione-o para ver detalhes sobre o que aconteceu.
- Segmentos com o tipo **Estático** *não* serão atualizados automaticamente. **Última atualização** mostra um carimbo de data/hora da última vez que o segmento estático foi executado ou atualizado manualmente.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Exporte segmentos para outros aplicativos para uso adicional dos dados. Exporte um segmento da página de segmentos ou da [página de exportações](export-destinations.md).

1. Acesse a página **Segmentos** e selecione o segmento que deseja exportar.

1. Selecione **Gerenciar exportações**. A página **Exportações (versão preliminar) para segmento** é aberta. Exiba todas as exportações configuradas agrupadas se elas contiverem o segmento atual ou não.

   1. Para adicionar o segmento selecionado a uma exportação, use a opção **Editar** a respectiva exportação para selecionar o segmento correspondente e, em seguida, salve. Em ambientes para clientes individuais, selecione a exportação na lista e selecione **Adicionar segmento** para alcançar o mesmo resultado.

   1. Para criar uma exportação com o segmento selecionado, selecione **Adicionar exportação**. Para obter mais informações sobre a criação de exportações, consulte [Configurar uma nova exportação](export-destinations.md#set-up-a-new-export).

1. Selecione **Voltar** para retornar à página principal dos segmentos.

## <a name="track-usage-of-a-segment"></a>Acompanhar o uso de um segmento

Se usar segmentos em aplicativos que são baseados na mesma organização do Microsoft Dataverse que está conectada com o Customer Insights, você poderá rastrear o uso de um segmento. Para [Segmentos do Customer Insights usados nas jornadas do cliente do Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), o sistema informa sobre o uso desse segmento.

Ao editar um segmento que está sendo usado no ambiente do Customer Insights, ou em um jornada do cliente em Marketing, um banner no [criador de segmentos](segment-builder.md) informa sobre as dependências. Inspecione os detalhes da dependência diretamente na faixa ou selecionando **Uso** no construtor de segmentos.

O painel **Uso do segmento** mostra os detalhes sobre o uso deste segmento em aplicativos baseados no Dataverse. Para segmentos usados em jornadas do cliente, você encontrará um link para inspecionar a jornada no Marketing onde esse segmento é usado. Se tiver permissões para acessar o aplicativo Marketing, exiba mais detalhes nele.

:::image type="content" source="media/segment-usage-pane.png" alt-text="Painel lateral com detalhes do uso do segmento no criador de segmentos.":::

O sistema informa sobre o uso de um segmento rastreado quando você tenta excluí-lo. Se o segmento que você está prestes a excluir for usado em um jornada do cliente no Marketing, essa jornada será interrompida para todos os usuários do segmento. Se a jornada fizer parte de uma campanha de marketing, a exclusão afetará a própria campanha. No entanto, você ainda pode excluir o segmento, apesar dos avisos.

:::image type="content" source="media/segment-usage-delete.png" alt-text="Caixa de diálogo para confirmar a exclusão do segmento quando ele é usado em um aplicativo do Dataverse.":::

### <a name="supported-apps"></a>Aplicativos compatíveis

O uso é atualmente rastreado nos seguintes aplicativos baseados no Dataverse:

- [Jornadas dos clientes no Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile)

[!INCLUDE [footer-include](includes/footer-banner.md)]
