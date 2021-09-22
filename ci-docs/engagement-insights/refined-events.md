---
title: Criar e modificar eventos refinados
description: Como criar e modificar eventos refinados.
ms.reviewer: mhart
ms.author: jefhar
author: mochimochi016
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 0344bac5f4d43df853309f43c94d95f962937f77c936ed7305c5de4a08835f04
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034760"
---
# <a name="create-and-modify-refined-events"></a>Criar e modificar eventos refinados

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]


Um evento são dados que representam o comportamento dos usuários, como as atividades em um site.

- Um evento *base* registra quando um usuário exibe uma página (evento de exibição) ou interage com o conteúdo (evento de ação).
- Um evento *refinado* é uma exibição virtual de um evento base. Você define eventos refinados removendo e adicionando propriedades ou filtrando eventos com base nos valores das propriedades.

Use eventos refinados para reduzir o escopo de um evento base para [exportação](export-events.md) ou para remover propriedades que não são necessárias para exposição.

## <a name="create-refined-events"></a>Criar eventos refinados

Há três maneiras de criar um evento refinado a partir de um evento base. 

1. Vá para **Dados**> **Eventos** e escolha uma das seguintes opções:
    - Selecione **Novos eventos** e, em seguida, selecione **Criar eventos refinados**.
    - Selecione um evento base para abrir uma exibição detalhada e selecione **Criar eventos refinados** no menu superior.
    - Selecione **Mais [...]** para abrir o menu de atalho de um evento base. Em seguida, selecione **Criar eventos refinados**.
    
    :::image type="content" source="media/create-refined-events-options.png" alt-text="Opções para criar eventos refinados.":::

1. Na caixa de diálogo **Criar eventos refinados**, insira as informações a seguir:

- Selecione um evento na lista suspensa **Eventos base** se você estiver criando um novo evento.
- Insira um nome na caixa **Nome de exibição de eventos refinados**.
- Opcionalmente, atualize o **Nome real** sugerido sem usar espaços.

3. Selecione **Criar** para aplicar suas configurações.

1. Na exibição detalhada do seu evento refinado, selecione **Adicionar e remover propriedades** para abrir o painel **Editar propriedades**. 

1. Use as caixas de seleção para selecionar as propriedades que deseja mostrar e aquelas que deseja ocultar. 
   :::image type="content" source="media/edit-properties-refined-events.png" alt-text="Editar propriedades de eventos refinados.":::

1. Selecione **Confirmar** para aplicar sua seleção.

1. Selecione **Salvar** para salvar a configuração.

## <a name="edit-refined-events"></a>Editar eventos refinados

Você pode alterar o nome e as propriedades de um evento refinado.

### <a name="edit-event-name"></a>Editar o nome do evento

1. Vá para **Dados** > **Eventos**. 
1. Selecione **Mais [...]** para um evento e, em seguida, selecione **Editar nome**.
1. Atualize o nome do evento e selecione **Renomear**.

### <a name="edit-selected-properties"></a>Editar propriedades selecionadas

1. Vá para **Dados** > **Eventos** e selecione os eventos refinados para abrir a exibição detalhada.
1. Selecione **Adicionar e remover propriedades**. 
1. Edite a marcação das caixas de seleção.
1. Selecione **Confirmar** e, em seguida, selecione **Salvar** para aplicar as alterações.

Para obter informações sobre como exportar eventos, consulte [Exportar eventos](export-events.md).
[!INCLUDE[footer-include](../includes/footer-banner.md)]
