---
title: Criar e gerenciar ambientes
description: Saiba como se inscrever no serviço e gerenciar ambientes.
ms.date: 03/28/2022
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: adkuppa
ms.author: adkuppa
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: ba29bcd173e615e544bd10e69043f310c009eb47
ms.sourcegitcommit: ae02ac950810242e2505d7d371b80210dc8a0777
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/29/2022
ms.locfileid: "8491984"
---
# <a name="manage-environments"></a>Gerenciar ambientes

## <a name="switch-environments"></a>Alternar ambientes

Selecione o controle de **Ambiente** no canto superior direito da página para alterar os ambientes.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de tela do controle para alternar ambientes.":::

Os administradores podem [criar](create-environment.md) e gerenciar ambientes.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Você pode editar alguns dos detalhes dos ambientes existentes.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

2.  Selecione o ícone **Editar**.

3. Na caixa **Editar ambiente**, você pode atualizar as configurações de ambiente.

Para obter mais informações sobre configurações de ambiente, consulte [Crie um novo ambiente](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Conectar-se ao Microsoft Dataverse
   
A etapa **Microsoft Dataverse** permite conectar o Customer Insights com o seu ambiente Dataverse. 

Forneça seu próprio ambiente do Microsoft Dataverse para compartilhar dados (perfis e insights) com aplicativos de negócios baseados no Dataverse, como o Dynamics 365 Marketing ou aplicativos baseados em modelo no Power Apps.

Para usar [modelos de previsão prontos para uso](predictions-overview.md#out-of-box-models), configure o compartilhamento de dados com o Dataverse. Ou você pode ativar a ingestão de dados de fontes de dados na infraestrutura local, fornecendo o URL do ambiente Microsoft Dataverse que sua organização administra.

Ao marcar a caixa de seleção de compartilhamento de dados para ativar o compartilhamento de dados com o Microsoft Dataverse, uma atualização completa e única das suas fontes de dados e de todos os outros processos será acionada.

> [!IMPORTANT]
> 1. O Customer Insights e o Dataverse devem estar na mesma região para habilitar o compartilhamento de dados.
> 1. Você deve ter uma função de administrador global no ambiente do Dataverse. Verifique se esse [ambiente do Dataverse está associado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de segurança e verifique se você foi incluído nesses grupos.
> 1. Nenhum ambiente existente do Customer Insights já está associado àquele ambiente do Dataverse. Veja como [remover uma conexão existente com um ambiente do Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).

:::image type="content" source="media/dataverse-enable-datasharing.png" alt-text="Opções de configuração para habilitar o compartilhamento de dados com o Microsoft Dataverse.":::

### <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Habilitar o compartilhamento de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage (versão preliminar)

Se o seu ambiente estiver configurado para usar o próprio Azure Data Lake Storage para armazenar dados do Customer Insights, é preciso fazer configurações adicionais para ativar o compartilhamento de dados com o Microsoft Dataverse.

1. Crie dois grupos de segurança na sua assinatura do Azure, um grupo **Leitor** e um **Colaborador**, depois defina o serviço do Microsoft Dataverse como o proprietário de ambos os grupos de segurança.
2. Gerencie a Lista de controle de acesso (ACL) no contêiner CustomerInsights na sua conta de armazenamento por meio desses grupos de segurança. Adicione o serviço do Microsoft Dataverse e qualquer aplicativo de negócios baseado no Dataverse, como o Dynamics 365 Marketing, no grupo de segurança **Leitor** com permissões **somente leitura**. Adicione *apenas* o aplicativo do Customers Insights no grupo de segurança **Colaborador** para conceder ambas as permissões de **leitura e gravação** para editar perfis e insights.
   
#### <a name="prerequisites"></a>Pré-requisitos

Para executar os scripts do PowerShell, você precisa importar os três módulos a seguir. 

1. Instale a versão mais recente do [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. No seu PC, pressione a tecla Windows no teclado e pesquise **Windows PowerShell** e selecione a opção **Executar como administrador**.
   1. Na janela do PowerShell que é aberta, digite `Install-Module AzureAD`.
2. Importe os três módulos.
    1. Na janela do PowerShell, digite `Install-Module -Name Az.Accounts` e siga as etapas. 
    1. Repita para `Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

#### <a name="configuration-steps"></a>Etapas de configuração

1. Faça o download dos dois scripts do PowerShell que você precisa executar do [repositório do GitHub](https://github.com/trin-msft/byol) dos nossos engenheiros.
    1. `CreateSecurityGroups.ps1`
       - Para executar esse script do PowerShell, você precisa das permissões de *administração do locatário*. 
       - Esse script do PowerShell cria dois grupos de segurança na sua assinatura do Azure: um para o grupo Leitor e outro para o grupo Colaborador, além de tornar o serviço do Microsoft Dataverse o proprietário desses dois grupos.
       - Execute esse script do PowerShell no Windows PowerShell informando o ID da assinatura do Azure contendo seu Azure Data Lake Storage. Abra o script do PowerShell em um editor para ver informações adicionais e a lógica implementada.
       - Salve os dois valores de ID do grupo de segurança gerados por esse script para usar no script `ByolSetup.ps1`.
       
        > [!NOTE]
        > A criação do grupo de segurança pode ser desabilitada no seu locatário. Nesse caso, seria necessário fazer uma configuração manual, e seu administrador do Azure AD precisaria [habilitar a criação do grupo de segurança](/azure/active-directory/enterprise-users/groups-self-service-management).

    2. `ByolSetup.ps1`
        - Você precisa da permissão *Proprietário de Dados do Blob de Armazenamento* no nível da conta de armazenamento/do contêiner para executar esse script, senão o script vai criar uma para você. Sua atribuição de função pode ser removida manualmente após a execução bem-sucedida do script.
        - Esse script do PowerShell adiciona o controle de acesso baseado em função (RBAC) necessário para o serviço do Microsoft Dataverse e quaisquer aplicativos empresariais baseados no Dataverse. Ele também atualiza a Lista de controle de acesso (ACL) no contêiner CustomerInsights para os grupos de segurança criados com o script `CreateSecurityGroups.ps1`. O grupo Colaborador terá a permissão *rwx* e o grupo Leitor terá apenas a permissão *r-x*.
        - Execute esse script do PowerShell no Windows PowerShell informando o ID da assinatura do Azure contendo seu Azure Data Lake Storage, o nome da conta de armazenamento, o nome do grupo de recursos e os valores de ID dos grupos de segurança Leitor e Colaborador. Abra o script do PowerShell em um editor para ver informações adicionais e a lógica implementada.
        - Copie a string de saída depois de executar o script com êxito. A string de saída se parece com isso: `https: //DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`
        
2. Insira a string de saída copiada acima no campo **Identificador de permissões** da etapa de configuração do ambiente para o Microsoft Dataverse.

:::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opções de configuração para habilitar o compartilhamento de dados do seu próprio Azure Data Lake Storage com o Microsoft Dataverse.":::

O Customer Insights não suporta os seguintes cenários de compartilhamento de dados:
- Se você ativar o compartilhamento de dados com o Dataverse, você não será capaz de [criar valores previstos ou ausentes em uma entidade](predictions.md).
- Se você habilitar o compartilhamento de dados com o Dataverse, não será possível ver nenhum relatório opcional do PowerBI Embedded no seu ambiente do Customer Insights.

### <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Remover uma conexão existente com um ambiente do Dataverse

Ao conectar a um ambiente do Dataverse, a mensagem de erro **Esta organização CDS já está anexada a outra instância do Customer Insights** significa que o ambiente do Dataverse já foi usado em um ambiente do Customer Insights. Você pode remover a conexão existente como administrador global no ambiente do Dataverse. Pode levar algumas horas para as alterações serem aplicadas.

1. Acesse [Power Apps](https://make.powerapps.com).
1. Selecione o ambiente no seletor.
1. Acesse **Soluções**
1. Desinstale ou exclua a solução chamada **Complemento do Cartão do Cliente do Dynamics 365 Customer Insights (versão preliminar)**.

ou 

1. Abra seu ambiente do Dataverse.
1. Vá para **Configurações Avançadas** > **Soluções**.
1. Desinstale a solução **CustomerInsightsCustomerCard**.

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Como administrador, você pode optar por copiar a configuração de um ambiente existente ao criar um novo. 

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

## <a name="set-up-a-copied-environment"></a>Configurar um ambiente copiado

Ao copiar a configuração do ambiente, os dados a seguir *não* são copiados:

- Perfis do cliente.
- Credenciais da fonte de dados. Você precisará fornecer as credenciais para cada fonte de dados e atualizar as fontes de dados manualmente.
- Fontes de dados da pasta do Common Data Model e do data lake gerenciado do Dataverse. Você precisará criar essas fontes de dados manualmente com o mesmo nome do ambiente de origem.
- Segredos de conexão que são usados para exportações e enriquecimentos. Você precisa autenticar novamente as conexões e, em seguida, reativar os enriquecimentos e as exportações. 

Ao copiar um ambiente, você verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para fontes de dados** para ver a lista de fontes de dados.

Todas as fontes de dados mostrarão um status **Credenciais Necessárias**. Edite as fontes de dados e insira as credenciais para atualizá-las.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de fontes de dados que foram copiadas e precisam de autenticação.":::

Após atualizar as fontes de dados, vá para **Dados** > **Unificar**. Aqui você encontrará configurações do ambiente de origem. Edite-os conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade unificada do cliente.

Quando a unificação de dados estiver concluída, vá para **Medidas** e **Segmentos** para atualizá-los também.

Antes de reativar as exportações e os enriquecimentos, acesse **Administrador** > **Conexões** para autenticar novamente as conexões no seu novo ambiente.

## <a name="change-the-owner-of-an-environment"></a>Altere o proprietário de um ambiente

Embora vários usuários possam ter permissões de administrador no Customer Insights, apenas um usuário é o proprietário de um ambiente. Por padrão, é o administrador que cria um ambiente inicialmente. Como administrador de um ambiente, você pode atribuir a propriedade a outro usuário com permissões de administrador.

1. Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

1. Selecione o ícone **Editar**.

1. Na caixa **Editar ambiente**, vá para a etapa **Informações básicas**.

1. No campo **Alterar proprietário do ambiente**, selecione o novo proprietário do ambiente.  

1. Selecione **Revisar e finalizar** e **Atualizar** para aplicar as alterações. 

## <a name="claim-ownership-of-an-environment"></a>Reivindicar a propriedade de um ambiente

Se o proprietário de um ambiente sair da organização ou sua conta de usuário for excluída, o ambiente não terá proprietário. Um usuário com permissões de administrador pode reivindicar a propriedade e se tornar o novo proprietário. Ele podem continuar sendo proprietário do ambiente ou [alterar a propriedade para outro administrador](#change-the-owner-of-an-environment). 

Para reivindicar a propriedade, selecione o botão **Assumir propriedade** que aparece na parte superior de cada página no Customer Insights quando o proprietário original deixou a organização.

## <a name="reset-an-existing-environment"></a>Redefinir um ambiente existente

Como proprietária do ambiente, você pode redefinir um ambiente a um estado vazio, caso queira apenas apagar todas as configurações e remover os dados ingeridos.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo. 

2.  Selecione o ambiente que deseja redefinir selecione as reticências (**...**). 

3. Escolha a opção **Redefinir**. 

4.  Para confirmar a exclusão, insira o nome do ambiente e selecione **Redefinir**.

## <a name="delete-an-existing-environment"></a>Excluir um ambiente existente

Como proprietário de um ambiente, você pode excluir um ambiente que administra.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

2.  Selecione o ambiente que deseja redefinir selecione as reticências (**...**). 

3. Escolha a opção **Excluir**. 

4.  Para confirmar a exclusão, insira o nome do ambiente e selecione **Excluir**.

> [!NOTE]
> A exclusão de um ambiente não remove a associação a um ambiente do Dataverse. Saiba como [remover uma conexão existente com um ambiente do Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
