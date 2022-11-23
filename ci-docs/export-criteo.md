---
title: Exportar segmentos para o Criteo (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Criteo.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 811752da943cd5e40608d48644a1744c7971d3c8
ms.sourcegitcommit: 40ae3322ac95913e485607494754dd03814e42bb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2022
ms.locfileid: "9760012"
---
# <a name="export-segments-to-criteo-preview"></a>Exportar segmentos para o Criteo (versão preliminar)

Exporte segmentos de Unified customer profiles para gerar campanhas, fornecer marketing de emails e usar grupos específicos de clientes com o Criteo.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta de redirecionamento do Criteo Dynamics](https://www.criteo.com/login/) e as credenciais de administrador correspondentes.
- [Segmentos configurados](segments.md).
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente por exportação para o Criteo, o que pode levar até 30 minutos. O número de perfis de cliente que você pode exportar para o Criteo depende de seu contrato com o Criteo.
- Apenas segmentos.

## <a name="set-up-connection-to-criteo"></a>Configurar a conexão com o Criteo

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Criteo**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Autenticar com o Criteo** e forneça seu nome de usuário e credenciais de administrador do Criteo.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Criteo. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
