---
title: Atribuir permissões de usuário
description: Saiba mais sobre permissões e funções de usuário.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-permissions
- ci-system-security
- customerInsights
ms.openlocfilehash: a59a672b6f7e1e67c2162ea14bb9860df0d551aa
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245405"
---
# <a name="assign-user-permissions"></a>Atribuir permissões de usuário

O acesso ao Customer Insights é restrito a usuários em sua organização que são adicionados ao aplicativo por um administrador. O administrador pode adicionar, editar ou remover usuários. Um usuário pode ser um único usuário, um grupo ou um aplicativo. Existem três tipos de funções que um usuário pode ter:

## <a name="viewer"></a>Espectador

- Explore insights e segmentos nas páginas **Página Inicial** e **Segmentos**.
- Pesquise e filtre perfis do cliente usando a página **Clientes**. Os campos devem ser pesquisáveis.
- Exiba e explore a página **Enriquecimento**.
- Explorar e exportar entidades usando a página **Entidades**.
- Exiba o status dos processos do sistema usando a página **Sistema**.
- Exiba exportações na página **Exportações**.
- Instale e use o painel **Power BI Customer Insights**.

## <a name="contributor"></a>Colaborador

- Todas as permissões disponíveis para o Visualizador.
- Carregue e transforme dados usando a página **Fontes de dados**.
- Conclua a **Unificação de Dados** que resulta na entidade do perfil unificado de cliente.
- Defina **Relacionamentos** e **Atividades**.
- Crie segmentos usando a página **Segmentos**.
- Crie medidas usando a página **Medidas**.
- Gerencie a configuração e enriqueça os perfis de cliente na página **Enriquecimento** (somente para os primeiros enriquecimentos da parte).
- Gerencie e crie exportações com base em [conexões compartilhadas com colaboradores](connections.md#allow-contributors-to-use-a-connection-for-exports).

## <a name="admin"></a>Administrador

- Todas as permissões disponíveis para o Colaborador.
- Altere as configurações na página **Sistema**, incluindo o idioma de trabalho, as agendas de atualização de seus processos do sistema e a exportação de logs de diagnóstico.
- Altere as configurações na página **Segurança**, incluindo usuários, chaves de API, links privados e cofre de chaves.
- Configure as definições de filtro e pesquisa para a página Clientes usando a página **Índice de filtro e pesquisa** (accessível pela página **Clientes**).
- Gerencie conexões e as permita para outras funções de usuário na página **Conexões**.
- Gerencie a configuração e enriqueça os perfis de cliente na página **Enriquecimento** (para todos os enriquecimentos).
- Gerencie e crie exportações na página **Exportações**.
- Instale e use o **Complemento do Cartão do Cliente**.
- Adicione e use o **conector do Power Apps**.
- Habilite o uso de [APIs do Customer Insights](apis.md).
- [Atribuir propriedade do ambiente](manage-environments.md#change-the-owner-of-an-environment) para outro administrador.

## <a name="admin-owner"></a>Administrador (proprietário)

- Todas as permissões disponíveis para o administrador.
- [Redefinir e excluir](manage-environments.md#reset-an-existing-environment-preview) o ambiente.

## <a name="add-users"></a>Adicionar usuários

1. Acesse **Administrador** > **Segurança** e selecione a guia **Usuários**.

1. Selecione **Adicionar usuários** para abrir o painel **Adicionar/Editar permissões**.

1. Use o campo **Pesquisar** para encontrar o usuário ou grupo do Azure Active Directory que deseja adicionar. Selecione uma **Função** para atribuir a esse usuário ou grupo.

1. Selecione **Salvar**. O ambiente atual será compartilhado automaticamente com o usuário ou os membros do grupo. Os usuários podem acessar o aplicativo Customer Insights e trabalhar de acordo com sua função especificada.

## <a name="view-current-permissions"></a>Ver as permissões atuais

Acesse **Administrador** > **Segurança** e selecione a guia **Usuários** para exibir a lista de usuários ativos e suas atribuições de função. Você pode classificar a lista de usuários por qualquer coluna ou usar a caixa de pesquisa para encontrar um usuário específico.

## <a name="manage-current-users"></a>Gerenciar usuários atuais

Acesse **Administrador** > **Segurança** e selecione a guia **Usuários**. Você pode classificar a lista de usuários por qualquer coluna ou usar a caixa de pesquisa para encontrar o usuário que deseja gerenciar.

Selecione um usuário para exibir as ações disponíveis.

- **Editar** para editar a função do usuário no Customer Insights. Selecione **Salvar** para confirmar a alteração.
- **Remover** para remover o usuário do acesso ao Customer Insights. Selecione **Excluir** para confirmar a exclusão.

[!INCLUDE [footer-include](includes/footer-banner.md)]
