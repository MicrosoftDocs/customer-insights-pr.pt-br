---
title: Exportar dados do Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a conexão com o Dynamics 365 Marketing.
ms.date: 08/21/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 163387779b64bd78ef08e2d96a5f1c9615062f28
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643759"
---
# <a name="connector-for-dynamics-365-marketing-preview"></a>Conector para o Dynamics 365 Marketing (versão preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use [segmentos](segments.md) para gerar campanhas e contatar grupos específicos de clientes com o Dynamics 365 Marketing. Para obter mais informações, consulte [Usar segments do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite"></a>Pré-requisito

Registros de contato [do Dynamics 365 Marketing ingeridos no Common Data Service](connect-power-query.md).

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
