---
title: Exibir perfis de cliente
description: Exibir seus dados de clientes unificados, incluindo o uso de pesquisa e filtros
ms.date: 06/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
searchScope:
- ci-customers-page
- ci-customer-card
- ci-activities
- ci-activities-wizard
- customerInsights
ms.openlocfilehash: 0c8edfd8f45ce7770d568811df2b38be1b04e73a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303769"
---
# <a name="view-customer-profiles"></a>Exibir perfis de cliente

Os perfis de cliente ficam disponíveis depois que você [cria a entidade *Cliente* unificada](data-unification.md). A visualização combinada de seus perfis unificados de cliente é exibida na página **Clientes**. Os clientes podem ser pessoas ou organizações.

Va para a página **Clientes** para visualizar os clientes e seus perfis. Cada perfil de cliente é representado por um bloco de cartão do cliente. Use os controles de paginação para obter mais registros. O cartão exibe campos da entidade do *Cliente* conforme definido no **Índice de pesquisa e filtro**. A ordem dos campos dentro de cada cartão é escolhida pelo sistema.

> [!NOTE]
> Se você não conseguir ver os blocos ao selecionar **Clientes**, o administrador precisará [definir pelo menos um atributo pesquisável](search-filter-index.md) no **Índice de pesquisa e filtro**.

:::image type="content" source="media/customers-page-result-tiles-B2C.png" alt-text="Página Clientes mostrando blocos de resultados.":::

Selecione uma das seguintes ações:
- [Ver detalhes do cliente](#view-customer-details)
- [Gerenciar índice de filtro e pesquisa](search-filter-index.md) (somente administradores)
- [Filtrar clientes](#filter-customers)
- **Expandir cartões** ou **Recolher cartões** para expandir ou recolher as informações exibidas no bloco do cliente
- **Classificar por** um atributo específico
- [Pesquisar clientes](#search-for-customers)

  > [!NOTE]
  > Para usar filtro e pesquisa, um administrador deve configurar os atributos pesquisáveis e definir os campos filtráveis usando o índice de filtro e pesquisa.

## <a name="search-for-customers"></a>Pesquisar clientes

Procure clientes inserindo um nome ou algum outro atributo em **Pesquisar clientes**. Os atributos pesquisáveis são definidos pelo administrador e provêm da entidade *Cliente* unificada.

> [!NOTE]
> **Cadeia de caracteres** é o único tipo de dados incluído na pesquisa. Use-o no campo **Pesquisar clientes** da página Clientes para procurar clientes.

## <a name="filter-customers"></a>Filtrar clientes

Filtre os clientes pelos campos da entidade *Cliente*. Os campos filtráveis são definidos pelo administrador.

1. Na página **Clientes**, selecione **Mostrar filtros**. O painel Filtro é exibido.

1. Marque as caixas próximas aos atributos pelos quais você deseja filtrar os clientes.

1. Remova todos os filtros selecionando **Limpar filtros** ou desmarque uma caixa de seleção ao lado de um atributo selecionado.

1. Selecione **Ocultar filtros** para fechar o painel de filtros.

1. Para salvar os resultados de filtro como um [segmento](segments.md), selecione **Salvar filtros como segmento**.
   1. Insira um nome para o segmento.
   1. Selecione **Salvar** para salvar o segmento.
   1. Escolha se deseja executar o segmento agora selecionando **Ativar** ou executá-lo **Posteriormente**.

## <a name="view-customer-details"></a>Ver detalhes do cliente

Na página **Clientes**, selecione um bloco de cliente para visualizar os detalhes do cliente selecionado.

:::image type="content" source="media/customers-details-B2C.png" alt-text="Página Detalhes do cliente.":::

Os detalhes do cliente incluem:

**Bloco do perfil do cliente**: mostra os diferentes valores da entidade *Cliente* unificada. Se um campo não tiver valor para o perfil de cliente selecionado, ele não será mostrado, exceto pelo campo de endereço. O bloco é estruturado em seções:

- A primeira seção mostra um conjunto predefinido de campos seguido por todos os campos que fazem parte do índice de pesquisa e filtro. Todos os campos relacionados ao endereço são combinados em uma única linha, que será mostrada mesmo se o perfil não contiver informações de endereço.
- Exibição de **Contatos para este cliente** em ambientes para contas comerciais (B-to-B). Cada contato é exibido com seus campos. Os campos vazios estão ocultos.
- **Campos adicionais** mostra os demais campos do cliente selecionado, exceto IDs.
- **IDs** lista todas as IDs dos nomes de entidade correspondentes. Os campos são identificados como IDs pela semântica.

**Linha do tempo da atividade** mostra dados se você configurou [atividades](activities.md). A visualização da linha do tempo contém atividades ordenadas cronologicamente do cliente selecionado, começando com a atividade mais recente.

**Insights**:

- **Medidas** mostra se você configurou [medidas de atributo do cliente](measures.md). Elas incluem KPIs calculados em torno de seus clientes no nível do cliente individual.

- **Interesses potenciais, marcas potenciais** mostram se você configurou um [enriquecimento de marca ou de afinidade de interesse](enrichment-microsoft.md). Representa interesses e afinidades potenciais para marcas com base em outros clientes cujo perfil é semelhante ao perfil do cliente selecionado.

Para retornar à página **Clientes**, selecione **Voltar para Clientes**.

## <a name="next-steps"></a>Próximas etapas

[Adicionar mais fontes de dados](data-sources.md) ,[enriquecer perfis unificados](enrichment-hub.md), ou [criar segmentos](segments.md) para trabalhar com perfis de clientes unificados em outros aplicativos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
