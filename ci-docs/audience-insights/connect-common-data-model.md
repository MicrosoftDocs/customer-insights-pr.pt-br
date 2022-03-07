---
title: Conectar os dados do Common Data Model a uma conta do Azure Data Lake
description: Trabalhe com dados do Common Data Model usando o Azure Data Lake Storage.
ms.date: 01/25/2022
ms.subservice: audience-insights
ms.topic: how-to
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-data-sources
- ci-create-data-source
- ci-attach-cdm
- customerInsights
ms.openlocfilehash: 1e3b28316c06d6a15dd5690837c365b0677a882e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354903"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Conectar a uma pasta do Common Data Model usando uma conta do Azure Data Lake

Este artigo fornece informações sobre como ingerir dados de uma pasta do Common Data Model usando sua conta Gen2 do Azure Data Lake Storage.

## <a name="important-considerations"></a>Considerações importantes

- Os dados no Azure Data Lake precisam seguir o padrão do Common Data Model. Outros formatos não têm suporte no momento.

- A ingestão de dados oferece suporte exclusivamente a contas de armazenamento *Gen2* do Azure Data Lake. Não é possível usar contas de armazenamento Gen1 do Azure Data Lake para ingerir dados.

- A conta do Azure Data Lake Storage deve ter o recurso [namespace hierárquico habilitado](/azure/storage/blobs/data-lake-storage-namespace).

- Para autenticar com uma entidade de serviço do Azure, verifique se ela está configurada em seu locatário. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md).

- O Azure Data Lake a partir do qual você deseja se conectar e ingerir dados deve estar na mesma região do Azure que o ambiente do Dynamics 365 Customer Insights. Não há suporte para conexões com uma pasta do Common Data Model de um data lake em uma região diferente do Azure. Para conhecer a região do Azure do ambiente, acesse **Administrador** > **Sistema** > **Sobre** em insights de público-alvo.

- Os dados armazenados em serviços online podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar ou se conectar aos dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais na Central de Confiabilidade da Microsoft](https://www.microsoft.com/trust-center).

## <a name="connect-to-a-common-data-model-folder"></a>Conectar-se a uma pasta do Common Data Model

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Selecione **Azure Data Lake Storage**, insira um **Nome** para a fonte de dados e selecione **Avançar**.

   - Se solicitado, selecione um dos conjuntos de dados de exemplo que pertencem ao seu setor e, em seguida, selecione **Avançar**. 

1. Você pode escolher entre usar uma opção baseada em recurso e uma opção baseada em assinatura para autenticação. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). Insira o **Endereço do servidor**, selecione **Entrar** e, em seguida, selecione **Avançar**.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo para inserir detalhes da nova conexão do Azure Data Lake.](media/enter-new-storage-details.png)
   > [!NOTE]
   > Você precisa de uma das seguintes funções para o contêiner ou conta de armazenamento mencionada acima para se conectar e criar uma fonte de dados:
   >  - Leitor de Dados do Storage Blob
   >  - Proprietário de Dados do Storage Blob
   >  - Colaborador de Dados do Storage Blob

1. Na caixa de diálogo **Selecionar uma pasta do Common Data Model**, selecione o arquivo manifest.json para importar os dados e selecione **Avançar**.
   > [!NOTE]
   > Qualquer arquivo model.json ou manifest.json associado a outra fonte de dados no ambiente não será mostrado na lista.

1. Você verá uma lista de entidades disponíveis no arquivo model.json ou manifest.json selecionado. Analise e selecione na lista de entidades disponíveis e, em seguida, selecione **Salvar**. Todas as entidades selecionadas serão ingeridas usando a nova fonte de dados.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo mostrando uma lista de entidades de um arquivo model.json.](media/review-entities.png)

8. Indique em quais entidades de dados você quer habilitar a criação de perfis de dados e, em seguida, selecione **Salvar**. A criação de perfil de dados permite a análise e outros recursos. Você pode selecionar a entidade inteira, que seleciona todos os atributos da entidade, ou selecionar certos atributos de sua escolha. Por padrão, nenhuma entidade está habilitada para criação de perfil de dados.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo mostrando uma criação de perfil de dados.](media/dataprofiling-entities.png)

9. Após salvar suas seleções, a página **Fontes de dados** será aberta. Agora você verá a conexão da pasta Common Data Model como uma fonte de dados.

> [!NOTE]
> Um arquivo model.json file ou manifest.json só pode ser associado a uma fonte de dados no mesmo ambiente. Contudo, o mesmo arquivo model.json file ou manifest.json pode ser usado para fontes de dados em vários ambientes.

## <a name="edit-a-common-data-model-folder-data-source"></a>Editar uma fonte de dados da pasta do Common Data Model

Você pode atualizar a chave de acesso para a conta de armazenamento que contém a pasta do Common Data Model. Você também pode alterar o arquivo model.json file ou manifest.json. Para conectar-se a um contêiner diferente na sua conta de armazenamento ou alterar o nome da conta, [crie uma nova conexão da fonte de dados](#connect-to-a-common-data-model-folder).

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Ao lado da fonte de dados que você deseja atualizar, selecione as reticências.

3. Selecione uma opção **Editar** na lista.

4. Opcionalmente, atualize a **Chave de acesso** e selecione **Avançar**.

   ![Caixa de diálogo para editar e atualizar uma chave de acesso para uma fonte de dados existente.](media/edit-access-key.png)

5. Ou você pode atualizar de uma conexão de chave de conta para uma conexão baseada em recursos ou baseada em assinatura. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). Você não pode alterar informações de **Contêiner** ao atualizar a conexão.
   > [!div class="mx-imgBorder"]

   > ![Caixa de diálogo para inserir detalhes de conexão do Azure Data Lake a uma conta de armazenamento existente.](media/enter-existing-storage-details.png)

   > [!NOTE]
   > Você precisa de uma das seguintes funções para o contêiner ou conta de armazenamento mencionada acima para se conectar e criar uma fonte de dados:
   >  - Leitor de Dados do Storage Blob
   >  - Proprietário de Dados do Storage Blob
   >  - Colaborador de Dados do Storage Blob


6. Opcionalmente, escolha outro arquivo model.json ou manifest.json com um conjunto diferente de entidades no contêiner.

7. Ou você pode selecionar entidades adicionais para ingestão. Você também pode remover quaisquer entidades já selecionadas, se não houver dependências.

   > [!IMPORTANT]
   > Se houver dependências no arquivo model.json ou manifest.json existente e no conjunto de entidades, você verá uma mensagem de erro e não será possível selecionar outro arquivo model.json ou manifest.json. Remova essas dependências antes de alterar o arquivo model.json ou manifest.json ou criar uma fonte de dados com o arquivo model.json ou manifest.json que deseja usar para evitar a remoção das dependências.

8. Ou você pode selecionar atributos ou entidades adicionais para habilitar a criação de perfil de dados ou desabilitar os já selecionados.   


[!INCLUDE[footer-include](../includes/footer-banner.md)]
