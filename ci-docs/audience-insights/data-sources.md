---
title: Usar fontes de dados para ingerir dados
description: Saiba como importar dados de várias fontes.
ms.date: 04/12/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: 75d597158233f75f0eb5f94389f9dba199d81719f2bbe4e5cc58d2a3afc7dcf8
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032836"
---
# <a name="data-sources-overview"></a>Visão geral de fontes de dados

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

O recurso de insights de público-alvo no Dynamics 365 Customer Insights conecta-se aos dados de um amplo conjunto de fontes. A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*. Depois de ingerir os dados, você pode [unificar](data-unification.md) e agir sobre eles.

## <a name="add-a-data-source"></a>Adicionar fonte de dados

Consulte os artigos detalhados sobre como adicionar uma fonte de dados, dependendo da opção escolhida.

Você pode adicionar uma fonte de dados de três maneiras principais:

- [Por meio de dezenas de conectores do Power Query](connect-power-query.md)
- [De uma pasta do Common Data Model](connect-common-data-model.md)
- [Do seu próprio lake do Microsoft Dataverse](connect-dataverse-managed-lake.md)

## <a name="add-data-from-on-premises-data-sources"></a>Adicionar dados de fontes de dados locais

Há suporte à ingestão de dados de fontes de dados locais nos insights de público-alvo com base nos fluxos de dados do Microsoft Power Platform. Os fluxos de dados podem ser habilitados no Customer Insights [fornecendo a URL do ambiente do Microsoft Dataverse](get-started-paid.md) durante a configuração do ambiente.

As fontes de dados criadas após a associação de um ambiente do Dataverse com o Customer Insights usará[fluxos de dados do Power Platform](/power-query/dataflows/overview-dataflows-across-power-platform-dynamics-365) por padrão. Os fluxos de dados oferecem suporte à conectividade local usando gateway de dados. Remova e recrie fontes de dados que existiam antes que um ambiente do Dataverse fosse associado para [usar os gateways de dados locais](/data-integration/gateway/service-gateway-app).

Os gateways de dados de um ambiente existente do Power BI ou do Power Apps ficará visível e você poderá reutilizá-lo no Customer Insights. A página de fontes de dados mostra links para acessar o ambiente do Microsoft Power Platform onde você pode exibir e configurar gateways locais de dados.

## <a name="review-ingested-data"></a>Analisar dados ingeridos

Você verá o nome de cada fonte de dados ingeridos, seu status e a última vez em que os dados foram atualizados para essa fonte. Você pode classificar a lista de fontes de dados por cada coluna.

> [!div class="mx-imgBorder"]
> ![Fonte de dados adicionada.](media/configure-data-datasource-added.png "Fonte de dados adicionada")

|Status  |Descrição  |
|---------|---------|
|Êxito   |A fonte de dados foi inserida com sucesso se um horário for mencionado na coluna **Atualizado**.
|Não iniciada   |A fonte de dados ainda não recebeu dados ou ainda está no modo de rascunho.         |
|Atualizando    |A ingestão de dados está em andamento. Você pode cancelar esta operação selecionando **Interromper atualização** na coluna **Ações**. A interrupção da atualização de uma fonte de dados a reverterá para o último estado de atualização.       |
|Falhou     |A ingestão de dados encontrou erros.         |

Selecione o valor na coluna **Status** de qualquer fonte de dados para revisar mais detalhes. No painel **Detalhes de progresso**, expanda **Fontes de dados**. Selecione **Ver detalhes** para obter mais informações sobre o status de atualização, incluindo detalhes do erro e atualizações do processo downstream.

O carregamento de dados pode levar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página **Entidades**. Para obter mais informações, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Atualizar uma fonte de dados

As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda. 

Acesse **Administrador** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações agendadas de todas as fontes de dados ingeridos.

Para atualizar uma fonte de dados sob demanda, siga estas etapas:

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Selecione as reticências verticais ao lado da fonte de dados que você deseja atualizar e selecione **Atualizar** na lista suspensa.

3. A fonte de dados agora é acionada para uma atualização manual. Atualizar um fonte de dados atualizará o esquema da entidade e os dados de todas as entidades especificadas na fonte de dados.

4. Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e que a fonte de dados seja revertida para seu último status de atualização.

## <a name="delete-a-data-source"></a>Excluir uma fonte de dados

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Selecione as reticências verticais ao lado da fonte de dados que você deseja remover e selecione **Excluir** no menu suspenso.

3. Confirme a exclusão.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
