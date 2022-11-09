---
title: Exportar segmentos para o Mailchimp (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Mailchimp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: d74672768afec94e899ff0aec8c118c2afcde368
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725018"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportar segmentos para o Mailchimp (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Mailchimp a fim de criar boletins informativos e campanhas por email.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Mailchimp](https://mailchimp.com/) e as credenciais de administrador correspondentes.
- [Públicos-alvo existentes no Mailchimp](https://mailchimp.com/help/create-audience/) e as [IDs de público-alvo](https://mailchimp.com/help/find-audience-id/) correspondentes.
- [Segmentos configurados](segments.md).
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 1 milhão de perfis de cliente por exportação para o Mailchimp, o que pode levar até três horas. O número de perfis de cliente que você pode exportar para o Mailchimp depende de seu contrato com o Mailchimp.
- Apenas segmentos.

## <a name="set-up-connection-to-mailchimp"></a>Configurar conexão com o Mailchimp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Mailchimp**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Autenticar com o Mailchimp** e forneça suas credenciais do Mailchimp.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Mailchimp. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Insira a **ID de público-alvo do Mailchimp**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Se preferir, exporte **Nome** e **Sobrenome** para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
