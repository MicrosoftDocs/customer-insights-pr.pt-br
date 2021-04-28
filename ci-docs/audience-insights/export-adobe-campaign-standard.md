---
title: Exportar dados do Customer Insights para o Adobe Campaign Standard
description: Saiba como usar os segmentos de insights de público-alvo no Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760267"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a><span data-ttu-id="d54ad-103">Usar segmentos do Customer Insights no Adobe Campaign Standard (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="d54ad-103">Use Customer Insights segments in Adobe Campaign Standard (preview)</span></span>

<span data-ttu-id="d54ad-104">Como um usuário de insights de público-alvo para o Dynamics 365 Customer Insights, você pode ter criado segmentos para tornar suas campanhas de marketing mais eficientes, visando públicos-alvo relevantes.</span><span class="sxs-lookup"><span data-stu-id="d54ad-104">As a user of audience insights for Dynamics 365 Customer Insights, you may have created segments to make your marketing campaigns more efficient by targeting relevant audiences.</span></span> <span data-ttu-id="d54ad-105">Para usar um segmento de insights de público-alvo na Adobe Experience Platform e em aplicativos, como o Adobe Campaign Standard, você deve seguir algumas etapas descritas neste artigo.</span><span class="sxs-lookup"><span data-stu-id="d54ad-105">To use a segment from audience insights in Adobe Experience Platform and applications like Adobe Campaign Standard, you need to follow a few steps outlined in this article.</span></span>

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama do processo das etapas descritas neste artigo.":::

## <a name="prerequisites"></a><span data-ttu-id="d54ad-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="d54ad-107">Prerequisites</span></span>

-   <span data-ttu-id="d54ad-108">Licença do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="d54ad-108">Dynamics 365 Customer Insights license</span></span>
-   <span data-ttu-id="d54ad-109">Licença do Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d54ad-109">Adobe Campaign Standard license</span></span>
-   <span data-ttu-id="d54ad-110">Conta de Armazenamento de Blobs do Azure</span><span class="sxs-lookup"><span data-stu-id="d54ad-110">Azure Blob Storage account</span></span>

## <a name="campaign-overview"></a><span data-ttu-id="d54ad-111">Visão Geral da Campanha</span><span class="sxs-lookup"><span data-stu-id="d54ad-111">Campaign Overview</span></span>

<span data-ttu-id="d54ad-112">Para entender melhor como você pode usar segmentos de insights de público-alvo na Adobe Experience Platform, vamos examinar um exemplo de campanha fictício.</span><span class="sxs-lookup"><span data-stu-id="d54ad-112">To better understand how you can use segments from audience insights in Adobe Experience Platform, let’s look at a fictitious sample campaign.</span></span>

<span data-ttu-id="d54ad-113">Vamos supor que sua empresa ofereça um serviço mensal baseado em assinatura para seus clientes nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="d54ad-113">Let’s assume that your company offers a monthly, subscription-based service to your customers in the United States.</span></span> <span data-ttu-id="d54ad-114">Você deseja identificar os clientes com assinaturas que devem ser renovadas nos próximos oito dias, mas que ainda não renovaram a assinatura.</span><span class="sxs-lookup"><span data-stu-id="d54ad-114">You want to identify customers whose subscriptions are due for renewal in the next eight days but haven't yet renewed their subscription.</span></span> <span data-ttu-id="d54ad-115">Para manter esses clientes, você deseja enviar a eles uma oferta promocional por email, usando o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d54ad-115">To keep these customers, you want to send them a promotional offer via email, using Adobe Campaign Standard.</span></span>

<span data-ttu-id="d54ad-116">Neste exemplo, queremos executar a campanha promocional por email uma vez.</span><span class="sxs-lookup"><span data-stu-id="d54ad-116">In this example, we want to run the promotional email campaign once.</span></span> <span data-ttu-id="d54ad-117">Este artigo não aborda o caso de uso de execução da campanha mais de uma vez.</span><span class="sxs-lookup"><span data-stu-id="d54ad-117">This article doesn’t cover the use-case of running the campaign more than once.</span></span> <span data-ttu-id="d54ad-118">No entanto, os insights de público-alvo e o Adobe Campaign Standard também podem ser configurados para funcionar em um cenário de campanha recorrente.</span><span class="sxs-lookup"><span data-stu-id="d54ad-118">However, audience insights and Adobe Campaign Standard can be configured to work for a recurring campaign scenario too.</span></span>

## <a name="identify-your-target-audience"></a><span data-ttu-id="d54ad-119">Identificar o público-alvo</span><span class="sxs-lookup"><span data-stu-id="d54ad-119">Identify your target audience</span></span>

<span data-ttu-id="d54ad-120">Em nosso cenário, presumimos que os endereços de email dos clientes estão disponíveis nos insights de público-alvo e suas preferências promocionais foram analisadas para identificar os membros do segmento.</span><span class="sxs-lookup"><span data-stu-id="d54ad-120">In our scenario, we assume that the email addresses of the customers are available in audience insights and their promotional preferences were analyzed to identify members of the segment.</span></span>

<span data-ttu-id="d54ad-121">O [segmento que você definiu nos insights de público-alvo](segments.md) é chamado **ChurnProneCustomers** e você planeja enviar a promoção por email a esses clientes.</span><span class="sxs-lookup"><span data-stu-id="d54ad-121">The [segment you defined in audience insights](segments.md) is called **ChurnProneCustomers** and you plan to send these customers the email promotion.</span></span>

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de tela da página de segmentos com o segmento ChurnProneCustomers criado.":::

<span data-ttu-id="d54ad-123">O email de oferta que você deseja enviar conterá o nome, o sobrenome e a data de término da assinatura do cliente.</span><span class="sxs-lookup"><span data-stu-id="d54ad-123">The offer email that you want to send out will contain the first name, last name, and the subscription end date of the customer.</span></span> <span data-ttu-id="d54ad-124">Ele informa os clientes sobre o desconto que terão se renovarem a assinatura antes que ela expire.</span><span class="sxs-lookup"><span data-stu-id="d54ad-124">It informs the customers about the discount they’ll get if they renew their subscription before it ends.</span></span>

## <a name="export-your-target-audience"></a><span data-ttu-id="d54ad-125">Exportar o público-alvo</span><span class="sxs-lookup"><span data-stu-id="d54ad-125">Export your target audience</span></span>

### <a name="configure-a-connection"></a><span data-ttu-id="d54ad-126">Configurar uma conexão</span><span class="sxs-lookup"><span data-stu-id="d54ad-126">Configure a connection</span></span>

<span data-ttu-id="d54ad-127">Com nosso público-alvo identificado, podemos configurar a exportação dos insights de público-alvo para uma conta de Armazenamento de Blobs do Azure.</span><span class="sxs-lookup"><span data-stu-id="d54ad-127">With our target audience identified, we can configure the export from audience insights to an Azure Blob Storage account.</span></span>

1. <span data-ttu-id="d54ad-128">Em insights do público-alvo, acesse **Administrador** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-128">In audience insights, go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="d54ad-129">Selecione **Adicionar conexão** e escolha **Campanha da Adobe** para configurar a conexão ou selecione **Configurar** no bloco **Campanha da Adobe**</span><span class="sxs-lookup"><span data-stu-id="d54ad-129">Select **Add connection** and choose **Adobe Campaign** to configure the connection or select **Set up** in the **Adobe Campaign** tile</span></span>

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Bloco de configuração para o Adobe Campaign Standard.":::

1. <span data-ttu-id="d54ad-131">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-131">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="d54ad-132">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="d54ad-132">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="d54ad-133">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="d54ad-133">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="d54ad-134">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="d54ad-134">Choose who can use this connection.</span></span> <span data-ttu-id="d54ad-135">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="d54ad-135">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="d54ad-136">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d54ad-136">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d54ad-137">Insira o **Nome da conta**, a **Chave de conta** e o **Contêiner** da conta de Armazenamento de Blobs do Azure para a qual deseja exportar o segmento.</span><span class="sxs-lookup"><span data-stu-id="d54ad-137">Enter the **Account name**, **Account key**, and **Container** of the Azure Blob Storage account where you want to export the segment to.</span></span>  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de tela da configuração da conta de armazenamento. "::: 

   - <span data-ttu-id="d54ad-139">Para saber mais sobre como encontrar o nome e a chave da conta do Azure Blob Storage, consulte [Gerenciar as configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).</span><span class="sxs-lookup"><span data-stu-id="d54ad-139">To learn more about how to find the Azure Blob storage account name and account key, see [Manage storage account settings in the Azure portal](/azure/storage/common/storage-account-manage).</span></span>

   - <span data-ttu-id="d54ad-140">Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span><span class="sxs-lookup"><span data-stu-id="d54ad-140">To learn how to create a container, see [Create a container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).</span></span>

1. <span data-ttu-id="d54ad-141">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="d54ad-141">Select **Save** to complete the connection.</span></span>

### <a name="configure-an-export"></a><span data-ttu-id="d54ad-142">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="d54ad-142">Configure an export</span></span>

<span data-ttu-id="d54ad-143">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="d54ad-143">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="d54ad-144">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="d54ad-144">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="d54ad-145">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-145">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="d54ad-146">Para criar uma exportação, selecione **Adicionar exportação**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-146">To create a new export, select **Add export**.</span></span>

1. <span data-ttu-id="d54ad-147">No campo **Conexão para exportação**, escolha uma conexão da seção da Campanha do Adobe.</span><span class="sxs-lookup"><span data-stu-id="d54ad-147">In the **Connection for export** field, choose a connection from the Adobe Campaign section.</span></span> <span data-ttu-id="d54ad-148">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="d54ad-148">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="d54ad-149">Escolha o segmento que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="d54ad-149">Choose the segment that you want to export.</span></span> <span data-ttu-id="d54ad-150">Neste exemplo, é **ChurnProneCustomers**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-150">In this example, it’s **ChurnProneCustomers**.</span></span>

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de tela da interface do usuário de seleção de segmentos com o segmento ChurnProneCustomers selecionado.":::

1. <span data-ttu-id="d54ad-152">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-152">Select **Next**.</span></span>

1. <span data-ttu-id="d54ad-153">Agora mapeamos os campos **Origem** do segmento de insights de público-alvo para os nomes de campo **Destino** no esquema de perfil do Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d54ad-153">Now we map the **Source** fields from the audience insights segment to the **Target** field names in the Adobe Campaign Standard profile schema.</span></span>

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapeamento de campo para o conector do Adobe Campaign Standard.":::

   <span data-ttu-id="d54ad-155">Se quiser adicionar mais atributos, selecione **Adicionar atributo**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-155">If you want to add more attributes, select **Add attribute**.</span></span> <span data-ttu-id="d54ad-156">O nome do destino pode ser diferente do nome do campo de origem para que você ainda possa mapear a saída do segmento de insights de público-alvo para o Adobe Campaign Standard se os campos não tiverem o mesmo nome nos dois sistemas.</span><span class="sxs-lookup"><span data-stu-id="d54ad-156">The target name can be different from the source field name so you can still map segment output from audience insights to Adobe Campaign Standard if the fields don’t have the same name in the two systems.</span></span>

   > [!NOTE]
   > <span data-ttu-id="d54ad-157">O endereço de email é usado como um campo de identidade, mas você pode usar qualquer outro identificador do perfil do cliente de seus insights de público-alvo para mapear os dados para o Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d54ad-157">Email address is used as an identity field but you can use any other identifier from your audience insights customer profile to map data to Adobe Campaign Standard.</span></span>

1. <span data-ttu-id="d54ad-158">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-158">Select **Save**.</span></span>

<span data-ttu-id="d54ad-159">Depois de salvar o destino da exportação, você a encontrará em **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="d54ad-159">After saving the export destination, you find it on **Data** > **Exports**.</span></span>

<span data-ttu-id="d54ad-160">Agora você pode [exportar o segmento sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="d54ad-160">You can now [export the segment on demand](export-destinations.md#run-exports-on-demand).</span></span> <span data-ttu-id="d54ad-161">A exportação também será executada a cada [atualização agendada](system.md).</span><span class="sxs-lookup"><span data-stu-id="d54ad-161">The export will also run with every [scheduled refresh](system.md).</span></span>

> [!NOTE]
> <span data-ttu-id="d54ad-162">Certifique-se de que o número de registros no segmento exportado esteja dentro do limite permitido de sua licença do Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d54ad-162">Ensure that the number of records in the exported segment are within the allowed limit of your Adobe Campaign Standard license.</span></span>

<span data-ttu-id="d54ad-163">Os dados exportados são armazenados no contêiner de Armazenamento de Blobs do Azure que você configurou acima.</span><span class="sxs-lookup"><span data-stu-id="d54ad-163">Exported data is stored in the Azure Blob storage container you configured above.</span></span> <span data-ttu-id="d54ad-164">O seguinte caminho de pasta é criado automaticamente em seu contêiner:</span><span class="sxs-lookup"><span data-stu-id="d54ad-164">The following folder path is automatically created in your container:</span></span>

<span data-ttu-id="d54ad-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span><span class="sxs-lookup"><span data-stu-id="d54ad-165">*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*</span></span>

<span data-ttu-id="d54ad-166">Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span><span class="sxs-lookup"><span data-stu-id="d54ad-166">Example: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv</span></span>

## <a name="configure-adobe-campaign-standard"></a><span data-ttu-id="d54ad-167">Configurar o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d54ad-167">Configure Adobe Campaign Standard</span></span>

<span data-ttu-id="d54ad-168">Quando um segmento de insights de público-alvo é exportado, ele contém as colunas que você selecionou ao definir o destino da exportação na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="d54ad-168">When a segment from audience insights is exported, it contains the columns you selected while defining the export destination in the previous step.</span></span> <span data-ttu-id="d54ad-169">Esses dados podem ser usados para [criar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span><span class="sxs-lookup"><span data-stu-id="d54ad-169">This data can be used to [create profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).</span></span>

<span data-ttu-id="d54ad-170">Para usar o segmento no Adobe Campaign Standard, precisamos estender o esquema do perfil no Adobe Campaign Standard para incluir dois campos adicionais.</span><span class="sxs-lookup"><span data-stu-id="d54ad-170">To use the segment in Adobe Campaign Standard, we need to extend the profile schema in Adobe Campaign Standard to include two additional fields.</span></span> <span data-ttu-id="d54ad-171">Saiba como [estender o recurso de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) com novos campos no Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d54ad-171">Learn how to [extend the profile resource](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) with new fields in Adobe Campaign Standard.</span></span>

<span data-ttu-id="d54ad-172">Em nosso exemplo, esses campos são *Nome do segmento e Data do segmento (opcional).*</span><span class="sxs-lookup"><span data-stu-id="d54ad-172">In our example, these fields are *Segment Name and Segment Date (optional).*</span></span>

<span data-ttu-id="d54ad-173">Usaremos esses campos para identificar os perfis no Adobe Campaign Standard para os quais queremos direcionar para esta campanha.</span><span class="sxs-lookup"><span data-stu-id="d54ad-173">We will use these fields to identify the profiles in Adobe Campaign Standard we want to target for this campaign.</span></span>

<span data-ttu-id="d54ad-174">Se não houver outros registros no Adobe Campaign Standard, além dos que vai importar, você poderá ignorar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="d54ad-174">If there are no other records in Adobe Campaign Standard, other than what you are going to import, you can skip this step.</span></span>

## <a name="import-data-into-adobe-campaign-standard"></a><span data-ttu-id="d54ad-175">Importar dados para o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d54ad-175">Import data into Adobe Campaign Standard</span></span>

<span data-ttu-id="d54ad-176">Agora que tudo está pronto, precisamos importar os dados do público-alvo preparados a partir dos percepções de público-alvo para o Adobe Campaign Standard para criar perfis.</span><span class="sxs-lookup"><span data-stu-id="d54ad-176">Now that everything is in place, we need to import the prepared audience data from audience insights into Adobe Campaign Standard to create profiles.</span></span> <span data-ttu-id="d54ad-177">Saiba [como importar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando um fluxo de trabalho.</span><span class="sxs-lookup"><span data-stu-id="d54ad-177">Learn [how to import profiles in Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) using a workflow.</span></span>

<span data-ttu-id="d54ad-178">O fluxo de trabalho de importação na imagem abaixo foi configurado para ser executado a cada 8 horas e procura segmentos de insights de público-alvo exportados (arquivo .csv no Armazenamento de Blobs do Azure).</span><span class="sxs-lookup"><span data-stu-id="d54ad-178">The import workflow in the image below has been configured to run every 8 hours and looks for exported audience insights segments (.csv file in Azure Blob Storage).</span></span> <span data-ttu-id="d54ad-179">O fluxo de trabalho extrai o conteúdo do arquivo .csv em uma ordem de coluna especificada.</span><span class="sxs-lookup"><span data-stu-id="d54ad-179">The workflow extracts the .csv file content in a specified column order.</span></span> <span data-ttu-id="d54ad-180">Este fluxo de trabalho foi criado para executar o tratamento básico de erros e garantir que cada registro tenha um endereço de email antes de hidratar os dados no Adobe Campaign Standard.</span><span class="sxs-lookup"><span data-stu-id="d54ad-180">This workflow has been built to perform basic error handling and ensure that each record has an email address before hydrating the data in Adobe Campaign Standard.</span></span> <span data-ttu-id="d54ad-181">O fluxo de trabalho também extrai o nome do segmento do nome do arquivo antes de executar upsert nos dados do Perfil do ACS.</span><span class="sxs-lookup"><span data-stu-id="d54ad-181">The workflow also extracts the segment name from the filename before upserting into ACS Profile data.</span></span>

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de tela de um fluxo de trabalho de importação na interface de usuário do Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a><span data-ttu-id="d54ad-183">Recuperar o público-alvo no Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d54ad-183">Retrieve the audience in Adobe Campaign Standard</span></span>

<span data-ttu-id="d54ad-184">Depois que os dados forem importados para o Adobe Campaign Standard, você [poderá criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes com base no *Nome do Segmento* e na *Data do Segmento* para selecionar os perfis que foram identificados para nossa campanha de exemplo.</span><span class="sxs-lookup"><span data-stu-id="d54ad-184">Once the data is imported into Adobe Campaign Standard, you [can create a workflow](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) and [query](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) the customers based on the *Segment Name* and *Segment Date* to select profiles that were identified for our sample campaign.</span></span>

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a><span data-ttu-id="d54ad-185">Criar e enviar o email usando o Adobe Campaign Standard</span><span class="sxs-lookup"><span data-stu-id="d54ad-185">Create and send the email using Adobe Campaign Standard</span></span>

<span data-ttu-id="d54ad-186">Crie o conteúdo do email e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o email.</span><span class="sxs-lookup"><span data-stu-id="d54ad-186">Create the email content and then [test and send](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) your email.</span></span>

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplo de email com oferta de renovação do Adobe Campaign Standard.":::
