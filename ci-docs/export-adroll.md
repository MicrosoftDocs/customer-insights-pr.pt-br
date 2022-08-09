---
title: Exportar segmentos para o AdRoll (versão preliminar)
description: Aprenda a configurar a conexão e exportar para o AdRoll.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8110eab199920ab8fc2ea15678139faf264a242a
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195736"
---
# <a name="export-segments-to-adroll-preview"></a>Exportar segmentos para o AdRoll (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o AdRoll e use-os para publicidade.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do AdRoll](https://www.adroll.com/) e as credenciais de administrador correspondentes.
- Uma [ID de Anunciante do AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 250.000 perfis de clientes por exportação para o AdRoll, o que pode levar até 10 minutos. O número de perfis de cliente que você pode exportar para o AdRoll depende de seu contrato com o AdRoll.
- Apenas segmentos. Um segmento deve conter pelo menos 100 perfis de cliente.

## <a name="set-up-connection-to-adroll"></a>Configurar conexão com o AdRoll

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **AdRoll**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Autenticar com o AdRoll** e forneça suas credenciais de administrador do AdRoll.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do AdRoll. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Digite seu **ID de anunciante AdRoll**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
