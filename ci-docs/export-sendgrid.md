---
title: Exportar segmentos para o SendGrid (versão preliminar)
description: Saiba como configurar a conexão e exportar para o SendGrid.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: f2990ad410dda0cbf952f82f3fc30b3a53a7bcd4
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196978"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segmentos para o SendGrid (versão preliminar)

Exporte segmentos de perfis de clientes unificados para as listas de contato do SendGrid e use-os para campanhas e marketing por email no SendGrid.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do SendGrid](https://sendgrid.com/) e as credenciais de administrador correspondentes.
- [Listas de contato existentes no SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts) e as IDs correspondentes.
- Uma [chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 100.000 perfis de cliente no total para o SendGrid, o que pode levar algumas horas. O número de perfis de cliente que você pode exportar para o SendGrid depende de seu contrato com o SendGrid.
- Apenas segmentos.

## <a name="set-up-connection-to-sendgrid"></a>Configurar conexão com o SendGrid

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **SendGrid**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua **chave de API do SendGrid**.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do SendGrid. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Insira a **ID de lista do SendGrid**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Se preferir, selecione campos como **Nome**, **Sobrenome**, **País/Região**, **Estado**, **Cidade** e **Código postal**.

1. Selecione os segmentos que você deseja exportar seguindo as limitações conhecidas.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
