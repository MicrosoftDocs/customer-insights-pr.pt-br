---
title: Trabalhar com APIs
description: Use APIs e entenda as limitações.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: 9326f821f9970ba2254ab804814e369abb677eb0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304728"
---
# <a name="work-with-customer-insights-apis"></a><span data-ttu-id="68da7-103">Trabalhar com APIs do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="68da7-103">Work with Customer Insights APIs</span></span>

<span data-ttu-id="68da7-104">O Dynamics 365 Customer Insights fornece APIs para criar seus próprios aplicativos com base em seus dados no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="68da7-104">Dynamics 365 Customer Insights provides APIs to build your own applications based on your data in Customer Insights.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="68da7-105">Os detalhes dessas APIs estão listados na [Referência de APIs do Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span><span class="sxs-lookup"><span data-stu-id="68da7-105">Details of these APIs are listed on the [Customer Insights APIs reference](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights).</span></span> <span data-ttu-id="68da7-106">Eles incluem informações adicionais sobre operações, parâmetros e respostas.</span><span class="sxs-lookup"><span data-stu-id="68da7-106">They include additional information about operations, parameters, and responses.</span></span>

<span data-ttu-id="68da7-107">Este artigo descreve como acessar as APIs do Customer Insights, criar um Registro de Azure App e começar a usar as bibliotecas de cliente disponíveis.</span><span class="sxs-lookup"><span data-stu-id="68da7-107">This article describes how to access the Customer Insights APIs, create an Azure App Registration, and get started with the available client libraries.</span></span>

## <a name="get-started-trying-the-customer-insights-apis"></a><span data-ttu-id="68da7-108">Comece a experimentar as APIs do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="68da7-108">Get started trying the Customer Insights APIs</span></span>

1. <span data-ttu-id="68da7-109">[Entre](https://home.ci.ai.dynamics.com) no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="68da7-109">[Sign in](https://home.ci.ai.dynamics.com) to Customer Insights.</span></span> <span data-ttu-id="68da7-110">Se você ainda não tem uma assinatura, [inscreva-se para obter uma avaliação do Customer Insights](https://aka.ms/tryci).</span><span class="sxs-lookup"><span data-stu-id="68da7-110">If you don't have a subscription yet, [sign up for a trial of Customer Insights](https://aka.ms/tryci).</span></span>

1. <span data-ttu-id="68da7-111">Para habilitar APIs em seu ambiente do Customer Insights, acesse **Administrador** > **Permissões**.</span><span class="sxs-lookup"><span data-stu-id="68da7-111">To enable APIs on your Customer Insights environment, go to **Admin** > **Permissions**.</span></span> <span data-ttu-id="68da7-112">Você precisará de permissões de administrador para fazer isso.</span><span class="sxs-lookup"><span data-stu-id="68da7-112">You'll need admin permissions to do so.</span></span>

1. <span data-ttu-id="68da7-113">Acesse a guia **APIs** e selecione o botão **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="68da7-113">Go to the **APIs** tab and select the **Enable** button.</span></span>    
 
   <span data-ttu-id="68da7-114">Habilitar as APIs cria uma chave de assinatura primária e secundária para sua instância, que é usada nas solicitações de API.</span><span class="sxs-lookup"><span data-stu-id="68da7-114">Enabling the APIs creates a primary and secondary subscription key for your instance that gets used in the API requests.</span></span> <span data-ttu-id="68da7-115">É possível regenerar as chaves selecionando **Regenerar primária** ou **Regenerar secundária** em **Administrador** > **Permissões** > **APIs**.</span><span class="sxs-lookup"><span data-stu-id="68da7-115">You can regenerate the keys by selecting the **Regenerate primary** or **Regenerate secondary** on **Admin** > **Permissions** > **APIs**.</span></span>

   :::image type="content" source="media/enable-apis.gif" alt-text="Habilitar APIs do Customer Insights":::

1. <span data-ttu-id="68da7-117">Selecione **Explorar nossas APIs** para [experimentar as APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span><span class="sxs-lookup"><span data-stu-id="68da7-117">Select **Explore our APIs** to [try out the APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).</span></span>

1. <span data-ttu-id="68da7-118">Escolha uma operação de API e selecione **Experimentar**.</span><span class="sxs-lookup"><span data-stu-id="68da7-118">Choose an API operation and select **Try it**.</span></span>

1. <span data-ttu-id="68da7-119">No painel lateral, defina o valor no menu suspenso **Autorização** como **implícito**.</span><span class="sxs-lookup"><span data-stu-id="68da7-119">In the side pane, set the value in the **Authorization** dropdown menu to **implicit**.</span></span> <span data-ttu-id="68da7-120">O cabeçalho `Authorization` será adicionado com um token de portador.</span><span class="sxs-lookup"><span data-stu-id="68da7-120">The `Authorization` header gets added with a bearer token.</span></span> <span data-ttu-id="68da7-121">Sua chave de assinatura será preenchida automaticamente.</span><span class="sxs-lookup"><span data-stu-id="68da7-121">Your subscription key will be automatically populated.</span></span>
  
1. <span data-ttu-id="68da7-122">Opcionalmente, adicione todos os parâmetros de consulta necessários.</span><span class="sxs-lookup"><span data-stu-id="68da7-122">Optionally, add all necessary query parameters.</span></span>

1. <span data-ttu-id="68da7-123">Role até a parte inferior do painel lateral e selecione **Enviar**.</span><span class="sxs-lookup"><span data-stu-id="68da7-123">Scroll to the bottom of the side pane and select **Send**.</span></span>

<span data-ttu-id="68da7-124">A resposta HTTP aparecerá logo abaixo.</span><span class="sxs-lookup"><span data-stu-id="68da7-124">The HTTP response will soon appear below.</span></span>

   :::image type="content" source="media/try-apis.gif" alt-text="Como testar as APIs.":::

## <a name="create-a-new-app-registration-in-the-azure-portal"></a><span data-ttu-id="68da7-126">Criar um registro de aplicativo no portal do Azure</span><span class="sxs-lookup"><span data-stu-id="68da7-126">Create a new app registration in the Azure portal</span></span>

<span data-ttu-id="68da7-127">Essas etapas ajudam você a começar a usar as APIs do Customer Insights em um aplicativo Azure usando permissões delegadas.</span><span class="sxs-lookup"><span data-stu-id="68da7-127">These steps help you get started with using the Customer Insights APIs in an Azure application using delegated permissions.</span></span> <span data-ttu-id="68da7-128">Certifique-se de concluir a [seção de Introdução](#get-started-trying-the-customer-insights-apis) primeiro.</span><span class="sxs-lookup"><span data-stu-id="68da7-128">Make sure to complete the [Getting started section](#get-started-trying-the-customer-insights-apis) first.</span></span>

1. <span data-ttu-id="68da7-129">Entre no [portal do Azure](https://portal.azure.com) com a conta que pode acessar os dados do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="68da7-129">Sign in to the [Azure portal](https://portal.azure.com) with the account that can access the Customer Insights data.</span></span>

1. <span data-ttu-id="68da7-130">À esquerda, selecione **Registros de aplicativo**.</span><span class="sxs-lookup"><span data-stu-id="68da7-130">On the left, select **App registrations**.</span></span>

1. <span data-ttu-id="68da7-131">Selecione **Novo registro**, forneça um nome de aplicativo e escolha o tipo de conta.</span><span class="sxs-lookup"><span data-stu-id="68da7-131">Select **New registration**, provide an application name and choose the account type.</span></span>
 
   <span data-ttu-id="68da7-132">Ou adicione uma URL de redirecionamento.</span><span class="sxs-lookup"><span data-stu-id="68da7-132">Optionally, add a redirect URL.</span></span> <span data-ttu-id="68da7-133">http://localhost é suficiente para desenvolver um aplicativo em seu computador local.</span><span class="sxs-lookup"><span data-stu-id="68da7-133">http://localhost is sufficient for developing an application on your local computer.</span></span>

1. <span data-ttu-id="68da7-134">No seu novo registro de aplicativo, vá para **Permissões de API**.</span><span class="sxs-lookup"><span data-stu-id="68da7-134">On your new App registration, go to **API permissions**.</span></span>

   :::image type="content" source="media/app-registration-1.gif" alt-text="Como definir permissões de API no registro do aplicativo.":::

1. <span data-ttu-id="68da7-136">Selecione **Adicionar uma permissão** e **Customer Insights** no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="68da7-136">Select **Add a permission** and select **Customer Insights** in the side pane.</span></span>

1. <span data-ttu-id="68da7-137">Em **Tipo de permissão**, selecione **Permissões delegadas** e, em seguida, selecione a permissão **user_impersonation**.</span><span class="sxs-lookup"><span data-stu-id="68da7-137">For **Permission type**, select **Delegated permissions** and then select the **user_impersonation** permission.</span></span>

1. <span data-ttu-id="68da7-138">Selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="68da7-138">Select **Add permissions**.</span></span> <span data-ttu-id="68da7-139">Se você precisar acessar a API sem que um usuário faça logon, consulte a seção [Permissões de aplicativo de servidor a servidor](#server-to-server-application-permissions).</span><span class="sxs-lookup"><span data-stu-id="68da7-139">If you need to access the API without a user signing in, review the [Server-to-server application permissions](#server-to-server-application-permissions) section.</span></span>

1. <span data-ttu-id="68da7-140">Selecione **Conceder consentimento do administrador para...** para concluir o registro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="68da7-140">Select **Grant admin consent for...** to complete the app registration.</span></span>

<span data-ttu-id="68da7-141">Você pode usar a ID do aplicativo/cliente para esse registro de aplicativo na Biblioteca de Autenticação da Microsoft (MSAL) para obter um token de portador para envio com sua solicitação à API.</span><span class="sxs-lookup"><span data-stu-id="68da7-141">You can use the Application/Client ID for this app registration with the Microsoft Authentication Library (MSAL) to obtain a bearer token to send with your request to the API.</span></span>

:::image type="content" source="media/grant-admin-consent.gif" alt-text="Conceder consentimento de administrador.":::

<span data-ttu-id="68da7-143">Para obter mais informações sobre MSAL, consulte [Visão geral da Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).</span><span class="sxs-lookup"><span data-stu-id="68da7-143">For more information about MSAL, see [Overview of Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview).</span></span>

<span data-ttu-id="68da7-144">Para obter mais informações sobre o registro de aplicativos no Azure, consulte [Registrar um aplicativo](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span><span class="sxs-lookup"><span data-stu-id="68da7-144">For more information about app registration in Azure, see [Register an application](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).</span></span>

<span data-ttu-id="68da7-145">Para obter informações sobre como usar as APIs em nossas bibliotecas de cliente, consulte [Bibliotecas de cliente do Customer Insights](#customer-insights-client-libraries).</span><span class="sxs-lookup"><span data-stu-id="68da7-145">For information on using the APIs in our client libraries, see [Customer Insights client libraries](#customer-insights-client-libraries).</span></span>

### <a name="server-to-server-application-permissions"></a><span data-ttu-id="68da7-146">Permissões de aplicativo de servidor a servidor</span><span class="sxs-lookup"><span data-stu-id="68da7-146">Server-to-server application permissions</span></span>

<span data-ttu-id="68da7-147">A [seção de registro de aplicativo](#create-a-new-app-registration-in-the-azure-portal) descreve como registrar um aplicativo que exige que um usuário faça logon para autenticação.</span><span class="sxs-lookup"><span data-stu-id="68da7-147">The [app registration section](#create-a-new-app-registration-in-the-azure-portal) outlines how to register an app that requires a user to sign in for authentication.</span></span> <span data-ttu-id="68da7-148">Saiba como criar um registro de aplicativo que não precise da interação do usuário e possa ser executado em um servidor.</span><span class="sxs-lookup"><span data-stu-id="68da7-148">Learn how to create an app registration that does not need user interaction and can be run on a server.</span></span>

1. <span data-ttu-id="68da7-149">No registro do seu aplicativo no portal do Azure, vá para **Permissões de API**.</span><span class="sxs-lookup"><span data-stu-id="68da7-149">On your App registration in the Azure portal, go to **API permissions**.</span></span>

1. <span data-ttu-id="68da7-150">Selecione **Adicionar permissão**.</span><span class="sxs-lookup"><span data-stu-id="68da7-150">Select **Add a permission**.</span></span> 

1. <span data-ttu-id="68da7-151">Selecione a guia **APIs que minha organização usa** e escolha **Dynamics 365 AI para Customer Insights** na lista.</span><span class="sxs-lookup"><span data-stu-id="68da7-151">Select the **APIs my organization uses** tab and choose **Dynamics 365 AI for Customer Insights** from the list.</span></span> 

1. <span data-ttu-id="68da7-152">Em **Tipo de permissão**, selecione **Permissões de aplicativo** e, em seguida, selecione a permissão **CustomerInsights.Api.All**.</span><span class="sxs-lookup"><span data-stu-id="68da7-152">For **Permission type**, select **Application permissions** and then select the **CustomerInsights.Api.All** permission.</span></span>

1. <span data-ttu-id="68da7-153">Selecione **Adicionar permissões**.</span><span class="sxs-lookup"><span data-stu-id="68da7-153">Select **Add permissions**.</span></span>

1. <span data-ttu-id="68da7-154">Volte para **Permissões de API** para o registro do seu aplicativo.</span><span class="sxs-lookup"><span data-stu-id="68da7-154">Go back to **API permissions** for your app registration.</span></span>

1. <span data-ttu-id="68da7-155">Selecione **Conceder consentimento do administrador para...** para concluir o registro do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="68da7-155">Select **Grant admin consent for...** to complete the app registration.</span></span>

   :::image type="content" source="media/grant-admin-consent.gif" alt-text="Conceder consentimento de administrador.":::

1. <span data-ttu-id="68da7-157">Para concluir, é preciso adicionar o nome do registro do aplicativo como um usuário no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="68da7-157">To conclude, we have to add the name of the app registration as a user in Customer Insights.</span></span>  
   
   <span data-ttu-id="68da7-158">Abra o Customer Insights, acesse **Administrador** > **Permissões** e selecione **Adicionar usuário**.</span><span class="sxs-lookup"><span data-stu-id="68da7-158">Open Customer Insights, go to **Admin** > **Permissions** and select **Add user**.</span></span>

1. <span data-ttu-id="68da7-159">Pesquise o nome do registro do seu aplicativo, selecione-o nos resultados da pesquisa e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="68da7-159">Search for the name of your app registration, select it from the search results, and select **Save**.</span></span>

## <a name="customer-insights-client-libraries"></a><span data-ttu-id="68da7-160">Bibliotecas de clientes do Customer Insights</span><span class="sxs-lookup"><span data-stu-id="68da7-160">Customer Insights client libraries</span></span>

<span data-ttu-id="68da7-161">Esta seção ajuda você a começar a usar as bibliotecas de clientes disponíveis para as APIs do Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="68da7-161">This section helps you get started using the client libraries available for the Customer Insights APIs.</span></span> <span data-ttu-id="68da7-162">Todo o código-fonte da biblioteca e os aplicativos de exemplo podem ser encontrados na [página do Customer Insights no GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span><span class="sxs-lookup"><span data-stu-id="68da7-162">All library source code and sample applications can be found on the [Customer Insights GitHub page](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).</span></span> 

### <a name="c-nuget"></a><span data-ttu-id="68da7-163">C# NuGet</span><span class="sxs-lookup"><span data-stu-id="68da7-163">C# NuGet</span></span>

<span data-ttu-id="68da7-164">Saiba como começar a usar as bibliotecas de clientes C# de NuGet.org. Para obter mais informações sobre o pacote NuGet, consulte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span><span class="sxs-lookup"><span data-stu-id="68da7-164">Learn how to get started using the C# client libraries from NuGet.org. For more information on the NuGet package, see [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).</span></span> <span data-ttu-id="68da7-165">Atualmente, esse pacote é direcionado às estruturas netstandard2.0 e netcoreapp2.0.</span><span class="sxs-lookup"><span data-stu-id="68da7-165">Currently, this package targets the netstandard2.0 and netcoreapp2.0 frameworks.</span></span>

#### <a name="add-the-c-client-library-to-a-c-project"></a><span data-ttu-id="68da7-166">Adicionar a biblioteca de cliente C# a um projeto C#</span><span class="sxs-lookup"><span data-stu-id="68da7-166">Add the C# client library to a C# project</span></span>

1. <span data-ttu-id="68da7-167">No Visual Studio, abra o **Gerenciador de Pacotes NuGet** para o seu projeto.</span><span class="sxs-lookup"><span data-stu-id="68da7-167">In Visual Studio, open the **NuGet Package Manager** for your project.</span></span>

1. <span data-ttu-id="68da7-168">Procure **Microsoft.Dynamics.CustomerInsights.Api**.</span><span class="sxs-lookup"><span data-stu-id="68da7-168">Search for **Microsoft.Dynamics.CustomerInsights.Api**.</span></span>

1. <span data-ttu-id="68da7-169">Selecione **Instalar** para adicionar o pacote ao projeto.</span><span class="sxs-lookup"><span data-stu-id="68da7-169">Select **Install** to add the package to the project.</span></span>
 
   <span data-ttu-id="68da7-170">Se desejar, execute este comando no **Console do Gerenciador de Pacotes NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span><span class="sxs-lookup"><span data-stu-id="68da7-170">Alternatively, run this command in the **NuGet Package Manager Console**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`</span></span>

   :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Adicione o pacote NuGet ao projeto do Visual Studio":::

#### <a name="use-the-c-client-library"></a><span data-ttu-id="68da7-172">Usar a biblioteca de cliente C#</span><span class="sxs-lookup"><span data-stu-id="68da7-172">Use the C# client library</span></span>

1. <span data-ttu-id="68da7-173">Use a [Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter um `AccessToken` usando seu [registro do Azure App](#create-a-new-app-registration-in-the-azure-portal) existente.</span><span class="sxs-lookup"><span data-stu-id="68da7-173">Use the [Microsoft Authentication Library (MSAL)](/azure/active-directory/develop/msal-overview) to get an `AccessToken` using your existing [Azure app registration](#create-a-new-app-registration-in-the-azure-portal).</span></span>

1. <span data-ttu-id="68da7-174">Depois de autenticar e adquirir um token com sucesso, crie um ou use um `HttpClient` existente com a **"Autorização" DefaultRequestHeaders** adicional definida como **Portador <access token>** e **Ocp-Apim-Subscription-Key** definido como [**chave de assinatura** do seu ambiente do Customer Insights](#get-started-trying-the-customer-insights-apis).</span><span class="sxs-lookup"><span data-stu-id="68da7-174">After successfully authenticating and acquiring a token, construct a new or use an existing `HttpClient` with the additional **DefaultRequestHeaders "Authorization"** set to **Bearer <access token>** and **Ocp-Apim-Subscription-Key** set to the [**subscription key** from your Customer Insights environment](#get-started-trying-the-customer-insights-apis).</span></span>   
 
   <span data-ttu-id="68da7-175">Redefina o cabeçalho **Autorização** quando apropriado.</span><span class="sxs-lookup"><span data-stu-id="68da7-175">Reset the **Authorization** header when appropriate.</span></span> <span data-ttu-id="68da7-176">Por exemplo, quando o token expirou.</span><span class="sxs-lookup"><span data-stu-id="68da7-176">For example, when the token expired.</span></span>

1. <span data-ttu-id="68da7-177">Passe este `HttpClient` para a construção do cliente `CustomerInsights`.</span><span class="sxs-lookup"><span data-stu-id="68da7-177">Pass this `HttpClient` into the construction of the `CustomerInsights` client.</span></span>

   :::image type="content" source="media/httpclient-sample.png" alt-text="Amostra de httpclient":::

1. <span data-ttu-id="68da7-179">Faça chamadas com o cliente para os "métodos de extensão", por exemplo, `GetAllInstancesAsync`.</span><span class="sxs-lookup"><span data-stu-id="68da7-179">Make calls with the client to the "extension methods"—for example, `GetAllInstancesAsync`.</span></span> <span data-ttu-id="68da7-180">Se o acesso ao `Microsoft.Rest.HttpOperationResponse` subjacente for preferencial, use os" métodos de mensagem http ", por exemplo, `GetAllInstancesWithHttpMessagesAsync`.</span><span class="sxs-lookup"><span data-stu-id="68da7-180">If access to the underlying `Microsoft.Rest.HttpOperationResponse` is preferred, use the "http message methods"—for example, `GetAllInstancesWithHttpMessagesAsync`.</span></span>

1. <span data-ttu-id="68da7-181">A resposta provavelmente será do tipo `object` porque o método pode retornar vários tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`).</span><span class="sxs-lookup"><span data-stu-id="68da7-181">The response will likely be of type `object` because the method can return multiple types (for example, `IList<InstanceInfo>` and `ApiErrorResult`).</span></span> <span data-ttu-id="68da7-182">Para verificar o tipo de retorno, você pode converter com segurança os objetos nos tipos de resposta especificados na [página de detalhes da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para essa operação.</span><span class="sxs-lookup"><span data-stu-id="68da7-182">To check the return type, you can safely cast the objects into the response types specified on the [API details page](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) for that operation.</span></span>    
   
   <span data-ttu-id="68da7-183">Se mais informações sobre a solicitação forem necessárias, use os **métodos de mensagem http** para acessar o objeto de resposta bruto.</span><span class="sxs-lookup"><span data-stu-id="68da7-183">If more information on the request is needed, use the **http message methods** to access the raw response object.</span></span>

### <a name="nodejs-package"></a><span data-ttu-id="68da7-184">Pacote NodeJS</span><span class="sxs-lookup"><span data-stu-id="68da7-184">NodeJS package</span></span>

<span data-ttu-id="68da7-185">Use as bibliotecas de cliente NodeJS disponíveis no NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span><span class="sxs-lookup"><span data-stu-id="68da7-185">Use the NodeJS client libraries available through NPM: https://www.npmjs.com/package/@microsoft/customerinsights</span></span>

### <a name="python-package"></a><span data-ttu-id="68da7-186">Pacote Python</span><span class="sxs-lookup"><span data-stu-id="68da7-186">Python package</span></span>

<span data-ttu-id="68da7-187">Use as bibliotecas de cliente Python disponíveis no PyPi: https://pypi.org/project/customerinsights/</span><span class="sxs-lookup"><span data-stu-id="68da7-187">Use the Python client libraries available through PyPi: https://pypi.org/project/customerinsights/</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
