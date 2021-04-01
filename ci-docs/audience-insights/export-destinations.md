---
title: Destinos de exportação
description: Exporte dados e gerencie destinos de exportação.
ms.date: 07/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5557442983f8c48cd46387009e0060beb6e764bb
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596071"
---
# <a name="export-destinations-preview-overview"></a>Visão geral de destinos de exportação (versão preliminar)

A página **Exportar destinos** mostra todos os locais para os quais você configurou para exportar dados. Você também pode adicionar novos destinos para exportação. Além disso, ela mostra as opções de exportação disponíveis no momento. Obtenha uma visão geral rápida, descrição e descubra o que você pode fazer com cada opção de extensibilidade. Exporte perfis, medidas e segmentos unificados para aplicativos suportados relevantes para seus negócios.

Vá para **Admin** > **Exportar destinos** para encontrar as seguintes opções de extensibilidade:

- [Adobe Campaign Standard](export-adobe-campaign-standard.md)
- [Adobe Experience Platform](export-adobe-experience-platform.md)
- [AdRoll](export-adroll.md)
- [Autopilot](export-autopilot.md)
- [Armazenamento de Blobs do Azure](export-azure-blob-storage.md)
- [Azure Data Lake Storage Gen2](export-azure-data-lake-storage-gen2.md)
- [Bot para o Microsoft Teams](export-teams-bot.md)
- [API do Customer Insights](apis.md)
- [DotDigital](export-dotdigital.md)
- [Dynamics 365 Customer Service (Complemento do Cartão do Cliente )](customer-card-add-in.md)
- [Dynamics 365 Marketing](export-dynamics365-marketing.md)
- [Dynamics 365 Sales](export-dynamics365-sales.md)
- [Hub de Vendas do Dynamics 365 (Complemento do Cartão do Cliente)](customer-card-add-in.md)
- [Gerenciador de Anúncios do Facebook](export-facebook.md)
- [Google Ads](export-google-ads.md)
- [LiveRamp&reg;](export-liveramp.md)
- [Mailchimp](export-mailchimp.md)
- [Marketo](export-marketo.md)
- [Power Automate](export-power-automate.md)
- [Power Apps](export-power-apps.md)
- [Power BI](export-power-bi.md)
- [SendGrid](export-sendgrid.md)
- [SFTP](export-sftp.md)

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