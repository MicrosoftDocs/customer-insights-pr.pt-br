---
title: Exportar segmentos para o Dynamics 365 Sales (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Dynamics 365 Sales.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
searchScope:
- ci-export
- customerInsights
ms.openlocfilehash: c3497f4625cada49ae33c6987e58994a15536f9b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195967"
---
# <a name="export-segments-to-dynamics-365-sales-preview"></a>Exportar segmentos para o Dynamics 365 Sales (versão preliminar)

Use seus dados de cliente para criar listas de marketing, fluxos de trabalho de acompanhamento e enviar promoções com o Dynamics 365 Sales.

## <a name="prerequisites"></a>Pré-requisitos

Os registros de contatos devem estar presentes no Dynamics 365 Sales antes de exportar um segmento do Customer Insights para o Sales. Leia mais sobre como ingerir contatos de [Dynamics 365 Sales usando Microsoft Dataverse](connect-dataverse-managed-lake.md).

   > [!NOTE]
   > A exportação de segmentos do Customer Insights para Vendas não criará novos registros de contato em instâncias de Vendas. Os registros de contato de Vendas devem ser ingeridos no Customer Insights e usados como fonte de dados. Também será necessário incluí-los na entidade unificada do Customer para mapear IDs de clientes para IDs de contatos antes que os segmentos possam ser exportados.

## <a name="known-limitations"></a>Limitações conhecidas

As exportações para o Dynamics 365 Sales estão limitadas a 100.000 por segmento, podendo levar até 3 horas para serem concluídas.

## <a name="set-up-connection-to-sales"></a>Configurar conexão com o Sales

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Dynamics 365 Sales**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Digite a URL do Sales da sua organização no campo **Endereço do servidor**.

1. Na seção **Conta de administrador do servidor**, selecione **Entrar** e escolha uma conta do Dynamics 365 Sales.

1. Mapeie um campo de ID de cliente para a ID de Contato do Dynamics 365.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Dynamics 365 Sales. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Selecione o campo ID de Contato na entidade Cliente que corresponde à ID de Contato do Dynamics 365.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
