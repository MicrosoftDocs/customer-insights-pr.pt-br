---
title: Exportar segmentos para a ActiveCampaign
description: Saiba como configurar a conexão e exportar para a ActiveCampaign.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e62888a6d618fb1154890e607d8c23d3767d35f7
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9725386"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportar segmentos para a ActiveCampaign (versão preliminar)

Exporte segmentos de perfis unificados de clientes para a ActiveCampaign e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta da ActiveCampaign](https://www.activecampaign.com/) e as credenciais de administrador correspondentes.
- Uma [ID de lista da ActiveCampaign](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign)
- Uma [chave de API da ActiveCampaign](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key) e o Nome do Host do Ponto de Extremidade REST.
- [Segmentos configurados](segments.md) no Customer Insights.
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 1 milhão de perfis de cliente por exportação para ActiveCampaign, o que pode levar até 90 minutos. O número de perfis de clientes que você pode exportar para ActiveCampaign depende de seu contrato com ActiveCampaign.
- Apenas segmentos.

## <a name="set-up-connection-to-activecampaign"></a>Configurar conexão para a ActiveCampaign

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **ActiveCampaign**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua Chave de API da ActiveCampaign e Nome do Host do Ponto de Extremidade REST. O Nome do host do ponto de extremidade REST é somente o nome do host, sem https://.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção da ActiveCampaign. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Insira a **ID da Lista da ActiveCampaign**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Como opção, você pode exportar o **Nome**, o **Sobrenome** e o **Telefone** para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
