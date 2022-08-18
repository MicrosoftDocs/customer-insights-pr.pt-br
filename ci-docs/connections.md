---
title: Visão geral de conexões (versão preliminar)
description: Conexões com outros serviços do Customer Insights.
ms.date: 08/04/2022
ms.reviewer: nikeller
ms.subservice: audience-insights
ms.topic: overview
author: m-hartmann
ms.author: mhart
manager: shellyha
searchScope:
- ci-connections
- customerInsights
ms.openlocfilehash: 8580dc7d90c75f66f73efc15f8e38f5e10fbb8a7
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245497"
---
# <a name="connections-preview-overview"></a>Visão geral de conexões (versão preliminar)

As conexões são a chave para permitir o compartilhamento de dados do Customer Insights e com o Customer Insights. Cada conexão estabelece o compartilhamento de dados com um serviço específico. Use conexões para [configurar enriquecimentos de terceiros](enrichment-hub.md) e [configurar exportações](export-destinations.md). A mesma conexão pode ser usada várias vezes. Por exemplo, uma conexão com o Dynamics 365 Marketing funciona para várias exportações e uma conexão da Leadspace pode ser usada para vários enriquecimentos.

## <a name="export-connections"></a>Conexões de exportação

Somente os administradores podem configurar novas conexões, mas eles podem [conceder acesso aos colaboradores](#allow-contributors-to-use-a-connection-for-exports) para usarem as conexões existentes. Os administradores controlam para onde os dados podem ir, os colaboradores definem o conteúdo e a frequência de acordo com suas necessidades.

## <a name="enrichment-connections"></a>Conexões de enriquecimento

Somente os administradores podem configurar novas conexões, mas as conexões criadas estão sempre disponíveis para os administradores e os colaboradores. Os administradores gerenciam credenciais e fornecem consentimento para a transferências de dados. As conexões podem então ser usadas para enriquecimentos pelos administradores e colaboradores.

## <a name="add-a-new-connection"></a>Adicionar uma nova conexão

### <a name="prerequisites"></a>Pré-requisitos

- [Permissões de administrador](permissions.md)
- Outros serviços da Microsoft, se houver, estão na mesma organização

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha o tipo de conexão que deseja criar. Ou, acesse a guia **Descobrir** e selecione **Configurar** em um bloco de conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Insira os detalhes necessários. Os campos exatos dependem do serviço ao qual você está se conectando. Para os detalhes de um tipo de conexão específico, consulte o artigo sobre o serviço de destino.

1. Se você [usar seu próprio Key Vault](use-azure-key-vault.md) para armazenar segredos, ative **Usar Key Vault** e escolha o segredo da lista.

1. Examine a conformidade e privacidade dos dados e selecione **Concordo**.

1. Selecione **Salvar** para criar a conexão.

### <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para terceiros ou para outros produtos da Microsoft, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados que podem ser confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o terceiro cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

O administrador do Dynamics 365 Customer Insights poderá remover a conexão a qualquer momento para interromper o uso da funcionalidade.

## <a name="allow-contributors-to-use-a-connection-for-exports"></a>Permitir que os colaboradores usem uma conexão para exportações

Ao configurar ou editar uma conexão de exportação, escolha quais usuários têm permissão para usar esta conexão específica para definir [exportações](export-destinations.md). Por padrão, uma conexão está disponível para os usuários com função de administrador. Altere a configuração **Escolher quem pode usar esta conexão** para permitir que os usuários com a função de colaborador usem a conexão.

- Os colaboradores não poderão visualizar ou editar a conexão. Eles verão apenas o nome de exibição e seu tipo ao criar uma exportação.
- Ao compartilhar uma conexão, você permite que os colaboradores usem uma conexão. Os colaboradores verão as conexões compartilhadas ao configurar as exportações. Eles podem gerenciar todas as exportações que usam essa conexão específica.
- Você pode alterar essa configuração enquanto mantém as exportações que já foram definidas pelos colaboradores.

## <a name="manage-existing-connections"></a>Gerenciar conexões existentes

1. Vá para **Administração** > **Conexões**.

1. Selecione a guia **Enriquecimento** ou **Exportações** para exibir uma lista de conexões de enriquecimento ou de exportação, o tipo de conexão, quando ela foi criada e quem tem acesso. Você pode classificar a lista de conexões por qualquer coluna.

1. Selecione a conexão para exibir as ações disponíveis.

   - **Edite** a conexão.
   - [**Remova**](#remove-a-connection) uma conexão.

### <a name="remove-a-connection"></a>Remover uma conexão

Se a conexão que você está removendo for usada por enriquecimentos ou exportações, desanexe-os ou remova-os primeiro. A caixa de diálogo de remoção guiará você para os enriquecimentos ou exportações relevantes.

> [!TIP]
> Os enriquecimentos desativados e as exportações desanexadas tornam-se inativos. Você os reativa adicionando outra conexão a eles na página [Enriquecimentos](enrichment-hub.md) ou [Exportações](export-destinations.md).

1. Vá para **Administração** > **Conexões**.

1. Selecione a guia **Enriquecimento** ou **Exportações**.

1. Selecione a conexão que deseja remover.

1. Selecione **Remover** no menu suspenso. Uma caixa de diálogo de confirmação será exibida.

   1. Se houver enriquecimentos ou exportações usando a conexão, selecione o botão para ver o que está usando-a.
      - **Exportações:** escolha entre **Remover** a exportação ou **Desanexar a conexão**. Desanexar a conexão mantém a configuração de exportação, mas ela não será executada até que outra conexão seja adicionada a ela.
      - **Enriquecimentos:** escolha entre **Excluir** ou **Desativar** os enriquecimentos.
   1. Assim que a conexão não tiver mais dependências, volte para **Administração** > **Conexões** e tente remover a conexão novamente.

1. Para confirmar a exclusão, selecione **Remover**.

## <a name="set-up-connections-with-secrets-managed-by-your-own-key-vault"></a>Configurar conexões com segredos gerenciados por seu próprio Key Vault

Algumas conexões precisam de segredos como chaves de API ou senhas. Algumas conexões oferecem suporte a segredos armazenados em seu Key Vault. Saiba mais sobre as conexões compatíveis e como configurá-las em [seu próprio Key Vault para Customer Insights](use-azure-key-vault.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
