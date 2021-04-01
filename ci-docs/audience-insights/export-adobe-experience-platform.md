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
# <a name="use-customer-insights-segments-in-adobe-experience-platform-preview"></a><span data-ttu-id="bd332-103">Usar segmentos do Customer Insights na Adobe Experience Platform (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="bd332-103">Use Customer Insights segments in Adobe Experience Platform (preview)</span></span>

<span data-ttu-id="bd332-104">Como um usuário de insights de público-alvo para o Dynamics 365 Customer Insights, você pode ter criado segmentos para tornar suas campanhas de marketing mais eficientes, visando públicos-alvo relevantes.</span><span class="sxs-lookup"><span data-stu-id="bd332-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="bd332-105">Para usar um segmento de insights de público-alvo na Adobe Experience Platform e em aplicativos, como o Adobe Campaign Standard, você deve seguir algumas etapas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="bd332-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/AEP-flow.png" alt-text="Diagrama do processo das etapas descritas neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="bd332-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="bd332-107">Prerequisites</span></span>

-   <span data-ttu-id="bd332-108">Licença do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="bd332-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="bd332-109">Licença da Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="bd332-109">Adobe Experience Platform license</span></span>
-   <span data-ttu-id="bd332-110">Licença do Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="bd332-110">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="bd332-111">Conta de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="bd332-111">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="bd332-112">Visão Geral da Campanha</span><span class="sxs-lookup"><span data-stu-id="bd332-112">Campaign Overview</span></span>

<span data-ttu-id="bd332-113">Para entender melhor como você pode usar segmentos de insights de público-alvo na Adobe Experience Platform, vamos examinar um exemplo de campanha fictício.</span><span class="sxs-lookup"><span data-stu-id="bd332-113">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="bd332-114">Vamos supor que sua empresa ofereça um serviço mensal baseado em assinatura para seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="bd332-114">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="bd332-115">Você deseja identificar os clientes com assinaturas que devem ser renovadas nos próximos oito dias, mas que ainda não renovaram a assinatura.</span><span class="sxs-lookup"><span data-stu-id="bd332-115">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="bd332-116">Para manter esses clientes, você deseja enviar a eles uma oferta promocional por email, usando a Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd332-116">To keep these customers, you want to send them a promotional offer via email, using Adobe Experience Platform.</span></span>

<span data-ttu-id="bd332-117">Neste exemplo, queremos executar a campanha promocional por email uma vez.</span><span class="sxs-lookup"><span data-stu-id="bd332-117">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="bd332-118">Este artigo não aborda o caso de uso de execução da campanha mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="bd332-118">This article doesn’t cover the use-case of running the campaign more than once.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="bd332-119">Identificar o público-alvo</span><span class="sxs-lookup"><span data-stu-id="bd332-119">Identify your target audience</span></span>

<span data-ttu-id="bd332-120">Em nosso cenário, presumimos que os endereços de email dos clientes estão disponíveis nos insights de público-alvo e suas preferências promocionais foram analisadas para identificar os membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="bd332-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="bd332-121">O [segmento que você definiu nos insights de público-alvo](segments.md) é chamado **ChurnProneCustomers** e você planeja enviar a promoção por email a esses clientes.</span><span class="sxs-lookup"><span data-stu-id="bd332-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de tela da página de segmentos com o segmento ChurnProneCustomers criado.":::

<span data-ttu-id="bd332-123">O email de oferta que você deseja enviar conterá o nome, o sobrenome e a data de término da assinatura do cliente.</span><span class="sxs-lookup"><span data-stu-id="bd332-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="bd332-124">Ele informa os clientes sobre o desconto que terão se renovarem a assinatura antes que ela expire.</span><span class="sxs-lookup"><span data-stu-id="bd332-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="bd332-125">Exportar o público-alvo</span><span class="sxs-lookup"><span data-stu-id="bd332-125">Export your target audience</span></span>

<span data-ttu-id="bd332-126">Com nosso público-alvo identificado, podemos configurar a exportação dos insights de público-alvo para uma conta de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="bd332-126">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="bd332-127">Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="bd332-127">In audience insights, go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="bd332-128">No bloco **Armazenamento de Blobs do Azure**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="bd332-128">In the **Azure Blob Storage** tile, select **Set up**.</span></span>

   :::image type="content" source="media/export-azure-blob-storage-tile.png" alt-text="Bloco de configuração para o Armazenamento de Blobs do Azure.":::

1. <span data-ttu-id="bd332-130">Forneça um **Nome de exibição** para este novo destino de exportação e, em seguida, insira o **Nome da conta**, a **Chave da conta** e o **Contêiner** da conta do Armazenamento de Blobs do Azure para a qual você deseja exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="bd332-130">Provide a **Display name** for this new export destination and then enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de tela da configuração da conta de armazenamento. "::: 

   - <span data-ttu-id="bd332-132">Para saber mais sobre como encontrar o nome e a chave da conta do Azure Blob Storage, consulte [Gerenciar as configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="bd332-132">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="bd332-133">Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="bd332-133">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="bd332-134">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="bd332-134">Select **Next**.</span></span>

1. <span data-ttu-id="bd332-135">Escolha o segmento que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="bd332-135">Choose the segment that you want to export.</span></span> <span data-ttu-id="bd332-136">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="bd332-136">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de tela da interface do usuário de seleção de segmentos com o segmento ChurnProneCustomers selecionado.":::

1. <span data-ttu-id="bd332-138">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="bd332-138">Select **Save**.</span></span>

<span data-ttu-id="bd332-139">Depois de salvar o destino da exportação, você o encontrará em **Administração** > **Exportações** > **Meus destinos de exportação**.</span><span class="sxs-lookup"><span data-stu-id="bd332-139">After saving the export destination, you find it on **Admin** > **Exports** > **My export destinations**.</span></span>

:::image type="content" source="media/export-destination-azure-blob-storage.png" alt-text="Captura de tela com lista de exportações e segmento de exemplo em destaque.":::

<span data-ttu-id="bd332-141">Agora você pode [exportar o segmento sob demanda](export-destinations.md#export-data-on-demand).</span><span class="sxs-lookup"><span data-stu-id="bd332-141">You can now [export the segment on demand](export-destinations.md#export-data-on-demand).</span></span> <span data-ttu-id="bd332-142">A exportação também será executada a cada [atualização agendada](system.md).</span><span class="sxs-lookup"><span data-stu-id="bd332-142">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bd332-143">Certifique-se de que o número de registros no segmento exportado esteja dentro do limite permitido de sua licença do Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="bd332-143">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="bd332-144">Os dados exportados são armazenados no contêiner de Armazenamento de Blobs do Azure que você configurou acima.</span><span class="sxs-lookup"><span data-stu-id="bd332-144">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="bd332-145">O seguinte caminho de pasta é criado automaticamente em seu contêiner:</span><span class="sxs-lookup"><span data-stu-id="bd332-145">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="bd332-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span><span class="sxs-lookup"><span data-stu-id="bd332-146">*%ContainerName%/CustomerInsights_%instanceID%/%ExportDestinationName%/%EntityName%/%Year%/%Month%/%Day%/%HHMM%/%EntityName%_%PartitionId%.csv*</span></span>

<span data-ttu-id="bd332-147">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span><span class="sxs-lookup"><span data-stu-id="bd332-147">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/BlobExport/ChurnSegmentDemo/2021/02/16/1433/ChurnProneCustomers_1.csv</span></span>

<span data-ttu-id="bd332-148">O *model.json* para as entidades exportadas residirá no nível do *%ExportDestinationName%*.</span><span class="sxs-lookup"><span data-stu-id="bd332-148">The *model.json* for the exported entities resides at the *%ExportDestinationName%* level.</span></span>

<span data-ttu-id="bd332-149">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span><span class="sxs-lookup"><span data-stu-id="bd332-149">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo/model.json</span></span>

## <a name="define-experience-data-model-xdm-in-adobe-experience-platform"></a><span data-ttu-id="bd332-150">Definir o Experience Data Model (XDM) na Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="bd332-150">Define Experience Data Model (XDM) in Adobe Experience Platform</span></span>

<span data-ttu-id="bd332-151">Antes que os dados exportados dos insights de público-alvo possam ser usados na Adobe Experience Platform, precisamos definir o esquema do Experience Data Model e [configurar os dados para o Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span><span class="sxs-lookup"><span data-stu-id="bd332-151">Before the exported data from audience insights can be used within Adobe Experience Platform, we need to define the Experience Data Model schema and [configure the data for the Real-time Customer Profile](https://experienceleague.adobe.com/docs/experience-platform/profile/tutorials/dataset-configuration.html#tutorials).</span></span>

<span data-ttu-id="bd332-152">Saiba [o que é XDM](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) e entenda as [noções básicas de composição de esquema](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span><span class="sxs-lookup"><span data-stu-id="bd332-152">Learn [what XDM is](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html) and understand the [basics of schema composition](https://experienceleague.adobe.com/docs/experience-platform/xdm/schema/composition.html#schema).</span></span>

## <a name="import-data-into-adobe-experience-platform"></a><span data-ttu-id="bd332-153">Importar dados para a Adobe Experience Platform</span><span class="sxs-lookup"><span data-stu-id="bd332-153">Import data into Adobe Experience Platform</span></span>

<span data-ttu-id="bd332-154">Agora que tudo está pronto, precisamos importar os dados do público-alvo preparados a partir dos percepções de público-alvo para a Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd332-154">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Experience Platform.</span></span>

<span data-ttu-id="bd332-155">Primeiro, [crie uma conexão da fonte de dados do Armazenamento de Blobs do Azure](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span><span class="sxs-lookup"><span data-stu-id="bd332-155">First, [create an Azure Blob Storage source connection](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/create/cloud-storage/blob.html#getting-started).</span></span>    

<span data-ttu-id="bd332-156">Depois que definir a conexão da fonte de dados, [configure um fluxo de dados](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) para uma conexão em lote de armazenamento em nuvem para importar a saída do segmento de insights de público-alvo para a Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd332-156">After defining the source connection, [configure a dataflow](https://experienceleague.adobe.com/docs/experience-platform/sources/ui-tutorials/dataflow/cloud-storage.html#ui-tutorials) for a cloud storage batch connection to import the segment output from audience insights into Adobe Experience Platform.</span></span>

## <a name="create-an-audience-in-adobe-campaign-standard"></a><span data-ttu-id="bd332-157">Criar um público-alvo no Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="bd332-157">Create an audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="bd332-158">Para enviar o email desta campanha, usaremos o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="bd332-158">To send the email for this campaign, we will use Adobe Campaign Standard.</span></span> <span data-ttu-id="bd332-159">Depois de importar os dados para a Adobe Experience Platform, precisamos [criar um público-alvo](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) no Adobe Campaign Standard usando os dados da Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd332-159">After importing the data into Adobe Experience Platform, we need to [create an audience](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/get-started-profiles-and-audiences.html#permission) in Adobe Campaign Standard using the data in Adobe Experience Platform.</span></span>

<span data-ttu-id="bd332-160">Saiba como [usar construtor de segmentos](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) no Adobe Campaign Standard para definir um público-alvo com base nos dados da Adobe Experience Platform.</span><span class="sxs-lookup"><span data-stu-id="bd332-160">Learn how to [use segment builder](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/working-with-adobe-experience-platform/aep-using-segment-builder.html#building-a-segment) in Adobe Campaign Standard to define an audience based on the data in Adobe Experience Platform.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="bd332-161">Criar e enviar o email usando o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="bd332-161">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="bd332-162">Crie o conteúdo do email e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o email.</span><span class="sxs-lookup"><span data-stu-id="bd332-162">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplo de email com oferta de renovação do Adobe Campaign Standard.":::