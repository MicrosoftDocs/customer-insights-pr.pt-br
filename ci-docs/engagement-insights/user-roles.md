---
title: Funções e permissões
description: Visão geral das funções e permissões disponíveis para membros do espaço de trabalho.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 07/06/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: 6d7f4db4a130fc15a69b380c892538db5492d96d8e13f3c070c6a6b9bd098371
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7036679"
---
# <a name="roles-and-permissions"></a>Funções e permissões

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um espaço de trabalho é como você armazena e gerencia eventos e relatórios. Um membro é um usuário que pode acessar um espaço de trabalho. Você pode atribuir membros ao espaço de trabalho e definir suas funções e permissões. As funções Administrador gerenciam espaços de trabalho e ambientes e configuram insights de participação para outros usuários. As funções Colaborador são voltadas para analistas que não precisam configurar insights de participação, mas desejam criar seus próprios relatórios, funis ou segmentos.

## <a name="permissions"></a>Permissões
  
O gráfico a seguir identifica as permissões de cada função. 

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
