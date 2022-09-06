---
title: Trabalhar com APIs do Customer Insights
description: Use APIs e entenda as limitações.
ms.date: 08/31/2022
ms.reviewer: wimohabb
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
searchScope:
- ci-system-api-usage
- customerInsights
ms.openlocfilehash: f499bff4a6ac07a88ff0f773b9cee77dc74989e8
ms.sourcegitcommit: 624b27bb65a0de1970dc1ac436643b493f0a31cf
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "9387326"
---
# <a name="work-with-customer-insights-apis"></a>Trabalhar com APIs do Customer Insights

O Dynamics 365 Customer Insights fornece APIs para criar seus próprios aplicativos com base em seus dados no Customer Insights.

> [!IMPORTANT]
> Os detalhes dessas APIs estão listados na [Referência de APIs do Customer Insights](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights). Eles incluem informações adicionais sobre operações, parâmetros e respostas.

Experimente as APIs do Customer Insights, crie um Registro do Azure App e comece a usar as bibliotecas de clientes.

## <a name="get-started-trying-the-customer-insights-apis"></a>Comece a experimentar as APIs do Customer Insights

Habilite as APIs do Customer Insights e experimente-as. Um administrador do Customer Insights deve habilitar o acesso da API ao Customer Insights. Depois que o acesso for habilitado, qualquer usuário poderá usar a API com a chave de assinatura.

1. [Entre](https://home.ci.ai.dynamics.com) no Customer Insights. Se você ainda não tem uma assinatura, [inscreva-se para obter uma avaliação do Customer Insights](https://aka.ms/tryci).

1. Acesse **Administrador** > **Segurança** e selecione a guia **APIs**.

1. Se o acesso da API ao ambiente não tiver sido configurado, selecione **Habilitar**.

   Habilitar as APIs cria uma chave de assinatura primária e secundária para sua instância, que é usada nas solicitações de API. Para regenerar as chaves, selecione **Regenerar primária** ou **Regenerar secundária** na guia **APIs**.

1. Selecione [**Explorar nossas APIs**](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights&operation=Get-all-instances) para experimentar as APIs.

1. Pesquise e selecione uma operação de API e, em seguida, selecione **Experimentar**.

   :::image type="content" source="media/try-api.png" alt-text="Como testar as APIs.":::

1. No painel lateral, defina o valor no menu suspenso **Autorização** como **implícito**. O cabeçalho `Authorization` será adicionado com um token de portador. Sua chave de assinatura será preenchida automaticamente.
  
1. Opcionalmente, adicione todos os parâmetros de consulta necessários.

1. Role até a parte inferior do painel lateral e selecione **Enviar**.

   A resposta HTTP será exibida na parte inferior do painel.

## <a name="create-a-new-app-registration-in-the-azure-portal"></a>Criar um registro de aplicativo no portal do Azure

Crie um novo [registro de aplicativo](/graph/auth-register-app-v2) para usar as APIs do Customer Insights em um aplicativo do Azure por meio de permissões delegadas.

1. Conclua a [seção Introdução](#get-started-trying-the-customer-insights-apis).

1. Entre no [portal do Azure](https://portal.azure.com) com a conta que pode acessar os dados do Customer Insights.

1. Procure e selecione **Registros de aplicativo**.

1. Selecione **Novo registro**, forneça um nome de aplicativo e escolha o tipo de conta.

   Ou adicione uma URL de redirecionamento. http://localhost é suficiente para desenvolver um aplicativo em seu computador local.

1. Selecione **Registrar**.

1. No seu novo registro de aplicativo, vá para **Permissões de API**.

1. Selecione **Adicionar uma permissão** e **Dynamics 365 AI for Customer Insights** no painel lateral.

1. Em **Tipo de permissão**, selecione **Permissões delegadas** e, em seguida, selecione a permissão **user_impersonation**.

1. Selecione **Adicionar permissões**.

1. Selecione **Conceder consentimento do administrador para...** para concluir o registro do aplicativo.

1. Para acessar a API sem que um usuário faça logon, vá para [Permissões de aplicativo de servidor para servidor](#server-to-server-application-permissions).

Você pode usar a ID do aplicativo/cliente para esse registro de aplicativo na [Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) a fim de obter um token de portador para envio com sua solicitação à API.

<!-- :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

Para obter informações sobre como usar as APIs em nossas bibliotecas de cliente, consulte [Bibliotecas de cliente do Customer Insights](#customer-insights-client-libraries).

### <a name="server-to-server-application-permissions"></a>Permissões de aplicativo de servidor a servidor

Crie um registro de aplicativo que não precise de interação do usuário e possa ser executado em um servidor.

1. No registro do seu aplicativo no portal do Azure, vá para **Permissões de API**.

1. Selecione **Adicionar permissão**.

1. Selecione a guia **APIs que minha organização usa** e escolha **Dynamics 365 AI para Customer Insights** na lista.

1. Em **Tipo de permissão**, selecione **Permissões de aplicativo** e, em seguida, selecione a permissão **CustomerInsights.Api.All**.

1. Selecione **Adicionar permissões**.

1. Volte para **Permissões de API** para o registro do seu aplicativo.

1. Selecione **Conceder consentimento do administrador para...** para concluir o registro do aplicativo.

   <!--  :::image type="content" source="media/grant-admin-consent.gif" alt-text="How to grant admin consent."::: -->

1. Adicione o nome do registro do aplicativo como um usuário no Customer Insights.

   1. Abra o Customer Insights, acesse **Administrador** > **Segurança** e selecione **Adicionar usuários**.

   1. Pesquise o nome do registro do seu aplicativo, selecione-o nos resultados da pesquisa e selecione **Salvar**.

## <a name="sample-queries"></a>Consultas de amostra

Para ver uma breve lista de consultas de exemplo OData para trabalhar com as APIs, consulte [Exemplos de consulta OData](odata-examples.md).

## <a name="customer-insights-client-libraries"></a>Bibliotecas de clientes do Customer Insights

Comece a usar as bibliotecas de clientes disponíveis para as APIs do Customer Insights. Todo o código-fonte da biblioteca e os aplicativos de exemplo podem ser encontrados na [página do Customer Insights no GitHub](https://github.com/microsoft/Dynamics365-CustomerInsights-Client-Libraries).

### <a name="c-nuget"></a>C# NuGet

Use as bibliotecas de clientes C# de NuGet.org. Atualmente, o pacote é direcionado às estruturas netstandard2.0 e netcoreapp2.0. Para obter mais informações sobre o pacote NuGet, consulte [Microsoft.Dynamics.CustomerInsights.Api](https://www.nuget.org/packages/Microsoft.Dynamics.CustomerInsights.Api/).

#### <a name="add-the-c-client-library-to-a-c-project"></a>Adicionar a biblioteca de cliente C# a um projeto C#

1. No Visual Studio, abra o **Gerenciador de Pacotes NuGet** para o seu projeto.

1. Procure **Microsoft.Dynamics.CustomerInsights.Api**.

1. Selecione **Instalar** para adicionar o pacote ao projeto.

   Se desejar, execute este comando no **Console do Gerenciador de Pacotes NuGet**: `Install-Package -Id Microsoft.Dynamics.CustomerInsights.Api -Source nuget.org -ProjectName <project name> [-Version <version>]`

   <!--  :::image type="content" source="media/visual-studio-nuget-package.gif" alt-text="Add NuGet package to Visual Studio project."::: -->

#### <a name="use-the-c-client-library"></a>Usar a biblioteca de cliente C#

1. Use a [Biblioteca de Autenticação da Microsoft (MSAL)](/azure/active-directory/develop/msal-overview) para obter um `AccessToken` usando seu [registro do Azure App](#create-a-new-app-registration-in-the-azure-portal) existente.

1. Depois de autenticar e adquirir um token com êxito, crie ou use um `HttpClient` existente com a **"Autorização" DefaultRequestHeaders** definida como **"Token de acesso" de Portador** e **Ocp-Apim-Subscription-Key** definida como a [**chave de assinatura** do ambiente do Customer Insights](#get-started-trying-the-customer-insights-apis).   

   Redefina o cabeçalho **Autorização** quando apropriado. Por exemplo, quando o token expirou.

1. Passe este `HttpClient` para a construção do cliente `CustomerInsights`.

   <!--   :::image type="content" source="media/httpclient-sample.png" alt-text="Sample of httpclient."::: -->

1. Faça chamadas com o cliente para os "métodos de extensão", por exemplo, `GetAllInstancesAsync`. Se o acesso ao `Microsoft.Rest.HttpOperationResponse` subjacente for preferencial, use os "métodos de mensagem http", por exemplo, `GetAllInstancesWithHttpMessagesAsync`.

1. A resposta provavelmente será do tipo `object` porque o método pode retornar vários tipos (por exemplo, `IList<InstanceInfo>` e `ApiErrorResult`). Para verificar o tipo de retorno, use os objetos nos tipos de resposta especificados na [página Detalhes da API](https://developer.ci.ai.dynamics.com/api-details#api=CustomerInsights) dessa operação.

   Se mais informações sobre a solicitação forem necessárias, use os **métodos de mensagem http** para acessar o objeto de resposta bruto.

### <a name="nodejs-package"></a>Pacote NodeJS

Use as bibliotecas de cliente NodeJS disponíveis no NPM: https://www.npmjs.com/package/@microsoft/customerinsights

### <a name="python-package"></a>Pacote Python

Use as bibliotecas de cliente Python disponíveis no PyPi: https://pypi.org/project/customerinsights/

[!INCLUDE [footer-include](includes/footer-banner.md)]
