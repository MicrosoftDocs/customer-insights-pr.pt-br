---
title: Usar fontes de dados para ingerir dados
description: Saiba como importar dados de várias fontes.
ms.date: 03/18/2022
ms.subservice: audience-insights
ms.topic: overview
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- customerInsights
ms.openlocfilehash: bcc50c6fa8f8e2a66ef6164bfa9022e068c0e374
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645528"
---
# <a name="data-sources-overview"></a>Visão geral de fontes de dados



O Dynamics 365 Customer Insights se conecta a dados de um ampla conjunto de fontes. A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*. Depois de ingerir os dados, você pode [unificar](data-unification.md) e agir sobre eles.

## <a name="add-a-data-source"></a>Adicionar fonte de dados

Consulte os artigos detalhados para saber como adicionar uma fonte de dados, dependendo da opção que você escolher.

É possível adicionar as seguintes fontes de dados:

- [Por meio de dezenas de conectores do Power Query](connect-power-query.md)
- [De uma pasta do Common Data Model](connect-common-data-model.md)
- [Do seu próprio lake do Microsoft Dataverse](connect-dataverse-managed-lake.md)
- [De um banco de dados do Azure Synapse Analytics](connect-synapse.md)

> [!NOTE]
> Se você estiver usando a versão de avaliação, a seção de métodos de importação incluirá uma opção **Biblioteca de dados do Customer Insights**. Escolha essa opção para selecionar um conjunto de dados de exemplo disponível para vários setores. Para obter mais informações, consulte [Avaliação do Dynamics 365 Customer Insights](trial-signup.md).

## <a name="add-data-from-on-premises-data-sources"></a>Adicionar dados de fontes de dados locais

Há suporte à ingestão de dados de fontes de dados locais com base em fluxos de trabalho do Microsoft Power Platform. Você pode habilitar Fluxos de dados no Customer Insights [fornecendo a URL do ambiente do Microsoft Dataverse](create-environment.md) ao configurar o ambiente.

As fontes de dados que são criadas após associar um ambiente do Dataverse ao Customer Insights usam [fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por padrão. Os fluxos de dados oferecem suporte à conectividade local usando gateway de dados. Você pode remover e recriar fontes de dados que existiam antes de um ambiente do Dataverse ser associado [usando gateways de dados locais](/data-integration/gateway/service-gateway-app).

Os gateways de dados de um ambiente existente do Power BI ou do Power Apps ficará visível e você poderá reutilizá-lo no Customer Insights. A página de fontes de dados mostra links para acessar o ambiente do Microsoft Power Platform onde você pode exibir e configurar gateways locais de dados.

> [!IMPORTANT]
> Verifique se os seus gateways estão atualizados com a versão mais recente. Você pode instalar uma atualização e reconfigurar um gateway em um prompt mostrado diretamente na tela do gateway ou [fazer download da versão mais recente](https://powerapps.microsoft.com/downloads/). Se você não usar a versão mais recente do gateway, a atualização do fluxo de dados vai falhar com mensagens de erro como **Não há suporte para a palavra-chave: propriedades de configuração. Nome do parâmetro: palavra-chave**.

## <a name="review-ingested-data"></a>Analisar dados ingeridos
Se o seu ambiente contém fluxos de dados do Power Platform, a página **Fontes de Dados** lista três seções: 
- **Compartilhado**: as fontes de dados que podem ser gerenciadas por todos os administradores do Customer Insights. Alguns exemplos de fontes de dados compartilhadas incluem os fluxos de dados do Power BI, sua própria conta de armazenamento e anexar a um data lake gerenciado do Dataverse.
- **Gerenciado por mim**: os fluxos de dados do Power Platform criados e que só podem ser gerenciados por você. Outros administradores do Customer Insights só podem visualizar esses fluxos de dados, mas não podem editar, atualizar ou excluir.
- **Gerenciado por outros**: os fluxos de dados do Power Platform criados por outros administradores. Você só pode visualizar. Aqui, é indicado o proprietário do fluxo de dados que você precisa contatar caso precise de qualquer ajuda.
> [!NOTE]
> Todas as entidades podem ser visualizadas e usadas por outros usuários. A contextualidade do usuário se aplica apenas às fontes de dados e não às entidades que resultam desses fluxos de dados.

Se nenhum fluxo de dados do Power Platform for usado, você não verá nenhum grupo ou seção. A página **Fontes de Dados** contém apenas uma lista de todas as fontes de dados.

Você verá o nome de cada fonte de dados ingeridos, seu status e a última vez em que os dados foram atualizados para essa fonte. Você pode classificar a lista de fontes de dados por cada coluna.

> [!div class="mx-imgBorder"]
> ![Fonte de dados adicionada.](media/configure-data-datasource-added.png "Fonte de dados adicionada")

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página **Entidades**. Para obter mais informações, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Atualizar uma fonte de dados

As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda. 

Acesse **Administrador** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações agendadas de todas as fontes de dados ingeridos.

Para atualizar uma fonte de dados sob demanda, siga estas etapas:

1. Acesse **Dados** > **Fontes de dados**.

2. Selecione as reticências verticais ao lado da fonte de dados que você deseja atualizar e selecione **Atualizar** na lista suspensa.

3. A fonte de dados agora é acionada para uma atualização manual. Atualizar um fonte de dados atualizará o esquema da entidade e os dados de todas as entidades especificadas na fonte de dados.

4. Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e que a fonte de dados seja revertida para seu último status de atualização.

## <a name="delete-a-data-source"></a>Excluir uma fonte de dados

1. Acesse **Dados** > **Fontes de dados**.

2. Selecione as reticências verticais ao lado da fonte de dados que você deseja remover e selecione **Excluir** no menu suspenso.

3. Confirme a exclusão.


[!INCLUDE [footer-include](includes/footer-banner.md)]
