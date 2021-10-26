---
title: Exibir e criar dimensões
description: Como criar e editar e excluir dimensões.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 136da1e1265c7087d861712d34d011b09cb60ad5
ms.sourcegitcommit: 565637f49cbdd05a82f42784f594c19cac299140
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7623618"
---
# <a name="view-and-create-dimensions"></a>Exibir e criar dimensões

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Uma dimensão é um atributo de um evento que pode descrever, filtrar ou agrupar dados. Se estiver executando uma promoção de marketing em seu site, você poderá usar as dimensões para classificar os visitantes por usuários novos e recorrentes.  

Os insights de participação incluem dimensões prontas para uso (OOB) para propriedades de eventos. Os exemplos incluem:

- Nome do navegador
- Nome da página
- Modelo do dispositivo
- Sistema operacional
- País/Região

## <a name="view-dimensions"></a>Exibir dimensões

As dimensões são baseadas nas propriedades de eventos existentes. Quando você usa o código de rastreamento para insights de participação, as dimensões do sistema são criadas automaticamente.

1. Acesse **Dados** no painel de navegação esquerdo. 
1. Selecione **Dimensões** para ver uma lista de todas as dimensões no espaço de trabalho. 
   > [!NOTE]
   > As dimensões geradas pelo sistema são somente leitura. Não é possível editá-las. Você pode somente criar e editar dimensões personalizadas.

## <a name="create-a-dimension"></a>Criar uma dimensão

Além das dimensões geradas pelo sistema, os administradores do ambiente e do espaço de trabalho podem criar dimensões personalizadas. As dimensões personalizadas são baseadas em propriedades padrão de eventos de base ou podem usar [propriedades personalizadas de um evento](advanced-SDK-implementation.md).

1. Acesse **Dados** > **Dimensões**.
1. Selecione **Nova dimensão**.

   :::image type="content" source="media/add-dimension.png" alt-text="Adicione uma dimensão a um evento.":::

1. No painel **Criar uma dimensão**, selecione uma propriedade na qual basear a dimensão. A lista de propriedades mostrará todas as propriedades no espaço de trabalho não atribuídas a uma dimensão.
   
   :::image type="content" source="media/create-new-dimension.png" alt-text="Crie uma nova dimensão.":::
      
3. Insira um nome na caixa **Nome de exibição**. Opcionalmente, você pode inserir uma **Descrição**.
4. Selecione **Criar** para salvar a dimensão. Pode levar até um minuto para que você possa usar a dimensão em um [relatório personalizado](custom-reports.md) ou [segmento](segments.md). 

## <a name="edit-a-dimension"></a>Editar uma dimensão

Você pode alterar o nome e a descrição de uma dimensão. Você só pode editar dimensões criadas pelo usuário, mas não pode editar dimensões do sistema.


1. Acesse **Dados** > **Dimensões**.
1. Selecione a dimensão que você deseja excluir.
1. No painel **Editar dimensão**, atualize a dimensão.
1. Selecione **Aplicar** para salvar suas alterações.

## <a name="delete-a-dimension"></a>Excluir uma dimensão

Você pode excluir somente as dimensões criadas pelo usuário, mas não pode remover as dimensões do sistema.

A exclusão de uma dimensão é permanente. Os relatórios e segmentos que usam uma dimensão excluída não funcionarão mais. 

1. Acesse **Dados** > **Dimensões**.
1. Selecione a dimensão que você deseja excluir.
1. No painel **Editar dimensão**, selecione **Excluir dimensão**.

   :::image type="content" source="media/delete-dimension.png" alt-text="Exclua uma dimensão de um evento.":::

1. Insira **CONFIRMAR EXCLUSÃO** (em maiúsculas) para confirmar a exclusão. 
1. Selecione **Excluir**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
