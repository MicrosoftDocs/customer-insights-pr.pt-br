---
title: Exportar dados do Customer Insights para a ActiveCampaign
description: Saiba como configurar a conexão e exportar para a ActiveCampaign.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 5d15b9bf7383d06070ac92d7a729fc6e6e00c9d7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645652"
---
# <a name="export-segments-to-activecampaign-preview"></a>Exportar segmentos para a ActiveCampaign (versão preliminar)

Exporte segmentos de perfis unificados de clientes para a ActiveCampaign e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Você ter uma [conta da ActiveCampaign](https://www.activecampaign.com/) e as credenciais de administrador correspondentes.
-   Você tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis de cliente unificados nos segmentos exportados contêm um campo com um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Você pode exportar até 1 milhão de perfis de clientes por exportação para ActiveCampaign e isso pode levar até 90 minutos para ser concluído.
- A exportação para a ActiveCampaign é limitada a segmentos.
- O número de perfis de clientes que você pode exportar para ActiveCampaign depende de seu contrato com ActiveCampaign.

## <a name="set-up-connection-to-activecampaign"></a>Configurar conexão para a ActiveCampaign

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **ActiveCampaign** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira sua [Chave de API da ActiveCampaign e Nome do Host do Ponto de Extremidade REST](https://help.activecampaign.com/hc/articles/207317590-Getting-started-with-the-API#how-to-obtain-your-activecampaign-api-url-and-key). O Nome do host do ponto de extremidade REST é somente o nome do host, sem https://. 

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar conexão à ActiveCampaign.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você poderá configurar uma exportação se tiver acesso a uma conexão desse tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção da ActiveCampaign. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira sua [**ID da Lista da ActiveCampaign**](https://help.activecampaign.com/hc/articles/360000030559-How-to-create-a-list-in-ActiveCampaign).    

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. É necessário exportar segmentos para a ActiveCampaign. Opcionalmente, você pode exportar Nome, Sobrenome, e Telefone para criar emails mais personalizados. Selecione Adicionar atributo para mapear esses campos.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para a ActiveCampaign, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que a ActiveCampaign cumpra quaisquer obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
