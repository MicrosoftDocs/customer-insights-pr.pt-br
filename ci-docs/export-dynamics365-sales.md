---
title: Exportar segmentos para o Dynamics 365 Sales (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Dynamics 365 Sales.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: b8e756313ca037dca41cb25587229808f0c584c9
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080797"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportar segmentos para o Dynamics 365 Sales (versão preliminar)

Use seus dados de cliente para criar listas de marketing, fluxos de trabalho de acompanhamento e enviar promoções com o Dynamics 365 Sales.

## <a name="known-limitations"></a>Limitações conhecidas

- As exportações para o Dynamics 365 Sales estão limitadas a 100 mil membros por segmento.
- As exportações de segmentos para o Dynamics 365 Sales podem levar até 3 horas para serem concluídas. 

## <a name="prerequisite-for-connection"></a>Pré-requisitos para conexão

1. Os registros de contatos devem estar presentes no Dynamics 365 Sales antes de exportar um segmento do Customer Insights para o Sales. Leia mais sobre como ingerir contatos de [Dynamics 365 Sales usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > A exportação de segmentos do Customer Insights para Vendas não criará novos registros de contato em instâncias de Vendas. Os registros de contato de Vendas devem ser ingeridos no Customer Insights e usados como fonte de dados. Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.

## <a name="set-up-the-connection-to-sales"></a>Configurar a conexão com o Sales

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Dynamics 365 Sales** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Digite a URL do Sales da sua organização no campo **Endereço do servidor**.

1. Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Sales.

1. Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Dynamics 365 Sales. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Escolha um ou mais segmentos.

1. Selecione **Salvar**

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

[!INCLUDE [footer-include](includes/footer-banner.md)]
