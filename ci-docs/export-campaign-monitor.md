---
title: Exportar segmentos para o Monitor de Campanha (versão preliminar)
description: Aprenda a configurar a conexão e exportar para o Monitor de Campanha.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 3c04fc26dc690cf32b45913257e82b9a0f617185
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196288"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segmentos para o Monitor de Campanha (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Monitor de Campanha e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Campaign Monitor](https://www.campaignmonitor.com/) e as credenciais de administrador correspondentes.
- Uma [ID de lista do Campaign Monitor](https://www.campaignmonitor.com/api/getting-started/#your-list-id).
- Uma [chave de API gerada](https://www.campaignmonitor.com/api/getting-started/) de **Configurações da Conta** no Campaign Monitor para obter a ID de lista da API.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente por exportação para o Campaign Monitor, o que pode levar até 20 minutos. O número de perfis de cliente que você pode exportar para o Campaign Monitor depende de seu contrato com o Campaign Monitor.
- Apenas segmentos.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar a conexão com o Monitor de Campanha

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Campaign Monitor**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão com o Monitor de Campanha.

1. Selecione **Autenticar com Monitor de Campanha** e forneça suas credenciais de administrador do Monitor de Campanha.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Para criar uma exportação, selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Monitor de Campanha. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Insira a **ID de Lista do Campaign Monitor**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. A exportação de segmentos para o Monitor de Campanha é necessária.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
