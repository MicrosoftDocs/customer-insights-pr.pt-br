---
title: Enriquecimento com importação personalizada do SFTP
description: Informações gerais sobre o enriquecimento de importação personalizada do SFTP.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 657afb6fcb68429680eb677734b4115e69769008
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953705"
---
# <a name="enrich-customer-profiles-with-custom-data-preview"></a>Enriquecer os perfis dos clientes com dados personalizados (versão preliminar)

A importação personalizada via SFTP permite que você importe dados que não precisam passar pelo processo de unificação de dados. É uma maneira flexível, segura e fácil de reunir seus dados. A importação personalizada via SFTP pode ser usada em combinação com a [exportação via SFTP](export-sftp.md), que permite exportar os dados de perfil do cliente necessários para aprimoramento. Os dados podem ser processados e enriquecidos, e a importação personalizada de SFTP pode ser usada para retornar os dados enriquecidos ao Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

- O nome do arquivo e a localização (caminho) do arquivo a ser importado no host SFTP são conhecidos.

- Um arquivo *model.json* que especifica o esquema do Common Data Model para os dados a serem importados está disponível. Esse arquivo deve estar no mesmo diretório do arquivo a ser importado.

- Uma [conexão](connections.md) SFTP foi [configurada](#configure-the-connection-for-sftp-custom-import).

## <a name="file-schema-example"></a>Exemplo de esquema de arquivo

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
                    "friendlyName": "Client ID",
                    "dataType": "string"
                },
                {
                    "name": "PreferredCity",
                    "friendlyName": "Preferred city for vacation",
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

## <a name="configure-the-connection-for-sftp-custom-import"></a>Configurar a conexão para a Importação Personalizada via SFTP

Você deve ser um [administrador](permissions.md#admin) no Customer Insights e ter as credenciais do usuário, URL e número da porta para o local SFTP de onde você deseja importar dados.

1. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administrador** > **Conexões** e selecione **Configurar** no bloco Importação Personalizada.

   :::image type="content" source="media/enrichment-SFTP-connection.png" alt-text="Página de configuração de conexão de Importação Personalizada.":::

1. Insira um nome para a conexão.

1. Insira um nome de usuário, senha e URL de host válidos para o servidor SFTP no qual residem os dados a serem importados.

1. Revise e forneça seu consentimento para a [Conformidade e privacidade dos dados](#data-privacy-and-compliance) selecionando **Eu concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Salvar**.

### <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados usando Importação Personalizada, você permite a transferência de dados fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft vai transferir esses dados de acordo com suas instruções, mas você é responsável por garantir que os dados atendam às obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.

## <a name="configure-the-import"></a>Configurar a importação

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** no bloco **Importação personalizada do SFTP**.

   :::image type="content" source="media/SFTP_Custom_Import_tile.png" alt-text="Bloco de importação personalizada via SFTP.":::

1. Revise a visão geral e selecione **Avançar**.

1. Selecionar a conexão. Entre em contato com um administrador se não houver um disponível.

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

1. Selecione **Avançar**

1. Insira o **Caminho** e **Nome do arquivo** do arquivo de dados que você deseja importar.

1. Selecione **Avançar**

1. Forneça um **Nome** para o enriquecimento e o **Nome da entidade de saída**.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Executar** para iniciar o processo de enriquecimento ou feche para voltar para a página **Enriquecimentos**.

## <a name="enrichment-results"></a>Resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
