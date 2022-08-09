---
title: Conectar-se a uma fonte de dados do Power Query (contém vídeo)
description: Faça a ingestão de dados por meio de um conector do Power Query (contém vídeo).
ms.date: 07/26/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: matgos
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: 7af51ed04fbd28149ea501c58e6fe71b5fa6d4b6
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207031"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectar-se a uma fonte de dados do Power Query

O Power Query oferece um amplo conjunto de conectores para ingerir dados. A maioria desses conectores são suportados por Dynamics 365 Customer Insights.

A adição de fontes de dados com base nos conectores do Power Query geralmente segue as etapas descritas nesta seção. No entanto, dependendo do conector que você usa, são necessárias informações diferentes. Para saber mais, consulte a documentação sobre conectores individuais na [Referência de conectores do Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Criar uma nova fonte de dados

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Selecione **Microsoft Power Query**.

1. Forneça um **Nome** e uma **Descrição** opcional para o fonte de dados e selecione **Avançar**.

1. Escolha um dos [conectores disponíveis](#available-power-query-data-sources). Neste exemplo, selecionamos o conector **Text/CSV**.

1. Insira os detalhes necessários nas **Configurações de conexão** para o conector selecionado e selecione **Avançar** para ver uma prévia dos dados.

1. Selecione **Transformar dados**.

1. A caixa de diálogo **Power Query – Editar consultas** permite que você revise e refine os dados. As entidades que os sistemas identificaram na sua fonte de dados selecionada aparecem no painel esquerdo.

   :::image type="content" source="media/data-manager-configure-edit-queries.png" alt-text="Caixa de diálogo Editar consultas":::

1. Você também poderá transformar seus dados. Selecione uma entidade para editar ou transformar. Use as opções na janela do Power Query para aplicar transformações. Cada transformação está listada em **Etapas aplicadas**. O Power Query fornece várias opções de [transformação pré-criada](/power-query/power-query-what-is-power-query#transformations).

   É recomendável usar as seguintes transformações:

   - Se você estiver ingerindo dados de um arquivo CSV, a primeira linha geralmente contém cabeçalhos. Acesse **Transformar** e selecione **Usar a primeira linha como cabeçalho**.
   - Certifique-se de que o tipo de dados esteja definido de forma adequada. Por exemplo, no caso de campos de data, selecione um tipo de data.

1. Para adicionar outras entidades à fonte de dados na caixa de diálogo **Editar consultas**, acesse **Página Inicial** e selecione **Obter dados**. Repita as etapas 5 a 10 até adicionar todas as entidades a esta fonte de dados. Se você possui um banco de dados que inclui vários conjuntos de dados, cada conjunto de dados é sua própria entidade.

1. Selecione **Salvar**. A página **Fontes de dados** abre mostrando a nova fonte de dados no status **Atualizando**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página [**Entidades**](entities.md).

> [!CAUTION]
> Uma fonte de dados baseada no Power Query cria um [fluxo de dados no Dataverse](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365). Não altere o nome de um fluxo de dados no centro de administração do Power Platform que seja usado no Customer Insights. Renomear um fluxo de dados causa problemas nas referências entre a fonte de dados do Customer Insights e o fluxo de dados do Dataverse.

### <a name="available-power-query-data-sources"></a>Fontes de dados do Power Query disponíveis

Consulte a [Referência de conectores do Power Query](/power-query/connectors/) para obter uma lista de conectores que você pode usar para importar dados para o Customer Insights.

Conectores com uma marca de seleção na coluna **Customer Insights (Fluxos de dados)** estão disponíveis para criar novas fontes de dados com base no Power Query. Revise a documentação de um conector específico para saber mais sobre seus pré-requisitos, [limitações de consulta](/power-query/power-query-online-limits) e outros detalhes.

## <a name="add-data-from-on-premises-data-sources"></a>Adicionar dados de fontes de dados locais

Há suporte à ingestão de dados de fontes de dados locais com base em fluxos de trabalho do Microsoft Power Platform (PPDFs). Você pode habilitar fluxos de dados no Customer Insights [fornecendo a URL do ambiente do Microsoft Dataverse](create-environment.md) ao configurar o ambiente.

As fontes de dados que são criadas após associar um ambiente do Dataverse ao Customer Insights usam [fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por padrão. Os fluxos de dados oferecem suporte à conectividade local usando gateway de dados. Você pode remover e recriar fontes de dados que existiam antes de um ambiente do Dataverse ser associado [usando gateways de dados locais](/data-integration/gateway/service-gateway-app).

Os gateways de dados de um ambiente existente do Power BI ou do Power Apps ficarão visíveis e você poderá reutilizá-los no Customer Insights. A página de fontes de dados mostra links para acessar o ambiente do Microsoft Power Platform onde você pode exibir e configurar gateways locais de dados.

> [!IMPORTANT]
> Verifique se os seus gateways estão atualizados com a versão mais recente. Você pode instalar uma atualização e reconfigurar um gateway em um prompt mostrado diretamente na tela do gateway ou [fazer download da versão mais recente](https://powerapps.microsoft.com/downloads/). Se você não usar a versão mais recente do gateway, a atualização do fluxo de dados vai falhar com mensagens de erro como **Não há suporte para a palavra-chave: propriedades de configuração. Nome do parâmetro: palavra-chave**.
>
> Os erros de gateways de dados local no Customer Insights geralmente são causados por problemas de configuração. Para obter mais informações sobre como solucionar problemas em gateways de dados, consulte [Solucionar problemas no gateway de dados local](/data-integration/gateway/service-gateway-tshoot).

## <a name="edit-power-query-data-sources"></a>Editar fonte de dados do Power Query

> [!NOTE]
> Talvez não seja possível fazer alterações nas fontes de dados que estão sendo usadas em um dos processos do aplicativo (segmentação ou unificação dedados, por exemplo).
>
> Na página **Configurações**, você pode acompanhar o andamento de cada um dos processos ativos. Quando um processo é concluído, você pode retornar à página **Fontes de Dados** e fazer suas alterações.

1. Acesse **Dados** > **Fontes de dados**.

1. Ao lado da fonte de dados que você deseja atualizar, selecione **Editar**

1. Aplique suas alterações e transformações na caixa de diálogo **Power Query – Editar consultas** conforme descrito na seção [Criar uma fonte de dados](#create-a-new-data-source).

1. Selecione **Salvar** para aplicar as alterações e voltar à página **Fontes de dados**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
