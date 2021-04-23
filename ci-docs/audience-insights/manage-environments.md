---
title: Criar e gerenciar ambientes
description: Saiba como se inscrever no serviço e gerenciar ambientes.
ms.date: 02/01/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 1c2dfdd2889b5cb6c5285b4d7cc7f52a3d6de4d1
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5598279"
---
# <a name="manage-environments"></a>Gerenciar ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Este artigo explica como criar uma nova organização e provisionar um ambiente.

## <a name="sign-up-and-create-an-organization"></a>Inscrever-se e criar uma organização

1. Acesse o site do [Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/).

2. Selecione **Começar**.

3. Escolha o cenário de inscrição de sua preferência e selecione o link correspondente.

4. Aceite os termos e condições e selecione **Continuar** para começar a criar a organização.

5. Depois que o ambiente for criado, você será redirecionado para [Customer Insights](https://home.ci.ai.dynamics.com).

6. Use o ambiente de demonstração para explorar o aplicativo ou crie um novo ambiente seguindo as etapas na próxima seção.

7. Após especificar as configurações do ambiente, selecione **Criar**.

8. Você será conectado depois que o ambiente for criado com êxito.

## <a name="create-an-environment-in-an-existing-organization"></a>Criar um ambiente em uma organização existente

Há duas maneiras de criar um novo ambiente. Você pode especificar uma configuração totalmente nova ou copiar algumas definições de configuração de um ambiente existente.

Para criar um ambiente:

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione **Novo**.

   > [!div class="mx-imgBorder"]
   > ![Configurações do ambiente](media/environment-settings-dialog.png)

1. Na caixa de diálogo **Criar novo ambiente**, selecione **Novo ambiente**.

   Se você quiser [copiar dados do ambiente atual](#additional-considerations-for-copy-configuration-preview), selecione **Copiar de um ambiente existente**. Você verá uma lista de todos os ambientes disponíveis da sua organização, dos quais é possível copiar dados.

1. Forneça os detalhes a seguir:
   - **Nome**: o nome deste ambiente. Esse campo já estará preenchido se você copiou de um ambiente existente, mas é possível alterá-lo.
   - **Região**: a região na qual o serviço é implantado e hospedado.
   - **Tipo**: selecione se você deseja criar um ambiente de produção ou área restrita.

2. Opcionalmente, é possível selecionar **Configurações avançadas**:

   - **Salvar todos os dados no**: especifica onde você deseja armazenar os dados de saída gerados do Customer Insights. Você terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerenciado pela equipe do Customer Insights) e Gen2 do **Azure Data Lake Storage** (seu próprio Azure Data Lake Storage). Por padrão, a opção de armazenamento do Customer Insights é selecionada.

   > [!NOTE]
   > Ao salvar dados no Azure Data Lake Storage, você concorda que os dados serão transferidos e armazenados na localização geográfica adequada para a conta de armazenamento do Azure, que pode ser diferente de onde os dados são armazenados no Dynamics 365 Customer Insights. [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)
   >
   > Atualmente, as entidades ingeridas são sempre armazenadas no data lake gerenciado do Customer Insights.
   > Oferecemos suporte apenas a contas de armazenamento do Azure Data Lake Gen2 da mesma região do Azure que você selecionou ao criar o ambiente.
   > Oferecemos suporte somente a contas de armazenamento habilitadas para o Namespace Hierárquico (HNS) do Azure Data Lake Gen2.

   - Para a opção Azure Data Lake Storage Gen2, você pode escolher entre uma opção baseada em recurso e uma opção baseada em assinatura para autenticação. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). O nome do **Contêiner** não pode ser alterado e será "customerinsights".
   
   - Se quiser usar [previsões](predictions.md) ou configurar o compartilhamento de dados com aplicativos e soluções com base no Microsoft Dataverse, forneça a URL do ambiente do Microsoft Dataverse em **Configurar compartilhamento de dados com o Microsoft Dataverse e habilitar recursos adicionais**. Selecione **Habilitar compartilhamento de dados** para compartilhar dados de saída do Customer Insights com um Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Atualmente, não há suporte para o compartilhamento de dados com o Microsoft Dataverse Managed Data Lake ao salvar todos os dados no seu Azure Data Lake Storage.
     > - Atualmente, não há suporte para a [previsão de valores ausentes em uma entidade](predictions.md) ao habilitar o compartilhamento de dados com o Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Opções de configuração para permitir o compartilhamento com o Microsoft Dataverse](media/Datasharing-with-DataverseMDL.png)

   Quando você executar processos, como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento especificada acima. Os arquivos de dados e arquivos model.json serão criados e adicionados às respectivas subpastas com base no processo executado.

   Se você criar vários ambientes do Customer Insights e optar por salvar as entidades de saída desses ambientes na sua conta de armazenamento, pastas separadas serão criadas para cada ambiente com ci_<environmentid> no contêiner.

### <a name="additional-considerations-for-copy-configuration-preview"></a>Considerações adicionais para configuração de cópia (versão preliminar)

As seguintes configurações são copiadas:

- Configurações do recurso
- Fontes de dados ingeridas/importadas
- Configuração de unificação de dados (Mapear, Corresponder, Mesclar)
- Segmentos
- Medidas
- Relações
- Atividades
- Índice de filtro e pesquisa
- Exportar destinos
- Atualização agendada
- Enriquecimentos
- Gerenciamento de modelos
- Atribuições de função

As seguintes configurações *não* são copiadas:

- Perfis do cliente.
- Credenciais da fonte de dados. Você precisará fornecer as credenciais para cada fonte de dados e atualizar as fontes de dados manualmente.
- Fontes de dados da pasta Common Data Model e do lake gerenciado do Common Data Service. Você precisará criar essas fontes de dados manualmente com o mesmo nome do ambiente de origem.

Ao copiar um ambiente, você verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para fontes de dados** para ver a lista de fontes de dados.

Todas as fontes de dados mostrarão um status **Credenciais Necessárias**. Edite as fontes de dados e insira as credenciais para atualizá-las.

> [!div class="mx-imgBorder"]
> ![Fontes de dados copiadas](media/data-sources-copied.png)

Após atualizar as fontes de dados, vá para **Dados** > **Unificar**. Aqui você encontrará configurações do ambiente de origem. Edite-os conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade unificada do cliente.

Quando a unificação de dados estiver concluída, vá para **Medidas** e **Segmentos** para atualizá-los também.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Você pode editar alguns dos detalhes dos ambientes existentes.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

2.  Selecione o ícone **Editar**.

3. Na caixa **Editar ambiente**, é possível atualizar o **Nome de exibição** do ambiente, mas não é possível alterar a **Região** ou o **Tipo**.

4. Se um ambiente estiver configurado para armazenar dados no Azure Data Lake Storage Gen2, você poderá atualizar a **Chave da conta**. No entanto, você não pode alterar o **Nome da conta** e o nome do **Recipiente**.

5. Opcionalmente, você pode atualizar de uma conexão baseada em chave de conta para uma conexão baseada em recurso ou assinatura. Após a atualização, não é possível reverter para a chave de conta. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). Você não pode alterar informações de **Contêiner** ao atualizar a conexão.

## <a name="reset-an-existing-environment"></a>Redefinir um ambiente existente

Como administrador, você pode redefinir um ambiente para um estado vazio se quiser excluir todas as configurações e remover os dados ingeridos.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo. 

2.  Selecione o ambiente que deseja redefinir e selecione as reticências **...**. 

3. Escolha a opção **Redefinir**. 

4.  Para confirmar a exclusão, insira o nome do ambiente e selecione **Redefinir**.

## <a name="delete-an-existing-environment-available-only-for-admins"></a>Excluir um ambiente existente (disponível apenas para administradores)

Como administrador, é possível excluir um ambiente administrado por você.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

2.  Selecione o ambiente que deseja redefinir e selecione as reticências **...**. 

3. Escolha a opção **Excluir**. 

4.  Para confirmar a exclusão, insira o nome do ambiente e selecione **Excluir**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]