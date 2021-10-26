---
title: Exportar eventos refinados
description: Como exportar eventos refinados e eventos de base.
ms.reviewer: mhart
ms.author: jusali
author: jusali
ms.date: 10/01/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7881f8f63134170a7f76e3c75dcfc5fa8930754b
ms.sourcegitcommit: 693458e13e4b4d94b6205093559912f6a4dc4a1c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/06/2021
ms.locfileid: "7606173"
---
# <a name="export-events"></a>Exportar eventos

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um evento representa o comportamento do usuário. Ele registra quando um usuário exibe uma página (evento de exibição) ou interage com o conteúdo (evento de ação). Quando você pode decidir quais propriedades dos dados deseja exibir em um relatório, esta exibição virtual dos dados é chamada de *evento refinado*. Para obter mais informações, consulte [Criar e modificar eventos](refined-events.md).

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

Existem duas maneiras de exibir o diálogo **Exportar eventos**: 
- Vá para **Dados** > **Exportações** e selecione **Nova exportação**.
- Acesse **Dados** > **Eventos**, selecione **Mais [...]** ao lado do evento que deseja exportar e selecione **Exportar** no menu suspenso. 

:::image type="content" source="media/new-export.png" alt-text="Criar uma nova exportação.":::

Você é guiado pelas etapas para criar uma exportação:

1. Forneça um **Nome de exportação** e, em seguida, selecione **Próximo**.

1. Na lista suspensa **Seleção de eventos**, escolha os eventos base e eventos refinados a serem incluídos na exportação. 

1. Na seção **Estrutura de arquivo**, selecione a cadência (por hora ou diária) para criar novos arquivos no armazenamento de destino e, em seguida, selecione **Próximo**. Os eventos são exportados continuamente à medida que chegam.

1. Na caixa de diálogo **Escolha o formato**, selecione o formato para sua exportação. Escolha entre entre os formatos **Modelo de Dados Comum**, **CSV** e **JSON**. Para usar a exportação com outros aplicativos do Dynamics 365, recomendamos o formato **Modelo de Dados Comum**.

1. Na caixa de diálogo **Escolha o destino**, especifique a localização do Azure Data Lake Storage Gen 2.
    1. **Nome da conta ADLS Gen 2** é o nome da conta de armazenamento na qual você deseja salvar a exportação. 
    1. **Caminho da pasta** define onde a exportação deve ser armazenada no sistema de arquivos e na estrutura de diretórios da conta de armazenamento.
    1. **Chave compartilhada** está disponível no portal do Azure para a conta de armazenamento.

1. Reveja e confirme suas seleções para finalizar.

## <a name="view-and-manage-exports"></a>Exibir e gerenciar exportações

Depois de configurar uma exportação, vá para **Dados** > **Exportações** para vê-la. Selecione **Mais [...]** para qualquer exportação existente, para editá-la ou excluí-la.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
