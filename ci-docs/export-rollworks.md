---
title: Exportar segmentos para o RollWorks (versão preliminar)
description: Saiba como configurar a conexão e exportar para o RollWorks.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d857bf5d11de86521c4a9d4fc665c020496d89d2
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725110"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportar segmentos para o RollWorks (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o RollWorks e use-os para publicidade.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do RollWorks](https://www.rollworks.com/) e as credenciais de administrador correspondentes.
- Uma [ID de anunciante do RollWorks](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 250.000 perfis de cliente por exportação para o RollWorks, o que pode levar até 10 minutos. O número de perfis de cliente que você pode exportar para o RollWorks depende de seu contrato com o RollWorks.
- Apenas segmentos.

## <a name="set-up-connection-to-rollworks"></a>Configurar conexão com o RollWorks

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **RollWorks**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão.  Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Autenticar com o RollWorks** e forneça suas credenciais de administrador do RollWorks.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do RollWorks. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Digite sua **ID de Anunciante do RollWorks**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
