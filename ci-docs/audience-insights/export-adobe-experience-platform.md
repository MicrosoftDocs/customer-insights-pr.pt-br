---
title: Exportar dados do Customer Insights para a Adobe Experience Platform
description: Saiba como usar os segmentos de insights de público-alvo na Adobe Experience Platform.
ms.date: 02/26/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: d1856861562be55c6d1d051050fe965560fa42f8
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596255"
---
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a>Usar segmentos do Customer Insights na Adobe Experience Platform (versão preliminar)

Como um usuário de insights de público-alvo para o Dynamics 365 Customer Insights, você pode ter criado segmentos para tornar suas campanhas de marketing mais eficientes, visando públicos-alvo relevantes. Para usar um segmento de insights de público-alvo na Adobe Experience Platform e em aplicativos, como o Adobe Campaign Standard, você deve seguir algumas etapas descritas neste artigo.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama do processo das etapas descritas neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

-   Licença do Dynamics 365 Customer Insights
-   Licença da Adobe Experience Platform
-   Licença do Adobe Campaign Standard
-   Conta de Armazenamento de Blobs do Azure

## <a name="campaign-overview"></a>Visão Geral da Campanha

Para entender melhor como você pode usar segmentos de insights de público-alvo na Adobe Experience Platform, vamos examinar um exemplo de campanha fictício.

Vamos supor que sua empresa ofereça um serviço mensal baseado em assinatura para seus clientes nos Estados Unidos. Você deseja identificar os clientes com assinaturas que devem ser renovadas nos próximos oito dias, mas que ainda não renovaram a assinatura. Para manter esses clientes, você deseja enviar a eles uma oferta promocional por email, usando a Adobe Experience Platform.

Neste exemplo, queremos executar a campanha promocional por email uma vez. Este artigo não aborda o caso de uso de execução da campanha mais de uma vez.

## <a name="identify-your-target-audience"></a>Identificar o público-alvo

Em nosso cenário, presumimos que os endereços de email dos clientes estão disponíveis nos insights de público-alvo e suas preferências promocionais foram analisadas para identificar os membros do segmento.

O [segmento que você definiu nos insights de público-alvo](segments.md) é chamado **ChurnProneCustomers** e você planeja enviar a promoção por email a esses clientes.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de tela da página de segmentos com o segmento ChurnProneCustomers criado.":::

O email de oferta que você deseja enviar conterá o nome, o sobrenome e a data de término da assinatura do cliente. Ele informa os clientes sobre o desconto que terão se renovarem a assinatura antes que ela expire.

## <a name="export-your-target-audience"></a>Exportar o público-alvo

Com nosso público-alvo identificado, podemos configurar a exportação dos insights de público-alvo para uma conta de Armazenamento de Blobs do Azure.

1. Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.

1. No bloco **Armazenamento de Blobs do Azure**, selecione **Configurar**.

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Bloco de configuração para o Armazenamento de Blobs do Azure.":::

1. Forneça um **Nome de exibição** para este novo destino de exportação e, em seguida, insira o **Nome da conta**, a **Chave da conta** e o **Contêiner** da conta do Armazenamento de Blobs do Azure para a qual você deseja exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de tela da configuração da conta de armazenamento. "::: 

   - Para saber mais sobre como encontrar o nome e a chave da conta do Azure Blob Storage, consulte [Gerenciar as configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

   - Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Avançar**.

1. Escolha o segmento que você deseja exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de tela da interface do usuário de seleção de segmentos com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Salvar**.

Depois de salvar o destino da exportação, você o encontrará em **Administração** > **Exportações** > **Meus destinos de exportação**.

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Captura de tela com lista de exportações e segmento de exemplo em destaque.":::

Agora você pode [exportar o segmento sob demanda](export-destinations.md#export-data-on-demand). A exportação também será executada a cada [atualização agendada](system.md).

> [!NOTE]
> Certifique-se de que o número de registros no segmento exportado esteja dentro do limite permitido de sua licença do Adobe Campaign Standard.

Os dados exportados são armazenados no contêiner de Armazenamento de Blobs do Azure que você configurou acima. O seguinte caminho de pasta é criado automaticamente em seu contêiner:

*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

O *model.json* para as entidades exportadas residirá no nível do *%ExportDestinationName%*.

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir o Experience Data Model (XDM) na Adobe Experience Platform

Antes que os dados exportados dos insights de público-alvo possam ser usados na Adobe Experience Platform, precisamos definir o esquema do Experience Data Model e [configurar os dados para o Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saiba [o que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e entenda as [noções básicas de composição de esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar dados para a Adobe Experience Platform

Agora que tudo está pronto, precisamos importar os dados do público-alvo preparados a partir dos percepções de público-alvo para a Adobe Experience Platform.

Primeiro, [crie uma conexão da fonte de dados do Armazenamento de Blobs do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).    

Depois que definir a conexão da fonte de dados, [configure um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para uma conexão em lote de armazenamento em nuvem para importar a saída do segmento de insights de público-alvo para a Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Criar um público-alvo no Adobe Campaign Standard

Para enviar o email desta campanha, usaremos o Adobe Campaign Standard. Depois de importar os dados para a Adobe Experience Platform, precisamos [criar um público-alvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) no Adobe Campaign Standard usando os dados da Adobe Experience Platform.

Saiba como [usar construtor de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) no Adobe Campaign Standard para definir um público-alvo com base nos dados da Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o email usando o Adobe Campaign Standard

Crie o conteúdo do email e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o email.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplo de email com oferta de renovação do Adobe Campaign Standard.":::