---
title: Exportar segmentos para o Adobe Experience Platform (versão preliminar)
description: Saiba como usar segmentos do Customer Insights no Adobe Experience Platform.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: fcb43e0956c6d1f0ef36b222dd2b718906364244
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195276"
---
# <a name="export-segments-to-adobe-experience-platform-preview"></a>Exportar segmentos para o Adobe Experience Platform (versão preliminar)

Exporte segmentos que visam públicos-alvo relevantes para o Adobe Experience Platform.

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama do processo das etapas descritas neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

- Uma licença do Adobe Experience Platform.
- Uma licença do Adobe Campaign Standard.
- O nome de uma [conta do Armazenamento de Blobs do Azure](/azure/storage/blobs/create-data-lake-storage-account) e a chave de conta. Para encontrar o nome e a chave, consulte [Gerenciar configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).
- Um [contêiner do Armazenamento de Blobs do Azure](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

## <a name="campaign-overview"></a>Visão Geral da Campanha

Para entender melhor como usar segmentos do Customer Insights no Adobe Experience Platform, vejamos uma campanha de amostra fictícia.

Vamos supor que sua empresa ofereça um serviço mensal baseado em assinatura para seus clientes nos Estados Unidos. Você deseja identificar os clientes com assinaturas que devem ser renovadas nos próximos oito dias, mas que ainda não renovaram a assinatura. Para manter esses clientes, você deseja enviar a eles uma oferta promocional por email, usando a Adobe Experience Platform.

Neste exemplo, queremos executar a campanha promocional por email uma vez. Este artigo não aborda o caso de uso de execução da campanha mais de uma vez.

## <a name="identify-your-target-audience"></a>Identificar o público-alvo

Em nosso cenário, supomos que os endereços de email dos clientes estão disponíveis no Customer Insights e suas preferências promocionais foram analisadas para identificar membros do segmento.

O [segmento que você definiu no Customer Insights](segments.md) é chamado de **ChurnProneCustomers** e você pretende enviar a esses clientes a promoção por email.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de tela da página de segmentos com o segmento ChurnProneCustomers criado.":::

O email de oferta que você deseja enviar conterá o nome, o sobrenome e a data de término da assinatura do cliente. Ele informa os clientes sobre o desconto que terão se renovarem a assinatura antes que ela expire.

## <a name="export-your-target-audience"></a>Exportar o público-alvo

Vamos configurar a exportação do Customer Insights para uma conta do Armazenamento de Blobs do Azure.

### <a name="set-up-connection-to-azure-blob-storage"></a>Configurar a conexão com o Armazenamento de Blobs do Azure

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Armazenamento de Blobs do Azure**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Digite o **Nome da conta**, **Chave da conta** e **Contêiner** da sua conta de Armazenamento de Blobs para a qual deseja exportar o segmento.  

   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de tela da configuração da conta de armazenamento. ":::

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

### <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do Armazenamento de Blobs do Azure. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Escolha o segmento que você deseja exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de tela da interface do usuário de seleção de segmentos com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

> [!NOTE]
> Certifique-se de que o número de registros no segmento exportado esteja dentro do limite permitido da sua licença do Adobe Campaign Standard.

Os dados exportados são armazenados no contêiner do Armazenamento de Blobs do Azure que você configurou. Os seguintes caminhos de pasta são criados automaticamente no seu contêiner:

- Para entidades de origem e entidades geradas pelo sistema:  

  *%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*

  Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv

- O *model.json* para as entidades exportadas residirá no nível do *%ExportDestinationName%*.

  Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a>Definir o modelo de dados de experiência (XDM) na Adobe Experience Platform

Antes de usar os dados exportados do Customer Insights no Adobe Experience Platform, defina o esquema do Modelo de Dados de Experiência e [configure os dados para o perfil do cliente em tempo real](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).

Saiba [o que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e entenda as [noções básicas de composição de esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).

## <a name="import-data-into-adobe-experience-platform"></a>Importar dados para o Adobe Experience Platform

Importe os dados de público-alvo preparados do Customer Insights para o Adobe Experience Platform.

1. [Crie uma conexão da fonte de dados do Armazenamento de Blobs do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).

1. [Configure um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para uma conexão em lote de armazenamento em nuvem para importar a saída do segmento do Customer Insights para o Adobe Experience Platform.

## <a name="create-an-audience-in-adobe-campaign-standard"></a>Crie um público-alvo no Adobe Campaign Standard

Para enviar o email para esta campanha, usaremos o Adobe Campaign Standard.

1. [Crie um público-alvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) no Adobe Campaign Standard usando os dados do Adobe Experience Platform.

1. [Use o construtor de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/audience-destinations/aep-using-segment-builder.html) no Adobe Campaign Standard para definir um público-alvo com base nos dados do Adobe Experience Platform.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o email usando o Adobe Campaign Standard

Crie o conteúdo do email e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o email.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplo de email com oferta de renovação do Adobe Campaign Standard.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
