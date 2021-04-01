---
title: Exportar dados do Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a conexão com o Dynamics 365 Marketing.
ms.date: 02/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 892aff643872f11307a2c43e5670edab657d7848
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597589"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Conector para o Dynamics 365 Marketing (versão preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use [segmentos](segments.md) para gerar campanhas e contatar grupos específicos de clientes com o Dynamics 365 Marketing. Para obter mais informações, consulte [Usar segments do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Pré-requisito

- Os registros de contatos devem estar presentes no Dynamics 365 Marketing antes de exportar um segmento do Customer Insights para o Marketing. Leia mais sobre como ingerir contatos no [Dynamics 365 Marketing usando o Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Exportar segmentos de insights de público-alvo para o Marketing não criará registros de contatos nas instâncias do Marketing. Os registros de contatos do Marketing devem ser ingeridos em insights de público-alvo e usados como uma fonte de dados. Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.

## <a name="configure-the-connector-for-marketing"></a>Configurar o conector para o Marketing

1. Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.

1. No **Dynamics 365 Marketing**, selecione **Configurar**.

1. Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.

1. Digite a URL do Marketing da sua organização no campo **Endereço do servidor**.

1. Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Marketing.

1. Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.

1. Selecione **Avançar**.

1. Escolha um ou mais segmentos.

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).


[!INCLUDE[footer-include](../includes/footer-banner.md)]