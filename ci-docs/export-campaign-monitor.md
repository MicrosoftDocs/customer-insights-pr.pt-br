---
title: Exportar dados do Customer Insights para Monitor de Campanha
description: Aprenda a configurar a conexão e exportar para o Monitor de Campanha.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b351e491ee830b6360d4efe33d32a726c2e553ba
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645602"
---
# <a name="export-segments-to-campaign-monitor-preview"></a>Exportar segmentos para o Monitor de Campanha (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Monitor de Campanha e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Você tem uma [conta do Monitor de Campanha](https://www.campaignmonitor.com/) e as credenciais de administrador correspondentes.
-   Você tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Você pode exportar até 1 milhão de perfis de clientes por exportação para o Campaign Monitor.
- A exportação para o Monitor de Campanha é limitada a segmentos.
- Exportar até 1 milhão de perfis de clientes para Campaign Monitor pode levar até 20 minutos para ser concluído. 
- O número de perfis de clientes que você pode exportar para Campaign Monitor depende e está limitado ao seu contrato com Campaign Monitor.

## <a name="set-up-connection-to-campaign-monitor"></a>Configurar a conexão com o Monitor de Campanha

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Monitor de Campanha** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o Monitor de Campanha.

1. Selecione **Autenticar com Monitor de Campanha** e forneça suas credenciais de administrador do Monitor de Campanha.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Monitor de Campanha. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira a [**ID da Lista do Monitor de Campanha**](https://www.campaignmonitor.com/api/getting-started/#your-list-id).    
   [Gerar a chave de API](https://www.campaignmonitor.com/api/getting-started/) de **Configurações da Conta** no Monitor de Campanha primeiro para exibir a ID da lista de API.  

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. A exportação de segmentos para o Monitor de Campanha é necessária.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Monitor de Campanha, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Monitor de Campanha atenda a todas as obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
