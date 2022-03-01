---
title: Introdução ao produto com início rápido
description: Tela de apresentação para configurar o recurso de insights de interação.
author: mochimochi016
ms.reviewer: mhart
ms.author: jefhar
ms.date: 11/05/2020
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: eebe51d343f6afbed52a66c52ab6a60eb5cd410367fb2e4409eb8679f357c91e
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7033893"
---
# <a name="first-run-experience"></a>Tela de apresentação

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Os insights de interação, um recurso do Dynamics 365 Customer Insights, permitem coletar e avaliar o comportamento dos clientes no seu site. Este artigo explica como se inscrever nos insights de interação, configurar um espaço de trabalho, adicionar membros a ele e fazer alterações.

## <a name="sign-up-for-a-demo-of-engagement-insights"></a>Inscrever-se em uma demonstração dos insights de interação

Você deve ter uma conta de usuário ativa do Microsoft Azure Active Directory. 

1. Abra o site dos [insights de interação](https://pi.dynamics.com/). 

1. Entre com sua conta corporativa ou de estudante.

1. Selecione sua região e use a caixa de seleção para indicar se aceita receber atualizações e ofertas por email.

1. Reveja os **Termos de Uso de insights de interação (versão preliminar)** e **Declaração de Privacidade** e, em seguida, selecione **Explore a demonstração** para aceitá-los.

1. Explore o produto usando um conjunto de dados de exemplo. 

## <a name="set-up-your-first-workspace-in-engagement-insights"></a>Configurar seu primeiro espaço de trabalho nos insights de interação

Um espaço de trabalho é como você armazena e gerencia eventos e relatórios.

Para criar seu primeiro espaço de trabalho

1. Nos insights de interação, selecione **Conectar seus dados** para iniciar o assistente. 

:::image type="content" source="media/banner.png" alt-text="Página do Customer Insights com o botão Conectar seus dados.":::

2. Escolha o tipo de atividade que você deseja avaliar em um novo espaço de trabalho. Atualmente, apenas **Atividades do site** está disponível. **Atividades do aplicativo** e **Atividades do dispositivo** estarão disponíveis em versões futuras.

1. Selecione **Avançar** para confirmar e criar o espaço de trabalho.

1. Adicione um trecho de código ao seu site para começar a receber dados nos insights de interação. Você pode implementar isso imediatamente ou compartilhar o código e as instruções com o administrador do seu site. Para encontrar o trecho de código mais tarde, vá para **Administração** > **Espaço de trabalho** > **Guia de instalação**.

   > [!IMPORTANT]
   > Os dados não serão exibidos no espaço de trabalho até que o código tenha sido implementado no seu site.

1. Selecione **Concluído** para abrir seu novo espaço de trabalho. 

## <a name="add-members-to-an-existing-workspace"></a>Adicionar membros a um espaço de trabalho existente

Por padrão, apenas a pessoa que criou o espaço de trabalho tem acesso a ele. Você pode adicionar outros usuários da sua organização a um espaço de trabalho existente a qualquer momento.

:::image type="content" source="media/add-members.png" alt-text="Página Membros com texto explicativo no botão Adicionar Membros.":::

1. Vá para **Administração** > **Espaço de trabalho** > **Membros**.

2. Selecione **Adicionar membros**. Use a caixa **Membros** para adicionar outras pessoas na sua organização. Você pode adicionar vários membros de uma vez.

3. Selecione uma **Função** para atribuir aos novos membros. Atualmente, **Administrador do espaço de trabalho** é a única seleção disponível. Outras funções serão adicionadas em versões futuras.

4. Selecione **Adicionar membros** para confirmar.

Para remover membros de um espaço de trabalho, selecione **...** ao lado do nome deles na página **Membros** e selecione **Excluir** no menu suspenso.

## <a name="edit-a-workspace"></a>Editar um espaço de trabalho

Você pode editar os detalhes dos espaços de trabalho existentes a qualquer momento.

:::image type="content" source="media/change-workspace-settings.png" alt-text="Página de configurações do espaço de trabalho com texto explicativo no nome e na descrição do espaço de trabalho.":::

1. Vá para **Administração** > **Espaço de trabalho** > **Configurações**.

1. Altere o **Nome** do seu espaço de trabalho.

1. Selecione **Salvar** para aplicar suas alterações.

## <a name="add-another-new-workspace"></a>Adicionar outro espaço de trabalho

:::image type="content" source="media/workspace-switcher.png" alt-text="Página do Customer Insights com texto explicativo no painel de navegação e na descrição.":::

Você pode criar espaços de trabalho adicionais para classificar seus dados.

1. No seletor de espaço de trabalho, selecione **Novo espaço de trabalho**.

1. Insira um **Nome** e uma **Descrição** opcional.

1. Selecione **Criar**.

## <a name="switch-between-workspaces"></a>Alternar entre espaços de trabalho

Para alternar entre os espaços de trabalho, selecione o alternador de espaço de trabalho. Você também pode criar um novo espaço de trabalho ou selecionar **Exemplo da Web** para ver relatórios e experimentar recursos usando dados de exemplo. 



[!INCLUDE[footer-include](../includes/footer-banner.md)]