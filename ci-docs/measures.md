---
title: Visão geral de medidas
description: Saiba como as medidas ajudam a analisar e refletir o desempenho do seu negócio.
ms.date: 03/24/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: v-wendysmith
ms.author: wameng
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-measures
- ci-measure-builder
- ci-measure-template
- ci-enrichment-details
- customerInsights
ms.openlocfilehash: 99368a7ab2e8d7b3e53c04fbf25bb23bd2e550a9
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245359"
---
# <a name="measures-overview"></a>Visão geral de medidas

As medidas ajudam você a entender melhor os comportamentos dos clientes e o desempenho dos negócios. Elas analisam para valores relevantes de [perfis unificados](data-unification.md). Por exemplo, uma empresa deseja ver o *gasto total por cliente* para entender o histórico ou a medida de um cliente específico ou medir as *vendas totais da empresa* para entender a receita de nível agregado em toda a empresa.

Crie medidas para planejar atividades comerciais consultando dados do cliente e extraindo insights. Por exemplo, crie uma medida de *gasto total por cliente* e *retorno total por cliente* para ajudar a identificar um grupo de clientes com alto gasto, porém com alto retorno. Em seguida, [crie um segmento](segments.md) com base nessas medidas para gerar as próximas melhores ações.

## <a name="create-a-measure"></a>Criar uma medida

Escolha como criar uma medida com base em seu público-alvo.

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

- Do zero com o construtor de medidas: [Criar sua própria](measure-builder.md).
- A partir de medidas comumente usadas: [Usar modelos predefinidos](measure-templates.md).

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

Do zero com o construtor de medidas: [Criar sua própria](measure-builder.md).

---

## <a name="manage-existing-measures"></a>Gerenciar medidas existentes

Acesse a página **Medidas** para exibir as medidas que criou, seus status, tipo de medida e a última vez em que os dados foram atualizados. Você pode classificar a lista de medidas por qualquer coluna ou usar a caixa de pesquisa para encontrar a medida que deseja gerenciar.

Selecione Avançar em uma medida para exibir as ações disponíveis. Selecione o nome da medida para visualizar a saída e baixar um arquivo CSV.

:::image type="content" source="media/measures-actions.png" alt-text="Ações para gerenciar medidas únicas."lightbox="media/measures-actions.png":::

- **Editar** a medida para alterar suas propriedades.
- **Atualizar** a medida para incluir os dados mais recentes.
- **Renomear** a medida.
- **Ativar** ou **Desativar** a medida. As medidas inativas não serão atualizadas durante uma [atualização agendada](schedule-refresh.md) e terão o **Status** listado como **Ignorada**, indicando que nem mesmo houve tentativa de atualização.
- **Marcar** para [gerenciar marcas](work-with-tags-columns.md#manage-tags) para a medida.
- **Excluir** a medida.
- **Colunas** para [personalizar as colunas](work-with-tags-columns.md#customize-columns) que são exibidas.
- **Filtro** para [filtrar as marcas](work-with-tags-columns.md#filter-on-tags).
- **Pesquisar nome**, para pesquisar pelo nome da medida.

## <a name="refresh-measures"></a>Atualizar medidas

As medidas podem ser atualizadas em uma agenda automática ou ser atualizadas manualmente sob demanda. Para atualizar manualmente uma ou mais medidas, selecione-as e escolha **Atualizar**. Para [agendar uma atualização automática](schedule-refresh.md), acesse **Administrador** > **Sistema** > **Agenda**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
