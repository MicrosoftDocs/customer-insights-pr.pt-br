---
title: Exportar segmentos para o Omnisend (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Omnisend.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c23d6d3538c4df6006c14064f95379169af06622
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196150"
---
# <a name="export-segments-to-omnisend-preview"></a>Exportar segmentos para o Omnisend (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Omnisend e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Omnisend](https://www.omnisend.com/) e as credenciais de administrador correspondentes.
- Uma [chave de API do Omnisend](https://support.omnisend.com/en/articles/1061890-generating-api-key)
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente por exportação para o Omnisend, o que pode levar até quatro horas. O número de perfis de clientes que você pode exportar para o Omnisend depende de seu contrato com o Omnisend.
- Apenas segmentos.

## <a name="set-up-connection-to-omnisend"></a>Configurar conexão com o Omnisend

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Omnisend**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são apenas administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua chave de API do Omnisend.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Omnisend. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Se preferir, exporte **Nome**, **Sobrenome**, **Endereço**, **País/Região**, **Estado**, **Cidade** e **Código Postal** para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
