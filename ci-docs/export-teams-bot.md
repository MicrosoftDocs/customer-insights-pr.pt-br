---
title: Bot do Teams para Dynamics 365 Customer Insights (versão preliminar)
description: Procure perfis de clientes unificados no Microsoft Teams com a ajuda de um bot.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: d140ae72578b48091a41005c4acafe03bac540da
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9195828"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a>Bot do Teams para Dynamics 365 Customer Insights (versão preliminar)

Conecte-se com o Microsoft Teams para permitir que um bot procure perfis de clientes unificados nos canais do Teams.

:::image type="content" source="media/teams-bot.png" alt-text="Bot do Teams mostrando um registro de cliente":::

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos uma [fonte de dados adicionada](data-sources.md).
- O [processo de unificação](data-unification.md) foi concluído.
- Os campos são adicionados ao [índice de pesquisa e filtro](search-filter-index.md).
- O Customer Insights e o Teams estão na mesma organização.
- Seu ambiente tem o público-alvo principal definido para clientes individuais. Não há suporte para contas comerciais.


> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWRElj]

## <a name="configure-the-bot"></a>Configurar o bot

1. Vá para **Administração** > **Conexões**.
1. No bloco do Microsoft Teams, selecione **Configurar**.
1. Você é redirecionado para a área **Aplicativos** no Teams. Você também pode abrir o Teams e selecionar **Aplicativos** no canto inferior esquerdo ou [obtê-lo do AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) diretamente.
1. Procure **Customer Insights** e selecione o aplicativo.
1. Selecione **Adicionar**.
1. Entre no Customer Insights no Teams. Uma mensagem de boas-vindas é exibida.

## <a name="things-you-can-do-with-the-bot"></a>O que você pode fazer com o bot

O bot fornece recursos de pesquisa para perfis unificados de clientes.

- Insira **pesquisar** seguido por um nome, endereço de email ou qualquer outro campo do perfil unificado de cliente que seja adicionado ao índice de pesquisa e filtro.

  Você receberá um cartão com até 15 campos do perfil do cliente resultante. Várias correspondências retornam uma lista de resultados onde você pode selecionar um perfil. Para procurar uma correspondência exata, adicione o termo entre aspas duplas.

- Se a sua organização mantém vários ambientes do Customer Insights na mesma organização, insira **switchinstance** para escolher a qual ambiente deseja conectar o bot.

- Insira **ajuda** para ver uma lista dos comandos disponíveis para o bot.  

[!INCLUDE [footer-include](includes/footer-banner.md)]