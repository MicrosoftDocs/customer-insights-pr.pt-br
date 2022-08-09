---
title: Exportar segmentos para o MoEngage
description: Saiba como configurar a conexão e exportar para o MoEngage.
ms.date: 07/26/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ffc591c01a5a9434cde41f2da25fa930a515b8c1
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9199071"
---
# <a name="export-segments-to-moengage-preview"></a>Exportar segmentos para o MoEngage (versão preliminar)

Exporte segmentos de perfis unificados de cliente para o MoEngage e use-os para marketing por email no MoEngage.

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

- [Conta do MoEngage](https://www.moengage.com/) e as credenciais de administrador correspondentes.
- Chave de API do MoEngage em Settings > API no MoEngage.
- [Segmentos configurados](segments.md) no Customer Insights.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 100.000 perfis de cliente por exportação para o MoEngage, o que pode levar até 15 minutos. O número de perfis de cliente que você pode exportar para o MoEngage depende de seu contrato com o MoEngage.
- Apenas segmentos.

## <a name="set-up-connection-to-moengage"></a>Configurar conexão com o MoEngage

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **MoEngage** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira a [ID da API de Dados e a chave de API do MoEngage](https://developers.moengage.com/hc/articles/4404674776724-Overview#:~:text=Navigate%20to%20Settings%20%3E%20APIs%20%3E%20DATA,ID%20Password%20%2D%20DATA%20API%20KEY).

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão com o MoEngage.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Para criar uma exportação, selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do MoEngage. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. Repita as mesmas etapas para outros campos opcionais.

1. Selecione os segmentos que você deseja exportar. Criaremos um ou mais segmentos com o mesmo nome dos segmentos selecionados no MoEngage em **Segmentos** > **Segmentos Personalizados**.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
