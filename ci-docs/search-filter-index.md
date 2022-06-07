---
title: Procurar e filtrar perfis de cliente
description: Encontre rapidamente informações sobre perfis unificados de clientes e filtre os atributos especificados.
ms.date: 11/01/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: 35bfd6530b9b80a4b0ec8ff992d9014534721907
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645668"
---
# <a name="customer-profiles-search--filter-index"></a>Perfis de clientes: índice de filtro e pesquisa

O resultado da unificação dos dados do cliente é uma entidade de Perfil do Cliente que fornece uma visão unificada da sua base total de clientes. Para [encontrar informações rapidamente sobre um cliente ou grupo de clientes específico](customer-profiles.md), você pode configurar o recurso **Pesquisar** e **Filtrar** na página **Clientes**. Leia para saber como os administradores podem editar os atributos na página **Índice de pesquisa e filtro**, que estão disponíveis para os usuários pesquisarem e filtrarem.

   :::image type="content" source="media/search-filter.png" alt-text="Filtro de pesquisa":::

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="add-fields-and-specify-attributes"></a>Adicionar campos e especificar atributos

Se for a primeira vez que você define atributos pesquisáveis como administrador, você precisará primeiro definir os campos indexados. Sugerimos que você escolha todos os atributos pelos quais os usuários possam pesquisar e filtrar clientes na página **Clientes**. Você só pode especificar atributos que existem na entidade Perfil do Cliente que você criou durante o processo de unificação de dados.

1. Abra a página **Clientes** e selecione **Índice de filtro e pesquisa**.

2. Selecione **+ Adicionar** para especificar os campos indexados.

3. Selecione os atributos na lista que você deseja adicionar como campos indexados. Você sempre pode adicionar mais atributos selecionando **Adicionar**. Você também pode remover quaisquer atributos selecionados usando o símbolo **Remover**.

## <a name="explore-the-indexed-customer-fields-table"></a>Explore a tabela de campos do cliente Indexado

As informações a seguir são apresentadas na tabela.

- **Nome**: Representa o nome do atributo, como aparece na entidade Perfil do Cliente.
- **Tipo de dados**: Especifica se o tipo de dados é uma cadeia de caracteres, um número ou uma data.
- **Incluído na pesquisa**: Especifica se esse atributo pode ser usado para pesquisar clientes na página **Clientes** usando o campo **Pesquisar**.
- **Adicionar Filtro**: Controle para definir como esse atributo pode ser usado para filtrar a página **Clientes**.

## <a name="editing-filtering-options-for-a-given-attribute"></a>Editando opções de filtragem para um determinado atributo

O menu **Filtro** na página **Clientes** pode incluir um número variável de níveis de atributo (por exemplo, diferentes faixas etárias para filtrar os clientes).

1. Selecione **Adicionar Filtro** para um determinado atributo na página **Índice de pesquisa e filtro**. Você pode definir o número de resultados e a ordem em que eles serão organizados. Dependendo do tipo de dados do atributo, um dos seguintes painéis será exibido.

- Atributos do tipo de string: Especifique o número de resultados desejados no painel **Opções do filtro da string** e a política de ordem pela qual eles serão organizados.

- Atributos do tipo numérico: Especifique os intervalos incluídos no painel **Opções do filtro de número** e a política de ordem pela qual eles serão organizados.

- Atributos do tipo de data: Especifique os intervalos incluídos no painel **Opções do filtro de data** e a política de ordem pela qual eles serão organizados.

2. Selecione **Salvar** para aplicar suas alterações.

3. Selecione **Executar** quando estiver pronto para aplicar suas configurações. Após o processamento das alterações, você as encontrará nos [cartões de cliente na página Cliente](customer-profiles.md). 

## <a name="next-steps"></a>Próximas etapas

Analise a [página de perfis unificados](customer-profiles.md) para pesquisar perfis ou usar os campos indexados para ver um subconjunto de todos os perfis unificados.


[!INCLUDE [footer-include](includes/footer-banner.md)]