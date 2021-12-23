---
title: Ingerir dados por meio de um conector do Power Query (Vídeo)
description: Conectores para fontes de dados com base no Power Query.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.openlocfilehash: 38c447d80a25feca087ca9f110278b8401423018
ms.sourcegitcommit: 12910882ca990ec0e890ed4deaf3dac7e01621e5
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2021
ms.locfileid: "7903826"
---
# <a name="connect-to-a-power-query-data-source"></a>Conectar-se à fonte de dados do Power Query

O Power Query oferece um amplo conjunto de conectores para ingerir dados. A maioria desses conectores são suportados por Dynamics 365 Customer Insights. 

A adição de fontes de dados com base nos conectores do Power Query geralmente segue as etapas descritas nesta seção. No entanto, dependendo do conector que você usa, são necessárias informações diferentes. Para saber mais, consulte a documentação sobre conectores individuais na [Referência do conector do Power Query](/power-query/connectors/).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN6EK]

## <a name="create-a-new-data-source"></a>Criar uma nova fonte de dados

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Selecione **Microsoft Power Query** e, em seguida, selecione **Avançar**.

1. Forneça um **Nome** para a fonte de dados e selecione **Avançar** para criar a fonte de dados.

1. Escolha um dos [conectores disponíveis](#available-power-query-data-sources). Neste exemplo, selecionamos o conector **Text/CSV**.

1. Insira os detalhes necessários nas **Configurações de conexão** para o conector selecionado e selecione **Avançar** para ver uma prévia dos dados.

1. Selecione **Transformar dados**. Nesta etapa, você adicionará entidades à sua fonte de dados. Entidades são conjuntos de dados. Se você possui um banco de dados que inclui vários conjuntos de dados, cada conjunto de dados é sua própria entidade.

1. A caixa de diálogo **Power Query - Editar consultas** permite revisar e refinar os dados. As entidades que os sistemas identificaram na sua fonte de dados selecionada aparecem no painel esquerdo.

   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo Editar consultas.](media/data-manager-configure-edit-queries.png "Caixa de diálogo Editar consultas")

1. Você também poderá transformar seus dados. Selecione uma entidade para editar ou transformar. Use as opções na janela do Power Query para aplicar as transformações. Cada transformação é listada em **Etapas aplicadas**. O Power Query fornece várias opções de transformação pré-criadas. Para obter mais informações, consulte [Transformações do Power Query](/power-query/power-query-what-is-power-query#transformations).

1. Você pode adicionar entidades adicionais à sua fonte de dados, selecionando **Obter dados** na caixa de diálogo **Editar consultas**.

   É recomendável usar as seguintes transformações:

   - Se você estiver ingerindo dados de um arquivo CSV, a primeira linha geralmente contém cabeçalhos. Vá para **Transformar tabela** e selecione **Usar cabeçalhos como primeira linha**.
   - Certifique-se de que o tipo de dados esteja definido de forma adequada.

1. Selecione **Salvar** no canto inferior direito da janela do Power Query para salvar as transformações. Depois de salvar, você encontrará sua fonte de dados em **Dados** > **Fontes de dados**.

1. Na página **Fontes de dados**, você observará que a nova fonte de dados está no status **Atualizando**.

## <a name="available-power-query-data-sources"></a>Fontes de dados do Power Query disponíveis

Consulte a [Referência do conector do Power Query](/power-query/connectors/) para obter uma lista de conectores que você pode usar para importar dados para o Customer Insights. 

Conectores com uma marca de seleção na coluna **Customer Insights (Dataflows)** estão disponíveis para criar novas fontes de dados com base no Power Query. Revise a documentação de um conector específico para saber mais sobre seus pré-requisitos, limitações e outros detalhes.

## <a name="edit-power-query-data-sources"></a>Editar fontes de dados do Power Query

> [!NOTE]
> Talvez não seja possível fazer alterações nas fontes de dados que estão sendo usadas no momento em um dos processos do aplicativo (*segmentação*, *corresponder* ou *mesclar*, por exemplo). 
>
> Na página **Configurações**, você pode acompanhar o andamento de cada um dos processos ativos. Quando um processo é concluído, você pode retornar à página **Fontes de Dados** e fazer suas alterações.

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Selecione as reticências verticais ao lado da fonte de dados que você deseja alterar e selecione **Editar** no menu suspenso.

   > [!div class="mx-imgBorder"]
   > ![Opção Editar.](media/edit-option-data-sources.png "Editar opção")

   [!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]
   
3. Aplique suas mudanças e transformações na caixa de diálogo **Power Query - Editar consultas**, conforme descrito na seção [Criar uma nova fonte de dados](#create-a-new-data-source).

4. Selecione **Salvar** no Power Query após concluir suas edições para salvar suas alterações.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
