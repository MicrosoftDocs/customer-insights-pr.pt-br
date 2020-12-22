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
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer os perfis dos clientes com dados personalizados (versão preliminar)

A importação personalizada via SFTP permite que você importe dados que não precisam passar pelo processo de unificação de dados. É uma maneira flexível, segura e fácil de reunir seus dados. A importação personalizada via SFTP pode ser usada em combinação com a [exportação via SFTP](export-sftp.md), que permite exportar os dados de perfil do cliente necessários para aprimoramento. Os dados podem ser processados e enriquecidos e a importação personalizada via SFTP pode ser usada para reunir os dados enriquecidos de volta para a capacidade de insights de público-alvo do Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a importação personalizada via SFTP, os seguintes pré-requisitos devem ser atendidos:

- Você tem credenciais de usuário (nome de usuário e senha) para o local de SFTP de onde os dados serão importados.
- Você tem a URL e o número da porta (geralmente 22) para o host STFP.
- Você tem o nome do arquivo e a localização do arquivo a ser importado no host SFTP.
- Existe um arquivo *model.json* que especifica o esquema para os dados que devem ser importados. Esse arquivo deve estar no mesmo diretório do arquivo a ser importado.
- Você tem a permissão de [Administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuração

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. No **Bloco de importação personalizada via SFTP**, selecione **Enriquecer meus dados**.

   > [!div class="mx-imgBorder"]
   > ![Bloco de importação personalizada via SFTP](media/SFTP_Custom_Import_tile.png "Bloco de importação personalizada via SFTP")

1. Selecione **Introdução** e forneça as credenciais e o endereço do servidor SFTP. Por exemplo, sftp://mysftpserver.com:22.

1. Insira o nome do arquivo que contém os dados e o caminho para o arquivo no servidor SFTP, se não estiver na pasta raiz.

1. Confirme todas as entradas selecionando **Conectar-se à importação personalizada**.

   > [!div class="mx-imgBorder"]
   > ![Submenu da configuração da importação personalizada via SFTP](media/SFTP_Custom_Import_Configuration_flyout.png "Submenu da configuração da importação personalizada via SFTP")

## <a name="defining-field-mappings"></a>Definição de mapeamentos de campo 

O diretório que contém o arquivo a ser importado no servidor SFTP também deve conter um arquivo *model.json*. Este arquivo define o esquema a ser usado para importar os dados. O esquema deve usar o [Common Data Model](https://docs.microsoft.com/common-data-model/) para especificar o mapeamento de campo. Um exemplo simples de arquivo model.json se parece com isto:

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

## <a name="enrichment-results"></a>Resultados de enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados a serem importados e da conexão com o servidor SFTP.

Após a conclusão do processo de enriquecimento, você pode revisar seus dados de enriquecimento personalizados recém-importados em **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Crie [segmentos](segments.md) e [medidas](measures.md) e [exporte os dados](export-destinations.md) para entregar experiências personalizadas aos seus clientes.


