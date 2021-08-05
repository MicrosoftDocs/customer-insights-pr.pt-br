---
title: Entidades e conjuntos de dados
description: Exiba os dados na página Entidades.
ms.date: 04/16/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.openlocfilehash: ac8b0671b20123091bef64e672fc53398fe8955a
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6553961"
---
# <a name="entities-in-audience-insights"></a>Entidades em insights de público-alvo

Após [configurar suas fontes de dados](data-sources.md), vá para a página **Entidades** para avaliar a qualidade dos dados ingeridos. As entidades são consideradas conjuntos de dados. Vários recursos do Dynamics 365 Customer Insights são criados com base nessas entidades. Analisá-los de perto pode ajudá-lo a validar a saída desses recursos.

A página **Entidades** lista as entidades e tem várias colunas:

- **Nome** : O nome da sua entidade de dados. Se você vir um símbolo de aviso próximo ao nome de uma entidade, significa que os dados dessa entidade não foram carregados com êxito.
- **Fonte**: O tipo de fontes de dados que ingeriu a entidade
- **Criada por**: Nome da pessoa que criou a entidade
- **Criada**: Data e hora de criação da entidade
- **Atualizada por**: Nome da pessoa que atualizou a entidade
- **Ultima atualização**: Data e hora da última atualização da entidade
- **Última atualização**: Data e hora da última atualização de dados

## <a name="explore-a-specific-entitys-data"></a>Explorar dados de uma entidade específica

Selecione uma entidade para explorar os diferentes campos e registros incluídos nessa entidade.

> [!div class="mx-imgBorder"]
> ![Selecione uma entidade.](media/data-manager-entities-data.png "Selecionar uma entidade")

- A guia **Dados** mostra uma tabela que lista detalhes sobre registros individuais da entidade.

> [!div class="mx-imgBorder"]
> ![Tabela de campos.](media/data-manager-entities-fields.PNG "Tabela de campos")

- A guia **Atributos** vem selecionada por padrão e mostra uma tabela para revisar os detalhes da entidade selecionada, como nomes de campo, tipos de dados e tipos. A coluna **Tipo** mostra os tipos associados de Common Data Model que são identificados automaticamente pelo sistema ou [mapeados manualmente](map-entities.md) pelos usuários. Esses tipos são tipos semânticos que podem ser diferentes dos tipos de dados dos atributos. Por exemplo, o campo *Email* abaixo tem o tipo de dados *Texto* mas seu tipo do Common Data Model (semântico) pode ser *Email* ou *Endereço de email*.

> [!NOTE]
> Ambas as tabelas mostram apenas uma amostra dos dados da sua entidade. Para visualizar o conjunto completo de dados, vá para a página **Fontes de dados**, selecione uma entidade, selecione **Editar** e, em seguida, visualize os dados dessa entidade com o editor Power Query, conforme explicado em [Fontes de dados](data-sources.md).

Para saber mais sobre os dados ingeridos na entidade, a coluna **Resumo** fornece algumas características importantes dos dados, como nulos, valores ausentes, valores exclusivos, contagens e distribuições, conforme aplicável a seus dados.

Selecione o ícone do gráfico para ver o resumo dos dados.

> [!div class="mx-imgBorder"]
> ![Símbolo de resumo.](media/data-manager-entities-summary.png "Tabela de resumo de dados")

## <a name="entity-specific-information"></a>Informações específicas da entidade

A seção a seguir fornece informações sobre algumas entidades criadas pelo sistema.

### <a name="corrupted-data-sources"></a>Fontes de dados corrompidas

Os campos de uma fonte de dados ingerida podem conter dados corrompidos. Os registros com campos corrompidos são expostos nas entidades criadas pelo sistema. Saber sobre os registros corrompidos ajuda a identificar quais dados devem ser revisados e atualizados no sistema de origem. Após a próxima atualização da fonte de dados, os registros corrigidos são ingeridos no Customer Insights e passados para os processos downstream. 

Por exemplo, uma coluna 'aniversário' tem o tipo de dados definido como 'data'. Um registro de cliente tem sua data de aniversário inserida como '01/01/19777'. O sistema sinalizará este registro como corrompido. Alguém agora poderá alterar a data de aniversário no sistema de origem para '1977'. Após uma atualização automática das fontes de dados, o campo agora tem um formato válido e o registro será removido da entidade corrompida. 

Acesse **Dados** > **Entidades** e procure as entidades corrompidas na seção **Sistema**. Esquema de nomenclatura de entidades corrompidas: 'DataSourceName_EntityName_corrupt'.

O Customer Insights ainda processa os registros corrompidos. No entanto, eles podem causar problemas ao trabalhar com os dados unificados.

As verificações a seguir são executadas nos dados ingeridos para expor os registros corrompidos: 

- Se o valor de um campo não corresponde ao tipo de dados de sua coluna.
- Se os campos contêm caracteres que fazem com que as colunas não correspondam ao esquema esperado. Por exemplo: aspas formatadas incorretamente, aspas sem escape ou caracteres de nova linha.
- Se houver colunas datetime/date/datetimeoffset, o formato deverá ser especificado no modelo caso não siga o formato ISO padrão.



[!INCLUDE[footer-include](../includes/footer-banner.md)]
