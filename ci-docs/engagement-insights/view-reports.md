---
title: Exibir relatórios de dados
description: Use os relatórios disponíveis para ver as atividades em tempo real no seu site.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 5ccdcb47db597154cf79b9f2e8fc238ab75dfde9
ms.sourcegitcommit: d9965f4bfc09391698a34042f6b44367e53819e3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "7582908"
---
# <a name="view-reports"></a>Exibir relatórios

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um relatório é uma coleção de visualizações de dados, usando os dados coletados por meio do SDK, que ajuda você a medir e compreender o comportamento do usuário. Os insights do engajamento do Dynamics 365 Customer Insights incluem relatórios prontos para uso para projetos Web e móveis.  

## <a name="web-reports"></a>Relatórios da Web

Você pode acessar relatórios Web em **Descobrir** no painel de navegação esquerdo.

:::image type="content" source="media/report-menu.png" alt-text="Navegação mostrando a lista de relatórios disponíveis.":::

### <a name="real-time-usage-report"></a>Relatório de uso em tempo real

O relatório **Uso em tempo real** fornece uma visão geral das atividades atuais no seu site que é atualizado automaticamente a cada minuto. Utilize o uso em tempo real para monitorar o impacto de campanhas de marketing, eventos de imprensa e outros cenários no tráfego do seu site.

### <a name="key-metrics-reports"></a>Relatórios das principais métricas

- As **Exibições de página** listam as exibições de página para páginas individuais e o número total de exibições de página durante o período selecionado.

- As **Visitas** exibem informações sobre o número de visitas e a duração delas.

- **Visitantes** fornecem informações sobre visitantes únicos e recorrentes do seu site.

### <a name="content-reports"></a>Relatórios de conteúdo

- Os **Links** exibem informações sobre o número e o tipo de cliques.

- As **Páginas de saída** listam os links que os visitantes clicaram para sair do seu site.

### <a name="traffic-sources-reports"></a>Relatórios de fontes de tráfego

- Os **Referenciadores** listam os domínios e URLs que indicaram visitantes ao seu site.

- Os **Códigos de acompanhamento** fornecem detalhes sobre os códigos de acompanhamento nos links que trouxeram visitantes ao seu site.

### <a name="visitor-profiles-reports"></a>Relatórios de perfis de visitantes

- Os **Dispositivos** listam os dispositivos físicos que foram usados para acessar seu site.

- **SO e navegadores** fornecem insights sobre os sistemas operacionais e navegadores que estavam em execução ao acessar o seu site.

- Os **Locais** exibem informações sobre os visitantes por país, região e cidade.

- Os **Idiomas** listam as exibições de página de acordo com os idiomas preferidos do visitante.

## <a name="mobile-reports"></a>Relatórios móveis

Os relatórios móveis são agrupados em categorias de uso em tempo real, aplicativo e usuário. Você pode acessar relatórios móveis em **Descobrir** no painel de navegação esquerdo.   

:::image type="content" source="media/mobile-reports.png" alt-text="Interface de usuário dos insights sobre engajamento mostrando o relatório de uso em tempo real que renderiza dados nos gráficos e listas.":::   

### <a name="real-time-usage"></a>Uso em tempo real

**Uso em tempo real** fornece uma visão geral da atividade atual no seu aplicativo móvel que atualiza automaticamente a cada minuto. Aplique o uso em tempo real para monitorar o número de usuários e sessões atualmente ativos no seu aplicativo e as principais exibições de tela.

### <a name="app-reports"></a>Relatórios de aplicativo

- As **Exibições de tela** listam as exibições de tela para telas individuais em um aplicativo e o número total de exibições de tela durante um período selecionado. Você pode visualizar as exibições de tela por nome de tela ou título de tela.

- As **Sessões** exibem informações sobre o número de sessões e a duração delas.

- A **Frequência de retorno** agrupa as contagens de sessão pelo número de dias desde a última sessão.

- Os **Usuários** mostram usuários novos e recorrentes do seu aplicativo móvel.

- Os **Eventos** listam todos os eventos coletados do seu aplicativo mais a contagem total para cada evento.

### <a name="user-reports"></a>Relatórios do usuário

- As **Versões do aplicativo** lista as versões do seu aplicativo móvel em uso por parte de sua base de usuário.

- **Dispositivos e versões do SO** fornecem insights sobre quais dispositivos e sistemas operacionais estão em execução ao acessar o seu aplicativo móvel.

- Os **Locais** exibem informações sobre os usuários do aplicativo por país, região e cidade.

## <a name="filter-by-time-or-date-range"></a>Filtrar por intervalo de data ou hora

Você pode selecionar o período de tempo ou intervalo de datas em um relatório web ou móvel para focar em um valor ou período de tempo. 

- Para selecionar um período de tempo, no canto superior direito da visualização do relatório, selecione um valor na lista suspensa do relatório. Você também pode escolher um **Período fixo**. 

  :::image type="content" source="media/filter-by-time.png" alt-text="Filtrar por intervalo de data ou hora.":::   

- Para a maioria dos relatórios, selecione um valor em um gráfico ou lista para filtrar o relatório.

> [!NOTE]
> A seleção do intervalo de tempo está desabilitada para um relatório de uso em tempo real; o intervalo de tempo de um relatório de uso em tempo real é "agora".


[!INCLUDE[footer-include](../includes/footer-banner.md)]
