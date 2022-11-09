---
title: Exportar segmentos para o Marketo (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Marketo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cba40b74b86a40fc41db856760c9361b755a8864
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724926"
---
# <a name="export-segments-to-marketo-preview"></a>Exportar segmentos para o Marketo (versão preliminar)

Exporte segmentos de perfis de clientes unificados para gerar campanhas, fornecer marketing por email e usar grupos específicos de clientes com o Marketo.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Marketo](https://login.marketo.com/) e as credenciais de administrador correspondentes.
- Uma [ID do cliente do Marketo, um Segredo do cliente e o Nome de Host do Ponto de Extremidade REST](https://developers.marketo.com/rest-api/authentication/).
- [Listas existentes no Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists) e as IDs correspondentes.
- [Segmentos configurados](segments.md).
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 1 milhão de perfis de cliente por exportação para o Marketo, o que pode levar até 3 horas. O número de perfis de cliente que você pode exportar para o Marketo depende de seu contrato com o Marketo.
- Apenas segmentos.

## <a name="set-up-connection-to-marketo"></a>Configurar conexão com o Marketo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Marketo**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua **ID do cliente do Marketo, o Segredo do cliente e Nome de Host do Ponto de Extremidade REST**. O Nome do host do ponto de extremidade REST é somente o nome do host, sem https://. Exemplo: xyz-abc-123.mktorest.com.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Marketo. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Insira a **ID de lista do Marketo**. A ID da lista é um valor puramente numérico. Por exemplo, se a ID de lista do Marketo for ST12345A7, remova o caractere antes e depois dos numerais e insira *12345*.

1. Na seção **Correspondência de dados**, selecione pelo menos um campo que representa o endereço de e-mail ou o ID Marketo do cliente.

1. Se preferir, você pode exportar **Nome**, **Sobrenome**, **Cidade**, **Estado** e **País/Região** para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

No Marketo, você pode encontrar seus segmentos nas [Listas do Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

[!INCLUDE [footer-include](includes/footer-banner.md)]
