---
title: Funções e permissões
description: Visão geral das funções e permissões disponíveis para membros do espaço de trabalho.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: ccc6a1b87b4cc28701e276b6e35432356e7647c4
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8227525"
---
# <a name="roles-and-permissions"></a>Funções e permissões

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um espaço de trabalho é onde você armazena e gerencia eventos e relatórios. Para mais informações, consulte [Criar um espaço de trabalho e adicionar membros](create-workspace.md). 

Um espaço de trabalho pode incluir as seguintes funções e permissões:

- *Membro*: usuários que podem acessar um espaço de trabalho. Você pode atribuir membros ao espaço de trabalho e definir suas funções e permissões. 
- *Administrador*: administram espaços de trabalho e ambientes de trabalho e configuram insights de engajamento para outros usuários. 
- *Contribuinte*: voltados para analistas que não precisam configurar insights de engajamento mas querem criar seus próprios relatórios, funis ou segmentos.

## <a name="permissions"></a>Permissões
  
A tabela a seguir identifica as permissões para cada função. 

| Permissão | Administrador do ambiente | Administrador do espaço de trabalho | Colaborador do ambiente | Colaborador do espaço de trabalho | 
|--|--|--|--|--|
| Criar ambientes (o criador se torna automaticamente o administrador do ambiente) | X* | X* | X* | X* |  
| Configurar o ambiente (membros do ambiente, excluir ambiente) | X |  |  |  |  
| Criar espaços de trabalho | X |  |  |  |  
| Configurar espaços de trabalho (membros do espaço de trabalho, excluir espaço de trabalho) | X | X |  |  |  
| Configurar eventos e eventos refinados | X | X | |  |  
| Exibir eventos do espaço de trabalho e eventos refinados | X | X | |  |  
| Exibir recursos do espaço de trabalho (relatórios, segmentos e métricas)| X | X | X | X |  
| Criar relatórios personalizados e funis | X | X | X | X |  
| Crie métricas e dimensões básicas| X | X |  |  |  
| Criar segmentos| X | X | X | X |  

*Só pode criar ambientes de avaliação em versão preliminar. 

## <a name="add-members"></a>Adicionar membros

Você pode adicionar e remover membros de espaços de trabalho e ambientes. Para obter mais informações, consulte [Ambientes e espaços de trabalho](manage-environments-workspaces.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
