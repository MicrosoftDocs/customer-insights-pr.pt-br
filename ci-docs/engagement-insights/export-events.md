---
title: Exportar eventos refinados
description: Como exportar eventos refinados e eventos de base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: faa0c3afb08d1c0282b2164ed914637ce9aad88117af37ba44fdb81e7610e574
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032371"
---
# <a name="export-events"></a>Exportar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um evento representa o comportamento do usuário. Ele registra quando um usuário exibe uma página (evento de exibição) ou interage com o conteúdo (evento de ação). Quando você pode decidir quais propriedades dos dados deseja exibir em um relatório, esta exibição virtual dos dados é chamada de *evento refinado*. 

- Você pode exportar eventos e eventos refinados para armazenamento externo. 
- As exportações são um fluxo de dados direto. Você não pode reabastecer o fluxo. 
- As exportações têm esquemas fixos. Se você adicionar propriedades personalizadas a um evento, elas não serão incluídas. Você precisará criar uma nova exportação.

## <a name="prerequisites"></a>Pré-requisitos

Antes de configurar uma exportação, você precisa ter acesso e uma assinatura ativa para o portal do Azure. Você precisará das informações da conta de armazenamento durante o processo de exportação. 

### <a name="create-an-azure-data-lake-storage-gen-2-accounts"></a>Crie uma conta do Azure Data Lake Storage Gen 2

1. Entre no portal do Azure e [crie uma nova conta de armazenamento](/azure/storage/common/storage-account-create). 

1. Certifique-se de habilitar **Namespace hierárquico** na guia **Avançado**. 

   :::image type="content" source="media/enable-hierarchical-namespace.png" alt-text="Habilite o namespace hierárquico na guia avançada.":::

1. Depois de implantado, vá para a conta de armazenamento recém-criada. No painel de navegação, selecione **Configurações** > **Chaves de acesso**. 

1. Copie o **Nome da conta** e **Chave** para usá-los ao criar uma nova exportação.
   :::image type="content" source="media/storage-account-access-keys.png" alt-text="Chaves de acesso em uma conta de armazenamento.":::

## <a name="export-events"></a>Exportar eventos

Há duas formas de exportar eventos: 
- Vá para **Dados** > **Exportações** e selecione **Nova exportação**.
- Acesse **Dados** > **Eventos**, selecione **Mais [...]** ao lado do evento que deseja exportar e selecione **Exportar** no menu suspenso. 

Você é guiado pelas etapas para criar uma exportação:

1. Forneça um **Nome de exportação**.

1. Na lista suspensa **Seleção de eventos**, escolha os eventos base e eventos refinados a serem incluídos na exportação. 

1. Em **Estrutura de arquivo**, selecione a cadência para criar novos arquivos no armazenamento de destino. Os eventos são exportados continuamente à medida que chegam.

1. Selecione o formato para sua exportação. Você pode escolher entre os formatos de **Modelo de Dados Comum**, **CSV** e **JSON**. Para usar a exportação com outros aplicativos do Dynamics 365, recomendamos o uso do formato de Modelo de Dados Comum.

1. Na etapa **Escolher destino**, especifique o local do Azure Data Lake Storage Gen 2.
    1. **Nome da conta ADLS Gen 2** é o nome da conta de armazenamento na qual você deseja salvar a exportação. 
    1. **Caminho da pasta** define onde a exportação deve ser armazenada no sistema de arquivos e na estrutura de diretórios da conta de armazenamento.
    1. **Chave compartilhada** está disponível no portal do Azure para a conta de armazenamento.

1. Revise e confirme suas seleções.

## <a name="view-and-manage-exports"></a>Exibir e gerenciar exportações

Depois de configurar uma exportação, vá para **Dados** > **Exportações** para vê-la. Selecione **Mais [...]** para qualquer exportação existente, para editá-la ou excluí-la.


[!INCLUDE[footer-include](../includes/footer-banner.md)]