---
title: Criar um espaço de trabalho
description: O propósito de um ambiente de trabalho e como criar um novo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 76b3466afd84aa439ea55afe90ae037825884f2d
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229063"
---
# <a name="create-a-new-workspace-and-add-members"></a>Crie um novo espaço de trabalho e adicione membros

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um espaço de trabalho é como você pode exibir a atividade do usuário em tempo real para entender melhor o seu público-alvo. É onde você armazena e gerencia eventos e relatórios.

Ao criar uma área de trabalho, você seleciona o tipo de dados nos quais deseja se concentrar. Você pode adicionar outros usuários, ou membros, a um espaço de trabalho existente a qualquer momento. 

## <a name="create-a-new-workspace"></a>Criar um espaço de trabalho

O processo de criação de um espaço de trabalho inclui a configuração do *ambiente* para organizar o espaço de trabalho. Um ambiente é um espaço que pode conter um ou mais espaços de trabalho. Você pode usar um ambiente para gerenciar seus espaços de trabalho e conexões ao recurso de insights de público-alvo.

1. Selecione **+Novo** no alternador de espaço de trabalho.

   :::image type="content" source="media/new-workspace.png" alt-text="Página do Customer Insights com texto explicativo no painel de navegação e na descrição.":::

1. No painel **Espaço de trabalho**, insira um **Nome do espaço de trabalho**.

   :::image type="content" source="media/workspace-name.png" alt-text="Digite um nome de espaço de trabalho.":::

1. Escolha o tipo de plataforma (Web ou móvel) que você deseja medir.

1. Selecione **Exibir configurações avançadas** para ativar ou desativar essas configurações opcionais:

   - Alterne **Desconhecido para conhecido** como "habilitado" para associar eventos da web a usuários que se autenticaram anteriormente. Para mais informações, consulte [Reconhecer eventos da web de visitantes autenticados anteriormente](unknown-to-known.md)
   - Alterne **Filtrar tráfego de bot** para "habilitado" para remover o tráfego da web por bots para este espaço de trabalho. 

1. Selecione **Concluído** quando terminar. 

1. Instale o trecho do código para começar a receber dados e selecione **Finalizar** para criar o espaço de trabalho. Para obter mais informações, consulte [Visão geral dos recursos de desenvolvedor](developer-resources.md).

> [!NOTE]
> Agora você pode adicionar membros e atribuir seu nível de permissão a partir da lista **Função**. Para obter mais informações, consulte [Funções e permissões](user-roles.md). 

Para obter mais informações, consulte [Gerenciar ambientes e espaços de trabalho](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
