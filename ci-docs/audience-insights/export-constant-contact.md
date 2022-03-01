---
title: Exportar dados do Customer Insights para o Constant Contact
description: Saiba como configurar a conexão e exportar para o Constant Contact.
ms.date: 03/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 29f4320c798db62609283e3c48f0b47a4f0b982f
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124259"
---
# <a name="export-segments-to-constant-contact-preview"></a>Exportar segmentos para o Constant Contact (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Constant Contact e use-os para atividades de marketing. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

-   Você deve ter uma [conta do Constant Contact](https://www.constantcontact.com/account-home) e as credenciais de administrador correspondentes.
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Você pode exportar até 1 milhão de perfis por vez para o Constant Contact.
- A exportação para o Constant Contact é limitada a segmentos.
- Exportar até 1 milhão de perfis para o Constant Contact pode levar até 1 hora para a conclusão. 
- O número de perfis que você pode exportar para o Constant Contact depende e está limitado ao seu contrato com o Constant Contact.

## <a name="set-up-connection-to-constant-contact"></a>Configurar conexão com o Constant Contact

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Constant Contact** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o Constant Contact.

1. Selecione **Autenticar com o AdRoll** e forneça suas credenciais de administrador do Constant Contact. 

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Constant Contact. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira sua [**ID da Lista do Constant Contact**](https://app.constantcontact.com/pages/contacts/ui#lists). Abra uma lista no Constant Contact para localizar a ID da lista na URL.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. A exportação de segmentos para o Constant Contact é necessária.

1. Opcionalmente, você pode exportar Nome e Sobrenome como campos adicionais para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Constant Contact, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Constant Contact atenda a todas as obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
