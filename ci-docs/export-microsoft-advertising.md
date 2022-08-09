---
title: Exportar segmentos para o Microsoft Advertising (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Microsoft Advertising.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 44217e7823ffbe14d232b3e33de1b4ea6ed69dcf
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196518"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segmentos para o Microsoft Advertising (versão preliminar)

Exporte segmentos do Customer Insights para o Microsoft Advertising para criar públicos-alvo de Correspondência de Clientes. Use esses públicos-alvo para suas campanhas publicitárias.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Microsoft Advertising](https://ads.microsoft.com/) e as credenciais de administrador correspondentes.
- ID do cliente e ID da conta do Microsoft Advertising. Encontre a ID do cliente (`cid`) e a ID da conta (`aid`) nos parâmetros da URL quando você estiver conectado ao Microsoft Advertising.
- Os termos de uso de Customer Match foram aceitos.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 500.000 perfis de cliente por exportação para o Microsoft Advertising, o que pode levar até 10 minutos.
- Apenas segmentos.

## <a name="set-up-connection-to-microsoft-advertising"></a>Configurar conexão com o Microsoft Advertising

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Microsoft Advertising**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. O padrão é administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira a **ID do Cliente do Microsoft Advertising**.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Autenticar com Microsoft Advertising** e forneça suas credenciais de administrador do Microsoft Advertising.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Microsoft Advertising. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Selecione os segmentos a serem exportados. Os públicos-alvo da Correspondência de Clientes no Microsoft Advertising são criados automaticamente com o nome dos segmentos selecionados para exportação. Cada segmento resultará em um público-alvo separado da Correspondência de Clientes.

1. Insira sua **ID do cliente e ID da conta do Microsoft Advertising**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo com o endereço de email de um cliente.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
