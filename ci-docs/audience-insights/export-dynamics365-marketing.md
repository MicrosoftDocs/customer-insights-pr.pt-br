---
title: Exportar dados do Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a conexão e exportar para o Dynamics 365 Marketing.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 195bee789dc043057b47c12c8d93e6d53edb59cd
ms.sourcegitcommit: e8e03309ba2515374a70c132d0758f3e1e1851d0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/04/2021
ms.locfileid: "5976786"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Usar segmentos no Dynamics 365 Marketing (versão preliminar)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Use [segmentos](segments.md) para gerar campanhas e contatar grupos específicos de clientes com o Dynamics 365 Marketing. Para obter mais informações, consulte [Usar segments do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments)

## <a name="prerequisite-for-a-connection"></a>Pré-requisitos para uma conexão

- Os registros de contatos devem estar presentes no Dynamics 365 Marketing antes de exportar um segmento do Customer Insights para o Marketing. Leia mais sobre como ingerir contatos no [Dynamics 365 Marketing usando o Common Data Services](connect-power-query.md).

  > [!NOTE]
  > Exportar segmentos de insights de público-alvo para o Marketing não criará registros de contatos nas instâncias do Marketing. Os registros de contatos do Marketing devem ser ingeridos em insights de público-alvo e usados como uma fonte de dados. Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.

## <a name="set-up-connection-to-marketing"></a>Configurar conexão com o Marketing

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Dynamics 365 Marketing** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Digite a URL do Marketing da sua organização no campo **Endereço do servidor**.

1. Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Marketing.

1. Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Dynamics 365 Marketing. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Escolha um ou mais segmentos.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
