---
title: Exibir perfis de cliente
description: Obtenha uma exibição combinada de seus dados de cliente unificados.
ms.date: 12/01/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 433e6ceda0ec7827bd672cff40f895d7719561df
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896313"
---
# <a name="customer-profiles"></a>Perfis do cliente

A página **Clientes** mostra uma exibição combinada de seus clientes, com base nos dados de perfil coletados usando [todas as fontes de dados](data-sources.md). Os perfis de clientes ficam disponíveis depois que você [cria a entidade do Cliente unificada](data-unification.md). Certifique-se de concluir o processo de unificação de dados para obter visões mais amplas de seus clientes. A página também permite que você procure clientes.

Os clientes podem ser indivíduos ou organizações (visualização). Cada perfil de cliente ou organização é representado por um bloco. Selecione um bloco para ver informações adicionais sobre esse cliente ou organização específica. Use os controles de paginação na parte inferior da página para ver registros adicionais.

> [!div class="mx-imgBorder"] 
> ![Perfis do cliente B2C](media/profiles-customers.png "Perfis do cliente B2C")

Organizações (Versão Prévia)
> [!div class="mx-imgBorder"] 
> ![Perfis do cliente B2B](media/profile-customers-b2b.png "Perfis do cliente B2B")

> [!NOTE]
> Se você não conseguir ver os blocos ao selecionar **Clientes** na navegação, seu administrador precisará [definir pelo menos um atributo pesquisável](search-filter-index.md) no **Índice de filtro e pesquisa**.

## <a name="search-for-customers"></a>Procurar clientes

Procure clientes inserindo um nome ou algum outro atributo na caixa de pesquisa. A pesquisa só funciona dentro da entidade Perfil do Cliente criada durante o processo de unificação de dados.

Como administrador, você pode configurar os atributos pesquisáveis usando a página **Índice de filtro e pesquisa**. Para obter mais informações, consulte [Gerenciar Índice de filtro e pesquisa](search-filter-index.md).

## <a name="filter-customers"></a>Filtrar clientes

Você pode filtrar os clientes pelos campos da entidade Perfil do Cliente. Semelhante à pesquisa, seu admin precisará primeiro definir os campos como filtráveis usando a página **Índice de filtro e pesquisa**.

1. Selecione **Filtro** na página **Clientes**.

2. Marque as caixas próximas aos atributos pelos quais você deseja filtrar os clientes.

   > [!div class="mx-imgBorder"] 
   > ![Perfis do cliente](media/profiles-customers3.png "Perfis do cliente")

3. Remova seus filtros selecionando **Limpar filtros** na página **Clientes**.

##  <a name="customer-details-page"></a>Página Detalhes do cliente

Selecione qualquer um dos blocos do cliente para abrir a **página Detalhes do cliente**. Essa exibição contém informações unificadas para o cliente selecionado.

Os detalhes do cliente incluem:

-   **Bloco do perfil do cliente:** este bloco mostra os diferentes valores da entidade unificada do perfil do cliente. Esses detalhes podem incluir endereço de email, nome, cidade e assim por diante. 

-   **Interesses potenciais, marcas potenciais:** mostra se você configurou um enriquecimento primário. Representa interesses e afinidades potenciais para marcas que um cliente com um perfil semelhante a este possa ter. Para obter mais informações, consulte [Enriquecer os perfis de clientes com afinidades de marca e de interesse](enrichment-microsoft.md).

-   **Medidas:** mostra se você configurou uma ou mais medidas de um tipo específico: medidas de atributo do cliente. Elas incluem KPIs calculados em torno de seus clientes no nível do cliente individual. Para obter mais informações, consulte [Definir e gerenciar medidas](measures.md).

-   **Linha do tempo da atividade:** mostra se você configurou atividades. A exibição da linha do tempo contém atividades classificadas cronologicamente desse cliente, começando com a atividade mais recente. Para obter mais informações, consulte [Atividades do cliente](activities.md).

Selecione **Voltar aos Clientes** para retornar à página de pesquisa do cliente.

## <a name="next-steps"></a>Próximas etapas

[Adicione mais fontes de dados](data-sources.md) ou [crie segmentos de clientes](segments.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]