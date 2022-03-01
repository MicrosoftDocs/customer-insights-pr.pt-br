---
title: Exportar dados do Customer Insights para o Mailchimp
description: Saiba como configurar a conexão com o Mailchimp.
ms.date: 10/26/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: edff494f6edf26a8b641cb1d788a715389ddb346
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405015"
---
# <a name="connector-for-mailchimp-preview"></a>Conector para Mailchimp (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Mailchimp a fim de criar boletins informativos e campanhas por email.

## <a name="prerequisites"></a>Pré-requisitos

-   Você deve ter uma [conta do Mailchimp](https://mailchimp.com/) e as credenciais de administrador correspondentes.
-   Há públicos-alvo existentes no Mailchimp e as IDs correspondentes. Para obter mais informações, consulte [públicos-alvo do Mailchimp](https://mailchimp.com/help/create-audience/).
-   Você deve ter [segmentos configurados](segments.md)
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="connect-to-mailchimp"></a>Conectar ao Mailchimp

1. Vá para **Administrador** > **Exportar destinos**.

1. Em **Mailchimp**, selecione **Configurar**.

1. Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Insira sua **[ID de público-alvo do Mailchimp](https://mailchimp.com/help/find-audience-id/)** e selecione **Conectar** para inicializar a conexão com o Mailchimp.

1. Selecione **Autenticar com o Mailchimp** e forneça suas credenciais do Mailchimp.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

   :::image type="content" source="media/export-connect-mailchimp.png" alt-text="Captura de tela de exportação da conexão com o Mailchimp":::

1. Selecione **Próximo** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. 

1. Opcionalmente, você pode exportar **Nome** e **Sobrenome** como campos adicionais para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar. Você pode exportar até 1 milhão de perfis de clientes no total para o Mailchimp.

   :::image type="content" source="media/export-segments-mailchimp.png" alt-text="Selecionar campos e segmentos para exportar para o Mailchimp":::

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab). No Mailchimp, agora você pode encontrar seus segmentos em [públicos-alvo do Mailchimp](https://mailchimp.com/help/create-audience/).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportação para o Mailchimp.
- A exportação para o Mailchimp é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode levar até três horas devido a limitações do provedor. 
- O número de perfis que você pode exportar para o Mailchimp depende e está limitado ao seu contrato com o Mailchimp.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Mailchimp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Mailchimp cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
