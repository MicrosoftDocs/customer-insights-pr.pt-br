---
title: Enriquecimento com importação personalizada do SFTP
description: Informações gerais sobre o enriquecimento de importação personalizada do SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f92b36ac5364ea8586f9cbba7ba03178641555c0
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304636"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="dbf95-103">Enriquecer os perfis dos clientes com dados personalizados (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="dbf95-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="dbf95-104">A importação personalizada via SFTP permite que você importe dados que não precisam passar pelo processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="dbf95-104">Secure File Transfer Protocol (SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="dbf95-105">É uma maneira flexível, segura e fácil de reunir seus dados.</span><span class="sxs-lookup"><span data-stu-id="dbf95-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="dbf95-106">A importação personalizada via SFTP pode ser usada em combinação com a [exportação via SFTP](export-sftp.md), que permite exportar os dados de perfil do cliente necessários para aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="dbf95-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="dbf95-107">Os dados podem ser processados e enriquecidos, e a importação personalizada de SFTP pode ser usada para trazer os dados enriquecidos de volta para o recurso de insights de público-alvo do Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="dbf95-107">The data can then be processed and enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="dbf95-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="dbf95-108">Prerequisites</span></span>

<span data-ttu-id="dbf95-109">Para configurar a importação personalizada via SFTP, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="dbf95-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="dbf95-110">Você tem o nome do arquivo e a localização (caminho) do arquivo a ser importado no host SFTP.</span><span class="sxs-lookup"><span data-stu-id="dbf95-110">You have the file name and location (path) of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="dbf95-111">Há um arquivo *model.json* que especifica o [esquema do Common Data Model](/common-data-model/) para que os dados sejam importados.</span><span class="sxs-lookup"><span data-stu-id="dbf95-111">There is a *model.json* file that specifies [the Common Data Model schema](/common-data-model/) for the data to be imported.</span></span> <span data-ttu-id="dbf95-112">Esse arquivo deve estar no mesmo diretório do arquivo a ser importado.</span><span class="sxs-lookup"><span data-stu-id="dbf95-112">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="dbf95-113">Uma conexão SFTP já foi configurada por um administrador *ou* você tem permissões de [administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="dbf95-113">An SFTP connection has already been configured by an administrator *or* you have [administrator](permissions.md#administrator) permissions.</span></span> <span data-ttu-id="dbf95-114">Você precisará das credenciais do usuário, da URL e do número da porta do local do SFTP de onde deseja importar os dados.</span><span class="sxs-lookup"><span data-stu-id="dbf95-114">You'll need the user credentials, URL, and port number for the SFTP location where you want to import data from.</span></span>


## <a name="configure-the-import"></a><span data-ttu-id="dbf95-115">Configurar a importação</span><span class="sxs-lookup"><span data-stu-id="dbf95-115">Configure the import</span></span>

1. <span data-ttu-id="dbf95-116">Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="dbf95-116">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="dbf95-117">No **bloco de importação personalizada via SFTP**, selecione **Enriquecer meus dados** e depois selecione **Começar agora**.</span><span class="sxs-lookup"><span data-stu-id="dbf95-117">On the **SFTP custom import tile**, select **Enrich my data** and then select **Get started**.</span></span>

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Bloco de importação personalizada via SFTP.":::

1. <span data-ttu-id="dbf95-119">Selecione uma [conexão](connections.md) na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="dbf95-119">Select a [connection](connections.md) from the dropdown list.</span></span> <span data-ttu-id="dbf95-120">Contate um administrador se nenhuma conexão estiver disponível.</span><span class="sxs-lookup"><span data-stu-id="dbf95-120">Contact an administrator if no connection is available.</span></span> <span data-ttu-id="dbf95-121">Se for um administrador, você poderá criar uma conexão selecionando **Adicionar conexão** e escolhendo **Importação Personalizada de SFTP** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="dbf95-121">If you are an administrator, you can create a connection by selecting **Add connection** and choosing **SFTP Custom Import** from the dropdown list.</span></span>

1. <span data-ttu-id="dbf95-122">Selecione **Conectar-se à Importação Personalizada** para confirmar a conexão selecionada.</span><span class="sxs-lookup"><span data-stu-id="dbf95-122">Select **Connect to Custom Import** to confirm the selected connection.</span></span>

1.  <span data-ttu-id="dbf95-123">Selecione **Avançar** e insira o **Caminho** e o **Nome do arquivo** de dados que deseja importar.</span><span class="sxs-lookup"><span data-stu-id="dbf95-123">Select **Next** and enter the **Path** and **Filename** of the data file that you want to import.</span></span>

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de tela ao inserir a localização dos dados.":::

1. <span data-ttu-id="dbf95-125">Selecione **Próximo** e forneça um nome para o enriquecimento e um nome para a entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="dbf95-125">Select **Next** and provide a name for the enrichment and a name for the output entity.</span></span> 

1. <span data-ttu-id="dbf95-126">Selecione **Salvar enriquecimento** depois de revisar suas escolhas.</span><span class="sxs-lookup"><span data-stu-id="dbf95-126">Select **Save enrichment** after reviewing your choices.</span></span>

## <a name="configure-the-connection-for-sftp-custom-import"></a><span data-ttu-id="dbf95-127">Configurar a conexão para a Importação Personalizada via SFTP</span><span class="sxs-lookup"><span data-stu-id="dbf95-127">Configure the connection for SFTP Custom Import</span></span> 

<span data-ttu-id="dbf95-128">Você deve ser um administrador para configurar as conexões.</span><span class="sxs-lookup"><span data-stu-id="dbf95-128">You need to be an administrator to configure connections.</span></span> <span data-ttu-id="dbf95-129">Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da Importação Personalizada.</span><span class="sxs-lookup"><span data-stu-id="dbf95-129">Select **Add connection** when configuring an enrichment *or* go to **Admin** > **Connections** and select **Set up** on the Custom Import tile.</span></span>

1. <span data-ttu-id="dbf95-130">Insira um nome para a conexão na caixa **Nome de exibição**.</span><span class="sxs-lookup"><span data-stu-id="dbf95-130">Enter a name for the connection in the **Display name** box.</span></span>

1. <span data-ttu-id="dbf95-131">Insira um nome de usuário, senha e URL de host válidos para o servidor SFTP no qual residem os dados a serem importados.</span><span class="sxs-lookup"><span data-stu-id="dbf95-131">Enter a valid username, password, and host URL for the SFTP server that the data to be imported resides on.</span></span>

1. <span data-ttu-id="dbf95-132">Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**.</span><span class="sxs-lookup"><span data-stu-id="dbf95-132">Review and provide your consent for **Data privacy and compliance** by selecting the **I agree** checkbox.</span></span>

1. <span data-ttu-id="dbf95-133">Selecione **Verificar** para validar a configuração.</span><span class="sxs-lookup"><span data-stu-id="dbf95-133">Select **Verify** to validate the configuration.</span></span>

1. <span data-ttu-id="dbf95-134">Assim que a verificação for concluída, a conexão poderá ser salva selecionando **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dbf95-134">Once the verification has completed, the connection can be saved by selecting **Save**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="dbf95-135">![Página de configuração de conexão da Experian](media/enrichment-SFTP-connection.png "Página de configuração de conexão da Experian")</span><span class="sxs-lookup"><span data-stu-id="dbf95-135">![Experian connection configuration page](media/enrichment-SFTP-connection.png "Experian connection configuration page")</span></span>


## <a name="defining-field-mappings"></a><span data-ttu-id="dbf95-136">Definição de mapeamentos de campo</span><span class="sxs-lookup"><span data-stu-id="dbf95-136">Defining field mappings</span></span> 

<span data-ttu-id="dbf95-137">O diretório que contém o arquivo a ser importado no servidor SFTP também deve conter um arquivo *model.json*.</span><span class="sxs-lookup"><span data-stu-id="dbf95-137">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="dbf95-138">Este arquivo define o esquema a ser usado para importar os dados.</span><span class="sxs-lookup"><span data-stu-id="dbf95-138">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="dbf95-139">O esquema deve usar o [Common Data Model](/common-data-model/) para especificar o mapeamento de campos.</span><span class="sxs-lookup"><span data-stu-id="dbf95-139">The schema has to use [Common Data Model](/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="dbf95-140">Um exemplo simples de arquivo model.json se parece com isto:</span><span class="sxs-lookup"><span data-stu-id="dbf95-140">A simple example of a model.json file looks like this:</span></span>

```
{
    "name": "EnrichmentFromMicrosoft",
    "description": "Model containing data enrichment",
    "entities": [
        {
            "name": "CustomImport",
            "attributes": [
                {
                    "name": "CustomerId",
                    "friendlyName": "Client id",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred City for vacation",
                    "dataType": "string"
                },
                {
                    "name": "PreferredTransportation",
                    "friendlyName": "Preferred transportation",
                    "dataType": "string"
                }
            ],
            "annotations": [
                {
                    "name": "c360:PrimaryKey",
                    "value": "CustomerId"
                }
            ]
        }
    ],
    "modifiedTime": "2020-01-02T12:00:00+08:00",
    "annotations": [
        {
            "name": "testAnnotation",
            "value": "testValue"
        }
    ]
}
```

## <a name="enrichment-results"></a><span data-ttu-id="dbf95-141">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="dbf95-141">Enrichment results</span></span>

<span data-ttu-id="dbf95-142">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="dbf95-142">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="dbf95-143">Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="dbf95-143">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="dbf95-144">O tempo de processamento dependerá do tamanho dos dados a serem importados e da conexão com o servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="dbf95-144">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="dbf95-145">Após a conclusão do processo de enriquecimento, você pode revisar seus dados de enriquecimento personalizados recém-importados em **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="dbf95-145">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="dbf95-146">Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="dbf95-146">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="dbf95-147">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="dbf95-147">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dbf95-148">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="dbf95-148">Next steps</span></span>

<span data-ttu-id="dbf95-149">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="dbf95-149">Build on top of your enriched customer data.</span></span> <span data-ttu-id="dbf95-150">Crie [segmentos](segments.md), [medidas](measures.md) e [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="dbf95-150">Create [segments](segments.md) and [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>

[!INCLUDE[footer-include](../includes/footer-banner.md)]
