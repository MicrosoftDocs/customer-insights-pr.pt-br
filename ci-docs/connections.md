---
title: Conexões com outros serviços do Customer Insights.
description: Compartilhe dados com outros serviços.
ms.date: 04/09/2021
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 2a3175737ac95e10d75fad4a69db303b0564c6cc
ms.sourcegitcommit: b515120bebd2638f2639004422cee3cff42fbdf7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/24/2022
ms.locfileid: "8800358"
---
# <a name="connections-preview-overview"></a>Visão geral de conexões (versão preliminar)

As conexões são a chave para permitir o compartilhamento de dados do Customer Insights e com o Customer Insights. Cada conexão estabelece o compartilhamento de dados com um serviço específico. As conexões são a base para [configurar enriquecimentos de terceiros](enrichment-hub.md) e [configurar exportações](export-destinations.md). A mesma conexão pode ser usada várias vezes. Por exemplo, uma conexão com o Dynamics 365 Marketing funciona para várias exportações e uma conexão da Leadspace pode ser usada para vários enriquecimentos.

Acesse **Administração** > **Conexões** para criar e visualizar conexões.

A guia **Conexões** mostra todas as conexões ativas. A lista mostra uma linha para cada conexão.

Obtenha uma rápida visão geral, uma descrição e descubra o que você pode fazer com cada opção de extensibilidade na guia **Descobrir**.

## <a name="exports"></a>Exportações

Somente os administradores podem configurar novas conexões, mas eles podem conceder acesso aos colaboradores para usarem as conexões existentes. Os administradores controlam para onde os dados podem ir, os colaboradores definem o conteúdo e a frequência de acordo com suas necessidades. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](#allow-contributors-to-use-a-connection-for-exports).

## <a name="enrichments"></a>Enriquecimentos

Somente os administradores podem configurar novas conexões, mas as conexões criadas estão sempre disponíveis para os administradores e os colaboradores. Os administradores gerenciam credenciais e fornecem consentimento para a transferências de dados. As conexões podem então ser usadas para enriquecimentos pelos administradores e colaboradores.

## <a name="add-a-new-connection"></a>Adicionar uma nova conexão

Para adicionar conexões, você deve ter [permissões de administrador](permissions.md). Se você se conectar a outros serviços da Microsoft, presumimos que os serviços estejam na mesma organização.

1. Acesse **Administração** > **Conexões (versão preliminar)**.

1. Acesse a guia **Conexões**.

1. Selecione **Adicionar conexão** para criar uma conexão. Escolha no menu suspenso o tipo de conexão que deseja criar.

1. No painel **Configurar conexão**, forneça os detalhes necessários.
   1. O **Nome de exibição** e o tipo de conexão descrevem uma conexão. Recomendamos escolher um nome que explique a finalidade e o objetivo dessa conexão.
   1. Os campos exatos dependem do serviço ao qual você está se conectando. Você pode saber mais sobre os detalhes de um tipo de conexão específico no artigo sobre o serviço de destino.
   1. Se você [usar seu próprio Key Vault](use-azure-key-vault.md) para armazenar segredos, ative **Usar Key Vault** e escolha o segredo da lista.

1. Para criar a conexão, selecione **Salvar**.

Você também pode selecionar **Configurar** em um bloco na aba **Descobrir**.

### <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permitir que os colaboradores usem uma conexão para exportações

Ao configurar ou editar uma conexão de exportação, você escolhe quais usuários têm permissão para usar esta conexão específica para definir [exportações](export-destinations.md). Por padrão, uma conexão está disponível para os usuários com função de administrador. Você pode alterar essa configuração em **Escolher quem pode usar esta conexão** e permitir que os usuários com função de colaborador usem a conexão.

- Os colaboradores não poderão visualizar ou editar a conexão. Eles verão apenas o nome de exibição e seu tipo ao criar uma exportação.
- Ao compartilhar uma conexão, você permite que os colaboradores usem uma conexão. Os colaboradores verão as conexões compartilhadas ao configurar as exportações. Eles podem gerenciar todas as exportações que usam essa conexão específica.
- Você pode alterar essa configuração enquanto mantém as exportações que já foram definidas pelos colaboradores.

## <a name="edit-a-connection"></a>Editar uma conexão

1. Acesse **Administração** > **Conexões (versão preliminar)**.

1. Acesse a guia **Conexões**.

1. Selecione as reticências verticais (&vellip;) para a conexão que você deseja editar.

1. Selecione **Editar**.

1. Altere os valores que deseja atualizar e selecione **Salvar**.

## <a name="remove-a-connection"></a>Remover uma conexão

Se a conexão que você está removendo for usada por enriquecimentos ou exportações, primeiro você precisa desanexá-los ou removê-los. A caixa de diálogo de remoção guiará você para os enriquecimentos ou exportações relevantes.

Os enriquecimentos e as exportações separados tornam-se inativos. Você os reativa adicionando outra conexão a eles na página [Enriquecimentos](enrichment-hub.md) ou [Exportações](export-destinations.md).

1. Acesse **Administração** > **Conexões (versão preliminar)**.

1. Acesse a guia **Conexões**.

1. Selecione as reticências verticais (&vellip;) para a conexão que você deseja remover.

1. Selecione **Remover** no menu suspenso. Uma caixa de diálogo de confirmação será exibida.

   1. Se houver enriquecimentos ou exportações usando a conexão, selecione o botão para ver o que está usando-a.
      - **Exportações:** você pode optar por remover ou desconectar as exportações para poder remover a conexão. Para desconectar uma exportação, os administradores podem usar a ação **Desconectar**. Esta ação está disponível para exportações individuais e múltiplas selecionadas. Ao desconectar, você mantém a configuração de exportação, mas ela não será executada até que outra conexão seja adicionada a ela.
      - **Enriquecimentos:** você pode optar por remover ou desativar os enriquecimentos para poder remover a conexão.
   1. Assim que a conexão não tiver mais dependências, volte para **Administração** > **Conexões** e tente remover a conexão novamente.

1. Para confirmar a exclusão, selecione **Remover**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurar conexões com segredos gerenciados por seu próprio Key Vault

Algumas conexões precisam de segredos como chaves de API ou senhas. Algumas conexões oferecem suporte a segredos armazenados em seu Key Vault. Saiba mais sobre as conexões compatíveis e como configurá-las em [seu próprio Key Vault para Customer Insights](use-azure-key-vault.md).
