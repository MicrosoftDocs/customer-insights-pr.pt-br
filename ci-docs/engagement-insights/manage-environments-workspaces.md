---
title: Gerenciar espaços de trabalho e ambientes
description: Como criar, renomear e excluir espaços de trabalho e ambientes.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 07/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: bf310b1a50ba7baac5d11d5f22ff42003fbba516efd7d165c00b59adc958da2e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034028"
---
# <a name="manage-environments-and-workspaces"></a>Gerenciar ambientes e espaços de trabalho

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

## <a name="overview"></a>Visão Geral

Um espaço de trabalho é um espaço para armazenar e gerenciar eventos e relatórios. É onde você pode ver as atividades do usuário em tempo real. Ao criar um espaço de trabalho, você seleciona o tipo de dados a serem enviados para ele. No momento, há suporte para dados Web e aplicativos móveis.

Um ambiente é um espaço onde você gerencia seus espaços de trabalho e conexões. A forma como você usa os ambientes depende da sua organização e do seu caso de uso. Por exemplo, você pode criar:

-   Um único ambiente.
-   Ambientes separados para teste e produção.
-   Ambientes separados para equipes ou departamentos específicos na sua organização que contenham eventos relevantes para cada público-alvo.
-   Ambientes separados para filiais globais diferentes da empresa.
-   Conexões com o recurso de insights de público-alvo do Customer Insights.

## <a name="choose-an-environment-and-create-a-workspace"></a>Escolher um ambiente e criar um espaço de trabalho 

Todo espaço de trabalho precisa estar em um ambiente. Você pode selecionar um ambiente pré-existente ou criar um novo ao criar um espaço de trabalho. Em seguida, você pode optar por adicionar membros ao espaço de trabalho e começar a coletar dados.

**Para criar seu primeiro espaço de trabalho**

1. Nos insights de interação, selecione **Novo** no alternador de espaço de trabalho. 

   :::image type="content" source="media/New-workspace.png" alt-text="Seletor de espaços de trabalho na página do Customer Insights.":::

1. Escolha um ambiente na lista ou selecione **Criar novo ambiente**.

1. Insira um nome em **Nome do espaço de trabalho**. 

1. Selecione o tipo de ambiente que deseja criar, dependendo se você quer medir o que acontece em um site ou aplicativo móvel. 

1. Você pode adicionar membros e atribuir seu nível de permissão a partir da lista **Função**. Em seguida, selecione **Concluir** para criar o espaço de trabalho ou **Avançar** para instalar o código. 

1. Instale o snippet de código para começar a receber dados e selecione **Concluído**. 

## <a name="manage-a-workspace"></a>Gerenciar um espaço de trabalho

Você pode manter vários espaços de trabalho simultaneamente em um ambiente. Sua [função](user-roles.md) determina como você pode trabalhar neles. 

 - Você precisa ser um administrador de ambiente ou de espaço de trabalho para gerenciar o espaço de trabalho.
 - Como administrador do espaço de trabalho, você pode renomear ou excluir os atuais espaços de trabalho. 

### <a name="edit-a-workspace-name"></a>Editar o nome de um espaço de trabalho

1. Vá para **Administração** > **Espaço de trabalho** e selecione **Configurações**.

1. Na caixa **Nome do espaço de trabalho**, insira um novo nome.

1. Selecione **Salvar** para aplicar suas alterações.

### <a name="delete-a-workspace"></a>Excluir um espaço de trabalho

A exclusão de um espaço de trabalho removerá permanentemente todo o seu conteúdo, dados, configurações e permissões. Essa ação não pode ser desfeita.

1. Vá para **Administração** > **Espaço de trabalho** e selecione **Configurações**.

1. Selecione **Excluir espaço de trabalho**. 

1. Na caixa de diálogo **Excluir espaço de trabalho**, insira **CONFIRMAR EXCLUSÃO**. 

1. Selecione **Excluir** para excluir permanentemente o espaço de trabalho.

### <a name="manage-workspace-members"></a>Gerenciar membros de um espaço de trabalho

1. Vá para **Administração** > **Espaço de trabalho** e selecione **Membros**.

1. Selecione **Adicionar membros** para conceder acesso e [atribuir funções](user-roles.md). Atualmente, apenas **Administrador do espaço de trabalho** está disponível.

1. Se você configurar uma [conexão com os insights de público-alvo](configure-connections.md), poderá selecionar **Permitir acesso a dados de perfis** para permitir que o membro veja relatórios baseados em [perfis de usuários](profile-reports.md).

1. Selecione **Adicionar membros** para adicioná-los ao seu espaço de trabalho.

## <a name="manage-an-environment"></a>Gerenciamento de ambiente

Como Administrador de ambiente, você pode acessar um ambiente no painel de navegação esquerdo. Você pode definir configurações do ambiente, outros Administradores de ambiente, espaços de trabalho e [conexões com os insights de público-alvo](configure-connections.md). Selecione as guias para mover-se entre as diferentes áreas do centro de administração.

:::image type="content" source="media/New-environment.png" alt-text="Centro de administração de ambientes.":::

### <a name="create-an-environment"></a>Criar um ambiente

1. No seletor de espaços de trabalho, selecione **Criar+**.

1. Na experiência guiada, abra o menu suspenso **Ambiente** e selecione **Criar novo ambiente**. 

1. Forneça um **Nome de ambiente**.

   :::image type="content" source="media/create-environment.png" alt-text="Entre na experiência guiada para especificar os detalhes do ambiente.":::

1. Escolha **Região** e selecione **Avançar**. 

1. Forneça um nome de espaço de trabalho e escolha o tipo de espaço de trabalho que deseja criar. 

1.  Ou então, adicione os membros e copie o trecho de código para concluir o processo de criação.

### <a name="rename-an-environment"></a>Renomear um ambiente

1. Vá para **Administração** > **Ambiente** e selecione **Configurações**.

1. Atualize o **Nome do ambiente** e selecione **Salvar** para aplicar suas alterações.

### <a name="manage-environment-members"></a>Gerenciar membros de um ambiente

1. Vá para **Administração** > **Ambiente** e selecione **Membros**.

1. Selecione **Adicionar membros** para atualizar membros e [atribuir funções](user-roles.md). Atualmente, apenas **Administrador do ambiente** está disponível.

1. Se você configurar uma [conexão com os insights de público-alvo](configure-connections.md), poderá selecionar **Permitir acesso a dados de perfis** para permitir que o membro veja relatórios baseados em [perfis de usuários](profile-reports.md).

1. Selecione **Adicionar membros** para adicioná-los ao seu ambiente.

### <a name="delete-an-environment"></a>Excluir um ambiente

Os administradores do ambiente podem excluir ambientes. Antes de excluir um ambiente, você deve remover todos os espaços de trabalho associados a ele.

1. Vá para **Administração** > **Ambiente** e selecione **Configurações**.

1. Selecione **Excluir ambiente**. 

1. Na caixa de diálogo **Excluir espaço de trabalho**, insira **CONFIRMAR EXCLUSÃO**. 

1. Selecione **Excluir** para excluir o ambiente de forma permanente.

## <a name="manage-connections"></a>Gerenciar conexões

Estabelecer conexões com os insights de público-alvo permite que você veja relatórios nos insights de interação com base em perfis de clientes unificados. 

Para obter mais informações, consulte [Configurar conexões](configure-connections.md).

## <a name="manage-personal-data"></a>Gerenciar dados pessoais

Para proteger os dados pessoais do seu cliente, você pode excluir ou exportar os dados identificáveis do usuário final.

Para obter mais informações, consulte [Excluir e exportar dados de eventos que contenham informações pessoais](delete-export-personal-data.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
