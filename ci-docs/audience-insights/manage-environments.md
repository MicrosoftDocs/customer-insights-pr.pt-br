---
title: Criar e gerenciar ambientes
description: Saiba como se inscrever no serviço e gerenciar ambientes.
ms.date: 06/15/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: 904ce68336cba4b7a4d5a37692b72d091400559d
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6304866"
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

> [!NOTE]
> As organizações podem criar *dois* ambientes para cada licença do Customer Insights. Se a sua organização adquirir mais de uma licença, [entre em contato com a nossa equipe de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade de complemento, baixe o [Guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Para criar um ambiente:

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione **Novo**.

   > [!div class="mx-imgBorder"]
   > ![Configurações de ambiente.](media/environment-settings-dialog.png)

1. Na caixa de diálogo **Criar um ambiente**, selecione **Novo ambiente**.

   Se você quiser [copiar dados do ambiente atual](#considerations-for-copy-configuration-preview), selecione **Copiar de um ambiente existente**. Você verá uma lista de todos os ambientes disponíveis da sua organização, dos quais é possível copiar dados.

1. Forneça os detalhes a seguir:
   - **Nome**: o nome deste ambiente. Esse campo já estará preenchido se você copiou de um ambiente existente, mas é possível alterá-lo.
   - **Tipo**: selecione se você deseja criar um ambiente de produção ou área restrita.
   - **Região**: a região na qual o serviço é implantado e hospedado.
   
1. Opcionalmente, é possível selecionar **Configurações avançadas**:

   - **Salvar todos os dados no**: especifica onde você deseja armazenar os dados de saída gerados do Customer Insights. Você terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerenciado pela equipe do Customer Insights) e **Azure Data Lake Storage** (seu próprio Azure Data Lake Storage). Por padrão, a opção de armazenamento do Customer Insights é selecionada.

     > [!NOTE]
     > Ao salvar dados no Azure Data Lake Storage, você concorda que os dados serão transferidos e armazenados na localização geográfica adequada para a conta de armazenamento do Azure, que pode ser diferente de onde os dados são armazenados no Dynamics 365 Customer Insights. [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > No momento, as entidade ingeridas são sempre armazenadas no Data Lake gerenciado do Customer Insights. 
     > 
     > Oferecemos suporte apenas para contas do Azure Data Lake Storage da mesma região Azure que você selecionou ao criar o ambiente. 
     > 
     > Oferecemos suporte apenas a contas do Azure Data Lake Storage que tenham um namespace hierárquico hierárquico habilitado.


   - Para a opção do Azure Data Lake Storage, você pode escolher entre uma opção baseada em recursos e outra baseada em assinatura para autenticação. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). O nome do **Contêiner** não pode ser alterado e será `customerinsights`.
   
   - Se você quiser usar [previsões](predictions.md), configure o compartilhamento de dados com o Microsoft Dataverse ou habilite a ingestão de dados de fontes de dados locais e forneça a URL do ambiente do Microsoft Dataverse em **Configurar compartilhamento de dados com o Microsoft Dataverse e habilitar recursos adicionais**. Selecione **Habilitar compartilhamento de dados** para compartilhar dados de saída do Customer Insights com um Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Atualmente, não há suporte para o compartilhamento de dados com o Microsoft Dataverse Managed Data Lake ao salvar todos os dados no seu Azure Data Lake Storage.
     > - Atualmente, não há suporte para a [previsão de valores ausentes em uma entidade](predictions.md) ao habilitar o compartilhamento de dados com o Microsoft Dataverse Managed Data Lake.

     > [!div class="mx-imgBorder"]
     > ![Opções de configuração para habilitar o compartilhamento de dados com o Microsoft Dataverse.](media/datasharing-with-DataverseMDL.png)

   Quando você executar processos, como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento especificada acima. Arquivos de dados e arquivos model.json serão criados e adicionados às pastas com base no nome do processo.

   Se você criar vários ambientes do Customer Insights e optar por salvar as entidades de saída desses ambientes na sua conta de armazenamento, pastas separadas serão criadas para cada ambiente com ci_<environmentid> no contêiner.

### <a name="considerations-for-copy-configuration-preview"></a>Considerações para a configuração de cópias (versão preliminar)

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
- As fontes de dados da pasta Common Data Model e Data Lake gerenciadas pelo Dataverse. Você precisará criar essas fontes de dados manualmente com o mesmo nome do ambiente de origem.

Ao copiar um ambiente, você verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para fontes de dados** para ver a lista de fontes de dados.

Todas as fontes de dados mostrarão um status **Credenciais Necessárias**. Edite as fontes de dados e insira as credenciais para atualizá-las.

> [!div class="mx-imgBorder"]
> ![Fontes de dados copiadas.](media/data-sources-copied.png)

Após atualizar as fontes de dados, vá para **Dados** > **Unificar**. Aqui você encontrará configurações do ambiente de origem. Edite-os conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade unificada do cliente.

Quando a unificação de dados estiver concluída, vá para **Medidas** e **Segmentos** para atualizá-los também.

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
   > - No momento, não há suporte para [Previsão de valores ausentes em uma entidade](predictions.md) ao habilitar o compartilhamento de dados com o Data Lake Gerenciado do Microsoft Dataverse.

   Depois de habilitar o compartilhamento de dados com o Microsoft Dataverse, uma atualização completa das suas fontes de dados e de outros processos será iniciada. Se os processos estiverem em execução no momento, você não verá a opção para habilitar o compartilhamento de dados com o Microsoft Dataverse. Aguarde a conclusão desses processos ou cancele-os para habilitar o compartilhamento de dados. 
   
   :::image type="content" source="media/datasharing-with-DataverseMDL.png" alt-text="Opções de configuração para habilitar o compartilhamento de dados com o Microsoft Dataverse.":::
   
   Quando você executar processos, como ingestão de dados ou criação de segmentos, as pastas correspondentes serão criadas na conta de armazenamento especificada acima. Arquivos de dados e arquivos model.json serão criados e adicionados às respectivas subpastas, dependendo do processo executado.

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
