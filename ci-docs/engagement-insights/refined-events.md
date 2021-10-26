---
title: Criar e modificar eventos
description: Como criar e modificar eventos.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 935dc4cd41218842e8406b747daef47de04e337a
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606172"
---
# <a name="create-and-modify-events"></a>Criar e modificar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um evento são dados que representam o comportamento dos usuários, como as atividades em um site.

- Um evento *base* registra quando um usuário exibe uma página (evento de exibição) ou interage com o conteúdo (evento de ação).
- Um evento *refinado* é uma exibição virtual de um evento base. Você define eventos refinados removendo e adicionando propriedades ou filtrando eventos com base nos valores das propriedades.

## <a name="prerequisites"></a>Pré-requisitos

Para obter eventos, os dados de seu site precisam primeiramente estar conectados a insights de engajamento com um trecho de código. Para mais informações, consulte [Instalar o SDK web em um site](instrument-website.md).

 :::image type="content" source="media/new-events-connect-data.png" alt-text="Conecte primeiro seus dados.":::

## <a name="create-refined-events"></a>Criar eventos refinados

Use eventos refinados para reduzir o escopo de um evento base para [exportação](export-events.md) ou para remover propriedades que não são necessárias para exposição.

> [!NOTE]
> Depois de adicionar o SDK web ao seu site, você pode visualizar seus eventos de base e criar eventos refinados. 

Para visualizar seus eventos de base:

1. Acesse **Dados** no painel de navegação esquerdo.

1. Selecione **Eventos** para ver uma lista de todos os eventos no espaço de trabalho.

    :::image type="content" source="media/data-events.png" alt-text="Visualizar eventos.":::

Para criar um evento refinado a partir de um evento base: 

1. Vá para **Dados** > **Eventos** e selecione **+ Novos eventos** na parte superior da tela.

1. Na caixa de diálogo **Novos eventos**, selecione **Criar eventos refinados** e então selecione **Próximo**.
   
     :::image type="content" source="media/new-events-wizard.png" alt-text="Assistente de novos eventos.":::
     
1. Na caixa de diálogo **Novos eventos**, insira as seguintes informações:

   - Selecione um evento da lista suspensa **Eventos de base**.
   - Insira um nome na caixa **Nome de exibição de eventos refinados**.
   - Opcionalmente, atualize o **Nome real** sugerido sem usar espaços.

1. Selecione **Criar** para aplicar suas configurações.

O evento refinado agora aparece em sua lista **Eventos**.

### <a name="edit-event-name"></a>Editar o nome do evento

Você pode alterar o nome e as propriedades de um evento básico ou refinado.

1. Vá para **Dados** > **Eventos**. 

1. Selecione **Mais [...]** para um evento e, em seguida, selecione **Editar nome**.
    
     :::image type="content" source="media/create-refined-events-options.png" alt-text="Opções para criar eventos refinados.":::

3. Atualize o nome do evento e selecione **Renomear**.

### <a name="view-the-details-of-a-refined-event"></a>Visualizar detalhes de um evento refinado:

1. Na lista **Evento**, selecione seu evento base ou refinado. 

1. Selecione **Adicionar e remover propriedades** no topo da tela para abrir o painel **Editar propriedades**. 

     :::image type="content" source="media/add-remove-properties.png" alt-text="Adicionar e remover propriedades.":::

1. Use as caixas de seleção para selecionar as propriedades que deseja mostrar e aquelas que deseja ocultar. 

   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editar propriedades de eventos refinados.":::

1. Selecione **Confirmar** para aplicar sua seleção e, em seguida, selecione **Salvar**.


### <a name="edit-selected-properties-for-a-refined-event"></a>Editar propriedades selecionadas para um evento refinado

1. Vá para **Dados** > **Eventos** e selecione os eventos refinados para abrir a exibição detalhada.
1. Selecione **Adicionar e remover propriedades**. 
1. Edite a marcação das caixas de seleção.
1. Selecione **Confirmar** e, em seguida, selecione **Salvar** para aplicar as alterações.

Para obter informações sobre como exportar eventos, consulte [Exportar eventos](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
