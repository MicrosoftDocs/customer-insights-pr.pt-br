---
title: Bot para Microsoft Teams
description: Procure perfis de clientes unificados no Microsoft Teams com a ajuda de um bot.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 89a293d5b6f9f5452b2ccba495d2475002806019
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645702"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot do Teams para Dynamics 365 Customer Insights (versão preliminar)

Conecte-se com o Microsoft Teams para permitir que um bot procure perfis de clientes unificados nos canais do Teams.

> [!div class="mx-imgBorder"]
> ![Bot do Teams mostrando um registro de cliente.](media/teams-bot.png "Bot do Teams mostrando um registro de cliente")

## <a name="prerequisites"></a>Pré-requisitos

Para instalar e configurar o bot, os seguintes pré-requisitos devem ser atendidos:

- Há pelo menos uma [fonte de dados adicionada](data-sources.md).
- O [processo de unificação](data-unification.md) foi concluído.
- Os campos são adicionados ao [índice de pesquisa e filtro](search-filter-index.md).
- O Customer Insights e o Teams estão na mesma organização.
- Seu ambiente tem o público-alvo principal definido para clientes individuais. Não há suporte para contas comerciais.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurar o bot

1. Vá para **Administrador** > **Exportar Destinos**.
1. No bloco do Microsoft Teams, selecione **Configurar**.
1. Você é redirecionado para a área **Aplicativos** no Teams. Você também pode abrir o Teams e selecionar **Aplicativos** no canto inferior esquerdo ou [obtê-lo do AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) diretamente.
1. Procure **Customer Insights** e selecione o aplicativo.
1. Selecione **Adicionar**.
1. Depois de entrar no Customer Insights no Teams, você verá uma mensagem de boas-vindas e poderá começar.

## <a name="things-you-can-do-with-the-bot"></a>O que você pode fazer com o bot

O bot fornece recursos de pesquisa para perfis unificados de clientes.

- Insira **pesquisar** seguido por um nome, endereço de email ou qualquer outro campo no perfil unificado do cliente que seja adicionado ao índice de pesquisa e filtro.

  Você receberá um cartão com até 15 campos do perfil do cliente resultante. Várias correspondências retornam uma lista de resultados onde você pode selecionar um perfil. Você pode adicionar o termo de pesquisa entre aspas duplas para procurar uma correspondência exata.

- Se a sua organização mantiver vários ambientes do Customer Insights na mesma organização, você poderá inserir **switchinstance** para escolher a qual ambiente deseja conectar o bot.

- Insira **ajuda** para ver uma lista dos comandos disponíveis para o bot.  


[!INCLUDE [footer-include](includes/footer-banner.md)]