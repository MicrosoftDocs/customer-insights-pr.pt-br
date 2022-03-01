---
title: Exportar dados do Customer Insights para o Marketo
description: Saiba como configurar a conexão com o Marketo.
ms.date: 11/12/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 34ccee2894f1f2b552d0c6a88a6810e2dfc677a3
ms.sourcegitcommit: 0b1d3ca11b8ba362a959da0eea15c37e9cdba084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4570389"
---
# <a name="connector-for-marketo-preview"></a>Conector para Marketo (versão preliminar)

Exporte segmentos de perfis de clientes unificados para gerar campanhas, fornecer marketing por email e usar grupos específicos de clientes com o Marketo.

## <a name="prerequisites"></a>Pré-requisitos

-   Você deve ter uma [conta do Marketo](https://login.marketo.com/) e as credenciais de administrador correspondentes.
-   Há listas existentes no Marketo e as IDs correspondentes. Para obter mais informações, consulte [listas do Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).
-   Você deve ter [segmentos configurados](segments.md).
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="connect-to-marketo"></a>Conectar-se ao Marketo

1. Vá para **Administrador** > **Exportar destinos**.

1. Em **Marketo**, selecione **Configurar**.

1. Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.

1. Insira **[ID de cliente do Marketo, Segredo do cliente e Nome de Host do Ponto de Extremidade REST](https://developers.marketo.com/rest-api/authentication/)**.

1. Insira sua **[ID de lista do Marketo](https://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists)** 

1. Selecione **Aceito** para confirmar a **Conformidade e privacidade dos dados** e selecione **Conectar** para inicializar a conexão com o Marketo.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

   :::image type="content" source="media/export-connect-marketo.png" alt-text="Captura de tela de exportação da conexão com o Marketo":::

1. Selecione **Próximo** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. 

1. Opcionalmente, você pode exportar **Nome**, **Sobrenome**, **Cidade**, **Estado** e **País/Região** como campos adicionais para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar. Você pode exportar até 1 milhão de perfis de clientes no total para o Marketo.

   :::image type="content" source="media/export-segment-marketo.png" alt-text="Selecionar campos e segmentos para exportar para o Marketo":::

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab). No Marketo, agora você pode encontrar seus segmentos em [listas do Marketo](ttps://docs.marketo.com/display/public/DOCS/Understanding+Static+Lists).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportação para o Marketo.
- A exportação para o Marketo é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode levar até 3 horas. 
- O número de perfis que você pode exportar para o Marketo depende e está limitado ao seu contrato com o Marketo.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Marketo, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Marketo cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
