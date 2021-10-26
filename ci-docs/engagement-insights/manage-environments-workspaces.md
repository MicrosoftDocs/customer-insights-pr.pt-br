---
title: Gerenciar espaços de trabalho e ambientes
description: Como criar, renomear e excluir espaços de trabalho e ambientes.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 279af24358a1d6ea2b4cc75d5496042af73a7cae
ms.sourcegitcommit: 53b133a716c73cb71e8bcbedc6273cec70ceba6c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/15/2021
ms.locfileid: "7645432"
---
# <a name="manage-environments-and-workspaces"></a>Gerenciar ambientes e espaços de trabalho

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Visão Geral

Este tópico discute como gerenciar áreas de trabalho e ambientes, uma vez que já tenham sido criados. 

- Um *espaço de trabalho* é um espaço para armazenar e gerenciar eventos e relatórios. É onde você pode ver as atividades do usuário em tempo real. Ao criar um espaço de trabalho, você seleciona o tipo de dados a serem enviados para ele. No momento, há suporte para dados Web e aplicativos móveis. Para mais informações, consulte [Criar um espaço de trabalho e adicionar membros](create-workspace.md).

- Um *ambiente* é um espaço onde você gerencia seus espaços de trabalho e conexões. Para obter mais informações, consulte [Criar um novo ambiente](create-new-environment.md).

## <a name="manage-an-existing-workspace"></a>Gerenciar um espaço de trabalho existente

Você pode manter vários espaços de trabalho simultaneamente em um ambiente. Sua [função](user-roles.md) determina como você pode trabalhar neles. 

 - Você precisa ser um administrador de ambiente ou de espaço de trabalho para gerenciar o espaço de trabalho.
 - Como administrador do espaço de trabalho, você pode renomear ou excluir os atuais espaços de trabalho. 

:::image type="content" source="media/workspace-edit.png" alt-text="Central de administração do espaço de trabalho.":::

### <a name="edit-a-workspace-name"></a>Editar o nome de um espaço de trabalho

1. Vá para **Administração** > **Espaço de trabalho** e selecione **Configurações**.

1. Na caixa **Nome do espaço de trabalho**, insira um novo nome.

1. Selecione **Salvar** para aplicar suas alterações.

### <a name="delete-a-workspace"></a>Excluir um espaço de trabalho

A exclusão de um espaço de trabalho removerá permanentemente todo o seu conteúdo, dados, configurações e permissões. Essa ação não pode ser desfeita.

1. Vá para **Administração** > **Espaço de trabalho** e selecione **Configurações**.

1. Selecione **Excluir espaço de trabalho**. 

1. Na caixa de diálogo **Excluir espaço de trabalho**, digite **CONFIRMAR EXCLUIR** em maiúsculas. 

1. Selecione **Excluir** para excluir permanentemente o espaço de trabalho.

### <a name="manage-workspace-members"></a>Gerenciar membros de um espaço de trabalho

1. Vá para **Administração** > **Espaço de trabalho** e selecione **Membros**.

1. Selecione **Adicionar membros** para conceder acesso e [atribuir funções](user-roles.md). Atualmente, apenas **Administrador do espaço de trabalho** está disponível.

1. Selecione **Adicionar membros** para adicioná-los ao seu espaço de trabalho.

## <a name="manage-an-existing-environment"></a>Gerenciar um ambiente existente

Como administrador de ambiente, você pode acessar um ambiente no painel de navegação esquerdo. Você pode definir as configurações do ambiente, outros administradores de ambiente e espaços de trabalho. Selecione as guias para mover-se entre as diferentes áreas do centro de administração.

:::image type="content" source="media/environment-edit.png" alt-text="Centro de administração de ambientes.":::

### <a name="rename-an-environment"></a>Renomear um ambiente

1. Vá para **Administração** > **Ambiente** e selecione **Configurações**.

1. Atualize o **Nome do ambiente** e selecione **Salvar** para aplicar suas alterações.

### <a name="manage-environment-members"></a>Gerenciar membros de um ambiente

1. Vá para **Administração** > **Ambiente** e selecione **Membros**.

1. Selecione **Adicionar membros** para atualizar membros e [atribuir funções](user-roles.md). Atualmente, apenas **Administrador do ambiente** está disponível.

1. Selecione **Adicionar membros** para adicioná-los ao seu ambiente.

### <a name="delete-an-environment"></a>Excluir um ambiente

Os administradores do ambiente podem excluir ambientes. Antes de excluir um ambiente, você deve remover todos os espaços de trabalho associados a ele.

1. Vá para **Administração** > **Ambiente** e selecione **Configurações**.

1. Selecione **Excluir ambiente**. 

1. Na caixa de diálogo **Excluir espaço de trabalho**, digite **CONFIRMAR EXCLUIR** em maiúsculas. 

1. Selecione **Excluir** para excluir o ambiente de forma permanente.

## <a name="manage-connections"></a>Gerenciar conexões

Estabelecer conexões com os insights de público-alvo permite que você veja relatórios nos insights de interação com base em perfis de clientes unificados. 

Para obter mais informações, consulte [Criar um link entre insights do público-alvo e insights de participação](integrate-audience-insights-engagement-insights.md).

## <a name="manage-personal-data"></a>Gerenciar dados pessoais

Para proteger os dados pessoais do seu cliente, você pode excluir ou exportar os dados identificáveis do usuário final.

Para obter mais informações, consulte [Excluir e exportar dados de eventos que contenham informações pessoais](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
