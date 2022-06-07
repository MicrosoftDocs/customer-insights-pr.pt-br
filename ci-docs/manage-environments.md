---
title: Como gerenciar ambientes
description: Saiba como gerenciar ambientes existentes do Customer Insights como administrador.
ms.date: 05/31/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: 62a5856edac5e66e5e42c93313d78fa6826469b3
ms.sourcegitcommit: f5af5613afd9c3f2f0695e2d62d225f0b504f033
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "8833478"
---
# <a name="how-to-manage-environments"></a>Como gerenciar ambientes

Administradores [criam](create-environment.md) e gerenciam ambientes. Eles podem alterar algumas configurações em ambientes existentes. Configurações de empresa, tipo, região, opção de armazenamento e Dataverse são corrigidas após a criação do ambiente. Se você quiser alterar essas configurações, redefina o ambiente ou crie um novo.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Você pode editar alguns dos detalhes dos ambientes existentes.

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ícone **Editar**.

   :::image type="content" source="media/edit-environment.png" alt-text="Ícone para editar as configurações do ambiente.":::

1. Na caixa **Editar ambiente**, você pode atualizar as configurações de ambiente.

Para começar com um novo ambiente, leia [Criar um novo ambiente](create-environment.md).

## <a name="change-the-owner-of-an-environment"></a>Altere o proprietário de um ambiente

Diversos usuários podem ter permissões de administrador, mas apenas um usuário é o proprietário de um ambiente. Por padrão, é o administrador que cria um ambiente inicialmente. Como administrador de um ambiente, você pode atribuir a propriedade a outro usuário com permissões de administrador.

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ícone **Editar**.

1. Na caixa **Editar ambiente**, vá para a etapa **Informações básicas**.

1. No campo **Alterar proprietário do ambiente**, selecione o novo proprietário do ambiente.  

1. Selecione **Revisar e finalizar** e **Atualizar** para aplicar as alterações.

## <a name="claim-ownership-of-an-environment"></a>Reivindicar a propriedade de um ambiente

Se a conta do usuário proprietário for excluída ou suspensa, o ambiente não terá um proprietário. Todos os usuários administradores podem reivindicar a propriedade e se tornar o novo proprietário. Ele podem continuar sendo proprietário do ambiente ou [alterar a propriedade para outro administrador](#change-the-owner-of-an-environment).

Para reivindicar a propriedade, selecione o botão **Assumir propriedade** que aparece na parte superior de cada página no Customer Insights quando o proprietário original deixou a organização.

## <a name="reset-an-existing-environment-preview"></a>Redefinir um ambiente existente (versão preliminar)

Como proprietária do ambiente, você pode redefinir um ambiente a um estado vazio, caso queira apenas apagar todas as configurações e remover os dados ingeridos.

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ambiente que deseja redefinir e selecione as reticências verticais (&vellip;).

1. Escolha a opção **Redefinir**.

   :::image type="content" source="media/reset-environment.png" alt-text="Controle para redefinir um ambiente.":::

1. Escolha se deseja redefinir todo o ambiente, tudo exceto as fontes de dados ou qualquer coisa que esteja configurada no Unified customer profile.

1. Para confirmar, insira o nome do ambiente e selecione **Restaurar**.

## <a name="delete-an-existing-environment"></a>Excluir um ambiente existente

Como proprietário de um ambiente, você pode excluir um ambiente que administra.

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ambiente que deseja redefinir e selecione as reticências verticais (&vellip;). 

1. Escolha a opção **Excluir**.

   :::image type="content" source="media/delete-environment.png" alt-text="Controle para excluir o ambiente.":::

1. Para confirmar a exclusão, insira o nome do ambiente e selecione **Excluir**.

> [!IMPORTANT]
> A exclusão de um ambiente não remove a conexão com um ambiente do Dataverse. Se você planeja conectar o mesmo ambiente do Dataverse com um novo ambiente do Customer Insights no futuro, é necessário remover essa conexão  Saiba como [remover uma conexão existente com um ambiente do Dataverse](customer-insights-dataverse.md#remove-an-existing-connection-to-a-dataverse-environment).

[!INCLUDE [footer-include](includes/footer-banner.md)]
