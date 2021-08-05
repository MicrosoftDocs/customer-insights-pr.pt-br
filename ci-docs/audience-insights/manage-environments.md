---
title: Criar e gerenciar ambientes
description: Saiba como se inscrever no serviço e gerenciar ambientes.
ms.date: 07/22/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 2f115269b9d07dd118ec18cc48b55de8aea9b5bb
ms.sourcegitcommit: 98267da3f3eddbdfbc89600a7f54e5e664a8f069
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2021
ms.locfileid: "6683459"
---
# <a name="manage-environments"></a>Gerenciar ambientes

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

## <a name="switch-environments"></a>Alternar ambientes

Selecione o controle de **Ambiente** no canto superior direito da página para alterar os ambientes.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de tela do controle para alternar ambientes.":::

Os administradores podem [criar](get-started-paid.md) e gerenciar ambientes.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Você pode editar alguns dos detalhes dos ambientes existentes.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

2.  Selecione o ícone **Editar**.

3. Na caixa **Editar ambiente**, é possível atualizar o **Nome de exibição** do ambiente, mas não é possível alterar a **Região** ou o **Tipo**.

4. Se um ambiente estiver configurado para armazenar dados no Azure Data Lake Storage, você pode atualizar a **Chave de conta**. No entanto, você não pode alterar o **Nome da conta** e o nome do **Recipiente**.

5. Como outra opção, você pode atualizar de uma conexão baseada em chave da conta para uma conexão baseada em recursos ou em assinatura. Após a atualização, não é possível reverter para a chave de conta. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). Você não pode alterar informações de **Contêiner** ao atualizar a conexão.

6. Opcionalmente, você pode fornecer uma URL do ambiente do Microsoft Dataverse em **Configurar compartilhamento de dados com o Microsoft Dataverse e habilitar recursos adicionais**. Esses recursos incluem o compartilhamento de dados com aplicativos e soluções baseados no Microsoft Dataverse, a ingestão de dados de fontes de dados locais ou o uso de [previsões](predictions.md). Selecione **Habilitar compartilhamento de dados** para compartilhar dados de saída do Customer Insights com um Data Lake Gerenciado do Microsoft Dataverse.

   > [!NOTE]
   > - Atualmente, não há suporte para o compartilhamento de dados com o Microsoft Dataverse Managed Data Lake ao salvar todos os dados no seu Azure Data Lake Storage.
   > - A [previsão de valores ausentes em uma entidade](predictions.md) e os relatórios do PowerBI Embedded em insights de público-alvo (se habilitados em seu ambiente) não têm suporte no momento se você habilitar o compartilhamento de dados com o data lake gerenciado do Microsoft Dataverse.

   Depois de habilitar o compartilhamento de dados com o Microsoft Dataverse, uma atualização completa das suas fontes de dados e de outros processos será iniciada. Se os processos estiverem em execução no momento, você não verá a opção para habilitar o compartilhamento de dados com o Microsoft Dataverse. Aguarde a conclusão desses processos ou cancele-os para habilitar o compartilhamento de dados. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opções de configuração para habilitar o compartilhamento de dados com o Microsoft Dataverse.":::
   
   Quando você executar processos, como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento especificada acima. Arquivos de dados e arquivos model.json serão criados e adicionados às respectivas subpastas, dependendo do processo executado.

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Ao criar um ambiente, você pode optar por copiar a configuração de um ambiente existente. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de tela das opções de configuração nas configurações do ambiente.":::

Você verá uma lista de todos os ambientes disponíveis da sua organização, dos quais é possível copiar dados.

As seguintes configurações são copiadas:

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

Os seguintes dados *não* são copiados:

- Perfis do cliente.
- Credenciais da fonte de dados. Você precisará fornecer as credenciais para cada fonte de dados e atualizar as fontes de dados manualmente.
- As fontes de dados da pasta Common Data Model e Data Lake gerenciadas pelo Dataverse. Você precisará criar essas fontes de dados manualmente com o mesmo nome do ambiente de origem.

Ao copiar um ambiente, você verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para fontes de dados** para ver a lista de fontes de dados.

Todas as fontes de dados mostrarão um status **Credenciais Necessárias**. Edite as fontes de dados e insira as credenciais para atualizá-las.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de fontes de dados que foram copiadas e precisam de autenticação.":::

Após atualizar as fontes de dados, vá para **Dados** > **Unificar**. Aqui você encontrará configurações do ambiente de origem. Edite-os conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade unificada do cliente.

Quando a unificação de dados estiver concluída, vá para **Medidas** e **Segmentos** para atualizá-los também.

## <a name="reset-an-existing-environment"></a>Redefinir um ambiente existente

Como administrador, você pode redefinir um ambiente para um estado vazio se quiser excluir todas as configurações e remover os dados ingeridos.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo. 

2.  Selecione o ambiente que deseja redefinir selecione as reticências (**...**). 

3. Escolha a opção **Redefinir**. 

4.  Para confirmar a exclusão, insira o nome do ambiente e selecione **Redefinir**.

## <a name="delete-an-existing-environment"></a>Excluir um ambiente existente

Como administrador, é possível excluir um ambiente administrado por você.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

2.  Selecione o ambiente que deseja redefinir selecione as reticências (**...**). 

3. Escolha a opção **Excluir**. 

4.  Para confirmar a exclusão, insira o nome do ambiente e selecione **Excluir**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
