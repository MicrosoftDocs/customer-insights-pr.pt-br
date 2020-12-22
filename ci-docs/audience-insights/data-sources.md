---
title: Usar fontes de dados para ingerir dados
description: Saiba como importar dados de várias fontes.
ms.date: 11/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: a720641f7499fc71ff5bceeba48d296c51f77242
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643939"
---
# <a name="overview-about-data-sources"></a>Visão geral sobre fontes de dados

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

O recurso de insights de público-alvo no Dynamics 365 Customer Insights conecta-se aos dados de um amplo conjunto de fontes. A conexão a uma fonte de dados é conhecida como o processo de *ingestão de dados*. Depois de ingerir os dados, você pode [unificar](data-unification.md) e agir sobre eles.

## <a name="add-a-data-source"></a>Adicionar fonte de dados

Consulte os artigos detalhados sobre como adicionar uma fonte de dados, dependendo da opção escolhida.

Você pode adicionar uma fonte de dados de três maneiras principais:

- [Por meio de dezenas de conectores do Power Query](connect-power-query.md)
- [De uma pasta do Common Data Model](connect-common-data-model.md)
- [Do seu próprio lake do Common Data Service](connect-common-data-service-lake.md)

> [!NOTE]
> Ainda não é possível adicionar dados de fontes de dados locais.

## <a name="review-ingested-data"></a>Analisar dados ingeridos

Você verá o nome de cada fonte de dados ingeridos, seu status e a última vez em que os dados foram atualizados para essa fonte. Você pode classificar a lista de fontes de dados por cada coluna.

> [!div class="mx-imgBorder"]
> ![Fonte de dados adicionada](media/configure-data-datasource-added.png "Fonte de dados adicionada")

|Status  |Descrição  |
|---------|---------|
|Êxito   |A fonte de dados foi inserida com sucesso se um horário for mencionado na coluna **Atualizado**.
|Não iniciada   |A fonte de dados ainda não recebeu dados ou ainda está no modo de rascunho.         |
|Atualizando    |A ingestão de dados está em andamento. Você pode cancelar esta operação selecionando **Interromper atualização** na coluna **Ações**. A interrupção da atualização de uma fonte de dados a reverterá para o último estado de atualização.       |
|Falhou     |A ingestão de dados encontrou erros.         |

Selecione **Status da Atualização** para revisar mais detalhes sobre o status de atualização, incluindo detalhes do erro e atualizações do processo downstream.

O carregamento de dados pode demorar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página **Entidades**. Para obter mais informações, consulte [Entidades](entities.md).

## <a name="refresh-a-data-source"></a>Atualizar uma fonte de dados

As fontes de dados podem ser atualizadas em uma programação automática ou manualmente sob demanda. 

Acesse **Administrador** > **Sistema** > [**Agendar**](system.md#schedule-tab) para configurar atualizações agendadas de todas as fontes de dados ingeridos.

Para atualizar uma fonte de dados sob demanda, siga estas etapas:

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Selecione as reticências verticais ao lado da fonte de dados que deseja atualizar e selecione **Atualizar** na lista suspensa.

3. A fonte de dados agora é acionada para uma atualização manual. Atualizar uma fonte de dados atualizará tanto o esquema da entidade quanto os dados de todas as entidades especificadas na fonte de dados.

4. Selecione **Parar de atualizar** se quiser cancelar uma atualização existente e que a fonte de dados seja revertida para seu último status de atualização.

## <a name="delete-a-data-source"></a>Excluir uma fonte de dados

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Selecione as reticências verticais ao lado da fonte de dados que você deseja remover e selecione **Excluir** no menu suspenso.

3. Confirme a exclusão.
