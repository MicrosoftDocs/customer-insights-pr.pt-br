---
title: Exportar segmentos para o Iterable (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Iterable.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 69e2bd207c98fc2530620018bf95dd869d1798f6
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724467"
---
# <a name="export-segments-to-iterable-preview"></a>Exportar segmentos para o Iterable (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Iterable e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Iterable](https://iterable.com/) e as credenciais de administrador correspondentes.
- Uma [chave de API do Iterable](https://support.iterable.com/hc/en-us/articles/360043464871)
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 1 milhão de perfis de cliente para o Iterable, o que pode levar até 30 minutos. O número de perfis de cliente que você pode exportar para o Iterable depende de seu contrato com o Iterable.
- Apenas segmentos.

## <a name="set-up-connection-to-iterable"></a>Configurar a conexão com o Iterable

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Iterable**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Informe sua Chave de API do Iterable para continuar com o login.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Iterable. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. A lista criada no Iterable receberá exatamente o mesmo nome do segmento no Dynamics 365 Customer Insights.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
