---
title: Gerenciar ambientes
description: Saiba como gerenciar ambientes existentes do Customer Insights como administrador.
ms.date: 08/15/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 6d48f7088d722b27ca69cd591178651bdb6e2c23
ms.sourcegitcommit: f959c85871777e5f4eab289e91b2fd114cd72153
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2022
ms.locfileid: "9588798"
---
# <a name="manage-environments"></a>Gerenciar ambientes

Administradores [criam](create-environment.md) e gerenciam ambientes. Eles podem alterar algumas configurações em ambientes existentes. Configurações de empresa, tipo, região, opção de armazenamento e Dataverse são corrigidas após a criação do ambiente. Se você quiser alterar essas configurações, [redefina o ambiente](#reset-an-existing-environment-preview) ou [crie um novo](create-environment.md).

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Edite os detalhes de um ambiente existente, como o nome ou a configuração do ambiente padrão.

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ícone **Editar**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ícone para editar as configurações do ambiente.":::

1. No painel **Editar ambiente**, atualize as configurações do ambiente.

1. Selecione **Revisar e finalizar** e **Atualizar** para aplicar as alterações.

## <a name="change-the-owner-of-an-environment"></a>Altere o proprietário de um ambiente

Diversos usuários podem ter permissões de administrador, mas apenas um usuário é o proprietário de um ambiente. Por padrão, é o administrador que cria um ambiente inicialmente. Como administrador de um ambiente, você pode atribuir a propriedade a outro usuário com permissões de administrador.

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ícone **Editar**.

1. No painel **Editar ambiente**, vá para a etapa **Informações básicas**.

1. No campo **Alterar proprietário do ambiente**, selecione o novo proprietário do ambiente.  

1. Selecione **Revisar e finalizar** e **Atualizar** para aplicar as alterações.

## <a name="claim-ownership-of-an-environment"></a>Reivindicar a propriedade de um ambiente

Se a conta do usuário proprietário for excluída ou suspensa, o ambiente não terá um proprietário. Todos os usuários administradores podem reivindicar a propriedade e se tornar o novo proprietário. O administrador proprietário pode continuar sendo o proprietário do ambiente ou [alterar a propriedade para outro administrador](#change-the-owner-of-an-environment).

Para reivindicar a propriedade, selecione o botão **Assumir propriedade** que aparece na parte superior de cada página no Customer Insights quando o proprietário original deixou a organização.

## <a name="reset-an-existing-environment-preview"></a>Redefinir um ambiente existente (versão preliminar)

Como proprietária do ambiente, redefina um ambiente a um estado vazio, caso queira apenas apagar todas as configurações e remover os dados ingeridos.

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ambiente que deseja redefinir e selecione as reticências verticais (&vellip;).

1. Selecione **Redefinir (versão preliminar)**.

   :::image type="content" source="media/reset-environment.png" alt-text="Controle para redefinir um ambiente.":::

1. Escolha se deseja redefinir todo o ambiente, tudo exceto as fontes de dados ou qualquer coisa que esteja configurada no Unified customer profile.

1. Para confirmar, insira o nome do ambiente e selecione **Restaurar**.

## <a name="delete-an-existing-environment"></a>Excluir um ambiente existente

Como proprietário de um ambiente, você pode excluí-lo.

> [!IMPORTANT]
> A exclusão de um ambiente não remove a conexão com um ambiente do Dataverse. Se você planeja conectar o mesmo ambiente do Dataverse com um novo ambiente do Customer Insights no futuro, você deve [remover essa conexão com um ambiente do Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ambiente que deseja excluir e selecione as reticências verticais (&vellip;). 

1. Escolha **Excluir**.

   :::image type="content" source="media/delete-environment.png" alt-text="Controle para excluir o ambiente.":::

1. Para confirmar a exclusão, insira o nome do ambiente e selecione **Excluir**.

[!INCLUDE [footer-include](includes/footer-banner.md)]
