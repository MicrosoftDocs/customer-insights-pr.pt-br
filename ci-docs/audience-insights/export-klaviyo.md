---
title: Exportar dados do Customer Insights para o Klaviyo
description: Saiba como configurar a conexão e exportar para o Klaviyo.
ms.date: 08/13/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 7c1297fd5381c00c07d6501186c51fe4798773d1
ms.sourcegitcommit: 205f931ec671a0ab1850f2c1c94df3307ffb62c9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/13/2021
ms.locfileid: "7385774"
---
# <a name="export-segment-lists-to-klaviyo-preview"></a>Exportar listas de segmentos para o Klaviyo (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Klaviyo e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Você tem uma [conta do Klaviyo](https://www.klaviyo.com/) e credenciais de administrador correspondentes.
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Você pode exportar até 100.000 perfis por exportação para o Klaviyo.
- A exportação para o Klaviyo é limitada a segmentos.
- Exportar até 1 milhão de perfis para o Klaviyo pode levar até 20 minutos para ser concluído. 
- O número de perfis que você pode exportar para o Klaviyo depende e está limitado ao seu contrato com o Klaviyo.

## <a name="set-up-connection-to-klaviyo"></a>Configurar conexão para o Klaviyo

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Klaviyo** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça a [chave de API do Klaviyo](https://help.klaviyo.com/hc/articles/115005062267-How-to-Manage-Your-Account-s-API-Keys) para continuar a se conectar. 

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão ao Klaviyo.

1. Selecione **Autenticar com Klaviyo** e forneça suas credenciais de administrador para o Klaviyo.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção Klaviyo. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira sua [**ID da Lista do Klaviyo**](https://help.klaviyo.com/hc/articles/115005078647-How-to-Find-a-List-ID).     

3. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. É necessário exportar segmentos para o Klaviyo.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Klaviyo, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Klaviyo cumpra obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
