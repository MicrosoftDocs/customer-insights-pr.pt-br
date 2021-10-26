---
title: Criar um novo ambiente
description: O propósito de um ambiente e como criar um novo.
author: jusali
ms.reviewer: mhart
ms.author: jusali
ms.date: 10/04/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 5e301b4ff0a7586fb143b154b773791b3bd645b7
ms.sourcegitcommit: 37182127b93b90846cc91fbeb26dd7a18cf5610a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/18/2021
ms.locfileid: "7648103"
---
# <a name="create-a-new-environment"></a>Criar um novo ambiente 

## <a name="overview"></a>Visão Geral

Um ambiente é um espaço onde você gerencia seus espaços de trabalho e conexões. A forma como você usa os ambientes depende da sua organização e do seu caso de uso. Por exemplo, você pode criar:

- Um único ambiente.
- Ambientes separados para teste e produção.
- Ambientes separados para equipes ou departamentos específicos na sua organização que contenham eventos relevantes para cada público-alvo.
- Ambientes separados para filiais globais diferentes da empresa.
- Conexões com o recurso de insights de público-alvo do Customer Insights.

## <a name="create-a-new-environment"></a>Criar um novo ambiente

1. No lado direito do banner principal, selecione o seletor de ambiente, e então **+Novo**.

   :::image type="content" source="media/environment-picker.png" alt-text="Selecione o seletor de ambientes.":::

1. No painel **Configuração**, digite um **Nome de ambiente**.

1. Escolha o **Tipo** de conta, dependendo do seu tipo de painel.

1. Escolha **Região** e selecione **Avançar**. 

1. Digite um **Nome do espaço de trabalho**, que permite coletar dados para sites ou aplicativos específicos. Para obter mais informações, consulte [Criar um espaço de trabalho](create-workspace.md).

1. Escolha o **Tipo de espaço de trabalho** (Web ou móvel) que você deseja criar. 

1. Selecione **Exibir configurações avançadas** para ativar ou desativar essas configurações opcionais:

   - Alterne **Desconhecido para conhecido** como "habilitado" para associar eventos da web a usuários que se autenticaram anteriormente. Para mais informações, consulte [Reconhecer eventos da web de visitantes autenticados anteriormente](unknown-to-known.md)
   - Alterne **Filtrar tráfego de bot** para "habilitado" para remover o tráfego da web por bots para este espaço de trabalho. 

1. Selecione **Concluído** quando terminar. 

1. Instale o trecho do código para começar a receber dados e selecione **Finalizar** para criar o espaço de trabalho. Para obter mais informações, consulte [Visão geral dos recursos de desenvolvedor](developer-resources.md).

> [!NOTE]
> Agora você pode adicionar membros e atribuir seu nível de permissão a partir da lista **Função**. Para obter mais informações, consulte [Funções e permissões](user-roles.md). 

Para obter mais informações, consulte [Gerenciar ambientes e espaços de trabalho](manage-environments-workspaces.md).

## <a name="work-with-your-new-environment"></a>Trabalhe com seu novo ambiente

- [Crie um espaço de trabalho](../engagement-insights/create-workspace.md) e adicione membros.
- [Adicione o código ao seu site](../engagement-insights/instrument-website.md) ou [aplicativo móvel](../engagement-insights/developer-resources.md#capture-events-from-mobile-apps).
- Visualize um [relatório em tempo real](../engagement-insights/view-reports.md) ou crie [relatórios personalizados](../engagement-insights/custom-reports.md).
- [Crie eventos refinados](../engagement-insights/refined-events.md) para exportação.
- [Exporte os dados](../engagement-insights/export-events.md) para o Data Lake Storage.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
