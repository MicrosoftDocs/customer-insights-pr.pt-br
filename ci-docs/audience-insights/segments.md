---
title: Segmentos em insights de público-alvo
description: Visão geral dos segmentos e como criá-los e gerenciá-los.
ms.date: 11/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 56978c984a91e85e86956e7eac1d59609c349b6a
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732574"
---
# <a name="segments-overview"></a>Visão geral dos segmentos

Os segmentos permitem agrupar seus clientes com base em atributos demográficos, transacionais ou comportamentais. Você pode usar segmentos para direcionar campanhas promocionais, atividades de vendas e ações de suporte ao cliente para atingir suas metas de negócios.

Os perfis de clientes que correspondem aos filtros de uma definição de segmento são chamados de *membros* de um segmento. Alguns [limites de serviço](service-limits.md) se aplicam.

## <a name="create-a-new-segment"></a>Criar um novo segmento

Há várias maneiras de criar um novo segmento: 

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

- Segmento complexo com construtor de segmentos: [Construa o nosso próprio](segment-builder.md#create-a-new-segment) 
- Segmentos simples com um operador: [Segmento rápido](segment-builder.md#quick-segments) 
- Forma de encontrar clientes semelhantes com tecnologia de IA: [Clientes semelhantes](find-similar-customer-segments.md) 
- Sugestões com IA com base em medidas ou atributos [Segmentos sugeridos para melhorar as medidas](suggested-segments.md) 
- Sugestões baseadas em atividades: [Segmentos sugeridos com base na atividade do cliente](suggested-segments-activity.md) 

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

- Segmento complexo com construtor de segmentos: [Construa o nosso próprio](segment-builder.md#create-a-new-segment)

---

## <a name="manage-existing-segments"></a>Gerenciar segmentos existentes

Acesse a página **Segmentos** para ver todos os seus segmentos salvos e gerenciá-los.

Cada segmento é representado por uma linha que inclui informações adicionais sobre o segmento.

:::image type="content" source="media/segments-selected-segment.png" alt-text="Segmento selecionado com a lista suspensa de opções e opções disponíveis.":::

As seguintes ações estão disponíveis quando você seleciona um segmento:

- **Exiba** os detalhes do segmento, incluindo a tendência de contagem de membros, uma visualização dos membros do segmento.
- **Edite** o segmento para alterar suas propriedades.
- **Criar duplicidade** de um segmento. Você pode optar por editar suas propriedades imediatamente ou simplesmente salvar a duplicidade.
- **Atualize** o segmento para incluir os dados mais recentes.
- **Ative** ou **desative** o segmento. Os segmentos têm dois estados possíveis: ativo ou inativo. Esses estados são úteis ao editar um segmento. Para segmentos inativos, a definição do segmento existe, mas ainda não contém nenhum cliente. Quando você ativa um segmento, o estado dele muda de "inativo" para "ativo" e ele começa a procurar clientes que correspondam à definição do segmento. Se uma [atualização programada](system.md#schedule-tab) estiver configurada, os segmentos inativos terão o **Status** listado como **Ignorado**, indicando que uma atualização nem mesmo foi tentada. Quando um segmento inativo for ativado, ele será atualizado e incluído nas atualizações agendadas.
  Como alternativa, você pode usar a funcionalidade **Agendar mais tarde** na lista suspensa **Ativar/desativar** para especificar data e hora futuras para a ativação e desativação de um segmento específico.
- **Renomeie** o segmento.
- **Baixe** a lista de membros como um arquivo .CSV.
- **Gerencie as exportações** para ver o segmento relacionado às exportações e gerenciá-las. [Saiba mais sobre as exportações.](export-destinations.md)
- **Exclua** o segmento.

## <a name="refresh-segments"></a>Atualizar segmentos

Você pode atualizar todos os segmentos de uma vez, selecionando **Atualizar tudo** na página **Segmentos** ou você pode atualizar um ou vários segmentos ao selecioná-los e escolher **Atualizar** nas opções. Como alternativa, você pode configurar uma atualização recorrente em **Admin** > **Sistema** > **Agendar**.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="export-segments"></a>Exportar segmentos

Você pode exportar um segmento da página de segmentos ou da [página de exportações](export-destinations.md). 

1. Vá para a página **Segmentos**.

1. Selecione **Mostrar mais [...]** para o segmento que você deseja exportar.

1. Selecione **Gerenciar exportações** na lista suspensa de ações.

1. A página **Exportações (versão preliminar) para segmento** é aberta. Você pode ver todas as exportações configuradas agrupadas contendo o segmento atual ou não.

   1. Para adicionar o segmento selecionado a uma exportação, use a opção **Editar** a respectiva exportação para selecionar o segmento correspondente e, em seguida, salve. Em ambientes para clientes individuais, você pode selecionar a exportação na lista e selecionar **Adicionar segmento** para alcançar o mesmo resultado.

   1. Para criar uma exportação com o segmento selecionado, selecione **Adicionar exportação**. Para obter mais informações sobre a criação de exportações, consulte [Configurar uma nova exportação](export-destinations.md#set-up-a-new-export).

1. Selecione **Voltar** para retornar à página principal dos segmentos.

## <a name="view-processing-history-and-segment-members"></a>Exibir histórico de processamento e membros do segmento

Você pode ver dados consolidados sobre um segmento revisando seus detalhes.

Na página **Segmentos**, selecione o segmento que deseja revisar.

A parte superior da página inclui um gráfico de tendências que visualiza as alterações na contagem de membros. Passe o mouse sobre os pontos de dados para ver a contagem de membros em uma data específica.

Você pode atualizar o período da visualização.

> [!div class="mx-imgBorder"]
> ![Intervalo de tempo do segmento.](media/segment-time-range.png "Intervalo de tempo do segmento")

A parte inferior contém uma lista dos membros do segmento.

> [!NOTE]
> Os campos que aparecem nesta lista são baseados nos atributos das entidades do seu segmento.
>
>A lista é uma visualização dos membros do segmento correspondentes e mostra os 100 primeiros registros do seu segmento, para que você possa avaliá-lo rapidamente e revisar suas definições, se necessário. Para ver todos os registros correspondentes, você precisa [exportar o segmento](export-destinations.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)] 
