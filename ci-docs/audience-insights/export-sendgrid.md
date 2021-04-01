---
title: Exportar dados do Customer Insights para o SendGrid
description: Saiba como configurar a conexão com o SendGrid.
ms.date: 12/08/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 1a1f679fa42d47d524ebfdd6e931ae2822565f77
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597267"
---
# <a name="connector-for-sendgrid-preview"></a>Conector para SendGrid (versão preliminar)

Exporte segmentos de perfis de clientes unificados para as listas de contato do SendGrid e use-os para campanhas e marketing por email no SendGrid. 

## <a name="prerequisites"></a>Pré-requisitos

-   Você deve ter uma [conta do SendGrid](https://sendgrid.com/) e as credenciais de administrador correspondentes.
-   Há listas de contato existentes no SendGrid e as IDs correspondentes. Para obter mais informações, consulte [SendGrid – Gerenciar contatos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="connect-to-sendgrid"></a>Conectar-se ao SendGrid

1. Vá para **Administrador** > **Exportar destinos**.

1. Em **SendGrid**, selecione **Configurar**.

1. Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.

   :::image type="content" source="media/export-sendgrid.PNG" alt-text="Painel de configuração de exportação do SendGrid.":::

1. Insira a **Chave de API do SendGrid** [Chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Insira a **[ID de lista do SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o SendGrid.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Próximo** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**, **País/Região**, **Estado**, **Cidade** e **CEP**.

1. Selecione os segmentos que você deseja exportar. É altamente **recomendável não exportar mais de 100.000 perfis de clientes no total** para o SendGrid. 

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 100.000 perfis no total para o SendGrid.
- A exportação para o SendGrid é limitada a segmentos.
- A exportação de até 100.000 perfis para o SendGrid pode levar até algumas horas para ser concluída. 
- O número de perfis que você pode exportar para o SendGrid depende e está limitado ao seu contrato com o SendGrid.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao SendGrid, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o SendGrid cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]