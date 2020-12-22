---
title: Home page nos insights de público-alvo
description: Comece a explorar o aplicativo na Home page.
ms.date: 09/30/2020
ms.reviewer: nimagen
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: bd16966eabb126d9c9945ededc53273df02c3369
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405039"
---
# <a name="create-a-new-environment"></a>Criar um novo ambiente

## <a name="create-a-trial-environment"></a>Criar um ambiente de avaliação

Você pode se inscrever em uma avaliação na [página de inscrição de avaliação](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

> [!NOTE]
> As avaliações expiram após 30 dias.

1. Escolha a opção **Inscrever-se em uma avaliação gratuita** e selecione **Inscrever-se agora**.

1. Forneça seu endereço corporativo ou de estudante, conte-nos mais sobre você e selecione **Avançar**.

1. Forneça um **Nome** para o novo ambiente. 

1. Selecione o tipo de avaliação.

1. Escolha a **Região** para o ambiente.

1. Opcionalmente, para administradores de uma organização do Dynamics 365: Selecione **Configurações avançadas** e forneça a URL da sua organização para usar recursos de previsão, como rotatividade de clientes.

1. Selecione **Criar**. 

Após a criação do ambiente, você verá o ambiente **Demonstração**, que permite explorar o aplicativo com dados fictícios. É possível alterar os dados de exemplo para corresponder ao seu setor. Selecione o ícone **Configurações** no cabeçalho e, em seguida, selecione **Configurações da demonstração**. Além disso, você pode alterar o tema visual. 

Você pode [alternar para o ambiente](#change-between-environments) criado durante o processo de inscrição para trabalhar com seus próprios dados.

## <a name="create-a-new-production-or-sandbox-environment"></a>Criar um novo ambiente de produção ou área restrita

No seu ambiente, selecione o ícone **Configurações** no cabeçalho e, em seguida, selecione **Novo ambiente**.

Siga as etapas como se você fosse [criar um ambiente de avaliação](#create-a-trial-environment). Você recebe uma opção adicional ao selecionar **Configurações avançadas** para armazenar os dados no seu próprio Azure Data Lake. Forneça o nome e a chave da conta para estabelecer uma conexão com o Azure Data Lake. Por padrão, os dados são armazenados no data lake gerenciado do Customer Insights.

> [!IMPORTANT]
> Ao salvar dados no Azure Data Lake Storage, você concorda que esses dados serão transferidos e armazenados no local geográfico adequado para a conta de armazenamento do Azure, que pode ser diferente de onde os dados são armazenados no Dynamics 365 Customer Insights.  [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="explore-the-home-page"></a>Explore a home page

Você pode [acessar seu ambiente do Customer Insights](https://home.ci.ai.dynamics.com/) na seguinte URL: [https://home.ci.ai.dynamics.com/](https://home.ci.ai.dynamics.com/).
A **Página Inicial** mostra uma visão geral da base de clientes e as principais métricas para rastrear a integridade do seu negócio.

> [!div class="mx-imgBorder"] 
> ![Insights na Home page](media/home-page-insights.png "Insights na Home page")

Em **Segmentos recentes**, você vê grupos de clientes com base em atributos demográficos, comportamentais ou transacionais que você definiu. [Criando segmentos](segments.md) ajuda você a direcionar melhor suas atividades de negócios.

**Medidas recentes** mostram blocos com [medidas](measures.md). As medidas são indicadores chave de desempenho (KPIs) que você definiu. Por exemplo, probabilidade média de rotatividade de clientes ou gasto médio online por cliente.

A seção **Enriquecimentos recentes** lista os resultados das execuções de enriquecimentos recém-concluídos. Os enriquecimentos adicionam informações sobre a base de clientes. Por exemplo, entender os interesses e marcas com os quais eles têm afinidade. Esta informação pode ser desbloqueada usando os recursos [enriquecimento](enrichment-microsoft-graph.md), após concluir as fases [mapear](map-entities.md), [corresponder](match-entities.md) e [mesclar](merge-entities.md).

## <a name="change-between-environments"></a>Mudança entre ambientes

Depois de instalar e configurar as [fontes de dados](data-sources.md), convém alternar de um ambiente de demonstração para um ambiente ativo. Usar o ambiente de produção permite que você trabalhe com seus próprios dados de cliente. Selecione o controle de **Ambiente** no canto superior direito da página para alterar os ambientes.

> [!div class="mx-imgBorder"] 
> ![Alterar ambiente](media/home-page-environment-switcher.png "Alterar ambiente")

Os administradores podem criar e gerenciar [vários ambientes](manage-environments.md). Manter mais de um ambiente pode ser útil se, por exemplo, sua organização operar internacionalmente e você precisar segregar dados e insights de maneiras diferentes.

## <a name="next-step"></a>Próxima etapa

Para ver seus próprios insights na home page, primeiro você precisa [adicionar fontes de dados](data-sources.md) e [unificar](data-unification.md) seus dados para criar perfis de clientes.
