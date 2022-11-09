---
title: Exportar segmentos para o Google Ads (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Google Ads.
ms.date: 07/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: a46623e609665f8031f223593a6644147e5209d8
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725064"
---
# <a name="export-segments-to-google-ads-preview"></a>Exportar segmentos para o Google Ads (versão preliminar)

Exporte segmentos de perfis de cliente unificados para uma lista de público-alvo do Google Ads e use-os para criar anúncios no Pesquisa Google, Gmail, YouTube e Google Display Network.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Google Ads](https://ads.google.com/) e as credenciais de administrador correspondentes.
- Uma [ID do cliente do Google Ads](https://support.google.com/google-ads/answer/1704344)
- Os requisitos da [Política de Customer Match](https://support.google.com/adspolicy/answer/6299717) devem ser cumpridos.
- Os requisitos dos [tamanhos de lista de remarketing](https://support.google.com/google-ads/answer/7558048) devem ser cumpridos.
- [Segmentos configurados](segments.md).
- Os perfis de clientes unificados nos segmentos exportados contêm campos que representam um endereço de e-mail, telefone, ID de anunciante móvel, ID de usuário de terceiros ou endereço.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Exportar até 1 milhão de perfis de cliente por exportação para o Google Ads, o que pode levar até 30 minutos devido a limitações do provedor.
- Apenas segmentos.
- A correspondência no Google Ads pode levar até 48 horas.

## <a name="set-up-connection-to-google-ads"></a>Configurar conexão com o Google Ads

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Google Ads**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua ID do cliente do Google Ads.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Autenticar com o Google Ads** e forneça suas credenciais do Google Ads.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Google Ads. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Escolha se você deseja usar um público-alvo existente ou criar um:
   - Para atualizar um público-alvo existente do Google Ads, insira a [ID de público-alvo do Google Ads](https://support.google.com/google-ads/answer/7558048?hl=en#:~:text=Audience%20lists%20is%20a%20section,Display%20Network%20through%20remarketing%20campaigns).
   - Para criar um novo público, deixe o campo ID de público-alvo do Google em branco. O Customer Insights automaticamente criará um público-alvo na sua conta do Google Ads e usará o nome do segmento exportado.

1. Na seção **Correspondência de dados**, selecione um ou mais campos de dados para exportar e selecione o campo que representa os campos de dados correspondentes no Customer Insights.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
