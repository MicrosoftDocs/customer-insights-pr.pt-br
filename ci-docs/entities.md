---
title: Entidades no Customer Insights
description: Exiba os dados na página Entidades.
ms.date: 12/06/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-entities
- customerInsight
ms.openlocfilehash: 0beaa46d47545ac195ced876b509dfc57821bfaf
ms.sourcegitcommit: ad74ace653db9a25fce4343adef7db1c9b0d8904
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/21/2022
ms.locfileid: "9183526"
---
# <a name="entities-in-customer-insights"></a>Entidades no Customer Insights

Após [configurar suas fontes de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos. As entidades são consideradas conjuntos de dados. Vários recursos do Dynamics 365 Customer Insights são criados com base nessas entidades. Analisá-los de perto pode ajudá-lo a validar a saída desses recursos.

À medida que você trabalha no Customer Insights enriquecendo dados ou criando segmentos, medidas e atividades, as entidades criadas a partir dessas ações são exibidas na página **Entidades**.

## <a name="view-a-list-of-entities"></a>Exibir uma lista de entidades

Vá para **Dados** > **Entidades** para ver uma lista de entidades. As informações a seguir de cada entidade são exibidas.

- **Nome**: nome da entidade de dados. Se você vir um símbolo de aviso próximo ao nome de uma entidade, significa que os dados dessa entidade não foram carregados com êxito.
- **Fonte**: tipo da fonte de dados que ingeriu a entidade.
- **Atualização**: hora da última atualização da entidade.
- **Status**: detalhes sobre a última atualização da entidade.

## <a name="explore-a-specific-entitys-data"></a>Explorar dados de uma entidade específica

1. Vá para **Dados** > **Entidades**.
1. Selecione uma entidade para abrir a página de detalhes.  
1. Explore os diferentes campos e registros incluídos nessa entidade.

- A guia **Atributos** vem selecionada por padrão e mostra os detalhes da entidade selecionada, como nomes de campo, tipos de dados e tipos. A coluna **Tipo** mostra os tipos associados de Common Data Model que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos usuários. Esses tipos são tipos semânticos que podem ser diferentes dos tipos de dados dos atributos. Por exemplo, o campo *Email* abaixo tem o tipo de dados *Cadeia de caracteres*, mas seu tipo Common Data Model (semântico) pode ser *Email*, *EmailAddress* ou *Identity.Service.Email*.

   :::image type="content" source="media/data-manager-entities-fields.png" alt-text="Tabela de campos.":::

   > [!NOTE]
   > Esta página mostra apenas um exemplo dos dados da sua entidade. Para exibir o conjunto de dados completo, acesse a página **Fontes de dados**, selecione uma entidade, selecione **Editar** e exiba os dados dessa entidade com o editor do Power Query, conforme explicado em [Fontes de dados](data-sources.md).

   Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características de dados importantes, como nulos, valores ausentes, valores exclusivos, contagens e distribuições, conforme aplicável a seus dados. Selecione o ícone do gráfico para ver o resumo dos dados.

   :::image type="content" source="media/data-manager-entities-summary.png" alt-text="Tabela de resumo de dados.":::

- A guia **Dados** mostra detalhes sobre registros individuais da entidade. Os detalhes listados dependem do tipo de dados da entidade.

   :::image type="content" source="media/data-manager-entities-data.png" alt-text="Selecione uma entidade.":::

- A guia **Relatórios** (disponível para algumas entidades) permite visualizar dados criando um relatório que inclui estas colunas:

  - **Nome do relatório**: nome do relatório.
  - **Criação de**: nome da pessoa que criou a entidade.
  - **Criação**: data e hora da criação da entidade.
  - **Edição de**: nome da pessoa que modificou a entidade.
  - **Edição**: data e hora da modificação da entidade.

## <a name="entity-specific-information"></a>Informações específicas da entidade

A seção a seguir fornece informações sobre algumas entidades criadas pelo sistema.

### <a name="corrupted-data-sources"></a>Fontes de dados corrompidas

Os campos de uma fonte de dados ingerida podem conter dados corrompidos. Os registros com campos corrompidos são expostos nas entidades criadas pelo sistema. Saber sobre os registros corrompidos ajuda a identificar quais dados devem ser revisados e atualizados no sistema de origem. Após a próxima atualização da fonte de dados, os registros corrigidos são ingeridos no Customer Insights e passados para os processos downstream. 

Por exemplo, uma coluna 'aniversário' tem o tipo de dados definido como 'data'. Um registro de cliente tem sua data de aniversário inserida como '01/01/19777'. O sistema sinalizará este registro como corrompido. Alguém agora poderá alterar a data de aniversário no sistema de origem para '1977'. Após uma atualização automática das fontes de dados, o campo agora tem um formato válido e o registro será removido da entidade corrompida.

Acesse **Dados** > **Entidades** e procure as entidades corrompidas na seção **Sistema**. Esquema de nomenclatura de entidades corrompidas: 'DataSourceName_EntityName_corrupt'. Selecione uma entidade corrompida para identificar os campos corrompidos e o motivo no nível de registro individual.

   :::image type="content" source="media/corruption-reason.png" alt-text="Motivo da corrupção.":::

O Customer Insights ainda processa os registros corrompidos. No entanto, eles podem causar problemas ao trabalhar com os dados unificados.

As verificações a seguir são executadas nos dados ingeridos para expor os registros corrompidos:

- Se o valor de um campo não corresponde ao tipo de dados de sua coluna.
- Se os campos contêm caracteres que fazem com que as colunas não correspondam ao esquema esperado. Por exemplo: aspas formatadas incorretamente, aspas sem escape ou caracteres de nova linha.
- Se houver colunas datetime/date/datetimeoffset, seu formato precisa ser especificado no modelo caso ele não siga o formato ISO padrão.

[!INCLUDE [footer-include](includes/footer-banner.md)]
