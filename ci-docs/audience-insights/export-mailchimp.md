---
title: Exportar dados do Customer Insights para o Mailchimp
description: Saiba como configurar a conexão e exportar para o Mailchimp.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ac6642c0ce02f1a92458a16250fd3b4cdef5fd1c
ms.sourcegitcommit: adb9c43ddaba25e511535d78a4bcf8815f154a7b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/06/2021
ms.locfileid: "6362495"
---
# <a name="export-segments-to-mailchimp-preview"></a>Exportar segmentos para o Mailchimp (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Mailchimp a fim de criar boletins informativos e campanhas por email.

## <a name="prerequisites-for-connection"></a>Pré-requisitos para conexão

-   Você deve ter uma [conta do Mailchimp](https://mailchimp.com/) e as credenciais de administrador correspondentes.
-   Há públicos-alvo existentes no Mailchimp e as IDs correspondentes. Para obter mais informações, consulte [públicos-alvo do Mailchimp](https://mailchimp.com/help/create-audience/).
-   Você deve ter [segmentos configurados](segments.md)
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportação para o Mailchimp.
- A exportação para o Mailchimp é limitada a segmentos.
- Exportar segmentos com 1 milhão de perfis pode levar até três horas. 
- O número de perfis que você pode exportar para o Mailchimp depende e está limitado ao seu contrato com o Mailchimp.

## <a name="set-up-connection-to-mailchimp"></a>Configurar conexão com o Mailchimp

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Mailchimp** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o Mailchimp.

1. Selecione **Autenticar com o Mailchimp** e forneça suas credenciais do Mailchimp.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-the-connector"></a>Configurar o conector

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados**> **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Mailchimp. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira sua **[ID do público-alvo do Mailchimp](https://mailchimp.com/help/find-audience-id/)**

3. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. 

1. Opcionalmente, você pode exportar **Nome** e **Sobrenome** para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar. Você pode exportar até 1 milhão de perfis de clientes no total para o Mailchimp.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Mailchimp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Mailchimp cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
