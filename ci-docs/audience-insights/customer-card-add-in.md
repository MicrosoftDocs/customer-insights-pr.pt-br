---
title: Instalar e configurar o Complemento do Cartão do Cliente
description: Instalar e configura o suplemento de Cartão de Cliente para o Dynamics 365 Customer Insights.
ms.date: 01/20/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: a6d5b49380ed129cf147698a16f5f3f597bf7fbc
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5268030"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="75f06-103">Suplemento do Cartão do Cliente (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="75f06-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="75f06-104">Obtenha uma exibição de 360 graus de seus clientes diretamente nos aplicativos do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75f06-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="75f06-105">Exiba dados demográficos, insights e linhas de tempo de atividades com o Suplemento do Cartão do Cliente.</span><span class="sxs-lookup"><span data-stu-id="75f06-105">View demographics, insights, and activity timelines with the Customer Card Add-in.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="75f06-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="75f06-106">Prerequisites</span></span>

- <span data-ttu-id="75f06-107">Aplicativo Dynamics 365 (como Hub de Vendas ou Hub do SAC), versão 9.0 e posterior com Interface Unificada ativada.</span><span class="sxs-lookup"><span data-stu-id="75f06-107">Dynamics 365 app (such as Sales Hub or Customer Service Hub), version 9.0 and later with Unified Interface enabled.</span></span>
- <span data-ttu-id="75f06-108">Perfis de clientes [ingeridos a partir do aplicativo do Dynamics 365 usando o Common Data Service](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="75f06-108">Customer profiles [ingested from the Dynamics 365 app using Common Data Service](connect-power-query.md).</span></span>
- <span data-ttu-id="75f06-109">Os usuários do complemento do cartão do cliente precisam ser [adicionados como usuários](permissions.md) nos insights de público-alvo.</span><span class="sxs-lookup"><span data-stu-id="75f06-109">Users of the Customer Card Add-in need to be [added as users](permissions.md) in audience insights.</span></span>
- <span data-ttu-id="75f06-110">[Recursos de pesquisa e filtro configurados](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="75f06-110">[Configured search and filter capabilities](search-filter-index.md).</span></span>
- <span data-ttu-id="75f06-111">Controle demográfico: campos demográficos (como idade ou sexo) estão disponíveis no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="75f06-111">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
- <span data-ttu-id="75f06-112">Controle de enriquecimento: Requer [enriquecimentos](enrichment-hub.md) ativos aplicados aos perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="75f06-112">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
- <span data-ttu-id="75f06-113">Controle de inteligência: requer dados gerados usando o Azure Machine Learning ([Previsões](predictions.md) ou [Modelos Personalizados](custom-models.md))</span><span class="sxs-lookup"><span data-stu-id="75f06-113">Intelligence control: Requires data generated using Azure Machine Learning ([Predictions](predictions.md) or [Custom Models](custom-models.md))</span></span>
- <span data-ttu-id="75f06-114">Controle de medida: requer [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="75f06-114">Measure control: Requires [configured measures](measures.md).</span></span>
- <span data-ttu-id="75f06-115">Controle de linha do tempo: requer [atividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="75f06-115">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="75f06-116">Instalar o Complemento do Cartão do Cliente</span><span class="sxs-lookup"><span data-stu-id="75f06-116">Install the Customer Card Add-in</span></span>

<span data-ttu-id="75f06-117">O Suplemento do Cartão do Cliente é uma solução para aplicativos customer engagement no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75f06-117">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="75f06-118">Para instalar a solução, vá para AppSource e procure **Cartão do Cliente do Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="75f06-118">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="75f06-119">Selecione o [Suplemento do Cartão do Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.</span><span class="sxs-lookup"><span data-stu-id="75f06-119">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="75f06-120">Pode ser necessário entrar com suas credenciais de administrador no aplicativo Dynamics 365 para instalar a solução.</span><span class="sxs-lookup"><span data-stu-id="75f06-120">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="75f06-121">Pode levar algum tempo para a solução ser instalada no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="75f06-121">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="75f06-122">Configurar o Suplemento do Cartão do Cliente</span><span class="sxs-lookup"><span data-stu-id="75f06-122">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="75f06-123">Como administrador, vá para a seção **Configurações** no Dynamics 365 e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="75f06-123">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="75f06-124">Selecione o link **Nome para Exibição** da solução **Suplemento do Cartão do Cliente do Dynamics 365 Customer Insights (versão prévia)**.</span><span class="sxs-lookup"><span data-stu-id="75f06-124">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="75f06-125">![Selecione nome para exibição](media/select-display-name.png "Selecione nome para exibição")</span><span class="sxs-lookup"><span data-stu-id="75f06-125">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="75f06-126">Selecione **Entrar** e insira as credenciais da conta de administrador que você usa para configurar o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="75f06-126">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="75f06-127">Verifique se o bloqueador de pop-up do navegador não bloqueia a janela de autenticação quando você seleciona o botão **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="75f06-127">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="75f06-128">Selecione o ambiente por meio do qual você deseja buscar dados.</span><span class="sxs-lookup"><span data-stu-id="75f06-128">Select the environment you want to fetch data from.</span></span>

1. <span data-ttu-id="75f06-129">Defina o mapeamento de campo para registros no aplicativo do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75f06-129">Define which the field mapping to records in the Dynamics 365 app.</span></span>
   - <span data-ttu-id="75f06-130">Para mapear com um contato, selecione o campo na entidade Cliente que corresponde à ID de sua entidade de contato.</span><span class="sxs-lookup"><span data-stu-id="75f06-130">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="75f06-131">Para mapear com uma conta, selecione o campo na entidade Cliente que corresponde à ID da entidade de sua conta.</span><span class="sxs-lookup"><span data-stu-id="75f06-131">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="75f06-132">![Campo ID de Contato](media/contact-id-field.png "Campo ID de Contato")</span><span class="sxs-lookup"><span data-stu-id="75f06-132">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="75f06-133">Selecione **Salvar configuração** para salvar as configurações.</span><span class="sxs-lookup"><span data-stu-id="75f06-133">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="75f06-134">Em seguida, você precisa atribuir funções de segurança no Dynamics 365 para que os usuários possam personalizar e exibir o cartão do cliente.</span><span class="sxs-lookup"><span data-stu-id="75f06-134">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="75f06-135">No Dynamics 365, vá para **Configurações** > **Segurança** > **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="75f06-135">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="75f06-136">Selecione os usuários para editar as funções do usuário e selecione **Gerenciar funções**.</span><span class="sxs-lookup"><span data-stu-id="75f06-136">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="75f06-137">Atribua a função **Personalizador de Cartão do Customer Insights** a usuários que personalizarão o conteúdo mostrado no cartão para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="75f06-137">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="75f06-138">Adicionar controles de cartão de cliente a formulários</span><span class="sxs-lookup"><span data-stu-id="75f06-138">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="75f06-139">Para adicionar os controles do Cartão do Cliente ao seu formulário de contato, vá para **Configurações** > **Personalizações** no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="75f06-139">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="75f06-140">Selecione **Personalizar o sistema**.</span><span class="sxs-lookup"><span data-stu-id="75f06-140">Select **Customize the System**.</span></span>

1. <span data-ttu-id="75f06-141">Navegue até a entidade **Contato**, expanda-a e selecione **Formulários**.</span><span class="sxs-lookup"><span data-stu-id="75f06-141">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="75f06-142">Selecione o formulário de contato ao qual você deseja adicionar os controles do Cartão do Cliente.</span><span class="sxs-lookup"><span data-stu-id="75f06-142">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="75f06-143">![Selecione o formulário de Contato](media/contact-active-forms.png "Selecione o formulário de Contato")</span><span class="sxs-lookup"><span data-stu-id="75f06-143">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="75f06-144">Para adicionar um controle, no editor de formulários, arraste qualquer campo do **Gerenciador de Campos** para o local em que deseja que o controle apareça.</span><span class="sxs-lookup"><span data-stu-id="75f06-144">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="75f06-145">Selecione o campo no formulário que você acabou de adicionar e selecione **Alterar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="75f06-145">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="75f06-146">Vá para a guia **Controles** e selecione **Adicionar Controle**.</span><span class="sxs-lookup"><span data-stu-id="75f06-146">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="75f06-147">Escolha um dos controles personalizados disponíveis e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="75f06-147">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="75f06-148">Na caixa de diálogo **Propriedades do Campo**, limpe a caixa de seleção **Exibir rótulo no formulário**.</span><span class="sxs-lookup"><span data-stu-id="75f06-148">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="75f06-149">Selecione a opção **Web** para o controle.</span><span class="sxs-lookup"><span data-stu-id="75f06-149">Select the **Web** option for the control.</span></span> <span data-ttu-id="75f06-150">Para o controle Enriquecimento, selecione qual tipo de enriquecimento você quer exibir, configurando o campo **enriqumentType**.</span><span class="sxs-lookup"><span data-stu-id="75f06-150">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="75f06-151">Adicione um controle de enriquecimento separado para cada tipo de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="75f06-151">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="75f06-152">Selecione **Salvar** e **Publicar** para publicar o formulário de contato atualizado.</span><span class="sxs-lookup"><span data-stu-id="75f06-152">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="75f06-153">Vá para o formulário de contato publicado.</span><span class="sxs-lookup"><span data-stu-id="75f06-153">Go to the published contact form.</span></span> <span data-ttu-id="75f06-154">Você verá o controle recém-adicionado.</span><span class="sxs-lookup"><span data-stu-id="75f06-154">You'll see the newly added control.</span></span> <span data-ttu-id="75f06-155">Pode ser necessário fazer login na primeira vez em que o utilizar.</span><span class="sxs-lookup"><span data-stu-id="75f06-155">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="75f06-156">Para personalizar o que você deseja mostrar no controle personalizado, selecione o botão de edição no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="75f06-156">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="75f06-157">Atualizar Suplemento do Cartão do Cliente</span><span class="sxs-lookup"><span data-stu-id="75f06-157">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="75f06-158">O Suplemento do Cartão do Cliente não é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="75f06-158">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="75f06-159">Para atualizar para a versão mais recente, siga este procedimento no aplicativo Dynamics 365 que tem o suplemento instalado.</span><span class="sxs-lookup"><span data-stu-id="75f06-159">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="75f06-160">No aplicativo Dynamics 365, acesse **Configurações** > **Personalização** e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="75f06-160">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="75f06-161">Na tabela de suplementos, procure **CustomerInsightsCustomerCard** e selecione a linha.</span><span class="sxs-lookup"><span data-stu-id="75f06-161">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="75f06-162">Selecione **Aplicar Atualização de Solução** na barra de ações.</span><span class="sxs-lookup"><span data-stu-id="75f06-162">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atualize a solução na Área de personalização dos aplicativos do Dynamics 365":::

1. <span data-ttu-id="75f06-164">Depois de iniciar o processo de atualização, você verá um indicador de carregamento até que a atualização seja concluída.</span><span class="sxs-lookup"><span data-stu-id="75f06-164">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="75f06-165">Se não houver uma versão mais recente, a atualização exibirá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="75f06-165">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]