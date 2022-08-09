---
title: Exportar segmentos para o DotDigital (versão preliminar)
description: Saiba como configurar a conexão e exportar para o DotDigital.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: cabaea84e31f8fe97bc558a8dca8d93bc40f43b7
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196058"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segmentos para o DotDigital (versão preliminar)

Exporte segmentos de perfis de clientes unificados para catálogos de endereços do DotDigital e use-os para campanhas, marketing por email e para criar segmentos de clientes com o DotDigital.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta DotDigital](https://dotdigital.com/) e um [usuário de API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user).
- Uma ID de DotDigital de um [novo](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book) ou já existente catálogo de endereços no DotDigital. A ID pode ser encontrada na URL ao selecionar e abrir um catálogo de endereços.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de cliente por exportação para o DotDigital, o que pode levar até três horas devido a limitações do provedor. O número de perfis de cliente que você pode exportar para o DotDigital depende de seu contrato com o DotDigital.
- Apenas segmentos.

## <a name="set-up-connection-to-dotdigital"></a>Configurar conexão com o DotDigital

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **DotDigital**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira seu **nome de usuário e senha da API DotDigital**.

1. Insira a **ID do catálogo de endereços do DotDigital**.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do DotDigital. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Se preferir, exporte **Nome**, **Sobrenome**, **Nome completo**, **Sexo** e **Código postal**.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

No DotDigital, encontre seus segmentos nos [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

[!INCLUDE [footer-include](includes/footer-banner.md)]
