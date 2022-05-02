---
title: Exportar dados do Customer Insights para o SendGrid
description: Saiba como configurar a conexão e exportar para o SendGrid.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 38dd782fdf06d5970e79e6deb6e8fc94252da585
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645680"
---
# <a name="export-segments-to-sendgrid-preview"></a>Exportar segmentos para o SendGrid (versão preliminar)

Exporte segmentos de perfis de clientes unificados para as listas de contato do SendGrid e use-os para campanhas e marketing por email no SendGrid. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

-   Você deve ter uma [conta do SendGrid](https://sendgrid.com/) e as credenciais de administrador correspondentes.
-   Há listas de contato existentes no SendGrid e as IDs correspondentes. Para obter mais informações, consulte [SendGrid – Gerenciar contatos](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts).
-   Você tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 100.000 perfis de clientes no total para o SendGrid.
- A exportação para o SendGrid é limitada a segmentos.
- Exportar até 100.000 perfis de clientes para o SendGrid pode levar algumas horas para ser concluído. 
- O número de perfis de clientes que você pode exportar para o SendGrid depende e está limitado ao seu contrato com o SendGrid.

## <a name="set-up-connection-to-sendgrid"></a>Configurar conexão com o SendGrid

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **SendGrid** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira a **Chave de API do SendGrid** [Chave de API do SendGrid](https://sendgrid.com/docs/ui/account-and-settings/api-keys/).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o SendGrid.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do SendGrid. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira a **[ID de lista do SendGrid](https://sendgrid.com/docs/ui/managing-contacts/create-and-manage-contacts/#manage-contacts)**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**, **País/Região**, **Estado**, **Cidade** e **CEP**.

1. Selecione os segmentos que você deseja exportar. É altamente **recomendável não exportar mais de 100.000 perfis de clientes no total** para o SendGrid. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao SendGrid, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o SendGrid cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]
