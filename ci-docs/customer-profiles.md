---
title: Exibir perfis de cliente
description: Obtenha uma exibição combinada de seus dados de cliente unificados.
ms.date: 05/13/2022
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
ms.openlocfilehash: 9bb7abc04afe38d73e1df9b252e1864fa6570d7e
ms.sourcegitcommit: 4ae316c856b8de0f08a4605f73e75a8c2cf51c4e
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2022
ms.locfileid: "8755767"
---
# <a name="customer-profiles"></a>Perfis do cliente

A página **Clientes** mostra uma visão combinada de seus perfis de clientes unificados. Os perfis do cliente estão disponíveis, já que você [criou a entidade cliente unificada](data-unification.md). A página permite pesquisar clientes e definir o índice dessa pesquisa.

Os clientes podem ser pessoas ou organizações. Cada perfil de cliente é representado por um bloco de cartão do cliente. Use os controles de paginação para obter mais registros. O cartão exibe campos da entidade do *Cliente* conforme definido no **Índice de pesquisa e filtro**. A ordem dos campos dentro de cada cartão é escolhida pelo sistema.

Selecione um bloco para ver os dados do cliente selecionado em uma página dedicada chamada [Página de detalhes do cliente](customer-profiles.md#customer-details-page).

> [!div class="mx-imgBorder"]
> ![Página do cliente mostrando blocos de resultados](media/customers-page-result-tiles-B2C.png "Página do cliente mostrando blocos de resultados")

> [!NOTE]
> Se você não consegue ver os blocos ao selecionar **Clientes** na navegação, seu administrador precisa [definir pelo menos um atributo pesquisável](search-filter-index.md) no **Índice de pesquisa e filtro**.

## <a name="search-for-customers"></a>Pesquisar clientes

Procure clientes inserindo um nome ou algum outro atributo na caixa de pesquisa. A pesquisa só funciona dentro da entidade *Cliente* criada durante o processo de unificação de dados.

Como administrador, você pode configurar os atributos pesquisáveis usando a página **Índice de filtro e pesquisa**. Para obter mais informações, vá para [Gerenciar índice de pesquisa e filtro](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar clientes

Você pode filtrar os clientes pelos campos da entidade *Cliente*. Semelhante à pesquisa, seu admin precisará primeiro definir os campos como filtráveis usando a página **Índice de filtro e pesquisa**.

1. Selecione **Mostrar filtros** na página **Clientes**.

1. Marque as caixas próximas aos atributos pelos quais você deseja filtrar os clientes.

1. Remova seus filtros selecionando **Limpar filtros** na página **Clientes**.

## <a name="customer-details-page"></a>Página Detalhes do cliente

Selecione qualquer um dos blocos do cliente para abrir a **página Detalhes do cliente**. Essa exibição contém informações unificadas para o cliente selecionado. Os detalhes do cliente incluem o seguinte conteúdo:

**Bloco do perfil do cliente**: Este bloco mostra os diferentes valores da entidade *Cliente* unificada. Se um campo não tiver valor para o perfil de cliente selecionado, ele não será exibido. O bloco é estruturado em seções:

- A primeira seção mostra um conjunto predefinido de campos seguido por todos os campos que fazem parte do índice de pesquisa e filtro. Todos os campos relacionados ao endereço são combinados em uma única linha se o perfil contiver tais campos.
- **Contatos para este cliente**: Em ambientes para contas corporativas, você verá todos os contatos relacionados a este cliente na segunda seção. Cada contato é exibido com seus campos. Os campos vazios estão ocultos.
- **Campos adicionais**: Mostra os demais campos do cliente selecionado, exceto os IDs.
- **IDs**: Lista todos os IDs sob seus nomes de entidade correspondentes. Os campos são identificados como IDs por sua semântica, que os categoriza como tal.

**Linha do tempo da atividade**: Mostra dados se você configurou atividades. A visualização da linha do tempo contém atividades ordenadas cronologicamente do cliente selecionado, começando com a atividade mais recente. Para obter mais informações, acesse [Atividades do cliente](activities.md).

**Insights**:

- **Medidas**: Mostra se você configurou uma ou mais medidas medidas de atributos do cliente. Elas incluem KPIs calculados em torno de seus clientes no nível do cliente individual. Para obter mais informações, vá para [Definir e gerenciar medidas](measures.md).

- **Interesses potenciais, marcas potenciais**: Mostra se você configurou um enriquecimento de marca ou afinidade de interesse. Representa interesses e afinidades potenciais para marcas com base em outros clientes cujo perfil é semelhante ao perfil do cliente selecionado. Para obter mais informações, vá para [Enriqueça os perfis dos clientes com afinidades de marca e interesse](enrichment-microsoft.md).

Para retornar à página de pesquisa do cliente, selecione **Voltar para Clientes**.

## <a name="next-steps"></a>Próximas etapas

[Adicionar mais fontes de dados](data-sources.md) ,[enriquecer perfis unificados](enrichment-hub.md), ou [criar segmentos](segments.md) para trabalhar com perfis de clientes unificados em outros aplicativos.

[!INCLUDE [footer-include](includes/footer-banner.md)]
