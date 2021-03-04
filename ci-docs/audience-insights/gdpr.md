---
title: Solicitações de Direitos do Titular dos Dados (DSR) no RGPD | Microsoft Docs
description: Responda a Solicitações do Titular dos Dados para o recurso de insights de público-alvo do Dynamics 365 Customer Insights.
ms.date: 05/14/2020
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed9aa09fba938606611c6ce86c2b250c5e19c606
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268672"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a><span data-ttu-id="02189-103">Solicitações de Direitos do Titular dos Dados (DSR) no GDPR</span><span class="sxs-lookup"><span data-stu-id="02189-103">Data Subject Rights (DSR) requests under GDPR</span></span>

## <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a><span data-ttu-id="02189-104">Responder a solicitações de exclusão do titular dos dados de RGPD para o recurso de insights de público-alvo do Dynamics 365 Customer Insights</span><span class="sxs-lookup"><span data-stu-id="02189-104">Responding to GDPR data subject delete requests for Dynamics 365 Customer Insights audience insights capability</span></span>

<span data-ttu-id="02189-105">O "direito de apagar" através de remoção de dados pessoais dos dados do cliente de uma organização é uma proteção chave no Regulamento Geral sobre a Proteção de Dados (RGPD).</span><span class="sxs-lookup"><span data-stu-id="02189-105">The “right to erasure” by the removal of personal data from an organization’s customer data is a key protection in the General Data Protection Regulation (GDPR).</span></span> <span data-ttu-id="02189-106">A remoção de dados pessoais inclui a remoção de todos os dados pessoais e os logs gerados pelo sistema, exceto informações de log de auditoria.</span><span class="sxs-lookup"><span data-stu-id="02189-106">Removing personal data includes removing all personal data and system-generated logs, except audit log information.</span></span>

### <a name="manage-data-subject-delete-requests"></a><span data-ttu-id="02189-107">Gerenciar solicitações de exclusão do titular dos dados</span><span class="sxs-lookup"><span data-stu-id="02189-107">Manage data subject delete requests</span></span>

<span data-ttu-id="02189-108">Os insights de público-alvo oferecem as seguintes experiências no produto para excluir dados pessoais de um cliente ou usuário específico:</span><span class="sxs-lookup"><span data-stu-id="02189-108">Audience insights offers the following in-product experiences to delete personal data for a specific customer or user:</span></span>

- <span data-ttu-id="02189-109">**Gerenciar solicitações de exclusão de dados do cliente** : Os dados do cliente no Customer Insights são ingeridos de fontes de dados originais externas ao Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02189-109">**Manage delete requests for customer data**: Customer data in Customer Insights is ingested from original data sources external to Customer Insights.</span></span> <span data-ttu-id="02189-110">Todas as solicitações de exclusão de RGPD devem ser executadas no fonte de dados original.</span><span class="sxs-lookup"><span data-stu-id="02189-110">All GDPR delete requests must be performed in the original data source.</span></span>
- <span data-ttu-id="02189-111">**Gerenciar solicitações de exclusão de dados do usuário do Customer Insights**: dados para usuários são criados pelo Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02189-111">**Manage delete requests for Customer Insights user data**: Data for users is created by Customer Insights.</span></span> <span data-ttu-id="02189-112">Todas as solicitações de exclusão de RGPD devem ser executadas no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02189-112">All GDPR delete requests must be performed in Customer Insights.</span></span>

#### <a name="manage-delete-requests-for-customer-data"></a><span data-ttu-id="02189-113">Gerenciar solicitações de exclusão de dados do cliente</span><span class="sxs-lookup"><span data-stu-id="02189-113">Manage delete requests for customer data</span></span>

<span data-ttu-id="02189-114">Um administrador do Customer Insights pode seguir estas etapas para remover dados do cliente que foram excluídos no fonte de dados:</span><span class="sxs-lookup"><span data-stu-id="02189-114">A Customer Insights admin can follow these steps to remove customer data that was deleted in the data source:</span></span>

1. <span data-ttu-id="02189-115">Entre no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02189-115">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="02189-116">Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.</span><span class="sxs-lookup"><span data-stu-id="02189-116">In audience insights, go to **Data** > **Data sources**</span></span>
3. <span data-ttu-id="02189-117">Para cada fonte de dados na lista que contém dados excluídos do cliente:</span><span class="sxs-lookup"><span data-stu-id="02189-117">For each data source in the list that contains deleted customer data:</span></span>
   1. <span data-ttu-id="02189-118">Selecione (...) e depois selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="02189-118">Select (...) and then select **Refresh**.</span></span>
   2. <span data-ttu-id="02189-119">Verifique o status da fonte de dados em **Status**.</span><span class="sxs-lookup"><span data-stu-id="02189-119">Check the status of the data source under **Status**.</span></span> <span data-ttu-id="02189-120">Uma marca de seleção significa que a atualização foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="02189-120">A check mark means the refresh was successful.</span></span> <span data-ttu-id="02189-121">Um triângulo de aviso significa que algo deu errado.</span><span class="sxs-lookup"><span data-stu-id="02189-121">A warning triangle means something went wrong.</span></span> <span data-ttu-id="02189-122">Se um triângulo de aviso for exibido, entre em contato com D365CI@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="02189-122">If a warning triangle is displayed, contact D365CI@microsoft.com.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="02189-123">![Tratar solicitações de exclusão de RGPD de dados do cliente](media/gdpr-data-sources.png "Tratar solicitações de exclusão de RGPD de dados do cliente")</span><span class="sxs-lookup"><span data-stu-id="02189-123">![Handling GDPR delete requests for customer data](media/gdpr-data-sources.png "Handling GDPR delete requests for customer data")</span></span>

#### <a name="manage-delete-requests-for-user-data"></a><span data-ttu-id="02189-124">Gerenciar solicitações de exclusão de dados do usuário</span><span class="sxs-lookup"><span data-stu-id="02189-124">Manage delete requests for user data</span></span>

<span data-ttu-id="02189-125">Um administrador do Customer Insights pode seguir estas etapas para excluir os dados do usuário do Customer Insights:</span><span class="sxs-lookup"><span data-stu-id="02189-125">A Customer Insights admin can follow these steps to delete Customer Insights user data:</span></span>

1. <span data-ttu-id="02189-126">Entre no Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="02189-126">Sign in to Dynamics 365 Customer Insights.</span></span>
2. <span data-ttu-id="02189-127">Nos insights de público-alvo, vá para **Administrador** > **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="02189-127">In audience insights, go to **Admin** > **Permissions**.</span></span>
3. <span data-ttu-id="02189-128">Marque a caixa de seleção do usuário que você deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="02189-128">Select the check box for the user you want to delete.</span></span>
4. <span data-ttu-id="02189-129">Selecione **Remover**.</span><span class="sxs-lookup"><span data-stu-id="02189-129">Select **Remove**.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="02189-130">![Tratar solicitações de exclusão de RGPD de dados do usuário](media/gdpr-permissions.png "Tratar solicitações de exclusão de RGPD de dados do usuário")</span><span class="sxs-lookup"><span data-stu-id="02189-130">![Handling GDPR delete requests foruser data](media/gdpr-permissions.png "Handling GDPR delete requests for user data")</span></span>

## <a name="responding-to-gdpr-data-subject-export-requests"></a><span data-ttu-id="02189-131">Responder a solicitações de exportação do titular dos dados de RGPD</span><span class="sxs-lookup"><span data-stu-id="02189-131">Responding to GDPR data subject export requests</span></span>

<span data-ttu-id="02189-132">Como parte de nosso compromisso de fazer parceria com você em sua jornada para o Regulamento Geral sobre a Proteção de Dados (GDPR), desenvolvemos uma documentação para ajudá-lo a se preparar.</span><span class="sxs-lookup"><span data-stu-id="02189-132">As part of our commitment to partner with you on your journey to the General Data Protection Regulation (GDPR), we’ve developed documentation to help you prepare.</span></span> <span data-ttu-id="02189-133">Essa documentação descreve as etapas que você pode seguir hoje para oferecer suporte à conformidade com o RGPD ao usar insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="02189-133">This documentation describes steps you can take today to support GDPR compliance when using audience insights.</span></span>

### <a name="manage-export-and-view-requests"></a><span data-ttu-id="02189-134">Gerenciar solicitações de exportação e exibição</span><span class="sxs-lookup"><span data-stu-id="02189-134">Manage export and view requests</span></span>

<span data-ttu-id="02189-135">O direito de portabilidade de dados permite que um titular dos dados solicite uma cópia de seus dados pessoais em um formato eletrônico (definido como “formato estruturado, comumente usado, legível por máquina e interoperável”) que pode ser transmitido para outro controlador de dados.</span><span class="sxs-lookup"><span data-stu-id="02189-135">The right of data portability allows data subjects to request a copy of their personal data in an electronic format (a “structured, commonly used, machine readable, and interoperable format”) that can be transmitted to another data controller.</span></span>

#### <a name="export-customer-data-tenant-admin"></a><span data-ttu-id="02189-136">Exportar dados do cliente (administrador do locatário)</span><span class="sxs-lookup"><span data-stu-id="02189-136">Export customer data (tenant admin)</span></span>

<span data-ttu-id="02189-137">Um administrador do locatário pode seguir estas etapas para exportar dados:</span><span class="sxs-lookup"><span data-stu-id="02189-137">A tenant administrator can follow these steps to export data:</span></span>

1. <span data-ttu-id="02189-138">Enviar um email para D365CI@microsoft.com especificando o endereço de email do cliente na solicitação.</span><span class="sxs-lookup"><span data-stu-id="02189-138">Send an email to D365CI@microsoft.com specifying the customer’s email address in the request.</span></span> <span data-ttu-id="02189-139">A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.</span><span class="sxs-lookup"><span data-stu-id="02189-139">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="02189-140">Reconheça a confirmação para exportar os dados para o cliente solicitado.</span><span class="sxs-lookup"><span data-stu-id="02189-140">Acknowledge the confirmation to export the data for the requested customer.</span></span>
3. <span data-ttu-id="02189-141">Receba os dados exportados através do endereço de e-mail do administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="02189-141">Receive the exported data through the tenant admin email address.</span></span>

#### <a name="export-user-data-tenant-admin"></a><span data-ttu-id="02189-142">Exportar dados do usuário (administrador do locatário)</span><span class="sxs-lookup"><span data-stu-id="02189-142">Export user data (tenant admin)</span></span>

1. <span data-ttu-id="02189-143">Enviar um email para D365CI@microsoft.com especificando o endereço de email do usuário na solicitação.</span><span class="sxs-lookup"><span data-stu-id="02189-143">Send an email to D365CI@microsoft.com specifying the user’s email address in the request.</span></span> <span data-ttu-id="02189-144">A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.</span><span class="sxs-lookup"><span data-stu-id="02189-144">The Customer Insights team will send an email to the registered tenant admin email address, asking for confirmation to export data.</span></span>
2. <span data-ttu-id="02189-145">Reconheça a confirmação para exportar os dados para o usuário solicitado.</span><span class="sxs-lookup"><span data-stu-id="02189-145">Acknowledge the confirmation to export the data for the requested user.</span></span>
3. <span data-ttu-id="02189-146">Receba os dados exportados através do endereço de e-mail do administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="02189-146">Receive the exported data through the tenant admin email address.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]