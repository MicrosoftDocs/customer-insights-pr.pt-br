---
title: Gerenciar o índice pesquisar e filtrar para perfis de cliente
description: Encontre rapidamente informações sobre perfis unificados de clientes e filtre os atributos especificados.
ms.date: 07/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-search-filter
- customerInsights
ms.openlocfilehash: dfbfcbff3ffb3e4483252377e591229631d38556
ms.sourcegitcommit: c45c3e044034bf866b0662f80a59166cee4ababe
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2022
ms.locfileid: "9187895"
---
# <a name="manage-the-search--filter-index-for-customer-profiles"></a>Gerenciar o índice pesquisar e filtrar para perfis de cliente

O resultado da unificação dos dados de seus clientes é uma entidade *Cliente* que fornece uma exibição unificada de sua base total de clientes. Para que os usuários [encontrarem informações sobre um cliente ou grupo de clientes específico](customer-profiles.md) com rapidez, um administrador deve configurar os recursos **Pesquisar** e **Filtrar** da página **Clientes**.

   :::image type="content" source="media/search-filter.png" alt-text="Filtro de pesquisa":::

## <a name="define-searchable-attributes-and-indexed-fields"></a>Definir atributos pesquisáveis e campos indexados

Se for a primeira vez que você define atributos pesquisáveis como administrador, defina os campos indexados primeiro. Sugerimos que você escolha todos os atributos pelos quais os usuários possam pesquisar e filtrar clientes na página **Clientes**. Somente os atributos que existem na entidade *Cliente* criados durante o processo de unificação dos dados podem ser especificados.

1. Acesse **Clientes** e selecione **Índice pesquisar e filtrar**.

1. Selecione **+ Adicionar**.

1. Selecione o atributo na lista que deseja adicionar como campos indexados e clique em **Aplicar**.

1. Para adicionar mais atributos, selecione **Adicionar**. Para remover um atributo selecionado, selecione-o e, em seguida, selecione **Excluir**.

   :::image type="content" source="media/search-filter-index.png" alt-text="Página Índice pesquisar e filtrar":::

1. Selecione **Executar** quando estiver pronto para aplicar as configurações de pesquisa e filtro. Depois que as alterações forem processadas, exiba-as nos [cartões de cliente na página Cliente](customer-profiles.md).

## <a name="define-filtering-options-for-a-given-attribute"></a>Definir as opções de filtragem para um determinado atributo

Configure os campos que podem ser usados para a filtragem de clientes na página **Clientes**.

1. Acesse **Clientes** e selecione **Índice pesquisar e filtrar**.

1. Selecione um atributo e **Adicionar filtro**. Defina o número de resultados e a ordem na qual eles serão organizados. Dependendo do tipo de dados do atributo, um dos painéis a seguir será exibido.

   - Atributos do tipo cadeia de caracteres: especifique o número de resultados desejados no painel **Filtro de cadeia de caracteres** e a política de ordem pela qual eles serão organizados.

   - Atributos do tipo numérico: especifique os intervalos incluídos no painel **Filtro de números** e a política de ordem pela qual eles serão organizados.

   - Atributos do tipo data: especifique os intervalos incluídos no painel **Filtro de datas** e a política de ordem pela qual eles serão organizados.

1. Selecione **OK**. Repita para todos os atributos pelos quais deseja filtrar.

1. Selecione **Executar** quando estiver pronto para aplicar as configurações de pesquisa e filtro. Depois que as alterações forem processadas, exiba-as nos [cartões de cliente na página Cliente](customer-profiles.md).

## <a name="view-indexed-customer-fields"></a>Exibir campos do cliente indexados

A página **Índice pesquisar e filtrar** exibe as seguintes informações:

- **Nome**: representa o nome do atributo como ela aparece na entidade *Cliente*.
- **Tipo de dados**: Especifica se o tipo de dados é uma cadeia de caracteres, um número ou uma data.
- **Incluído na pesquisa**: Especifica se esse atributo pode ser usado para pesquisar clientes na página **Clientes** usando o campo **Pesquisar**.
- **Adicionar Filtro**: Controle para definir como esse atributo pode ser usado para filtrar a página **Clientes**.

## <a name="next-steps"></a>Próximas etapas

Analise a [página de perfis unificados](customer-profiles.md) para pesquisar perfis ou usar os campos indexados para ver um subconjunto de todos os perfis unificados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
