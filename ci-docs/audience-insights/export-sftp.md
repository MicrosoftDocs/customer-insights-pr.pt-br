---
title: Exportar dados do Customer Insights para hosts SFTP
description: Aprenda a configurar a conexão com um host de SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643489"
---
# <a name="connector-for-sftp-preview"></a><span data-ttu-id="afe0f-103">Conector do SFTP (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="afe0f-103">Connector for SFTP (preview)</span></span>

<span data-ttu-id="afe0f-104">Use seus dados de cliente em aplicativos de terceiros, exportando-os para um host SFTP (Secure File Transfer Protocol).</span><span class="sxs-lookup"><span data-stu-id="afe0f-104">Use your customer data in third-party applications by exporting them to a Secure File Transfer Protocol(SFTP) host.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="afe0f-105">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="afe0f-105">Prerequisites</span></span>

- <span data-ttu-id="afe0f-106">Disponibilidade de um host de SFTP e credenciais correspondentes.</span><span class="sxs-lookup"><span data-stu-id="afe0f-106">Availability of a SFTP host and corresponding credentials.</span></span>

## <a name="connect-to-sftp"></a><span data-ttu-id="afe0f-107">Conecte-se ao SFTP</span><span class="sxs-lookup"><span data-stu-id="afe0f-107">Connect to SFTP</span></span>

1. <span data-ttu-id="afe0f-108">Vá para **Administrador** > **Exportar destinos**.</span><span class="sxs-lookup"><span data-stu-id="afe0f-108">Go to **Admin** > **Export destinations**.</span></span>

1. <span data-ttu-id="afe0f-109">Em **SFTP**, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="afe0f-109">Under **SFTP**, select **Set up**.</span></span>

1. <span data-ttu-id="afe0f-110">Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="afe0f-110">Give your destination a recognizable name in the **Display name** field.</span></span>

1. <span data-ttu-id="afe0f-111">Forneça um **Nome de usuário**, uma **Senha** e um **Nome de host** para sua conta SFTP.</span><span class="sxs-lookup"><span data-stu-id="afe0f-111">Provide a **Username**, **Password** and **Hostname** for your SFTP account.</span></span> <span data-ttu-id="afe0f-112">Exemplo: se a pasta raiz do seu servidor SFTP for /root/folder e você quiser que os dados sejam exportados para /root/folder/ci_export_destination_folder, o host deverá ser sftp://<server_address>/ci_export_destination_folder".</span><span class="sxs-lookup"><span data-stu-id="afe0f-112">Example: If your SFTP server's root folder is /root/folder, and you would like the data to be exported to /root/folder/ci_export_destination_folder, the the host should be sftp://<server_address>/ci_export_destination_folder".</span></span>

1. <span data-ttu-id="afe0f-113">Selecione **Verificar** para testar a conexão.</span><span class="sxs-lookup"><span data-stu-id="afe0f-113">Select **Verify** to test the connection.</span></span>

1. <span data-ttu-id="afe0f-114">Após a verificação bem-sucedida, escolha se deseja exportar seus dados **Fechados** ou **Descompactados** e selecione o **delimitador de campo** para os arquivos exportados.</span><span class="sxs-lookup"><span data-stu-id="afe0f-114">After successful verification, choose if you want to export your data **Zipped** or **Unzipped**, and select the **field delimiter** for the exported files.</span></span>

1. <span data-ttu-id="afe0f-115">Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.</span><span class="sxs-lookup"><span data-stu-id="afe0f-115">Select **I agree** to confirm the **Data privacy and compliance**.</span></span>

1. <span data-ttu-id="afe0f-116">Selecione **Próximo** para começar a configurar a exportação.</span><span class="sxs-lookup"><span data-stu-id="afe0f-116">Select **Next** to start configuring the export.</span></span>

## <a name="configure-the-connection"></a><span data-ttu-id="afe0f-117">Configurar a conexão</span><span class="sxs-lookup"><span data-stu-id="afe0f-117">Configure the connection</span></span>

1. <span data-ttu-id="afe0f-118">Selecione os **atributos do cliente** que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="afe0f-118">Select the **customer attributes** you want to export.</span></span> <span data-ttu-id="afe0f-119">Você pode exportar um ou vários atributos.</span><span class="sxs-lookup"><span data-stu-id="afe0f-119">You can export one or multiple attributes.</span></span>

1. <span data-ttu-id="afe0f-120">Selecione **Avançar**.</span><span class="sxs-lookup"><span data-stu-id="afe0f-120">Select **Next**.</span></span>

1. <span data-ttu-id="afe0f-121">Selecione os segmentos que você deseja exportar.</span><span class="sxs-lookup"><span data-stu-id="afe0f-121">Select the segments you want to export.</span></span>

1. <span data-ttu-id="afe0f-122">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="afe0f-122">Select **Save**.</span></span>

## <a name="export-the-data"></a><span data-ttu-id="afe0f-123">Exportar os dados</span><span class="sxs-lookup"><span data-stu-id="afe0f-123">Export the data</span></span>

<span data-ttu-id="afe0f-124">Você pode [exportar dados sob demanda](export-destinations.md).</span><span class="sxs-lookup"><span data-stu-id="afe0f-124">You can [export data on demand](export-destinations.md).</span></span> <span data-ttu-id="afe0f-125">A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="afe0f-125">The export will also run with every [scheduled refresh](system.md#schedule-tab).</span></span>

## <a name="data-privacy-and-compliance"></a><span data-ttu-id="afe0f-126">Conformidade e privacidade dos dados</span><span class="sxs-lookup"><span data-stu-id="afe0f-126">Data privacy and compliance</span></span>

<span data-ttu-id="afe0f-127">Ao habilitar o Dynamics 365 Customer Insights para transmitir dados via SFTP, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais.</span><span class="sxs-lookup"><span data-stu-id="afe0f-127">When you enable Dynamics 365 Customer Insights to transmit data via SFTP, you allow transfer of data outside of the compliance boundary for Dynamics 365 Customer Insights, including potentially sensitive data such as Personal Data.</span></span> <span data-ttu-id="afe0f-128">A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o destino de exportação cumpra as obrigações de privacidade e segurança que possam existir.</span><span class="sxs-lookup"><span data-stu-id="afe0f-128">Microsoft will transfer such data at your instruction, but you are responsible for ensuring that the export destination meets any privacy or security obligations you may have.</span></span> <span data-ttu-id="afe0f-129">Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).</span><span class="sxs-lookup"><span data-stu-id="afe0f-129">For more information, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=396732).</span></span>
<span data-ttu-id="afe0f-130">Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="afe0f-130">Your Dynamics 365 Customer Insights Administrator can remove this export destination at any time to discontinue use of this functionality.</span></span>
