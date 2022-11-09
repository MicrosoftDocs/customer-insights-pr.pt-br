---
title: Exportar segmentos para o Braze (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Braze.
ms.date: 10/06/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: a3967008ec166cb6f099659b0791f1318126c0da
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725202"
---
# <a name="export-segments-to-braze-preview"></a>Exportar segmentos para o Braze (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Braze e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Braze](https://www.braze.com/) e as respectivas credenciais de administrador.
- Uma [chave de API do Braze](https://www.braze.com/docs/api/basics/)
- Seu [Ponto de extremidade REST do Braze](https://www.braze.com/docs/api/basics/#api-definitions) 
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de e-mail e um ID do cliente do Braze.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 1 milhão de perfis de cliente para o Braze, o que pode levar até 40 minutos. O número de perfis de cliente que você pode exportar para o Braze depende de seu contrato com o Braze.
- Apenas segmentos.
- O Link Privado do Azure não tem suporte para a exportação do Braze.

## <a name="set-up-connection-to-braze"></a>Configurar a conexão com o Braze

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Braze**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Informe sua Chave de API do Braze para continuar com o login.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Braze. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira seu ponto de extremidade REST no campo **Nome do host** no seguinte formato: `rest.iad-03.braze.com`.

1. Insira um nome para a exportação.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. No campo **ID do cliente** selecione o campo que representa a Id do Braze do cliente. Os segmentos no Braze serão criados com o mesmo nome do segmento no Dynamics 365 Customer Insights. Você pode escolher mais campos opcionais para dados correspondentes.

1. Selecione as entidades ou os segmentos que deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
