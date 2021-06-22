---
title: Exportar dados do Customer Insights para hosts SFTP
description: Saiba como configurar a conexão e exportar para um local do SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 000b44dc8e5cc419132bd17e359fbdd5879caf1b
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124305"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a><span data-ttu-id="3dc42-103">Exportar segmentos e outros dados para o SFTP (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="3dc42-103">Export segments and other data to SFTP (preview)</span></span>

<span data-ttu-id="3dc42-104">Use dados de clientes em aplicativos de terceiros, exportando-os para um local do SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="3dc42-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) location.</span></span>

## <a name="prerequisites-for-connection"></a><span data-ttu-id="3dc42-105">Pré-requisitos para conexão</span><span class="sxs-lookup"><span data-stu-id="3dc42-105">Prerequisites for connection</span></span>

- <span data-ttu-id="3dc42-106">Disponibilidade de um host SFTP e credenciais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="3dc42-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="3dc42-107">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="3dc42-107">Known limitations</span></span>

- <span data-ttu-id="3dc42-108">O tempo de execução de uma exportação depende do desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="3dc42-108">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="3dc42-109">Recomendamos dois núcleos de CPU e 1Gb de memória como configuração mínima do servidor.</span><span class="sxs-lookup"><span data-stu-id="3dc42-109">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="3dc42-110">Exportar entidades de até 100 milhões de perfis de cliente pode levar 90 minutos ao usar a configuração mínima recomendada de dois núcleos de CPU e 1 Gb de memória.</span><span class="sxs-lookup"><span data-stu-id="3dc42-110">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="set-up-connection-to-sftp"></a><span data-ttu-id="3dc42-111">Configurar conexão com o SFTP</span><span class="sxs-lookup"><span data-stu-id="3dc42-111">Set up connection to SFTP</span></span>

1. <span data-ttu-id="3dc42-112">Vá para **Administração** > **Conexões**.</span><span class="sxs-lookup"><span data-stu-id="3dc42-112">Go to **Admin** > **Connections**.</span></span>

1. <span data-ttu-id="3dc42-113">Selecione **Adicionar conexão** e escolha **SFTP** para configurar a conexão.</span><span class="sxs-lookup"><span data-stu-id="3dc42-113">Select **Add connection** and choose **SFTP** to configure the connection.</span></span>

1. <span data-ttu-id="3dc42-114">Dê um nome reconhecível à sua conexão no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="3dc42-114">Give your connection a recognizable name in the **Display name** field.</span></span> <span data-ttu-id="3dc42-115">O nome e o tipo da conexão a descrevem.</span><span class="sxs-lookup"><span data-stu-id="3dc42-115">The name and the type of the connection describe this connection.</span></span> <span data-ttu-id="3dc42-116">Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.</span><span class="sxs-lookup"><span data-stu-id="3dc42-116">We recommend choosing a name that explains the purpose and target of the connection.</span></span>

1. <span data-ttu-id="3dc42-117">Escolha quem pode usar essa conexão.</span><span class="sxs-lookup"><span data-stu-id="3dc42-117">Choose who can use this connection.</span></span> <span data-ttu-id="3dc42-118">Se você não fizer nada, o padrão será Administradores.</span><span class="sxs-lookup"><span data-stu-id="3dc42-118">If you take no action, the default will be Administrators.</span></span> <span data-ttu-id="3dc42-119">Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).</span><span class="sxs-lookup"><span data-stu-id="3dc42-119">For more information, see [Allow contributors to use a connection for exports](connections.md#allow-contributors-to-use-a-connection-for-exports).</span></span>

1. <span data-ttu-id="3dc42-120">Forneça um **Nome de usuário**, uma **Senha**, um **Nome de host** e uma **Pasta de exportação** para sua conta SFTP.</span><span class="sxs-lookup"><span data-stu-id="3dc42-120">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="3dc42-121">Selecione **Verificar** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="3dc42-121">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="3dc42-122">Escolha se você deseja exportar seus dados **Compactados com o Gzip** ou **Descompactados** e o **delimitador de campo** para os arquivos exportados.</span><span class="sxs-lookup"><span data-stu-id="3dc42-122">Choose if you want to export your data **Gzipped** or **Unzipped** and the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="3dc42-123">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="3dc42-123">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="3dc42-124">Selecione **Salvar** para concluir a conexão.</span><span class="sxs-lookup"><span data-stu-id="3dc42-124">Select **Save** to complete the connection.</span></span>

## <a name="configure-an-export"></a><span data-ttu-id="3dc42-125">Configurar uma exportação</span><span class="sxs-lookup"><span data-stu-id="3dc42-125">Configure an export</span></span>

<span data-ttu-id="3dc42-126">Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo.</span><span class="sxs-lookup"><span data-stu-id="3dc42-126">You can configure this export if you have access to a connection of this type.</span></span> <span data-ttu-id="3dc42-127">Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).</span><span class="sxs-lookup"><span data-stu-id="3dc42-127">For more information, see [Permissions needed to configure an export](export-destinations.md#set-up-a-new-export).</span></span>

1. <span data-ttu-id="3dc42-128">Vá para **Dados** > **Exportações**.</span><span class="sxs-lookup"><span data-stu-id="3dc42-128">Go to **Data** > **Exports**.</span></span>

1. <span data-ttu-id="3dc42-129">Para criar uma nova exportação, selecione **Adicionar destino**.</span><span class="sxs-lookup"><span data-stu-id="3dc42-129">To create a new export, select **Add destination**.</span></span>

1. <span data-ttu-id="3dc42-130">No campo **Conexão para exportação**, escolha uma conexão da seção do SFTP.</span><span class="sxs-lookup"><span data-stu-id="3dc42-130">In the **Connection for export** field, choose a connection from the SFTP section.</span></span> <span data-ttu-id="3dc42-131">Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.</span><span class="sxs-lookup"><span data-stu-id="3dc42-131">If you don't see this section name, there are no connections of this type available to you.</span></span>

1. <span data-ttu-id="3dc42-132">Selecione as entidades, por exemplo, segmentos que deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="3dc42-132">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="3dc42-133">Cada entidade selecionada será dividida em até cinco arquivos de saída quando exportada.</span><span class="sxs-lookup"><span data-stu-id="3dc42-133">Each selected entity will be split up into up to five output files when exported.</span></span> 

1. <span data-ttu-id="3dc42-134">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3dc42-134">Select **Save**.</span></span>

<span data-ttu-id="3dc42-135">Salvar uma exportação não a executa imediatamente.</span><span class="sxs-lookup"><span data-stu-id="3dc42-135">Saving an export doesn't run the export immediately.</span></span>

<span data-ttu-id="3dc42-136">A exportação é executada com cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="3dc42-136">The export runs with every [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="3dc42-137">Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand).</span><span class="sxs-lookup"><span data-stu-id="3dc42-137">You can also [export data on demand](export-destinations.md#run-exports-on-demand).</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="3dc42-138">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="3dc42-138">Data privacy and compliance</span></span>

<span data-ttu-id="3dc42-139">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados via SFTP, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="3dc42-139">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="3dc42-140">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o destino de exportação cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="3dc42-140">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="3dc42-141">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="3dc42-141">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="3dc42-142">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="3dc42-142">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
