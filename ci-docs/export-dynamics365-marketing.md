---
title: Exportar dados do Customer Insights para o Dynamics 365 Marketing
description: Saiba como configurar a conexão e exportar para o Dynamics 365 Marketing.
ms.date: 08/24/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: 7227f3f9e7699a9b5ad546789de5e568b56da579
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645518"
---
# <a name="use-segments-in-dynamics-365-marketing-preview"></a>Usar segmentos no Dynamics 365 Marketing (versão preliminar)



Use [segmentos](segments.md) para gerar campanhas e contatar grupos específicos de clientes com o Dynamics 365 Marketing. Para obter mais informações, consulte [Usar segmentos do Dynamics 365 Customer Insights com o Dynamics 365 Marketing](/dynamics365/marketing/customer-insights-segments).

Se você estiver usando os novos recursos do Dynamics 365 Marketing para orquestração da jornada do cliente em tempo real em uma organização Dataverse, não precisará criar uma exportação padrão para o Dynamics 365 Marketing. Os contatos e segmentos do Customer Insights estão disponíveis diretamente no Dynamics 365 Marketing após conectar o Marketing e o Customer Insights. Antes de excluir as exportações existentes, revise a documentação em [como conectar o Customer Insights e a orquestração de jornada do cliente do Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile).

## <a name="prerequisite-for-a-connection"></a>Pré-requisitos para uma conexão

- Os registros de contatos devem estar presentes no Dynamics 365 Marketing antes de exportar um segmento do Customer Insights para o Marketing. Leia mais sobre como ingerir contatos no [Dynamics 365 Marketing usando o Microsoft Dataverse](connect-dataverse-managed-lake.md).

  > [!NOTE]
  > A exportação de segmentos do Customer Insights para Marketing não criará novos registros de contato em instâncias de Marketing. Os registros de contato de Marketing devem ser ingeridos no Customer Insights e usados como fonte de dados. Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.

## <a name="set-up-connection-to-marketing"></a>Configurar conexão com o Marketing

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Dynamics 365 Marketing** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Digite a URL do Marketing da sua organização no campo **Endereço do servidor**.

1. Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Marketing.

1. Mapeie o campo ID do Contato na entidade Cliente para a ID de Contato do Dynamics 365.

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

[!INCLUDE [footer-include](includes/footer-banner.md)]
