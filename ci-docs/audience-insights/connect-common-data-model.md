---
title: Conectar os dados do Common Data Model a uma conta do Azure Data Lake
description: Trabalhe com dados do Common Data Model usando o Azure Data Lake Storage.
ms.date: 05/29/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 25de23e615704a72f6b41d98ae9418beb338e77e
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643444"
---
# <a name="connect-to-a-common-data-model-folder-using-an-azure-data-lake-account"></a>Conectar a uma pasta do Common Data Model usando uma conta do Azure Data Lake

Este artigo fornece informações sobre como ingerir dados de uma pasta do Common Data Model usando sua conta Gen2 do Azure Data Lake Storage.

## <a name="important-considerations"></a>Considerações importantes

- Os dados no Azure Data Lake precisam seguir o padrão do Common Data Model. Outros formatos não têm suporte no momento.

- A ingestão de dados oferece suporte exclusivamente a contas de armazenamento *Gen2* do Azure Data Lake. Não é possível usar contas de armazenamento Gen1 do Azure Data Lake para ingerir dados.

- Para autenticar com uma entidade de serviço do Azure, verifique se ela está configurada em seu locatário. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md).

- O Azure Data Lake a partir do qual você deseja se conectar e ingerir dados deve estar na mesma região do Azure que o ambiente do Dynamics 365 Customer Insights. Não há suporte para conexões com uma pasta do Common Data Model de um data lake em uma região diferente do Azure. Para conhecer a região do Azure do ambiente, acesse **Administrador** > **Sistema** > **Sobre** em insights de público-alvo.

- Os dados armazenados em serviços online podem ser armazenados em um local diferente daquele onde os dados são processados ou armazenados no Dynamics 365 Customer Insights. Ao importar ou se conectar a dados armazenados em serviços online, você concorda que os dados podem ser transferidos e armazenados com o Dynamics 365 Customer Insights. [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)

## <a name="connect-to-a-common-data-model-folder"></a>Conectar-se a uma pasta do Common Data Model

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

1. Selecione **Adicionar fonte de dados**.

1. Selecione **Conectar-se a uma pasta do Common Data Model**, insira um **Nome** para a fonte de dados e selecione **Avançar**.

1. Você pode escolher entre usar uma opção baseada em recurso e uma opção baseada em assinatura para autenticação. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). Insira as informações do **Contêiner** e selecione **Avançar**.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo para inserir detalhes da conexão para o Azure Data Lake](media/enter-new-storage-details.png)

1. Na caixa de diálogo **Selecionar uma pasta do Common Data Model**, selecione o arquivo model.json para importar os dados e selecione **Avançar**.
   > [!NOTE]
   > Qualquer arquivo model.json associado a outra fonte de dados no ambiente não será mostrado na lista.

1. Você obterá uma lista de entidades disponíveis no arquivo model.json selecionado. Você pode revisar e selecionar da lista de entidades disponíveis e selecionar **Salvar**. Todas as entidades selecionadas serão ingeridas usando a nova fonte de dados.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo mostrando uma lista de entidades de um arquivo model.json](media/review-entities.png)

8. Indique quais entidades de dados você quer habilitar na criação de perfil de dados e selecione **Salvar**. A criação de perfil de dados permite a análise e outros recursos. Você pode selecionar a entidade inteira, que seleciona todos os atributos da entidade, ou selecionar certos atributos de sua escolha. Por padrão, nenhuma entidade está habilitada para criação de perfil de dados.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo mostrando uma criação de perfil de dados](media/dataprofiling-entities.png)

9. Após salvar suas seleções, a página **Fontes de dados** será aberta. Agora você verá a conexão da pasta Common Data Model como uma fonte de dados.

> [!NOTE]
> Um arquivo model.json só pode ser associado a uma fonte de dados no mesmo ambiente. Contudo, o mesmo arquivo model.json pode ser usado para fontes de dados em vários ambientes.

## <a name="edit-a-common-data-model-folder-data-source"></a>Editar uma fonte de dados da pasta do Common Data Model

Você pode atualizar a chave de acesso para a conta de armazenamento que contém a pasta do Common Data Model. Você também pode alterar o arquivo model.json. Para conectar-se a um contêiner diferente na sua conta de armazenamento ou alterar o nome da conta, [crie uma nova conexão da fonte de dados](#connect-to-a-common-data-model-folder).

1. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2. Ao lado da fonte de dados que você deseja atualizar, selecione as reticências.

3. Selecione uma opção **Editar** na lista.

4. Opcionalmente, atualize a **Chave de acesso** e selecione **Avançar**.

   ![Caixa de diálogo para editar e atualizar uma chave de acesso para uma fonte de dados existente](media/edit-access-key.png)

5. Ou você pode atualizar de uma conexão de chave de conta para uma conexão baseada em recursos ou baseada em assinatura. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). Você não pode alterar informações de **Contêiner** ao atualizar a conexão.
   > [!div class="mx-imgBorder"]
   > ![Caixa de diálogo para inserir detalhes da conexão para o Azure Data Lake](media/enter-existing-storage-details.png)

6. Opcionalmente, escolha um arquivo model.json diferente com um conjunto diferente de entidades do contêiner.

7. Ou você pode selecionar entidades adicionais para ingestão. Você também pode remover quaisquer entidades já selecionadas, se não houver dependências.

   > [!IMPORTANT]
   > Se houver dependências no arquivo model.json existente e no conjunto de entidades, você verá uma mensagem de erro e não poderá selecionar um arquivo model.json diferente. Remova essas dependências antes de alterar o arquivo model.json ou crie uma nova fonte de dados com o arquivo model.json que você deseja usar para evitar a remoção das dependências.

8. Ou você pode selecionar atributos ou entidades adicionais para habilitar a criação de perfil de dados ou desabilitar os já selecionados.   
