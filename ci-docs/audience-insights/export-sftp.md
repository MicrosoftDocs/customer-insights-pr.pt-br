---
title: Exportar dados do Customer Insights para hosts SFTP
description: Aprenda a configurar a conexão com um host de SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267984"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="22056-103">Conector do SFTP (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="22056-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="22056-104">Use seus dados de cliente em aplicativos de terceiros, exportando-os para um host SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="22056-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol (SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="22056-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="22056-105">Prerequisites</span></span>

- <span data-ttu-id="22056-106">Disponibilidade de um host SFTP e credenciais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="22056-106">Availability of an SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="22056-107">Conectar ao SFTP</span><span class="sxs-lookup"><span data-stu-id="22056-107">Connect to SFTP</span></span>

1. <span data-ttu-id="22056-108">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="22056-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="22056-109">Em **SFTP**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="22056-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="22056-110">Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="22056-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="22056-111">Forneça um **Nome de usuário**, uma **Senha**, um **Nome de host** e uma **Pasta de exportação** para sua conta SFTP.</span><span class="sxs-lookup"><span data-stu-id="22056-111">Provide a **Username**, **Password**, **Hostname**, and **Export folder** for your SFTP account.</span></span>

1. <span data-ttu-id="22056-112">Selecione **Verificar** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="22056-112">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="22056-113">Após a verificação com sucesso, escolha se deseja exportar os dados de conteúdo **Gzip** ou **Descompactado** e selecione o **delimitador de campo** para os arquivos exportados.</span><span class="sxs-lookup"><span data-stu-id="22056-113">After successful verification, choose if you want to export your data **Gzipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="22056-114">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="22056-114">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="22056-115">Selecione **Próximo** para começar a configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="22056-115">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-export"></a><span data-ttu-id="22056-116">Configurar a exportação</span><span class="sxs-lookup"><span data-stu-id="22056-116">Configure the export</span></span>

1. <span data-ttu-id="22056-117">Selecione as entidades, por exemplo, segmentos que deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="22056-117">Select the entities, for example segments, you want to export.</span></span>

   > [!NOTE]
   > <span data-ttu-id="22056-118">Cada entidade selecionada terá até cinco arquivos de saída quando exportada.</span><span class="sxs-lookup"><span data-stu-id="22056-118">Each selected entity will be up to five output files when exported.</span></span> 

1. <span data-ttu-id="22056-119">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="22056-119">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="22056-120">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="22056-120">Export the data</span></span>

<span data-ttu-id="22056-121">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="22056-121">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="22056-122">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="22056-122">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="22056-123">Limitações conhecidas</span><span class="sxs-lookup"><span data-stu-id="22056-123">Known limitations</span></span>

- <span data-ttu-id="22056-124">O tempo de execução de uma exportação depende do desempenho do sistema.</span><span class="sxs-lookup"><span data-stu-id="22056-124">The runtime of an export depends on your system performance.</span></span> <span data-ttu-id="22056-125">Recomendamos dois núcleos de CPU e 1Gb de memória como configuração mínima do servidor.</span><span class="sxs-lookup"><span data-stu-id="22056-125">We recommend two CPU cores and 1 Gb of memory as minimal configuration of your server.</span></span> 
- <span data-ttu-id="22056-126">Exportar entidades de até 100 milhões de perfis de cliente pode levar 90 minutos ao usar a configuração mínima recomendada de dois núcleos de CPU e 1 Gb de memória.</span><span class="sxs-lookup"><span data-stu-id="22056-126">Exporting entities with up to 100 million customer profiles can take 90 minutes when using the recommended minimal configuration of two CPU cores and 1 Gb of memory.</span></span> 

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="22056-127">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="22056-127">Data privacy and compliance</span></span>

<span data-ttu-id="22056-128">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados via SFTP, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="22056-128">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="22056-129">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o destino de exportação cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="22056-129">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="22056-130">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="22056-130">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="22056-131">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="22056-131">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]