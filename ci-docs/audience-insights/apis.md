---
title: Trabalhar com APIs
description: Use APIs e entenda as limitações.
ms.date: 05/10/2021
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: b1e022f8afb8b7dbb707636009b6a25ee242a4e0
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354771"
---
# <a name="work-with-customer-insights-apis"></a>Trabalhar com APIs do Customer Insights

O Dynamics 365 Customer Insights fornece APIs para criar seus próprios aplicativos com base em seus dados no Customer Insights.

> [!IMPORTANT]
> Os detalhes dessas APIs estão listados na [Referência de APIs do Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Eles incluem informações adicionais sobre operações, parâmetros e respostas.

Este artigo descreve como acessar as APIs do Customer Insights, criar um Registro de Azure App e começar a usar as bibliotecas de cliente disponíveis.

## <a name="get-started-trying-the-customer-insights-apis"></a>Comece a experimentar as APIs do Customer Insights

1. [Entre](https://home.ci.ai.dynamics.com) no Customer Insights. Se você ainda não tem uma assinatura, [inscreva-se para obter uma avaliação do Customer Insights](https://aka.ms/tryci).

1. Para habilitar APIs em seu ambiente do Customer Insights, acesse **Administrador** > **Permissões**. Você precisará de permissões de administrador para fazer isso.

1. Acesse a guia **APIs** e selecione o botão **Habilitar**.    
 
   Habilitar as APIs cria uma chave de assinatura primária e secundária para sua instância, que é usada nas solicitações de API. É possível regenerar as chaves selecionando **Regenerar primária** ou **Regenerar secundária** em **Administrador** > **Permissões** > **APIs**.

<!--  :::image type="content" source="media/enable-apis.gif" alt-text="Enable Customer Insights APIs."::: -->

1. Selecione **Explorar nossas APIs** para [experimentar as APIs](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances).

1. Escolha uma operação de API e selecione **Experimentar**.

1. No painel lateral, defina o valor no menu suspenso **Autorização** como **implícito**. O cabeçalho `Authorization` será adicionado com um token de portador. Sua chave de assinatura será preenchida automaticamente.
  
1. Opcionalmente, adicione todos os parâmetros de consulta necessários.

1. Role até a parte inferior do painel lateral e selecione **Enviar**.

A resposta HTTP aparecerá logo abaixo.

<!--   :::image type="content" source="media/try-apis.gif" alt-text="How to test the APIs."::: -->

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Criar um registro de aplicativo no portal do Azure

Essas etapas ajudam você a começar a usar as APIs do Customer Insights em um aplicativo Azure usando permissões delegadas. Certifique-se de concluir a [seção de Introdução](#get-started-trying-the-customer-insights-apis) primeiro.

1. Entre no [portal do Azure](https://portal.azure.com) com a conta que pode acessar os dados do Customer Insights.

1. À esquerda, selecione **Registros de aplicativo**.

1. Selecione **Novo registro**, forneça um nome de aplicativo e escolha o tipo de conta.
 
   Ou adicione uma URL de redirecionamento. http://localhost é suficiente para desenvolver um aplicativo em seu computador local.

1. No seu novo registro de aplicativo, vá para **Permissões de API**.

<!--   :::image type="content" source="media/app-registration-1.gif" alt-text="How to set API permissions in App registration."::: -->

1. Selecione **Adicionar uma permissão** e **Customer Insights** no painel lateral.

1. Em **Tipo de permissão**, selecione **Permissões delegadas** e, em seguida, selecione a permissão **user_impersonation**.

1. Selecione **Adicionar permissões**. Se você precisar acessar a API sem que um usuário faça logon, consulte a seção [Permissões de aplicativo de servidor a servidor](#server-to-server-application-permissions).

1. Selecione **Conceder consentimento do administrador para...** para concluir o registro do aplicativo.

Você pode usar a ID do aplicativo/cliente para esse registro de aplicativo na Biblioteca de Autenticação da Microsoft (MSAL) para obter um token de portador para envio com sua solicitação à API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Para obter mais informações sobre MSAL, consulte [Visão geral da Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview).

Para obter mais informações sobre o registro de aplicativos no Azure, consulte [Registrar um aplicativo](/azure/active-directory/develop/quickstart-register-app.md#register-an-application).

Para obter informações sobre como usar as APIs em nossas bibliotecas de cliente, consulte [Bibliotecas de cliente do Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permissões de aplicativo de servidor a servidor

A [seção de registro de aplicativo](#create-a-new-app-registration-in-the-azure-portal) descreve como registrar um aplicativo que exige que um usuário faça logon para autenticação. Saiba como criar um registro de aplicativo que não precise da interação do usuário e possa ser executado em um servidor.

1. No registro do seu aplicativo no portal do Azure, vá para **Permissões de API**.

1. Selecione **Adicionar permissão**. 

1. Selecione a guia **APIs que minha organização usa** e escolha **Dynamics 365 AI para Customer Insights** na lista. 

1. Em **Tipo de permissão**, selecione **Permissões de aplicativo** e, em seguida, selecione a permissão **CustomerInsights.Api.All**.

1. Selecione **Adicionar permissões**.

1. Volte para **Permissões de API** para o registro do seu aplicativo.

1. Selecione **Conceder consentimento do administrador para...** para concluir o registro do aplicativo.

 <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Para concluir, é preciso adicionar o nome do registro do aplicativo como um usuário no Customer Insights.  
   
   Abra o Customer Insights, acesse **Administrador** > **Permissões** e selecione **Adicionar usuário**.

1. Pesquise o nome do registro do seu aplicativo, selecione-o nos resultados da pesquisa e selecione **Salvar**.

## <a name="customer-insights-client-libraries"></a>Bibliotecas de clientes do Customer Insights

Esta seção ajuda você a começar a usar as bibliotecas de clientes disponíveis para as APIs do Customer Insights. Todo o código-fonte da biblioteca e os aplicativos de exemplo podem ser encontrados na [página do Customer Insights no GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries). 

### <a name="c-nuget"></a>C# NuGet

Saiba como começar a usar as bibliotecas de clientes C# de NuGet.org. Para obter mais informações sobre o pacote NuGet, consulte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/). Atualmente, esse pacote é direcionado às estruturas netstandard2.0 e netcoreapp2.0.

#### <a name="add-the-c-client-library-to-a-c-project"></a>Adicionar a biblioteca de cliente C# a um projeto C#

1. No Visual Studio, abra o **Gerenciador de Pacotes NuGet** para o seu projeto.

1. Procure **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selecione **Instalar** para adicionar o pacote ao projeto.
 
   Se desejar, execute este comando no **Console do Gerenciador de Pacotes NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

 <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Usar a biblioteca de cliente C#

1. Use a [Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter um `AccessToken` usando seu [registro do Azure App](#create-a-new-app-registration-in-the-azure-portal) existente.

1. Depois de autenticar e adquirir um token com êxito, crie um ou use um `HttpClient` existente com a **"Autorização" DefaultRequestHeaders** adicional definida como **"Token de acesso" de Portador** e **Ocp-Apim-Subscription-Key** definida como a [**chave de assinatura** de seu ambiente do Customer Insights](#get-started-trying-the-customer-insights-apis).   
 
   Redefina o cabeçalho **Autorização** quando apropriado. Por exemplo, quando o token expirou.

1. Passe este `HttpClient` para a construção do cliente `CustomerInsights`.

<!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Faça chamadas com o cliente para os "métodos de extensão", por exemplo, `GetAllInstancesAsync`. Se o acesso ao `Microsoft.Rest.HttpOperationResponse` subjacente for preferencial, use os" métodos de mensagem http ", por exemplo, `GetAllInstancesWithHttpMessagesAsync`.

1. A resposta provavelmente será do tipo `object` porque o método pode retornar vários tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`). Para verificar o tipo de retorno, você pode converter com segurança os objetos nos tipos de resposta especificados na [página de detalhes da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) para essa operação.    
   
   Se mais informações sobre a solicitação forem necessárias, use os **métodos de mensagem http** para acessar o objeto de resposta bruto.

### <a name="nodejs-package"></a>Pacote NodeJS

Use as bibliotecas de cliente NodeJS disponíveis no NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pacote Python

Use as bibliotecas de cliente Python disponíveis no PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE[footer-include](../includes/footer-banner.md)]
