---
title: Destinos de exportação
description: Exporte dados e gerencie destinos de exportação.
ms.date: 07/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 63caa2ebdd7d637d14ac9c9cc7972095803aee2f
ms.sourcegitcommit: 0260ed244b97c2fd0be5e9a084c4c489358e8d4f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/18/2021
ms.locfileid: "5477119"
---
# <a name="export-destinations-preview-overview"></a>Visão geral de destinos de exportação (versão preliminar)

A página **Exportar destinos** mostra todos os locais para os quais você configurou para exportar dados. Você também pode adicionar novos destinos para exportação. Além disso, ela mostra as opções de exportação disponíveis no momento. Obtenha uma visão geral rápida, descrição e descubra o que você pode fazer com cada opção de extensibilidade. Exporte perfis, medidas e segmentos unificados para aplicativos suportados relevantes para seus negócios.

Vá para **Admin** > **Exportar destinos** para encontrar as seguintes opções de extensibilidade:

- [Complemento do Cartão do Cliente do Dynamics 365](customer-card-add-in.md)
- [Conector do Facebook Ads Manager](export-facebook.md)
- [Power Automateconector](export-power-automate.md)
- [Power Appsconector](export-power-apps.md)
- [Power BIconector](export-power-bi.md)
- [Autopilot](export-autopilot.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Armazenamento de Blobs do Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [SendGrid](export-sendgrid.md)
- [Conector&reg; LiveRamp](export-liveramp.md)
- [Bot para o Microsoft Teams](export-teams-bot.md)
- [Mailchimp](export-mailchimp.md)
- [API do Customer Insights](apis.md)

## <a name="add-a-new-export-destination"></a>Adicionar um novo destino de exportação

Para adicionar destinos de exportação, você tem [permissões de administrador](permissions.md). Se você exportar para os serviços da Microsoft, assumimos que os dois serviços estão na mesma organização.

1. Vá para **Administrador** > **Exportar destinos**.

1. Mude para a guia **Meus destinos de exportação**.

1. Selecione **Adicionar destino** para criar um novo destino de exportação.

1. No painel **Adicionar destino**, selecione o **Tipo** de destino de exportação no menu suspenso.

1. Forneça os detalhes necessários e selecione **Avançar** para criar o destino de exportação.

Você também pode selecionar **Configurar** em um bloco na aba **Descobrir**.

## <a name="view-export-destinations"></a>Exibir Destinos de exportação

Depois de criar destinos de exportação, você os encontrará em uma tabela na guia **Meus destinos de exportação**. Esta tabela possui três colunas:

- **Nome de exibição**: o nome que você inseriu ao criar o destino.
- **Tipo**: o tipo de destino de exportação que você definiu ao criar o destino.
- **Criado**: a data na qual você criou o destino.

## <a name="edit-an-export-destination"></a>Editar um destino de exportação

1. Selecione as reticências verticais para o Destino de exportação que você deseja editar.

   > [!div class="mx-imgBorder"]
   > ![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")

1. Selecione **Editar** no menu suspenso.

1. Altere os valores que exigem atualização e selecione **Salvar**.

## <a name="export-data-on-demand"></a>Exportar dados sob demanda

Depois de configurar um conector para um destino de exportação, as exportações serão executadas a cada [atualização agendada](system.md#schedule-tab).

Para exportar dados sem aguardar uma atualização agendada, vá para a guia **Meus destinos de exportação** em **Administrador** > **Destinos de exportação**.

> [!div class="mx-imgBorder"]
> ![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")

- Selecione **Exportação** acima da lista para executar a exportação para todos os destinos de exportação simultaneamente.
- Selecione as reticências (...) após um item da lista e escolha a opção **Exportação** para executar a exportação para um único destino de exportação.

## <a name="remove-an-export-destination"></a>Remover um Destino de exportação

Para remover um Destino de exportação, inicie da página principal **Destinos de exportação**.

1. Selecione as reticências verticais para o Destino de exportação que você deseja remover.

   > [!div class="mx-imgBorder"]
   > ![Reticências verticais](media/export-destinations-page-ellipsis.png "Reticências verticais")

2. Selecione **Remover** no menu suspenso.

3. Confirme a remoção selecionando **Remover** na tela de confirmação.


[!INCLUDE[footer-include](../includes/footer-banner.md)]