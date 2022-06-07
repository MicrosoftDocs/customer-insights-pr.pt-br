---
title: Enriquecimento com importação personalizada do SFTP
description: Informações gerais sobre o enriquecimento de importação personalizada do SFTP.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f52d24cbe793bee7948ad2af31059cd3edf40f94
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645524"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer os perfis dos clientes com dados personalizados (versão preliminar)

A importação personalizada via SFTP permite que você importe dados que não precisam passar pelo processo de unificação de dados. É uma maneira flexível, segura e fácil de reunir seus dados. A importação personalizada via SFTP pode ser usada em combinação com a [exportação via SFTP](export-sftp.md), que permite exportar os dados de perfil do cliente necessários para aprimoramento. Os dados podem ser processados e enriquecidos, e a importação personalizada de SFTP pode ser usada para retornar os dados enriquecidos ao Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a importação personalizada via SFTP, os seguintes pré-requisitos devem ser atendidos:

- Você tem o nome do arquivo e a localização (caminho) do arquivo a ser importado no host SFTP.
- Há um arquivo *model.json* que especifica o [esquema do Common Data Model](/common-data-model/) para que os dados sejam importados. Esse arquivo deve estar no mesmo diretório do arquivo a ser importado.
- Uma conexão SFTP já foi configurada por um administrador *ou* você tem permissões de [administrador](permissions.md#admin). Você precisará das credenciais do usuário, da URL e do número da porta do local do SFTP de onde deseja importar os dados.


## <a name="configure-the-import"></a>Configurar a importação

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. No **bloco de importação personalizada via SFTP**, selecione **Enriquecer meus dados** e depois selecione **Começar agora**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Bloco de importação personalizada via SFTP.":::

1. Selecione uma [conexão](connections.md) na lista suspensa. Contate um administrador se nenhuma conexão estiver disponível. Se for um administrador, você poderá criar uma conexão selecionando **Adicionar conexão** e escolhendo **Importação Personalizada de SFTP** na lista suspensa.

1. Selecione **Conectar-se à Importação Personalizada** para confirmar a conexão selecionada.

1.  Selecione **Avançar** e insira o **Caminho** e o **Nome do arquivo** de dados que deseja importar.

    :::image type="content" source="media/enrichment-SFTP-path-and-filename.png" alt-text="Captura de tela ao inserir a localização dos dados.":::

1. Selecione **Próximo** e escolha o conjunto de dados do cliente. Isso pode ser todos os perfis de clientes ou um segmento.

1. Selecione **Próximo** e forneça um nome para o enriquecimento e um nome para a entidade de saída. 

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurar a conexão para a Importação Personalizada via SFTP 

Você deve ser um administrador para configurar as conexões. Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da Importação Personalizada.

1. Insira um nome para a conexão na caixa **Nome de exibição**.

1. Insira um nome de usuário, senha e URL de host válidos para o servidor SFTP no qual residem os dados a serem importados.

1. Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Assim que a verificação for concluída, a conexão poderá ser salva selecionando **Salvar**.

   > [!div class="mx-imgBorder"]
   > ![Página de configuração de conexão da Experian.](media/enrichment-SFTP-connection.png "Página de configuração de conexão da Experian")


## <a name="defining-field-mappings"></a>Definição de mapeamentos de campo 

O diretório que contém o arquivo a ser importado no servidor SFTP também deve conter um arquivo *model.json*. Este arquivo define o esquema a ser usado para importar os dados. O esquema deve usar o [Common Data Model](/common-data-model/) para especificar o mapeamento de campos. Um exemplo simples de arquivo model.json se parece com isto:

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

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]