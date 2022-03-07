---
title: Criar ambientes do Customer Insights
description: Etapas para criar ambientes com uma assinatura licenciada para o Dynamics 365 Customer Insights.
ms.date: 02/24/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: c37afd5649f8cf40d5379f3d39d0cbd96cde3bd3
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354081"
---
# <a name="create-an-environment-in-audience-insights"></a>Criar um ambiente de insights do público-alvo

Este artigo explica como criar um novo ambiente depois que sua organização comprou uma assinatura do Dynamics 365 Customer Insights. 

As organizações podem criar *dois* ambientes para cada licença do Customer Insights. Se sua organização adquire mais de uma licença, [entre em contato com nossa equipe de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade de complemento, baixe o [Guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!NOTE]
> Se você está procurando avaliar o serviço, consulte [Configurar um ambiente de avaliação](../trial-signup.md).

## <a name="create-a-new-environment"></a>Criar um novo ambiente

Depois de adquirir uma licença de assinatura do Customer Insights, o administrador global do locatário do Microsoft 365 recebe um email que o convida a criar o ambiente. Acesse [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para começar. 

Uma experiência guiada ajuda você nas etapas para reunir todas as informações necessárias para um novo ambiente. Você precisa de [permissões de administrador](permissions.md) em insights de público-alvo para criar ou gerenciar ambientes.

1. Em insights do público-alvo, abra o seletor de ambiente e selecione **+ Novo**.
  
   :::image type="content" source="../engagement-insights/media/environment-picker.png" alt-text="Selecione o seletor de ambientes.":::

1. Siga a experiência guiada descrita nas seções a seguir.

### <a name="step-1-provide-environment-information"></a>Etapa 1: Forneça informações sobre o ambiente

Na etapa **Informações básicas**, escolha se deseja criar um ambiente do zero ou [copiar dados de outro ambiente](manage-environments.md#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Caixa de diálogo para criar um ambiente do Customer Insights.":::

Forneça os detalhes a seguir:
   - **Nome**: o nome deste ambiente. Esse campo já estará preenchido se você copiou de um ambiente existente, mas é possível alterá-lo.
   - **Escolha seu negócio**: Escolha o público-alvo primário para o novo ambiente. Você pode trabalhar com clientes individuais (B2C) ou [contas de negócios](work-with-business-accounts.md) (B2B).
   - **Tipo**: selecione se você deseja criar um ambiente de produção ou de área restrita. Os ambientes de área restrita não permitem atualização de dados agendada e são destinados à pré-implementação e teste. Os ambientes de sandbox usam o mesmo público-alvo primário que o ambiente de produção atualmente selecionado.
   - **Região**: a região na qual o serviço é implantado e hospedado.

### <a name="step-2-configure-data-storage"></a>Etapa 2: Configure o armazenamento de dados

Na etapa **Armazenamento de dados**, escolha onde armazenar os dados de insights do público-alvo.

Você terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerenciado pela equipe do Customer Insights) e o **Azure Data Lake Storage** (seu próprio Azure Data Lake Storage). Por padrão, a opção de armazenamento do Customer Insights é selecionada.

:::image type="content" source="media/data-storage-environment.png" alt-text="Escolha o Azure Data Lake Storage para armazenar seus dados de insights de público-alvo.":::

Salvando dados no Azure Data Lake Storage, você concorda que os dados serão transferidos e armazenados no local geográfico apropriado para essa conta de armazenamento do Azure. Este local pode ser diferente de onde os dados são armazenados no Dynamics 365 Customer Insights. Saiba mais em [Microsoft Trust Center](https://www.microsoft.com/trust-center).

> [!NOTE]
> O Customer Insights atualmente oferece suporte para o seguinte:
> - Entidades ingeridas de fluxos de dados do Power BI que são armazenados em um data lake gerenciado pelo Microsoft Dataverse.  
> - Azure Data Lake Storage contas da mesma região do Azure que você selecionou ao criar o ambiente.
> - Contas do Azure Data Lake Storage que são Gen2 e têm *namespace hierárquico* habilitado. As contas de armazenamento do Azure Data Lake Gen1 não têm suporte.

Para a opção do Azure Data Lake Storage, você pode escolher entre uma opção baseada em recursos e outra baseada em assinatura para autenticação. Para obter mais informações, consulte [Conectar-se a uma conta do  Azure Data Lake Storage usando uma entidade de serviço do Azure](connect-service-principal.md). O nome do **Conteiner** será `customerinsights` e não pode ser alterado.

Quando os processos do sistema, como a ingestão de dados, estão concluídos, o sistema cria pastas correspondentes na conta de armazenamento que você especificou. Os arquivos de dados e os arquivos *model.json* são criados e adicionados às pastas com base no nome do processo.

Se você criar vários ambientes de Customer Insights e optar por salvar as entidades de saída desses ambientes em sua conta de armazenamento, o Customer Insights cria pastas separadas para cada ambiente com `ci_environmentID` no container.

### <a name="step-3-connect-to-microsoft-dataverse"></a>Etapa 3: Conecte ao Microsoft Dataverse
   
A etapa **Microsoft Dataverse** permite conectar o Customer Insights com o seu ambiente Dataverse.

Forneça seu próprio ambiente do Microsoft Dataverse para compartilhar dados (perfis e insights) com aplicativos de negócios baseados no Dataverse, como o Dynamics 365 Marketing ou aplicativos baseados em modelo no Power Apps. Deixe este campo vazio se você não tiver seu próprio ambiente do Dataverse e provisionaremos um para você.

Conectar-se ao seu ambiente do Dataverse também permite que você [faça a ingestão de dados de fontes de dados locais usando fluxos de dados e gateways do Power Platform](data-sources.md#add-data-from-on-premises-data-sources). Você também pode usar [ modelos de previsão prontos para uso](predictions-overview.md?tabs=b2c#out-of-box-models) conectando-se a um ambiente do Dataverse.

> [!IMPORTANT]
> O Customer Insights e o Dataverse devem estar na mesma região para habilitar o compartilhamento de dados.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartilhamento de dados com o Microsoft Dataverse habilitado automaticamente para novas instâncias de rede.":::

> [!NOTE]
> O Customer Insights não suporta os seguintes cenários de compartilhamento de dados:
> - Se salvar todos os dados no seu próprio Azure Data Lake Storage, você não poderá habilitar o compartilhamento de dados com um data lake gerenciado do Dataverse.
> - Se você ativar o compartilhamento de dados com o Dataverse, você não será capaz de [criar valores previstos ou ausentes em uma entidade](predictions.md).

### <a name="step-4-finalize-the-settings"></a>Etapa 4: Finalize a configuração

Na etapa **Revisão**, repasse todas as configurações especificadas. Quando tudo parecer correto, selecione **Criar** para configurar o ambiente. 

Você também pode alterar a maioria das configurações posteriormente. Para obter mais informações, consulte [Gerenciar ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabalhe com seu novo ambiente

Reveja os seguintes artigos para ajudá-lo a começar a configurar o Customer Insights: 

- [Adicionar mais usuários e atribuir permissões](permissions.md).
- [Ingerir suas fontes de dados](data-sources.md) e executá-las por meio do [processo de unificação de dados](data-unification.md) para obter [perfis de clientes unificados](customer-profiles.md).
- [Enriquecer os perfis de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Criar segmentos](segments.md) para agrupar clientes e [métricas](measures.md) para revisar os KPIs.
- [Configurar conexões](connections.md) e [exportações](export-destinations.md) para processar subconjuntos de seus dados em outros aplicativos.
