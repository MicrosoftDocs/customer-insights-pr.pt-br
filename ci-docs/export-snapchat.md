---
title: Exportar segmentos para o Snapchat (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Snapchat.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 85443dcb54ebd58182997fbb56a738901f2a051f
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195368"
---
# <a name="export-segments-to-snapchat-preview"></a>Exportar segmentos para o Snapchat (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Snapchat e use-os para publicidade.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta comercial do Snapchat](https://business.snapchat.com/), uma [conta do Snapchat Ads](https://ads.snapchat.com/) e as credenciais de administrador correspondentes. Você deve ser pelo menos membro de uma Conta da Organização e ser Gerente de Dados de uma Conta de Anúncios específica.
- Pelo menos um público-alvo no Snapchat Audience Manager do tipo SAM (Snap Audience Match).
- A [ID de Segmento/Público-alvo do Snapchat](https://businesshelp.snapchat.com/s/article/custom-audiences). A ID do público-alvo pode ser encontrada na URL depois de selecionar o público no Snapchat Audience Manager.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente, o que pode levar até 15 minutos.
- Apenas segmentos.

## <a name="set-up-connection-to-snapchat"></a>Configurar conexão com o Snapchat

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Snapchat**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Autenticar com o Snapchat** e forneça suas credenciais de administrador do Snapchat.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Snapchat. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Insira a **ID de Segmento/Público-alvo do Snapchat**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
