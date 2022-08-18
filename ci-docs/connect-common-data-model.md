---
title: Conectar a uma pasta do Common Data Model usando uma conta do Azure Data Lake
description: Trabalhe com dados do Common Data Model usando o Azure Data Lake Storage.
ms.date: 07/27/2022
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: b237c291bb4dd22ca22ab2cdd8b6293490aa83e1
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245770"
---
# <a name="connect-to-data-in-azure-data-lake-storage"></a>Conectar-se a dados no Azure Data Lake Storage

Ingira dados no Dynamics 365 Customer Insights usando sua conta do Azure Data Lake Storage Gen2. A ingestão de dados pode ser completa ou incremental.

## <a name="prerequisites"></a>Pré-requisitos

- A ingestão de dados dá suporte a contas do Azure Data Lake Storage *Gen2* exclusivamente. Não é possível usar contas do Data Lake Gen1 para ingerir dados.

- A conta do Azure Data Lake Storage devem ter o [namespace hierárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace). Os dados devem ser armazenados em um formato de pasta hierárquica que defina a pasta raiz e possua subpastas para cada entidade. As subpastas podem ter dados completos ou pastas de dados incrementais.

- Para autenticar com uma entidade de serviço do Azure, verifique se ela está configurada em seu locatário. Para obter mais informações, consulte [Conectar-se a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md).

- O Azure Data Lake Storage ao qual você deseja se conectar e do qual deseja ingerir dados tem que estar na mesma região do Azure do que o ambiente do Dynamics 365 Customer Insights. Não há suporte para conexões com uma pasta do Common Data Model de um data lake em uma região diferente do Azure. Para conhecer a região do Azure do ambiente, vá para **Administrador** > **Sistema** > **Sobre** no Customer Insights.

- Os dados armazenados em serviços online podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar ou se conectar aos dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center).

- A entidade de serviço do Customer Insights deve estar em uma das seguintes funções para acessar a conta de armazenamento. Para obter mais informações, consulte [Conceder permissões à entidade de serviço para acessar a conta de armazenamento](connect-service-principal.md#grant-permissions-to-the-service-principal-to-access-the-storage-account).
  - Leitor de Dados do Storage Blob
  - Proprietário de Dados do Storage Blob
  - Colaborador de Dados do Storage Blob

- Os dados em seu Data Lake Storage devem seguir o padrão do Common Data Model padrão para armazenamento de seus dados e ter o manifesto do Common Data Model para representar o esquema dos arquivos de dados (*.csv ou *.parquet). O manifesto deve fornecer os detalhes das entidades, como colunas de entidade e tipos de dados, e o local do arquivo de dados e o tipo de arquivo. Para obter mais informações, consulte [O manifesto do Common Data Model](/common-data-model/sdk/manifest). Se o manifesto não estiver presente, os usuários Administradores com acesso de Proprietário de Dados de Blob de Armazenamento ou Colaborador de Dados de Blob de Armazenamento poderão definir o esquema ao ingerir os dados.

## <a name="connect-to-azure-data-lake-storage"></a>Conectar-se ao Azure Data Lake Storage

1. Acesse **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Selecione **Azure Data Lake Storage**.

   :::image type="content" source="media/data_sources_ADLS.png" alt-text="Caixa de diálogo para inserir detalhes da conexão para o Azure Data Lake." lightbox="media/data_sources_ADLS.png":::

1. Insira um **Nome** para a fonte de dados e uma **Descrição** opcional. O nome identifica exclusivamente a fonte de dados e é referenciado em processos downstream e não pode ser alterado.

1. Escolha uma das opções a seguir para **Conectar seu armazenamento usando**. Para obter mais informações, consulte [Conectar o Customer Insights a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md).

   - **Recurso do Azure**: insira a **ID do Recurso**. Opcionalmente, se você quiser ingerir dados de uma conta de armazenamento por meio de um Link Privado do Azure, selecione **Habilitar Link Privado**. Para obter mais informações, consulte [Links Privados](security-overview.md#set-up-an-azure-private-link).
   - **Assinatura do Azure**: selecione **Subscrição** e, em seguida, **Grupo de recursos** e **Conta de armazenamento**. Opcionalmente, se você quiser ingerir dados de uma conta de armazenamento por meio de um Link Privado do Azure, selecione **Habilitar Link Privado**. Para obter mais informações, consulte [Links Privados](security-overview.md#set-up-an-azure-private-link).
  
   > [!NOTE]
   > Você precisa de uma das seguintes funções para o contêiner ou conta de armazenamento para criar a fonte de dados:
   >
   >  - O Leitor de Dados do Blob de Armazenamento é suficiente para ler de uma conta de armazenamento e ingerir os dados para o Customer Insights. 
   >  - O Proprietário ou Colaborador de Dados do Blob de Armazenamento é necessário se você quiser editar os arquivos de manifesto diretamente no Customer Insights.  
  
1. Escolha o nome do **Contêiner** que contém os dados e o esquema (arquivo model.json ou manifest.json) de onde importar dados e selecione **Avançar**.
   > [!NOTE]
   > Qualquer arquivo model.json ou manifest.json associado a outra fonte de dados no ambiente não será mostrado na lista. Contudo, o mesmo arquivo model.json file ou manifest.json pode ser usado para fontes de dados em vários ambientes.

1. Para criar um novo esquema, vá para [Criar um novo arquivo de esquema](#create-a-new-schema-file).

1. Para usar um esquema existente, navegue até a pasta que contém o arquivo model.json ou manifest.cdm.json. Você pode pesquisar em um diretório para localizar o arquivo.

1. Selecione o arquivo json e selecione **Avançar**. Uma lista de entidades disponíveis é exibida.

   :::image type="content" source="media/review-entities.png" alt-text="Caixa de diálogo de uma lista de entidades a serem selecionadas":::

1. Selecione as entidades que você deseja incluir.

   :::image type="content" source="media/ADLS_required.png" alt-text="Caixa de diálogo mostrando Obrigatório para Chave primária":::

   > [!TIP]
   > Para editar uma entidade em uma interface de edição do JSON, selecione a entidade e, depois, **Editar arquivo de esquema**. Faça as alterações e selecione **Salvar**.

1. Para entidades selecionadas que exigem ingestão incremental, **Obrigatório** é exibido sob **Atualização incremental**. Para cada uma dessas entidades, consulte [Configurar uma atualização incremental para fontes de dados do Azure Data Lake](incremental-refresh-data-sources.md).

1. Para entidades selecionadas onde uma chave primária não tiver sido definida, **Obrigatório** é exibido sob **Chave primária**. Para cada uma destas entidades:
   1. Selecione **Obrigatória**. O painel **Editar entidade** é exibido.
   1. Escolha a **Chave primária**. A chave primária é um atributo exclusivo da entidade. Para um atributo ser uma chave primária válida, ele não deve ter valores duplicados, valores ausentes ou valores nulos. Os atributos de tipo de dados de cadeia de caracteres, inteiro e GUID são compatíveis como chaves primárias.
   1. Opcionalmente, altere o padrão de partição.
   1. Selecione **Fechar** para salvar e fechar o painel.

1. Selecione o número de **Atributos** para cada entidade incluída. A página **Gerenciar atributos** é exibida.

   :::image type="content" source="media/dataprofiling-entities.png" alt-text="Caixa de diálogo para selecionar a criação de perfil de dados.":::

   1. Crie atributos, edite ou exclua atributos existentes. Você pode alterar o nome, o formato de dados ou adicionar um tipo semântico.
   1. Para habilitar análises e outros recursos, selecione **Criação de perfil de dados** para toda a entidade ou para atributos específicos. Por padrão, nenhuma entidade está habilitada para criação de perfil de dados.
   1. Selecione **Concluído**.

1. Selecione **Salvar**. A página **Fontes de dados** abre mostrando a nova fonte de dados no status **Atualizando**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página [**Entidades**](entities.md).

### <a name="create-a-new-schema-file"></a>Criar um arquivo de esquema

1. Selecione **Novo arquivo de esquema**.

1. Insira um nome para o arquivo e selecione **Salvar**.

1. Selecione **Nova entidade**. O painel **Nova Entidade** é exibido.

1. Insira o nome da entidade e escolha o **Localização de arquivos de dados**.
   - **Vários arquivos .csv ou .parquet**: navegue até a pasta raiz, selecione o tipo de padrão e insira a expressão.
   - **Arquivos .csv ou .parquet únicos**: navegue até o arquivo .csv ou .parquet e selecione-o.

   :::image type="content" source="media/ADLS_new_entity_location.png" alt-text="Caixa de diálogo para criar uma entidade com Localização de arquivos de dados realçada.":::

1. Selecione **Salvar**.

   :::image type="content" source="media/ADLS_new_entity_define_attributes.png" alt-text="Caixa de diálogo para definir ou gerar atributos automaticamente.":::

1. Selecione **definir os atributos** para adicionar manualmente os atributos ou selecione **gerá-los automaticamente**. Para definir os atributos, insira um nome, selecione o formato de dados e o tipo semântico opcional. Para atributos gerados automaticamente:

   1. Depois que os atributos forem gerados automaticamente, selecione **Revisar atributos**. A página **Gerenciar atributos** é exibida.

   1. Garanta que o formato de dados esteja correto para cada atributo.

   1. Para habilitar análises e outros recursos, selecione **Criação de perfil de dados** para toda a entidade ou para atributos específicos. Por padrão, nenhuma entidade está habilitada para criação de perfil de dados.

      :::image type="content" source="media/dataprofiling-entities.png" alt-text="Caixa de diálogo para selecionar a criação de perfil de dados.":::

   1. Selecione **Concluído**. A página **Selecionar entidades** é exibido.

1. Continue a adicionar entidades e atributos, se aplicável.

1. Depois que todas as entidades tiverem sido adicionadas, selecione **Incluir** para incluir as entidades na ingestão de fonte de dados.

   :::image type="content" source="media/ADLS_required.png" alt-text="Caixa de diálogo mostrando Obrigatório para Chave primária":::

1. Para entidades selecionadas que exigem ingestão incremental, **Obrigatório** é exibido sob **Atualização incremental**. Para cada uma dessas entidades, consulte [Configurar uma atualização incremental para fontes de dados do Azure Data Lake](incremental-refresh-data-sources.md).

1. Para entidades selecionadas onde uma chave primária não tiver sido definida, **Obrigatório** é exibido sob **Chave primária**. Para cada uma destas entidades:
   1. Selecione **Obrigatória**. O painel **Editar entidade** é exibido.
   1. Escolha a **Chave primária**. A chave primária é um atributo exclusivo da entidade. Para um atributo ser uma chave primária válida, ele não deve ter valores duplicados, valores ausentes ou valores nulos. Os atributos de tipo de dados de cadeia de caracteres, inteiro e GUID são compatíveis como chaves primárias.
   1. Opcionalmente, altere o padrão de partição.
   1. Selecione **Fechar** para salvar e fechar o painel.

1. Selecione **Salvar**. A página **Fontes de dados** abre mostrando a nova fonte de dados no status **Atualizando**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

O carregamento de dados pode levar algum tempo. Após uma atualização bem-sucedida, os dados ingeridos podem ser revisados na página [**Entidades**](entities.md).

## <a name="edit-an-azure-data-lake-storage-data-source"></a>Editar uma fonte de dados do Azure Data Lake Storage

Você pode atualizar a opção *Conecte-se à conta de armazenamento usando*. Para obter mais informações, consulte [Conectar o Customer Insights a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). Para conectar-se a um contêiner diferente na sua conta de armazenamento ou alterar o nome da conta, [crie uma nova conexão da fonte de dados](#connect-to-azure-data-lake-storage).

1. Acesse **Dados** > **Fontes de dados**.

1. Ao lado da fonte de dados que você deseja atualizar, selecione **Editar**.

   :::image type="content" source="media/data_sources_edit_ADLS.png" alt-text="Caixa de diálogo para editar a fonte de dados do Azure Data Lake.":::

1. Altere qualquer uma das seguintes informações:

   - **Descrição**
   - **Conecte seu armazenamento usando** e informações de conexão. Você não pode alterar informações de **Contêiner** ao atualizar a conexão.
      > [!NOTE]
      > Uma das funções a seguir deve ser atribuída à conta de armazenamento ou contêiner:
        > - Leitor de Dados do Storage Blob
        > - Proprietário de Dados do Storage Blob
        > - Colaborador de Dados do Storage Blob

   - **Habilite o Link Privado** se quiser ingerir dados de uma conta de armazenamento por meio de um Link Privado do Azure. Para obter mais informações, consulte [Links Privados](security-overview.md#set-up-an-azure-private-link).

1. Selecione **Avançar**
1. Altere um dos seguintes:
   - Navegue até um arquivo model.json ou manifest.json diferente com um conjunto diferente de entidades do contêiner.
   - Para adicionar outras entidades para ingestão, selecione **Nova entidade**.
   - Para remover quaisquer entidades já selecionadas se não houver dependências, selecione a entidade e escolha **Excluir**.
      > [!IMPORTANT]
      > Se houver dependências no arquivo model.json ou manifest.json existente e no conjunto de entidades, você verá uma mensagem de erro e não será possível selecionar outro arquivo model.json ou manifest.json. Remova essas dependências antes de alterar o arquivo model.json ou manifest.json ou criar uma fonte de dados com o arquivo model.json ou manifest.json que deseja usar para evitar a remoção das dependências.
   - Para alterar a localização do arquivo de dados ou a chave primária, selecione **Editar**.
   - Para alterar os dados de ingestão incremental, consulte [Configurar uma atualização incremental para fontes de dados do Azure Data Lake](incremental-refresh-data-sources.md).
   - Altere apenas o nome da entidade para corresponder ao nome da entidade no arquivo .json.

     > [!NOTE]
     > Sempre mantenha o nome da entidade no Customer Insights igual ao nome da entidade no arquivo model.json ou manifest.json após a ingestão. O Customer Insights valida todos os nomes de entidade com model.json ou manifest.json durante cada atualização do sistema. Se o nome de uma entidade for alterado dentro ou fora do Customer Insights, ocorrerá um erro porque ele não conseguirá encontrar o novo nome da entidade no arquivo .json. Se o nome de uma entidade ingerida foi alterado acidentalmente, edite o nome da entidade no Customer Insights para que corresponda ao nome no arquivo .json.

1. Selecione **Atributos** para adicionar ou alterar atributos ou para habilitar a criação de perfil de dados. Em seguida, selecione **Concluído**.

1. Clique em **Salvar** para aplicar suas alterações e voltar para a página **Fontes de dados**.

   [!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
