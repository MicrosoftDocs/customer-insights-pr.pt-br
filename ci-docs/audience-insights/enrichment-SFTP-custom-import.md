---
title: Enriquecimento com importação personalizada do SFTP
description: Informações gerais sobre o enriquecimento de importação personalizada do SFTP.
ms.date: 11/18/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jdahl
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 59f7f05ca0825ba147e9e93f10fa3508ec3a16dd
ms.sourcegitcommit: ff824bbbd31fd666ab0da682bf48ea31580d242c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/18/2020
ms.locfileid: "4568402"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a><span data-ttu-id="7ed36-103">Enriquecer os perfis dos clientes com dados personalizados (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="7ed36-103">Enrich customer profiles with custom data (preview)</span></span>

<span data-ttu-id="7ed36-104">A importação personalizada via SFTP permite que você importe dados que não precisam passar pelo processo de unificação de dados.</span><span class="sxs-lookup"><span data-stu-id="7ed36-104">Secure File Transfer Protocol(SFTP) custom import enables you to import data that doesn't have to go through the process of data unification.</span></span> <span data-ttu-id="7ed36-105">É uma maneira flexível, segura e fácil de reunir seus dados.</span><span class="sxs-lookup"><span data-stu-id="7ed36-105">It's a flexible, secure, and easy way to bring in your data.</span></span> <span data-ttu-id="7ed36-106">A importação personalizada via SFTP pode ser usada em combinação com a [exportação via SFTP](export-sftp.md), que permite exportar os dados de perfil do cliente necessários para aprimoramento.</span><span class="sxs-lookup"><span data-stu-id="7ed36-106">SFTP custom import can be used in combination with [SFTP export](export-sftp.md) that lets you export the customer profile data that is needed for enrichment.</span></span> <span data-ttu-id="7ed36-107">Os dados podem ser processados e enriquecidos e a importação personalizada via SFTP pode ser usada para reunir os dados enriquecidos de volta para a capacidade de insights de público-alvo do Dynamics 365 Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="7ed36-107">The data can then be processed, enriched, and SFTP custom import can be used to bring the enriched data back to the audience insights capability of Dynamics 365 Customer Insights.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ed36-108">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="7ed36-108">Prerequisites</span></span>

<span data-ttu-id="7ed36-109">Para configurar a importação personalizada via SFTP, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="7ed36-109">To configure SFTP custom import, the following prerequisites must be met:</span></span>

- <span data-ttu-id="7ed36-110">Você tem credenciais de usuário (nome de usuário e senha) para o local de SFTP de onde os dados serão importados.</span><span class="sxs-lookup"><span data-stu-id="7ed36-110">You have user credentials (user name and password) for the SFTP location where the data that is going to be imported from.</span></span>
- <span data-ttu-id="7ed36-111">Você tem a URL e o número da porta (geralmente 22) para o host STFP.</span><span class="sxs-lookup"><span data-stu-id="7ed36-111">You have the URL and port number (usually 22) for the STFP host.</span></span>
- <span data-ttu-id="7ed36-112">Você tem o nome do arquivo e a localização do arquivo a ser importado no host SFTP.</span><span class="sxs-lookup"><span data-stu-id="7ed36-112">You have the filename and location of the file to be imported on the SFTP host.</span></span>
- <span data-ttu-id="7ed36-113">Existe um arquivo *model.json* que especifica o esquema para os dados que devem ser importados.</span><span class="sxs-lookup"><span data-stu-id="7ed36-113">There's a *model.json* file that specifies the schema for the data that are to be imported.</span></span> <span data-ttu-id="7ed36-114">Esse arquivo deve estar no mesmo diretório do arquivo a ser importado.</span><span class="sxs-lookup"><span data-stu-id="7ed36-114">This file must be in the same directory as the file to import.</span></span>
- <span data-ttu-id="7ed36-115">Você tem a permissão de [Administrador](permissions.md#administrator).</span><span class="sxs-lookup"><span data-stu-id="7ed36-115">You have [Administrator](permissions.md#administrator) permission.</span></span>

## <a name="configuration"></a><span data-ttu-id="7ed36-116">Configuração</span><span class="sxs-lookup"><span data-stu-id="7ed36-116">Configuration</span></span>

1. <span data-ttu-id="7ed36-117">Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.</span><span class="sxs-lookup"><span data-stu-id="7ed36-117">Go to **Data** > **Enrichment** and select the **Discover** tab.</span></span>

1. <span data-ttu-id="7ed36-118">No **Bloco de importação personalizada via SFTP**, selecione **Enriquecer meus dados**.</span><span class="sxs-lookup"><span data-stu-id="7ed36-118">On the **SFTP custom import tile**, select **Enrich my data**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7ed36-119">![Bloco de importação personalizada via SFTP](media/SFTP_Custom_Import_tile.png "Bloco de importação personalizada via SFTP")</span><span class="sxs-lookup"><span data-stu-id="7ed36-119">![SFTP Custom Import tile](media/SFTP_Custom_Import_tile.png "SFTP Custom Import tile")</span></span>

1. <span data-ttu-id="7ed36-120">Selecione **Introdução** e forneça as credenciais e o endereço do servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="7ed36-120">Select **Get started** and provide the credentials and the address for the SFTP server.</span></span> <span data-ttu-id="7ed36-121">Por exemplo, sftp://mysftpserver.com:22.</span><span class="sxs-lookup"><span data-stu-id="7ed36-121">For example, sftp://mysftpserver.com:22.</span></span>

1. <span data-ttu-id="7ed36-122">Insira o nome do arquivo que contém os dados e o caminho para o arquivo no servidor SFTP, se não estiver na pasta raiz.</span><span class="sxs-lookup"><span data-stu-id="7ed36-122">Enter the name of the file that contains the data and path to the file on the SFTP server if it's not in the root folder.</span></span>

1. <span data-ttu-id="7ed36-123">Confirme todas as entradas selecionando **Conectar-se à importação personalizada**.</span><span class="sxs-lookup"><span data-stu-id="7ed36-123">Confirm all inputs by selecting **Connect to Custom Import**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="7ed36-124">![Submenu da configuração da importação personalizada via SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Submenu da configuração da importação personalizada via SFTP")</span><span class="sxs-lookup"><span data-stu-id="7ed36-124">![SFTP Custom Import Configuration flyout](media/SFTP_Custom_Import_Configuration_flyout.png "SFTP Custom Import Configuration flyout")</span></span>

## <a name="defining-field-mappings"></a><span data-ttu-id="7ed36-125">Definição de mapeamentos de campo</span><span class="sxs-lookup"><span data-stu-id="7ed36-125">Defining field mappings</span></span> 

<span data-ttu-id="7ed36-126">O diretório que contém o arquivo a ser importado no servidor SFTP também deve conter um arquivo *model.json*.</span><span class="sxs-lookup"><span data-stu-id="7ed36-126">The directory that contains the file to be imported on the SFTP server must also contain a *model.json* file.</span></span> <span data-ttu-id="7ed36-127">Este arquivo define o esquema a ser usado para importar os dados.</span><span class="sxs-lookup"><span data-stu-id="7ed36-127">This file defines the schema to use for importing the data.</span></span> <span data-ttu-id="7ed36-128">O esquema deve usar o [Common Data Model](https://docs.microsoft.com/common-data-model/) para especificar o mapeamento de campo.</span><span class="sxs-lookup"><span data-stu-id="7ed36-128">The schema has to use [the Common Data Model](https://docs.microsoft.com/common-data-model/) to specify the field mapping.</span></span> <span data-ttu-id="7ed36-129">Um exemplo simples de arquivo model.json se parece com isto:</span><span class="sxs-lookup"><span data-stu-id="7ed36-129">A simple example of a model.json file looks like this:</span></span>

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

## <a name="enrichment-results"></a><span data-ttu-id="7ed36-130">Resultados de enriquecimento</span><span class="sxs-lookup"><span data-stu-id="7ed36-130">Enrichment results</span></span>

<span data-ttu-id="7ed36-131">Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos.</span><span class="sxs-lookup"><span data-stu-id="7ed36-131">To start the enrichment process, select **Run** from the command bar.</span></span> <span data-ttu-id="7ed36-132">Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab).</span><span class="sxs-lookup"><span data-stu-id="7ed36-132">You can also let the system run the enrichment automatically as part of a [scheduled refresh](system.md#schedule-tab).</span></span> <span data-ttu-id="7ed36-133">O tempo de processamento dependerá do tamanho dos dados a serem importados e da conexão com o servidor SFTP.</span><span class="sxs-lookup"><span data-stu-id="7ed36-133">The processing time will depend on the size of the data to be imported and the connection to the SFTP server.</span></span>

<span data-ttu-id="7ed36-134">Após a conclusão do processo de enriquecimento, você pode revisar seus dados de enriquecimento personalizados recém-importados em **Meus enriquecimentos**.</span><span class="sxs-lookup"><span data-stu-id="7ed36-134">After the enrichment process completes, you can review your newly imported custom enrichment data under **My enrichments**.</span></span> <span data-ttu-id="7ed36-135">Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="7ed36-135">Additionally, you'll find the time of the last update and the number of enriched profiles.</span></span>

<span data-ttu-id="7ed36-136">Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.</span><span class="sxs-lookup"><span data-stu-id="7ed36-136">You can access a detailed view of each enriched profile by selecting **View enriched data**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ed36-137">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7ed36-137">Next steps</span></span>

<span data-ttu-id="7ed36-138">Compile com base nos dados de cliente enriquecidos.</span><span class="sxs-lookup"><span data-stu-id="7ed36-138">Build on top of your enriched customer data.</span></span> <span data-ttu-id="7ed36-139">Crie [segmentos](segments.md) e [medidas](measures.md) e [exporte os dados](export-destinations.md) para entregar experiências personalizadas aos seus clientes.</span><span class="sxs-lookup"><span data-stu-id="7ed36-139">Create [segments](segments.md), [measures](measures.md), and [export the data](export-destinations.md) to deliver personalized experiences to your customers.</span></span>


