---
title: Entidades e conjuntos de dados
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
ms.openlocfilehash: c1094bc2f6d137087b317ed20d0615289d6f1187
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645653"
---
# <a name="entities-in-customer-insights"></a>Entidades no Customer Insights

Após [configurar suas fontes de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos. As entidades são consideradas conjuntos de dados. Vários recursos do Dynamics 365 Customer Insights são criados com base nessas entidades. Analisá-los de perto pode ajudá-lo a validar a saída desses recursos.

A página **Entidades** lista as entidades e inclui estas colunas:

- **Nome**: o nome da entidade de dados. Se você vir um símbolo de aviso próximo ao nome de uma entidade, significa que os dados dessa entidade não foram carregados com êxito.
- **Fonte**: tipo da fonte de dados que ingeriu a entidade.
- **Atualização**: hora da última atualização da entidade.
- **Status**: detalhes sobre a última atualização da entidade.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="explore-a-specific-entitys-data"></a>Explorar dados de uma entidade específica

1. Vá para **Dados** > **Entidades**.
1. Na página **Entidades**, selecione uma entidade para abrir a página de detalhes.  
1. Explore os diferentes campos e registros incluídos nessa entidade.

- A guia **Atributos** vem selecionada por padrão e mostra uma tabela para revisar os detalhes da entidade selecionada, como nomes de campo, tipos de dados e tipos. A coluna **Tipo** mostra os tipos associados de Common Data Model que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos usuários. Esses tipos são tipos semânticos que podem ser diferentes dos tipos de dados dos atributos. Por exemplo, o campo *Email* abaixo tem o tipo de dados *Texto* mas seu tipo do Common Data Model (semântico) pode ser *Email* ou *Endereço de email*.

> [!div class="mx-imgBorder"]
> ![Tabela de campos.](media/data-manager-entities-fields.PNG "Tabela de campos")

> [!NOTE]
> Esta página mostra apenas um exemplo dos dados da sua entidade. Para exibir o conjunto de dados completo, acesse a página **Fontes de dados**, selecione uma entidade, selecione **Editar** e exiba os dados dessa entidade com o editor do Power Query, conforme explicado em [Fontes de dados](data-sources.md).

Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características importantes dos dados, como nulos, valores ausentes, valores exclusivos, contagens e distribuições, conforme aplicável a seus dados. Selecione o ícone do gráfico para ver o resumo dos dados.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumo.](media/data-manager-entities-summary.png "Tabela de resumo de dados")

- A guia **Dados** mostra uma tabela que lista detalhes sobre registros individuais da entidade. Os detalhes listados dependem do tipo de dados da entidade.

> [!div class="mx-imgBorder"]
> ![Selecione uma entidade.](media/data-manager-entities-data.png "Selecione uma entidade")

- A guia **Relatórios** (disponível para algumas entidades) permite que você visualize seus dados criando um relatório e inclui estas colunas:

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

Acesse **Dados** > **Entidades** e procure as entidades corrompidas na seção **Sistema**. Esquema de nomenclatura de entidades corrompidas: 'DataSourceName_EntityName_corrupt'. Selecione uma entidade corrompida para identificar todos os campos corrompidos e o motivo no nível de registro individual.
> [!div class="mx-imgBorder"]
> ![Motivo da corrupção.](media/corruption-reason.png "Motivo da corrupção")

O Customer Insights ainda processa os registros corrompidos. No entanto, eles podem causar problemas ao trabalhar com os dados unificados.

As verificações a seguir são executadas nos dados ingeridos para expor os registros corrompidos: 

- Se o valor de um campo não corresponde ao tipo de dados de sua coluna.
- Se os campos contêm caracteres que fazem com que as colunas não correspondam ao esquema esperado. Por exemplo: aspas formatadas incorretamente, aspas sem escape ou caracteres de nova linha.
- Se houver colunas datetime/date/datetimeoffset, seu formato precisa ser especificado no modelo caso ele não siga o formato ISO padrão.


[!INCLUDE [footer-include](includes/footer-banner.md)]
