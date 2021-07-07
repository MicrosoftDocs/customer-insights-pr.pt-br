---
title: Exportar dados do Customer Insights para o Salesforce Marketing Cloud
description: Saiba como configurar a conexão e exportar para o Salesforce Marketing Cloud.
ms.date: 06/24/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 123f8b2dbb6140785dec6c1b4164d2f513f66a53
ms.sourcegitcommit: 057079532e31c12bac36f374857ba3dc847d6ad0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6314573"
---
# <a name="export-segments-and-other-data-to-salesforce-marketing-cloud-preview"></a><span data-ttu-id="55222-103">Exportar segmentos e outros dados para o Salesforce Marketing Cloud (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="55222-103">Export segments and other data to Salesforce Marketing Cloud (preview)</span></span>

<span data-ttu-id="55222-104">Use seus dados do cliente no Salesforce Marketing Cloud ao exportá-los por meio de um local SFTP (Secure File Transfer Protocol, protocolo de transferência segura de arquivo).</span><span class="sxs-lookup"><span data-stu-id="55222-104">Use your customer data in Salesforce Marketing Cloud by exporting them through a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="55222-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="55222-105">Prerequisites for connection</span></span>

- <span data-ttu-id="55222-106">Disponibilidade de um host SFTP e as credenciais de administrador correspondentes.</span><span class="sxs-lookup"><span data-stu-id="55222-106">Availability of an SFTP host and corresponding admin credentials.</span></span> [<span data-ttu-id="55222-107">Como configurar locais SFTP para o Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="55222-107">How to setup SFTP locations for Salesforce Marketing Cloud</span></span>](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="known-limitations"></a><span data-ttu-id="55222-108">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="55222-108">Known limitations</span></span>

- <span data-ttu-id="55222-109">O tempo de execução de uma exportação depende do desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="55222-109">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="55222-110">Recomendamos dois núcleos de CPU e 1Gb de memória como configuração mínima do servidor.</span><span class="sxs-lookup"><span data-stu-id="55222-110">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="55222-111">A exportação de entidades com até 100 milhões de perfis de cliente pode levar 90 minutos usando as configurações mínimas recomendadas.</span><span class="sxs-lookup"><span data-stu-id="55222-111">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration.</span></span> 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a><span data-ttu-id="55222-112">Configurar a conexão para o Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="55222-112">Set up the connection to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="55222-113">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="55222-113">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="55222-114">Selecione **Adicionar conexão** e escolha **Salesforce Marketing Cloud** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="55222-114">Select **Add connection** and choose **Salesforce Marketing Cloud** to configure the connection.</span></span>

1. <span data-ttu-id="55222-115">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="55222-115">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="55222-116">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="55222-116">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="55222-117">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="55222-117">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="55222-118">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="55222-118">Choose who can use this connection.</span></span> <span data-ttu-id="55222-119">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="55222-119">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="55222-120">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="55222-120">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="55222-121">Forneça um **Nome de usuário**, uma **Senha**, um **Nome de host** e uma **Pasta de exportação** para sua conta SFTP.</span><span class="sxs-lookup"><span data-stu-id="55222-121">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="55222-122">Selecione **Verificar** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="55222-122">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="55222-123">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="55222-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="55222-124">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="55222-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="55222-125">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="55222-125">Configure an export</span></span>

<span data-ttu-id="55222-126">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="55222-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="55222-127">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="55222-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="55222-128">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="55222-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="55222-129">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="55222-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="55222-130">No campo **Conexão para exportação**, escolha uma conexão da seção do SFTP.</span><span class="sxs-lookup"><span data-stu-id="55222-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="55222-131">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="55222-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="55222-132">Escolha se você deseja exportar seus dados **Compactados com o Gzip** ou **Descompactados** e o **delimitador de campo** para os arquivos exportados.</span><span class="sxs-lookup"><span data-stu-id="55222-132">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="55222-133">Selecione as entidades, por exemplo, segmentos que deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="55222-133">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="55222-134">Cada entidade selecionada será dividida em até cinco arquivos de saída quando exportada.</span><span class="sxs-lookup"><span data-stu-id="55222-134">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="55222-135">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="55222-135">Select **Save**.</span></span>

<span data-ttu-id="55222-136">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="55222-136">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="55222-137">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="55222-137">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="55222-138">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="55222-138">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a><span data-ttu-id="55222-139">Importar dados do Customer Insights do local SFTP para o Salesforce Marketing Cloud</span><span class="sxs-lookup"><span data-stu-id="55222-139">Import Customer Insights data from SFTP location to Salesforce Marketing Cloud</span></span>

1. <span data-ttu-id="55222-140">Crie [extensões de dados no Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o arquivo de dados do Customer Insights do local SFTP.</span><span class="sxs-lookup"><span data-stu-id="55222-140">Create [data extensions in Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) to import the Customer Insights data file from the SFTP location.</span></span>

2. <span data-ttu-id="55222-141">[Importe os dados do local SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) na extensão de dados do Salesforce Marketing Cloud.</span><span class="sxs-lookup"><span data-stu-id="55222-141">[Import the data from the SFTP location](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) into the Salesforce Marketing Cloud data extension.</span></span> 

3. <span data-ttu-id="55222-142">Configure a automação para importar os dados nas extensões de dados.</span><span class="sxs-lookup"><span data-stu-id="55222-142">Set up the automation to import the data into the data extensions.</span></span> <span data-ttu-id="55222-143">Saiba mais sobre [automações de transferência de arquivo e automações agendadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="55222-143">Learn more about [file drop automations and scheduled automations](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).</span></span>

   <span data-ttu-id="55222-144">Defina uma [automação de transferência de dados](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou uma [automação agendada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="55222-144">Define a [file drop automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) or a  [scheduled automation](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).</span></span> 

<span data-ttu-id="55222-145">Veja a seguir um exemplo de uma [automação com o SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span><span class="sxs-lookup"><span data-stu-id="55222-145">Here's an example of [an automation with SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="55222-146">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="55222-146">Data privacy and compliance</span></span>

<span data-ttu-id="55222-147">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados via SFTP, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="55222-147">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="55222-148">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o destino de exportação cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="55222-148">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="55222-149">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="55222-149">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="55222-150">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="55222-150">Your Dynamics 365 Customer Insights administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
