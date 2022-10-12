---
title: Conecte-se aos dados em um data lake gerenciado do Microsoft Dataverse
description: Importar dados de um data lake gerenciado pelo Microsoft Dataverse.
ms.date: 08/18/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
manager: shellyha
ms.reviewer: v-wendysmith
searchScope:
- ci-dataverse
- customerInsights
ms.openlocfilehash: 0d9612525344c8ac99b6e3edfe33a426dc0a474b
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9609777"
---
# <a name="connect-to-data-in-a-microsoft-dataverse-managed-data-lake"></a>Conecte-se aos dados em um data lake gerenciado do Microsoft Dataverse

Os usuários do Microsoft Dataverse podem se conectar rapidamente a entidades analíticas em um lake gerenciado pelo Microsoft Dataverse. Apenas uma fonte de dados de um ambiente pode usar simultaneamente o mesmo lake gerenciado pelo Dataverse.

> [!NOTE]
> Você deve ser um administrador na organização do Dataverse para prosseguir e exibir a lista de entidades disponíveis no lake gerenciado.

## <a name="prerequisites"></a>Pré-requisitos

- Os dados armazenados em serviços online, como o Azure Data Lake Storage, podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar ou se conectar aos dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center).

- Apenas as entidades Dataverse com o [controle de alterações](/power-platform/admin/enable-change-tracking-control-data-synchronization) habilitado são visíveis. Essas entidades podem ser exportadas para o data lake gerenciado do Dataverse e usadas no Customer Insights. As tabelas do Dataverse prontas para uso têm o controle de alterações habilitado por padrão. Você precisa ativar o controle de alterações para tabelas personalizadas. Para verificar se uma tabela do Dataverse está com o controle de alterações habilitado, acesse [Power Apps](https://make.powerapps.com) > **Dados** > **Tabelas**. Encontre a tabela que você está procurando e selecione-a. Acesse **Configurações** > **Opções avançadas** e verifique a configuração **Controlar alterações**.

## <a name="connect-to-a-dataverse-managed-lake"></a>Conectar-se a um data lake gerenciado do Dataverse

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Selecione **Microsoft Dataverse**.

1. Insira um **Nome** para a fonte de dados e uma **Descrição** opcional.

1. Forneça o **Endereço do servidor** para a organização do Dataverse e selecione **Entrar**.

1. Selecione as tabelas que você deseja ingerir como entidades no Customer Insights na lista disponível.

   > [!NOTE]
   > Se algumas tabelas já estiverem selecionadas, elas podem ser usadas por outros aplicativos do Dynamics 365 (como o Dynamics 365 Sales Insights ou o Customer Service Insights). Não é possível alterar a seleção. Essas tabelas estarão disponíveis como entidades assim que a fonte de dados for criada.

    :::image type="content" source="media/select-dataverse-entities.png" alt-text="Caixa de diálogo mostrando uma lista de entidades no ambiente do Dataverse.":::

1. Salve sua seleção para começar a sincronizar as tabelas selecionadas do Dataverse. Você encontrará a conexão recém-adicionada na página **Fontes de dados**. Ela será enfileirada para atualização e mostrará a contagem de entidades como zero até que todas as tabelas selecionadas sejam sincronizadas.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página [**Entidades**](entities.md).

## <a name="edit-a-dataverse-managed-lake-data-source"></a>Edite uma fonte de dados de lake gerenciado do Dataverse

Você só editará a seleção da entidade depois de criar a fonte de dados. Por exemplo, se entidades adicionais foram adicionadas ao Dataverse e você quiser importá-las também.
Para conectar-se a um data lake diferente do Dataverse, [crie uma nova fonte de dados](#connect-to-a-dataverse-managed-lake).

1. Acesse **Dados** > **Fontes de dados**.

1. Ao lado da fonte de dados que você deseja atualizar, selecione **Editar**

1. Selecione mais entidades na lista de entidades disponíveis.

1. Clique em **Salvar** para aplicar suas alterações e voltar para a página **Fontes de dados**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="common-reasons-for-ingestion-errors-or-corrupted-data"></a>Motivos comuns para erros de ingestão ou dados corrompidos

As verificações a seguir são executadas nos dados ingeridos para expor os registros corrompidos:

- Se o valor de um campo não corresponde ao tipo de dados de sua coluna.
- Se os campos contêm caracteres que fazem com que as colunas não correspondam ao esquema esperado. Por exemplo: aspas formatadas incorretamente, aspas sem escape ou caracteres de nova linha.
- Se houver colunas datetime/date/datetimeoffset, seu formato precisa ser especificado no modelo caso ele não siga o formato ISO padrão.

### <a name="schema-or-data-type-mismatch"></a>Incompatibilidade de esquema ou tipo de dados

Se os dados não estiverem de acordo com o esquema, os registros serão classificados como corrompidos. Corrija os dados de origem ou o esquema e reinsira os dados.

### <a name="datetime-fields-in-the-wrong-format"></a>Campos de data e hora no formato errado

Os campos de data e hora na entidade não estão nos formatos ISO ou en-US. O formato de data e hora padrão no Customer Insights é o formato en-US. Todos os campos de data e hora em uma entidade devem estar no mesmo formato. O Customer Insights oferece suporte a outros formatos, desde que as anotações ou características sejam feitas no nível de origem ou entidade no modelo ou manifest.json. Por exemplo: 

**Model.json**

   ```json
      "annotations": [
        {
          "name": "ci:CustomTimestampFormat",
          "value": "yyyy-MM-dd'T'HH:mm:ss:SSS"
        },
        {
          "name": "ci:CustomDateFormat",
          "value": "yyyy-MM-dd"
        }
      ]   
   ```

  Em um manifest.json, o formato de data e hora pode ser especificado no nível da entidade ou no nível do atributo. No nível da entidade, use "exhibitsTraits" na entidade no *.manifest.cdm.json para definir o formato de data e hora. No nível do atributo, use "appliedTraits" no atributo no entityname.cdm.json.

**Manifest.json no nível da entidade**

```json
"exhibitsTraits": [
    {
        "traitReference": "is.formatted.dateTime",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd'T'HH:mm:ss"
            }
        ]
    },
    {
        "traitReference": "is.formatted.date",
        "arguments": [
            {
                "name": "format",
                "value": "yyyy-MM-dd"
            }
        ]
    }
]
```

**Entity.json no nível do atributo**

```json
   {
      "name": "PurchasedOn",
      "appliedTraits": [
        {
          "traitReference": "is.formatted.date",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-dd"
            }
          ]
        },
        {
          "traitReference": "is.formatted.dateTime",
          "arguments" : [
            {
              "name": "format",
              "value": "yyyy-MM-ddTHH:mm:ss"
            }
          ]
        }
      ],
      "attributeContext": "POSPurchases/attributeContext/POSPurchases/PurchasedOn",
      "dataFormat": "DateTime"
    }
```

[!INCLUDE [footer-include](includes/footer-banner.md)]
