---
title: Trabalhar com dados do Customer Insights no Microsoft Dataverse
description: Saiba como conectar o Customer Insights e o Microsoft Dataverse e saiba quais entidades de saída são exportadas para o Dataverse.
ms.date: 08/15/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
searchScope:
- ci-system-diagnostic
- customerInsights
ms.openlocfilehash: 0d536259f310b41fe12922baeebdc4569937db08
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9303815"
---
# <a name="work-with-customer-insights-data-in-microsoft-dataverse"></a>Trabalhar com dados do Customer Insights no Microsoft Dataverse

O Customer Insights oferece a opção de disponibilizar entidades de saída no [Microsoft Dataverse](/powerapps/maker/data-platform/data-platform-intro). Essa integração permite o fácil compartilhamento de dados e o desenvolvimento personalizado por meio de uma abordagem de pouco código/nenhum código. As [entidades de saída](#output-entities) estão disponíveis como tabelas em um ambiente do Dataverse. Você pode usar os dados para qualquer outro aplicativo com base nas tabelas do Dataverse. Essas tabelas permitem cenários como fluxos de trabalho automatizados por meio do Power Automate ou a criação de aplicativos com o Power Apps.

Conectar-se ao seu ambiente do Dataverse também permite que você [faça a ingestão de dados de fontes de dados locais usando fluxos de dados e gateways do Power Platform](connect-power-query.md#add-data-from-on-premises-data-sources).

## <a name="prerequisites"></a>Pré-requisitos

- Os ambientes do Customer Insights e do Dataverse devem estar hospedados na mesma região.
- Uma função de administrador global configurada no ambiente do Dataverse. Verifique se esse [ambiente do Dataverse está associado](/power-platform/admin/control-user-access#associate-a-security-group-with-a-dataverse-environment) a determinados grupos de segurança e verifique se você foi incluído nesses grupos.
- Nenhum outro ambiente do Customer Insights está associado ao ambiente do Dataverse que você quer conectar. Veja como [remover uma conexão existente com um ambiente do Dataverse](#remove-an-existing-connection-to-a-dataverse-environment).
- Um ambiente do Microsoft Dataverse conectado a uma única conta de armazenamento se você configurar o ambiente para [usar seu Azure Data Lake Storage](own-data-lake-storage.md).

## <a name="dataverse-storage-capacity-entitlement"></a>Direito de capacidade de armazenamento do Dataverse

Uma assinatura do Customer Insights dá direito a capacidade extra em relação à [capacidade de armazenamento do Dataverse](/power-platform/admin/capacity-storage) atual da sua organização. A capacidade adicionada depende do número de perfis usados pela sua assinatura.

**Exemplo:**

Supondo que você tenha 15 GB de armazenamento de banco de dados e 20 GB de armazenamento de arquivos por 100.000 perfis de cliente. Se sua assinatura incluir 300.000 perfis de clientes, sua capacidade total de armazenamento será de 45 GB (3 x 15 GB) de armazenamento de banco de dados e 60 GB de armazenamento de arquivos (3 x 20 GB). Da mesma forma, se você tiver uma assinatura B-to-B com 30 mil contas, sua capacidade total de armazenamento será de 45 GB (3 x 15 GB) de armazenamento de banco de dados e 60 GB de armazenamento de arquivos (3 x 20 GB).

A capacidade de log não é incremental e fixa para a organização.

Para obter mais informações detalhadas sobre os direitos de capacidade, consulte o [Guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

## <a name="connect-a-dataverse-environment-to-customer-insights"></a>Conectar um ambiente do Dataverse ao Customer Insights

A etapa do **Microsoft Dataverse** permite que você conecte o Customer Insights ao seu ambiente do Dataverse, [criando um ambiente do Customer Insights](create-environment.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartilhamento de dados com o Microsoft Dataverse habilitado automaticamente para novos ambientes.":::

1. Forneça a URL para seu ambiente do Dataverse ou deixe em branco para que uma seja criada para você.

   > [!NOTE]
   > Depois de estabelecer a conexão entre o Customer Insights e o Dataverse, não altere o nome da organização no ambiente do Dataverse. O nome da organização é usado na URL do Dataverse, e um nome alterado interrompe a conexão com o Customer Insights.

   [Os administradores da Power Platform podem controlar quem pode criar ambientes do Dataverse](/power-platform/admin/control-environment-creation). Se você estiver tentando configurar um novo ambiente do Customer Insights e não conseguir, o administrador pode ter desabilitado a criação de ambientes do Dataverse para todos, exceto administradores.

1. Se você estiver usando sua própria conta do Data Lake Storage:
   1. Selecione **Habilitar o compartilhamento de dados** com o Dataverse.
   1. Insira o **Identificador de permissões**. Para obter o identificador de permissões, [habilite o compartilhamento de dados com o Dataverse de seu próprio Azure Data Lake Storage](#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

## <a name="enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview"></a>Habilitar o compartilhamento de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage (versão preliminar)

Em [sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md), verifique se o usuário que está configurando o ambiente do Customer Insights tem pelo menos permissões de **Leitor de Dados do Storage Blob** no contêiner `customerinsights` na conta de armazenamento.

### <a name="limitations"></a>Limitações

- Apenas um mapeamento individual entre uma organização do Dataverse e uma conta do Azure Data Lake Storage. Depois que uma organização do Dataverse estiver conectada a uma conta de armazenamento, ela não poderá se conectar a outra conta de armazenamento. Essa limitação impede que o Dataverse preencha várias contas de armazenamento.
- O compartilhamento de dados não funcionará se uma configuração de Link Privado do Azure for necessária para acessar sua conta do Azure Data Lake Storage porque ela está atrás de um firewall. No momento, o Dataverse não oferece suporte à conexão com pontos de extremidade privados por meio de um Link Privado.

### <a name="set-up-security-groups-on-your-own-azure-data-lake-storage"></a>Configurar grupos de segurança em seu próprio Azure Data Lake Storage

1. Crie dois grupos de segurança na sua assinatura do Azure, um grupo **Leitor** e um **Colaborador**, depois defina o serviço do Microsoft Dataverse como o proprietário de ambos os grupos de segurança.

1. Gerencie a Lista de controle de acesso (ACL) no contêiner `customerinsights` na sua conta de armazenamento por meio desses grupos de segurança.
   1. Adicione o serviço do Microsoft Dataverse e qualquer aplicativo de negócios baseado no Dataverse, como o Dynamics 365 Marketing, no grupo de segurança **Leitor** com permissões **somente leitura**.
   1. Adicione *apenas* o aplicativo do Customers Insights no grupo de segurança **Colaborador** para conceder ambas as permissões de **leitura e gravação** para editar perfis e insights.

### <a name="set-up-powershell"></a>Configurar o PowerShell

Configure o PowerShell para executar scripts do PowerShell.

1. Instale a versão mais recente do [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2).
   1. No seu PC, pressione a tecla Windows no teclado e pesquise **Windows PowerShell** e selecione a opção **Executar como administrador**.
   1. Na janela do PowerShell que é aberta, digite `Install-Module AzureAD`.

1. Importe os três módulos.
   1. Na janela do PowerShell, digite `Install-Module -Name Az.Accounts` e siga as etapas.
   1. Repita para `Install-Module -Name Az.Resources` e `Install-Module -Name Az.Storage`.

### <a name="execute-powershell-scripts-and-obtain-the-permission-identifier"></a>Executar scripts do PowerShell e obter o identificador de permissões

1. Faça o download dos dois scripts do PowerShell que você precisa executar do [repositório do GitHub](https://github.com/trin-msft/byol) dos nossos engenheiros.
   - `CreateSecurityGroups.ps1`: requer permissões de administrador de locatário.
   - `ByolSetup.ps1`: requer permissões de proprietário de dados do blob de armazenamento no nível da conta/contêiner de armazenamento. Este script criará a permissão para você. Sua atribuição de função pode ser removida manualmente após a execução bem-sucedida do script.

1. Execute `CreateSecurityGroups.ps1` no Windows PowerShell informando o ID da assinatura do Azure contendo seu Azure Data Lake Storage. Abra o script do PowerShell em um editor para ver informações adicionais e a lógica implementada.

   Esse script cria dois grupos de segurança em sua assinatura do Azure: um para o grupo Leitor e outro para o grupo Colaborador. O serviço do Microsoft Dataverse é o proprietário desses dois grupos de segurança.

1. Salve os dois valores de ID do grupo de segurança gerados por esse script para usar no script `ByolSetup.ps1`.

   > [!NOTE]
   > A criação do grupo de segurança pode ser desabilitada no seu locatário. Nesse caso, seria necessário fazer uma configuração manual, e seu administrador do Azure AD precisaria [habilitar a criação do grupo de segurança](/azure/active-directory/enterprise-users/groups-self-service-management).

1. Execute `ByolSetup.ps1` no Windows PowerShell informando o ID da assinatura do Azure contendo seu Azure Data Lake Storage, o nome da conta de armazenamento, o nome do grupo de recursos e os valores de ID dos grupos de segurança Leitor e Colaborador. Abra o script do PowerShell em um editor para ver informações adicionais e a lógica implementada.

   Esse script adiciona o controle de acesso baseado em função necessário para o serviço do Microsoft Dataverse e quaisquer aplicativos empresariais baseados no Dataverse. Ele também atualiza a Lista de controle de acesso (ACL) no contêiner `customerinsights` para os grupos de segurança criados com o script `CreateSecurityGroups.ps1`. O grupo Colaborador recebe a permissão *rwx* e o grupo Leitor recebe apenas a permissão *r-x*.

1. Copie a string de saída que se parece com: `https://DVBYODLDemo/customerinsights?rg=285f5727-a2ae-4afd-9549-64343a0gbabc&cg=720d2dae-4ac8-59f8-9e96-2fa675dbdabc`

1. Insira a string de saída copiada no campo **Identificador de permissões** da etapa de configuração do ambiente para o Microsoft Dataverse.

   :::image type="content" source="media/dataverse-enable-datasharing-BYODL.png" alt-text="Opções de configuração para habilitar o compartilhamento de dados do seu próprio Azure Data Lake Storage com o Microsoft Dataverse.":::

## <a name="remove-an-existing-connection-to-a-dataverse-environment"></a>Remover uma conexão existente com um ambiente do Dataverse

Ao conectar a um ambiente do Dataverse, a mensagem de erro **Esta organização CDS já está anexada a outra instância do Customer Insights** significa que o ambiente do Dataverse já foi usado em um ambiente do Customer Insights. Você pode remover a conexão existente como administrador global no ambiente do Dataverse. Pode levar algumas horas para as alterações serem aplicadas.

1. Acesse [Power Apps](https://make.powerapps.com).
1. Selecione o ambiente no seletor.
1. Acesse **Soluções**.
1. Desinstale ou exclua a solução chamada **Complemento do Cartão do Cliente do Dynamics 365 Customer Insights (versão preliminar)**.

ou

1. Abra seu ambiente do Dataverse.
1. Vá para **Configurações Avançadas** > **Soluções**.
1. Desinstale a solução **CustomerInsightsCustomerCard**.

Se a remoção da conexão falhar devido a dependências, você precisará removê-las também. Para obter mais informações, leia [Como remover dependências](/power-platform/alm/removing-dependencies).

## <a name="output-entities"></a>Entidades de saída

Algumas entidades de saída do Customer Insights estão disponíveis como tabelas no Dataverse. As seções abaixo descrevem o esquema esperado dessas tabelas.

- [Perfil do Cliente](#customerprofile)
- [AlternateKey](#alternatekey)
- [UnifiedActivity](#unifiedactivity)
- [CustomerMeasure](#customermeasure)
- [Enriquecimento](#enrichment)
- [Previsão](#prediction)
- [Associação ao segmento](#segment-membership)

### <a name="customerprofile"></a>Perfil do Cliente

Esta tabela contém o perfil de cliente unificado do Customer Insights. O esquema para um perfil de cliente unificado depende das entidades e dos atributos usados no processo de unificação de dados. Um esquema de perfil de cliente geralmente contém um subconjunto dos atributos da [Definição do Common Data Model do Perfil do Cliente](/common-data-model/schema/core/applicationcommon/foundationcommon/crmcommon/solutions/customerinsights/customerprofile).

### <a name="alternatekey"></a>AlternateKey

A tabela AlternateKey contém as chaves das entidades que participaram do processo de unificação.

|Column  |Digitar  |Descrição  |
|---------|---------|---------|
|DataSourceName    |Cadeia de Caracteres         | Nome da fonte de dados. Por exemplo: `datasource5`        |
|EntityName        | String        | Nome da entidade no Customer Insights. Por exemplo: `contact1`        |
|AlternateValue    |String         |ID alternativa que é mapeada para a ID do cliente. Exemplo: `cntid_1078`         |
|KeyRing           | Texto com várias linhas        | Valor JSON  </br> Exemplo: [{"dataSourceName":" datasource5 ",</br>"entityName":" contact1",</br>"preferredKey":" cntid_1078",</br>"keys":[" cntid_1078"]}]       |
|CustomerId         | Cadeia de Caracteres        | ID do perfil de cliente unificado.         |
|AlternateKeyId     | GUID         |  GUID determinístico AlternateKey baseado em msdynci_identifier       |
|msdynci_identifier |   Cadeia de Caracteres      |   `DataSourceName|EntityName|AlternateValue`  </br> Exemplo: `testdatasource|contact1|cntid_1078`    |

### <a name="unifiedactivity"></a>UnifiedActivity

Esta tabela contém atividades de usuários que estão disponíveis no Customer Insights.

| Column            | Type        | Description                                                                              |
|-------------------|-------------|------------------------------------------------------------------------------------------|
| CustomerId        | String      | ID do Perfil do cliente                                                                      |
| ActivityId        | String      | ID interna da atividade do cliente (chave primária)                                       |
| SourceEntityName  | Cadeia de Caracteres      | Nome da entidade de origem                                                                |
| SourceActivityId  | Cadeia de Caracteres      | Chave primária da entidade de origem                                                       |
| ActivityType      | Cadeia de Caracteres      | Tipo de atividade semântica ou nome da atividade personalizada                                        |
| ActivityTimeStamp | DATETIME    | Carimbo de data/hora da atividade                                                                      |
| Title             | String      | Título ou nome da atividade                                                               |
| Description       | Cadeia de Caracteres      | Descrição da atividade                                                                     |
| URL               | Cadeia de Caracteres      | Link para uma URL externa específica à atividade                                         |
| SemanticData      | Cadeia de caracteres JSON | Inclui uma lista de pares de chave/valor para os campos de mapeamento semântico específicos ao tipo de atividade |
| RangeIndex        | Cadeia de Caracteres      | Carimbo de data/hora Unix usado para classificar a linha do tempo de atividades e as consultas de intervalo em vigor |
| mydynci_unifiedactivityid   | GUID | ID interna da atividade do cliente (ActivityId) |

### <a name="customermeasure"></a>CustomerMeasure

Esta tabela contém os dados de saída de medidas baseadas em atributos do cliente.

| Column             | Digitar             | Descrição                 |
|--------------------|------------------|-----------------------------|
| CustomerId         | Cadeia de Caracteres           | ID do Perfil do cliente        |
| Medidas           | Cadeia de caracteres JSON      | Inclui uma lista de pares de chave/valor para o nome da medida e valores para o cliente fornecido | 
| msdynci_identifier | Cadeia de Caracteres           | `Customer_Measure|CustomerId` |
| msdynci_customermeasureid | GUID      | ID do Perfil do cliente |


### <a name="enrichment"></a>Enriquecimento

Esta tabela contém a saída do processo de enriquecimento.

| Column               | Digitar             |  Descrição                                          |
|----------------------|------------------|------------------------------------------------------|
| CustomerId           | Cadeia de Caracteres           | ID do Perfil do cliente                                 |
| EnrichmentProvider   | Cadeia de Caracteres           | Nome do provedor para o enriquecimento                                  |
| EnrichmentType       | Cadeia de Caracteres           | Tipo de enriquecimento                                      |
| Valores               | Cadeia de caracteres JSON      | Lista de atributos produzidos pelo processo de enriquecimento |
| msdynci_enrichmentid | GUID             | GUID determinístico gerado a partir de msdynci_identifier |
| msdynci_identifier   | Cadeia de Caracteres           | `EnrichmentProvider|EnrichmentType|CustomerId`         |

### <a name="prediction"></a>Previsão

Esta tabela contém a saída das previsões do modelo.

| Column               | Type        | Description                                          |
|----------------------|-------------|------------------------------------------------------|
| CustomerId           | String      | ID do Perfil do cliente                                  |
| ModelProvider        | String      | Nome do provedor do modelo                                      |
| Modelo                | Cadeia de Caracteres      | Nome do modelo                                                |
| Valores               | Cadeia de caracteres JSON | Lista de atributos produzidos pelo modelo |
| msdynci_predictionid | GUID        | GUID determinístico gerado a partir de msdynci_identifier | 
| msdynci_identifier   | String      |  `Model|ModelProvider|CustomerId`                      |

### <a name="segment-membership"></a>Associação ao segmento

Esta tabela contém informações de associação ao segmento de perfis do cliente.

| Column        | Type | Description                        |
|--------------------|--------------|-----------------------------|
| CustomerId        | String       | ID do Perfil do Cliente        |
| SegmentProvider      | String       | Aplicativo que publica os segmentos.      |
| SegmentMembershipType | String       | Tipo de cliente registrado por esta associação ao segmento. Oferece suporte a vários tipos, como Cliente, Contato ou Conta. Padrão: Cliente  |
| Segmentos       | Cadeia de caracteres JSON  | Lista de segmentos exclusivos dos quais o perfil do cliente é membro      |
| msdynci_identifier  | String   | Identificador exclusivo do registro da associação ao segmento. `CustomerId|SegmentProvider|SegmentMembershipType|Name`  |
| msdynci_segmentmembershipid | GUID      | GUID determinístico gerado de `msdynci_identifier`          |


[!INCLUDE [footer-include](includes/footer-banner.md)]
