---
title: Home page nos insights de público-alvo
description: Comece a explorar o aplicativo na Home page.
ms.date: 01/07/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: bf9080c564850bca0c239b7317eed2fc0f77d9f3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597221"
---
# <a name="create-a-new-environment"></a>Criar um novo ambiente

## <a name="create-a-trial-environment"></a>Criar um ambiente de avaliação

Você pode se inscrever em uma avaliação na [página de inscrição de avaliação](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> As avaliações expiram após 30 dias.

1. Escolha a opção **Inscrever-se em uma avaliação gratuita** e selecione **Inscrever-se agora**.

1. Forneça seu endereço corporativo ou de estudante, conte-nos mais sobre você e selecione **Avançar**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Caixa de diálogo para se inscrever em uma instância de avaliação":::

1. Forneça um **Nome** para o novo ambiente. 

1. Selecione o tipo de avaliação.

1. Escolha a **Região** para o ambiente.

1. Opcionalmente, para administradores de uma organização do Dynamics 365: Selecione **Configurações avançadas** e forneça a URL da sua organização para usar recursos de previsão, como rotatividade de clientes.

1. Selecione **Criar**. 

Após a criação do ambiente, você verá o ambiente **Demonstração**, que permite explorar o aplicativo com dados fictícios. É possível alterar os dados de exemplo para corresponder ao seu setor. Selecione o ícone **Configurações** no cabeçalho e, em seguida, selecione **Configurações da demonstração**. Além disso, você pode alterar o tema visual. 

Você pode [alternar para o ambiente](#switch-environments) criado durante o processo de inscrição para trabalhar com seus próprios dados.

## <a name="create-a-new-production-or-sandbox-environment"></a>Criar um novo ambiente de produção ou área restrita

No seu ambiente, clique no seletor de **Ambientes** no cabeçalho do aplicativo e selecione **Novo**.

Siga as etapas como se você fosse [criar um ambiente de avaliação](#create-a-trial-environment). Por padrão, os dados são armazenados no data lake gerenciado do Customer Insights. Você recebe uma opção adicional ao selecionar **Configurações avançadas** para armazenar os dados no seu próprio Azure Data Lake. Forneça o nome e a chave da conta para estabelecer uma conexão com o Azure Data Lake. 

> [!IMPORTANT]
> Ao salvar dados no Azure Data Lake Storage, você concorda que esses dados serão transferidos e armazenados no local geográfico adequado para a conta de armazenamento do Azure, que pode ser diferente de onde os dados são armazenados no Dynamics 365 Customer Insights.  [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explore a home page

Você pode [acessar insights de público-alvo do Dynamics 365 Customer Insights](https://home.ci.ai.dynamics.com/) na seguinte URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
A **Página Inicial** mostra uma visão geral de segmentos, medidas e dados de enriquecimento (se configurados) após concluir as fases de [mapeamento](map-entities.md), [correspondência](match-entities.md) e [mesclagem](merge-entities.md).

> [!div class="mx-imgBorder"] 
> ![Insights na Home page](media/home-page-insights.png "Insights na Home page")

Em **Segmentos recentes**, você vê grupos de clientes com base em atributos demográficos, comportamentais ou transacionais que você definiu. [Criar segmentos](segments.md) ajuda a agrupar a base de clientes e direcionar melhor as atividades comerciais.

As **medidas recentes** mostram blocos com [indicadores chave de desempenho (KPIs)](measures.md) que você definiu. Por exemplo, a probabilidade média de um cliente se desligar ou o gasto online médio por cliente.

A seção **Enriquecimentos recentes** lista os resultados das execuções de enriquecimentos recém-concluídos. Os [enriquecimentos](enrichment-hub.md) adicionam informações sobre a base de clientes. Por exemplo, entender os interesses e marcas com os quais eles têm afinidade.

## <a name="switch-environments"></a>Alternar ambientes

Selecione o controle de **Ambiente** no canto superior direito da página para alterar os ambientes.

> [!div class="mx-imgBorder"] 
> ![Alterar ambiente](media/home-page-environment-switcher.png "Alterar ambiente")

Os administradores podem criar e gerenciar [vários ambientes](manage-environments.md). Manter mais de um ambiente pode ser útil se, por exemplo, sua organização operar internacionalmente e você precisar segregar dados e insights de maneiras diferentes.

## <a name="next-step"></a>Próxima etapa

Para ver seus próprios insights na home page, primeiro você precisa [adicionar fontes de dados](data-sources.md) e [unificar](data-unification.md) seus dados para criar perfis de clientes.


[!INCLUDE[footer-include](../includes/footer-banner.md)]