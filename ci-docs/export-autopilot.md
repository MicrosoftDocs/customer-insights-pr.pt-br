---
title: Exportar segmentos para o Autopilot (versão preliminar)
description: Aprenda a configurar a conexão e exportar para o Autopilot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b4b14ba9de2c7e20175fac664a705f2212a411fd
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724743"
---
# <a name="export-segments-to-autopilot-preview"></a>Exportar segmentos para o Autopilot (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Autopilot e use-os para marketing por email no Autopilot.

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

- Uma [conta do Autopilot](https://www.autopilothq.com/) e as credenciais de administrador correspondentes.
- Uma [chave de API do Autopilot](https://autopilot.docs.apiary.io/#)
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 100.000 perfis de cliente por exportação para o Autopilot, o que pode levar algumas horas. O número de perfis de cliente que você pode exportar para o Autopilot depende de seu contrato com o Autopilot.
- Apenas segmentos.

## <a name="set-up-connection-to-autopilot"></a>Configurar conexão com o Autopilot

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Autopilot**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua chave de API do Autopilot.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Autopilot. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Opcionalmente, exporte outros campos, como **Nome** e **Sobrenome**.

1. Selecione os segmentos que você deseja exportar concordando com as limitações conhecidas.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
