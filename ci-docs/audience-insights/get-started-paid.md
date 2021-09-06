---
title: Criar e configurar uma licença paga do Customer Insights
description: Etapas para obter uma assinatura licenciada do Dynamics 365 Customer Insights e configurá-lo.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: b5f76f4c468b88aaf7037dbd2ee3bed449fbeaa5f645d52278eee05b36b4e328
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7034438"
---
# <a name="get-started-with-a-paid-subscription"></a>Introdução a uma assinatura paga

Este artigo explica como criar um novo ambiente depois que sua organização comprou uma assinatura do Dynamics 365 Customer Insights. Se quiser comprar o Customer Insights, nossas opções de contato estão listadas no [site do Dynamics 365 Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/). 

Se você quiser experimentar o serviço e os recursos, consulte [Configure um ambiente de teste](get-started-trial.md).

## <a name="create-an-environment-in-an-existing-organization"></a>Criar um ambiente em uma organização existente

Depois que comprar uma licença de assinatura do Customer Insights, o administrador global do locatário do Microsoft 365 receberá um email convidando-o para criar o ambiente. Acesse [https://home.ci.dynamics.com/start](https://home.ci.dynamics.com/start) para começar. 

O Customer Insights não é licenciado por usuário, portanto, não será exibido na área Licenças. Se estiver procurando a licença no centro de administração do Microsoft 365, acesse **Seus produtos**. 

> [!NOTE]
> As organizações podem criar *dois* ambientes para cada licença do Customer Insights. Se a sua organização adquirir mais de uma licença, [entre em contato com a nossa equipe de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade de complemento, baixe o [Guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

Para criar um ambiente:

1. Na caixa de diálogo **Criar um ambiente**, selecione **Novo ambiente**.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Caixa de diálogo para criar um ambiente do Customer Insights.":::

   Recomendamos começar a configurar um ambiente do zero. No entanto, se for um administrador ou membro de um ambiente de teste, você poderá [copiar dados de outro ambiente](manage-environments.md#copy-the-environment-configuration), escolhendo **Copiar do ambiente existente**. Você verá uma lista de todos os ambientes disponíveis da sua organização, dos quais é possível copiar dados.

1. Forneça os detalhes a seguir:
   - **Nome**: o nome deste ambiente. Esse campo já estará preenchido se você copiou de um ambiente existente, mas é possível alterá-lo.
   - **Região**: a região na qual o serviço é implantado e hospedado.
   - **Tipo**: selecione se você deseja criar um ambiente de produção ou de área restrita. Os ambientes de área restrita não permitem atualização de dados agendada e são destinados à pré-implementação e teste.
   
1. Opcionalmente, é possível selecionar **Configurações avançadas**:

   - **Salvar todos os dados no**: especifica onde você deseja armazenar os dados de saída gerados do Customer Insights. Você terá duas opções: **Armazenamento do Customer Insights** (um Azure Data Lake gerenciado pela equipe do Customer Insights) e **Azure Data Lake Storage** (seu próprio Azure Data Lake Storage). Por padrão, a opção de armazenamento do Customer Insights é selecionada.

     > [!NOTE]
     > Ao salvar dados no Azure Data Lake Storage, você concorda que os dados serão transferidos e armazenados na localização geográfica adequada para a conta de armazenamento do Azure, que pode ser diferente de onde os dados são armazenados no Dynamics 365 Customer Insights. [Saiba mais no Microsoft Trust Center.](https://www.microsoft.com/trust-center)
     >
     > No momento, entidades ingeridas de fluxos de dados do Power BI são armazenadas no Data Lake gerenciado pelo Microsoft Dataverse. 
     > 
     > Oferecemos suporte apenas para contas do Azure Data Lake Storage da mesma região Azure que você selecionou ao criar o ambiente. 
     > 
     > Oferecemos suporte apenas a contas do Azure Data Lake Storage que tenham um namespace hierárquico hierárquico habilitado.


   - Para a opção do Azure Data Lake Storage, você pode escolher entre uma opção baseada em recursos e outra baseada em assinatura para autenticação. Para obter mais informações, consulte [Conectar insights de público-alvo a uma conta do Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure](connect-service-principal.md). O nome do **Contêiner** não pode ser alterado e será `customerinsights`.
   
   - Se você quiser usar [modelos prontos para uso](predictions-overview.md#out-of-box-models), configure o compartilhamento de dados com o Microsoft Dataverse ou habilite a ingestão de dados de fontes de dados locais, forneça a URL do ambiente do Microsoft Dataverse em **Configurar o compartilhamento de dados com o Microsoft Dataverse e habilitar recursos adicionais**. Selecione **Habilitar compartilhamento de dados** para compartilhar dados de saída do Customer Insights com um Microsoft Dataverse Managed Data Lake.

     > [!NOTE]
     > - Atualmente, não há suporte para o compartilhamento de dados com o Microsoft Dataverse Managed Data Lake ao salvar todos os dados no seu Azure Data Lake Storage.
     > - No momento, não há suporte para [Previsão de valores ausentes em uma entidade](predictions.md) ao habilitar o compartilhamento de dados com o Data Lake Gerenciado do Microsoft Dataverse.

     :::image type="content" source="media/Datasharing-with-DataverseMDL.png" alt-text="Opções de configuração para habilitar o compartilhamento de dados com o Microsoft Dataverse.":::

   Quando os processos do sistema, como a ingestão de dados, são concluídos, o sistema cria pastas correspondentes na conta de armazenamento que você especificou. Os arquivos de dados e os arquivos model.json são criados e adicionados a pastas com base no nome do processo.

   Se você criar vários ambientes do Customer Insights e optar por salvar as entidades de saída desses ambientes na sua conta de armazenamento, pastas separadas serão criadas para cada ambiente com ci_<environmentid> no contêiner.

1. Selecione **Criar** para configurar o ambiente. 

## <a name="configure-an-environment"></a>Configurar um ambiente

Examine os artigos a seguir para ajudá-lo a começar a configurar o Customer Insights. 

- [Adicionar mais usuários e atribuir permissões](permissions.md).
- [Ingerir suas fontes de dados](data-sources.md) e executá-las por meio do [processo de unificação de dados](data-unification.md) para obter [perfis de clientes unificados](customer-profiles.md).
- [Enriquecer os perfis de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- Criar [segmentos](segments.md) para agrupar clientes e KPIs de análise de [medidas](measures.md).
- Configurar [conexões](connections.md) e [exportações](export-destinations.md) para processar subconjuntos de seus dados em outros aplicativos.
