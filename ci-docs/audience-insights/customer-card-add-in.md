---
title: Suplemento do Cartão do Cliente para aplicativos Dynamics 365
description: Mostre dados de insights do público-alvo em aplicativos Dynamics 365 com este suplemento.
ms.date: 05/18/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 88492943ddbf9ae30c64d92b261433b74f34f682
ms.sourcegitcommit: d74430270f1b754322287c4f045d7febdae35be2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6059574"
---
# <a name="customer-card-add-in-preview"></a><span data-ttu-id="65ae2-103">Suplemento do Cartão do Cliente (versão prévia)</span><span class="sxs-lookup"><span data-stu-id="65ae2-103">Customer Card Add-in (preview)</span></span>

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

<span data-ttu-id="65ae2-104">Obtenha uma exibição de 360 graus de seus clientes diretamente nos aplicativos do Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65ae2-104">Get a 360-degree view of your customers directly in Dynamics 365 apps.</span></span> <span data-ttu-id="65ae2-105">Com o Suplemento do Cartão do Cliente instalado em um aplicativo Dynamics 365 compatível, você pode escolher exibir dados demográficos, insights e cronogramas de atividades.</span><span class="sxs-lookup"><span data-stu-id="65ae2-105">With the Customer Card Add-in installed in a supported Dynamics 365 app you can choose to display demographics, insights, and activity timelines.</span></span> <span data-ttu-id="65ae2-106">O suplemento recuperará dados do Customer Insights sem afetar os dados no aplicativo conectado Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65ae2-106">The add-in will retrieve data from Customer Insights without affecting the data in the connected Dynamics 365 app.</span></span> 

## <a name="prerequisites"></a><span data-ttu-id="65ae2-107">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="65ae2-107">Prerequisites</span></span>

- <span data-ttu-id="65ae2-108">O suplemento só funciona com aplicativos baseados em modelo do Dynamics 365, como Vendas ou Customer Service, versão 9.0 e superior.</span><span class="sxs-lookup"><span data-stu-id="65ae2-108">The add-in only works with Dynamics 365 model-driven apps, such as Sales or Customer Service, version 9.0 and later.</span></span>
- <span data-ttu-id="65ae2-109">Para que seus dados do Dynamics 365 sejam mapeados para os perfis de clientes de insights do público-alvo, eles precisam ser [ingeridos do aplicativo Dynamics 365 usando o conector do Common Data Service ](connect-power-query.md).</span><span class="sxs-lookup"><span data-stu-id="65ae2-109">For your Dynamics 365 data to map to the audience insights customer profiles they need to be [ingested from the Dynamics 365 app using the Common Data Service connector](connect-power-query.md).</span></span>
- <span data-ttu-id="65ae2-110">Todos os usuários do Dynamics 365 do Suplemento de Cartão do Cliente devem ser [adicionados como usuários](permissions.md) nos insights do público-alvo para ver os dados.</span><span class="sxs-lookup"><span data-stu-id="65ae2-110">All Dynamics 365 users of the Customer Card Add-in must be [added as users](permissions.md) in audience insights to see the data.</span></span>
- <span data-ttu-id="65ae2-111">[É preciso que haja recursos de filtro e pesquisa configurados](search-filter-index.md) em insights de público-alvo para que a pesquisa de dados funcione.</span><span class="sxs-lookup"><span data-stu-id="65ae2-111">[Configured search and filter capabilities](search-filter-index.md) in audience insights are required for lookup of data to work.</span></span>
- <span data-ttu-id="65ae2-112">Cada controle de suplemento depende de dados específicos nos insights do público-alvo:</span><span class="sxs-lookup"><span data-stu-id="65ae2-112">Each add-in control relies on specific data in audience insights:</span></span>
  - <span data-ttu-id="65ae2-113">Controle de medida: requer [medidas configuradas](measures.md).</span><span class="sxs-lookup"><span data-stu-id="65ae2-113">Measure control: Requires [configured measures](measures.md).</span></span>
  - <span data-ttu-id="65ae2-114">Controle de inteligência: requer dados gerados usando [previsões](predictions.md) ou [modelos personalizados](custom-models.md).</span><span class="sxs-lookup"><span data-stu-id="65ae2-114">Intelligence control: Requires data generated using [predictions](predictions.md) or [custom models](custom-models.md).</span></span>
  - <span data-ttu-id="65ae2-115">Controle demográfico: campos demográficos (como idade ou sexo) estão disponíveis no perfil de cliente unificado.</span><span class="sxs-lookup"><span data-stu-id="65ae2-115">Demographic control: Demographic fields(such as age or gender) are available in the unified customer profile.</span></span>
  - <span data-ttu-id="65ae2-116">Controle de enriquecimento: Requer [enriquecimentos](enrichment-hub.md) ativos aplicados aos perfis de clientes.</span><span class="sxs-lookup"><span data-stu-id="65ae2-116">Enrichment control: Requires active [enrichments](enrichment-hub.md) applied to customer profiles.</span></span>
  - <span data-ttu-id="65ae2-117">Controle de linha do tempo: requer [atividades configuradas](activities.md).</span><span class="sxs-lookup"><span data-stu-id="65ae2-117">Timeline control: Requires [configured activities](activities.md).</span></span>

## <a name="install-the-customer-card-add-in"></a><span data-ttu-id="65ae2-118">Instalar o Complemento do Cartão do Cliente</span><span class="sxs-lookup"><span data-stu-id="65ae2-118">Install the Customer Card Add-in</span></span>

<span data-ttu-id="65ae2-119">O Suplemento do Cartão do Cliente é uma solução para aplicativos customer engagement no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65ae2-119">The Customer Card Add-in is a solution for customer engagement apps in Dynamics 365.</span></span> <span data-ttu-id="65ae2-120">Para instalar a solução, vá para AppSource e procure **Cartão do Cliente do Dynamics**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-120">To install the solution, go to AppSource and search for **Dynamics Customer Card**.</span></span> <span data-ttu-id="65ae2-121">Selecione o [Suplemento do Cartão do Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-121">Select the [Customer Card Add-in on AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) and select **Get It Now**.</span></span>

<span data-ttu-id="65ae2-122">Pode ser necessário entrar com suas credenciais de administrador no aplicativo Dynamics 365 para instalar a solução.</span><span class="sxs-lookup"><span data-stu-id="65ae2-122">You may need to sign in with your admin credentials for the Dynamics 365 app to install the solution.</span></span>

<span data-ttu-id="65ae2-123">Pode levar algum tempo para a solução ser instalada no seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="65ae2-123">It can take some time for the solution to be installed to your environment.</span></span>

## <a name="configure-the-customer-card-add-in"></a><span data-ttu-id="65ae2-124">Configurar o Suplemento do Cartão do Cliente</span><span class="sxs-lookup"><span data-stu-id="65ae2-124">Configure the Customer Card Add-in</span></span>

1. <span data-ttu-id="65ae2-125">Como administrador, vá para a seção **Configurações** no Dynamics 365 e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-125">As an admin, go to the **Settings** section in Dynamics 365 and select **Solutions**.</span></span>

1. <span data-ttu-id="65ae2-126">Selecione o link **Nome para Exibição** da solução **Suplemento do Cartão do Cliente do Dynamics 365 Customer Insights (versão prévia)**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-126">Select the **Display Name** link for the **Dynamics 365 Customer Insights Customer Card Add-in (Preview)** solution.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65ae2-127">![Selecione nome para exibição](media/select-display-name.png "Selecione nome para exibição")</span><span class="sxs-lookup"><span data-stu-id="65ae2-127">![Select display name](media/select-display-name.png "Select display name")</span></span>

1. <span data-ttu-id="65ae2-128">Selecione **Entrar** e insira as credenciais da conta de administrador que você usa para configurar o Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="65ae2-128">Select **Sign in** and enter the credentials for the admin account you use to configure Customer Insights.</span></span>

   > [!NOTE]
   > <span data-ttu-id="65ae2-129">Verifique se o bloqueador de pop-up do navegador não bloqueia a janela de autenticação quando você seleciona o botão **Entrar**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-129">Check that the browser pop-up blocker does not block the authentication window when you select the **Sign in** button.</span></span>

1. <span data-ttu-id="65ae2-130">Selecione o ambiente do Customer Insights do qual você deseja extrair os dados.</span><span class="sxs-lookup"><span data-stu-id="65ae2-130">Select the Customer Insights environment you want to fetch data from.</span></span>

1. <span data-ttu-id="65ae2-131">Defina o mapeamento de campo para registros no aplicativo Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65ae2-131">Define the field mapping to records in the Dynamics 365 app.</span></span> <span data-ttu-id="65ae2-132">Dependendo de seus dados no Customer Insights, você pode escolher mapear estas opções:</span><span class="sxs-lookup"><span data-stu-id="65ae2-132">Depending on your data in Customer Insights you can choose to map the following options:</span></span>
   - <span data-ttu-id="65ae2-133">Para mapear com um contato, selecione o campo na entidade Cliente que corresponde à ID de sua entidade de contato.</span><span class="sxs-lookup"><span data-stu-id="65ae2-133">To map with a contact, select the field in the Customer entity that matches the ID of your contact entity.</span></span>
   - <span data-ttu-id="65ae2-134">Para mapear com uma conta, selecione o campo na entidade Cliente que corresponde à ID da entidade de sua conta.</span><span class="sxs-lookup"><span data-stu-id="65ae2-134">To map with an account, select the field in the Customer entity that matches the ID of your account entity.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="65ae2-135">![Campo ID de Contato](media/contact-id-field.png "Campo ID de Contato")</span><span class="sxs-lookup"><span data-stu-id="65ae2-135">![Contact ID field](media/contact-id-field.png "Contact ID field")</span></span>

1. <span data-ttu-id="65ae2-136">Selecione **Salvar configuração** para salvar as configurações.</span><span class="sxs-lookup"><span data-stu-id="65ae2-136">Select **Save configuration** to save the settings.</span></span>

1. <span data-ttu-id="65ae2-137">Em seguida, você precisa atribuir funções de segurança no Dynamics 365 para que os usuários possam personalizar e exibir o cartão do cliente.</span><span class="sxs-lookup"><span data-stu-id="65ae2-137">Next, you need to assign security roles in Dynamics 365 so users can customize and see the customer card.</span></span> <span data-ttu-id="65ae2-138">No Dynamics 365, vá para **Configurações** > **Segurança** > **Usuários**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-138">In Dynamics 365, go to **Settings** > **Security** > **Users**.</span></span> <span data-ttu-id="65ae2-139">Selecione os usuários para editar as funções do usuário e selecione **Gerenciar funções**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-139">Select the users to edit user roles and select **Manage roles**.</span></span>

1. <span data-ttu-id="65ae2-140">Atribua a função **Personalizador de Cartão do Customer Insights** a usuários que personalizarão o conteúdo mostrado no cartão para toda a organização.</span><span class="sxs-lookup"><span data-stu-id="65ae2-140">Assign the **Customer Insights Card Customizer** role to users who will customize the content shown on the card for the whole organization.</span></span>

## <a name="add-customer-card-controls-to-forms"></a><span data-ttu-id="65ae2-141">Adicionar controles de cartão de cliente a formulários</span><span class="sxs-lookup"><span data-stu-id="65ae2-141">Add Customer Card controls to forms</span></span>
  
1. <span data-ttu-id="65ae2-142">Para adicionar os controles do Cartão do Cliente ao seu formulário de contato, vá para **Configurações** > **Personalizações** no Dynamics 365.</span><span class="sxs-lookup"><span data-stu-id="65ae2-142">To add the Customer Card controls to your Contact form, go to the **Settings** > **Customizations** in Dynamics 365.</span></span>

1. <span data-ttu-id="65ae2-143">Selecione **Personalizar o sistema**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-143">Select **Customize the System**.</span></span>

1. <span data-ttu-id="65ae2-144">Navegue até a entidade **Contato**, expanda-a e selecione **Formulários**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-144">Browse to the **Contact** entity, expand it and select **Forms**.</span></span>

1. <span data-ttu-id="65ae2-145">Selecione o formulário de contato ao qual você deseja adicionar os controles do Cartão do Cliente.</span><span class="sxs-lookup"><span data-stu-id="65ae2-145">Select the contact form to which you want to add the Customer Card controls.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="65ae2-146">![Selecione o formulário de Contato](media/contact-active-forms.png "Selecione o formulário de Contato")</span><span class="sxs-lookup"><span data-stu-id="65ae2-146">![Select Contact form](media/contact-active-forms.png "Select Contact form")</span></span>

1. <span data-ttu-id="65ae2-147">Para adicionar um controle, no editor de formulários, arraste qualquer campo do **Gerenciador de Campos** para o local em que deseja que o controle apareça.</span><span class="sxs-lookup"><span data-stu-id="65ae2-147">To add a control, in the form editor, drag any field from the **Field Explorer** to where you want the control to appear.</span></span>

1. <span data-ttu-id="65ae2-148">Selecione o campo no formulário que você acabou de adicionar e selecione **Alterar Propriedades**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-148">Select the field on the form that you just added, and select **Change Properties**.</span></span>

1. <span data-ttu-id="65ae2-149">Vá para a guia **Controles** e selecione **Adicionar Controle**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-149">Go to the **Controls** tab and select **Add Control**.</span></span> <span data-ttu-id="65ae2-150">Escolha um dos controles personalizados disponíveis e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-150">Choose one of the available custom controls and select **Add**.</span></span>

1. <span data-ttu-id="65ae2-151">Na caixa de diálogo **Propriedades do Campo**, limpe a caixa de seleção **Exibir rótulo no formulário**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-151">In the **Field Properties** dialog, clear the **Display label on the form** check box.</span></span>

1. <span data-ttu-id="65ae2-152">Selecione a opção **Web** para o controle.</span><span class="sxs-lookup"><span data-stu-id="65ae2-152">Select the **Web** option for the control.</span></span> <span data-ttu-id="65ae2-153">Para o controle Enriquecimento, selecione qual tipo de enriquecimento você quer exibir, configurando o campo **enriqumentType**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-153">For the Enrichment control, select which enrichment type you want to display by configuring the **enrichmentType** field.</span></span> <span data-ttu-id="65ae2-154">Adicione um controle de enriquecimento separado para cada tipo de enriquecimento.</span><span class="sxs-lookup"><span data-stu-id="65ae2-154">Add a separate enrichment control for each enrichment type.</span></span>

1. <span data-ttu-id="65ae2-155">Selecione **Salvar** e **Publicar** para publicar o formulário de contato atualizado.</span><span class="sxs-lookup"><span data-stu-id="65ae2-155">Select **Save** and **Publish** to publish the updated contact form.</span></span>

1. <span data-ttu-id="65ae2-156">Vá para o formulário de contato publicado.</span><span class="sxs-lookup"><span data-stu-id="65ae2-156">Go to the published contact form.</span></span> <span data-ttu-id="65ae2-157">Você verá o controle recém-adicionado.</span><span class="sxs-lookup"><span data-stu-id="65ae2-157">You'll see the newly added control.</span></span> <span data-ttu-id="65ae2-158">Pode ser necessário fazer login na primeira vez em que o utilizar.</span><span class="sxs-lookup"><span data-stu-id="65ae2-158">You might need to sign in the first time you use it.</span></span>

1. <span data-ttu-id="65ae2-159">Para personalizar o que você deseja mostrar no controle personalizado, selecione o botão de edição no canto superior direito.</span><span class="sxs-lookup"><span data-stu-id="65ae2-159">To customize what you want to show on the custom control, select the edit button in the upper-right corner.</span></span>

## <a name="upgrade-customer-card-add-in"></a><span data-ttu-id="65ae2-160">Atualizar Suplemento do Cartão do Cliente</span><span class="sxs-lookup"><span data-stu-id="65ae2-160">Upgrade Customer Card Add-in</span></span>
<span data-ttu-id="65ae2-161">O Suplemento do Cartão do Cliente não é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="65ae2-161">The Customer Card Add-in doesn't upgrade automatically.</span></span> <span data-ttu-id="65ae2-162">Para atualizar para a versão mais recente, siga este procedimento no aplicativo Dynamics 365 que tem o suplemento instalado.</span><span class="sxs-lookup"><span data-stu-id="65ae2-162">To upgrade to the latest version, follow this procedure in the Dynamics 365 app that has the Add-in installed.</span></span>

1. <span data-ttu-id="65ae2-163">No aplicativo Dynamics 365, acesse **Configurações** > **Personalização** e selecione **Soluções**.</span><span class="sxs-lookup"><span data-stu-id="65ae2-163">In the Dynamics 365 app, go to **Settings** > **Customization** and select **Solutions**.</span></span>

1. <span data-ttu-id="65ae2-164">Na tabela de suplementos, procure **CustomerInsightsCustomerCard** e selecione a linha.</span><span class="sxs-lookup"><span data-stu-id="65ae2-164">In the table of add-ins look for **CustomerInsightsCustomerCard** and select the row.</span></span>

1. <span data-ttu-id="65ae2-165">Selecione **Aplicar Atualização de Solução** na barra de ações.</span><span class="sxs-lookup"><span data-stu-id="65ae2-165">Select the **Apply Solution Upgrade** in the action bar.</span></span>

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atualize a solução na Área de personalização dos aplicativos do Dynamics 365":::

1. <span data-ttu-id="65ae2-167">Depois de iniciar o processo de atualização, você verá um indicador de carregamento até que a atualização seja concluída.</span><span class="sxs-lookup"><span data-stu-id="65ae2-167">After starting the upgrade process, you'll see a loading indicator until the upgrade completes.</span></span> <span data-ttu-id="65ae2-168">Se não houver uma versão mais recente, a atualização exibirá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="65ae2-168">If there's no newer version, the upgrade will show an error message.</span></span>


[!INCLUDE[footer-include](../includes/footer-banner.md)]
