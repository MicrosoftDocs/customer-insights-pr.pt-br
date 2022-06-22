---
title: Como criar um novo ambiente
description: Etapas para criar ambientes para o Dynamics 365 Customer Insights.
ms.date: 05/31/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: mukeshpo
ms.author: mukeshpo
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-home
- customerInsights
ms.openlocfilehash: 6dfaa09cd80498e9a4e4dea6a07ce6e9d29105e2
ms.sourcegitcommit: 5e26cbb6d2258074471505af2da515818327cf2c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/14/2022
ms.locfileid: "9011531"
---
# <a name="how-to-create-a-new-environment"></a>Como criar um novo ambiente

Depois de [adquirir uma licença de assinatura do Dynamics 365 Customer Insights](paid-license.md), o administrador global do locatário do Microsoft 365 recebe um email que o convida a criar o ambiente. Acesse [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para começar. Nesse cenário, você pode acessar diretamente a [Etapa 1: forneça informações básicas](#step-1-provide-basic-information).

Após a criação do primeiro ambiente, o administrador global do locatário do Microsoft 365 pode [adicionar usuários de sua organização como administradores](permissions.md). De agora em diante, esses administradores podem gerenciar usuários e ambientes. Se sua organização adquirir mais de uma licença do Customer Insights, [entre em contato com nossa equipe de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade adicional, consulte o [guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544).

> [!TIP]
> Se você está procurando avaliar o serviço, consulte [Configurar um ambiente de avaliação](trial-signup.md).

## <a name="prerequisites"></a>Pré-requisitos

Você precisa de [permissões de administrador](permissions.md) no Customer Insights para criar ou gerenciar ambientes.

## <a name="start-the-environment-creation-process"></a>Inicie o processo de criação do ambiente

1. Abra o seletor de ambiente e selecione **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Selecione o seletor de ambientes.":::

1. Siga a experiência guiada descrita nas seções a seguir para fornecer todas as informações necessárias para um novo ambiente. Se você configurou um ambiente anteriormente, também pode [copiar a configuração](#copy-the-environment-configuration).

## <a name="step-1-provide-basic-information"></a>Etapa 1: forneça informações básicas

Na etapa **Informações básicas**, escolha se deseja criar um ambiente do zero ou [copiar dados de outro ambiente](#copy-the-environment-configuration).

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Caixa de diálogo para criar um ambiente do Customer Insights.":::

Forneça os detalhes a seguir:

- **Nome**: o nome deste ambiente. Esse campo já estará preenchido se você copiou de um ambiente existente, mas é possível alterá-lo.
- **Escolha seu negócio**: Escolha o público-alvo primário para o novo ambiente. Você pode trabalhar com clientes individuais (B2C) ou [contas de negócios](work-with-business-accounts.md) (B2B). Se sua organização faz negócios principalmente com indivíduos, como um varejista ou uma cafeteria, escolha consumidores individuais. Caso seu público-alvo principal seja outras empresas, como uma montadora de automóveis ou uma empresa de papel, escolha contas comerciais.
- **Tipo**: selecione se você deseja criar um ambiente de produção ou de área restrita. Os ambientes de área restrita não permitem atualização de dados agendada e são destinados à pré-implementação e teste. Os ambientes de sandbox usam o mesmo público-alvo primário que o ambiente de produção atualmente selecionado.
- **Região**: a região na qual o serviço é implantado e hospedado. Para [usar sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md) ou [conectar-se a uma organização existente do Microsoft Dataverse](customer-insights-dataverse.md), o ambiente do Customer Insights deve estar na mesma região.

## <a name="step-2-configure-data-storage"></a>Etapa 2: Configure o armazenamento de dados

Na etapa **Armazenamento de dados**, escolha onde armazenar os dados do Customer Insights.

Há duas opções para você escolher:

- **Armazenamento do Customer Insights**: o armazenamento de dados é gerenciado pela equipe do Customer Insights. É a opção padrão e, a menos que haja requisitos específicos para armazenar dados em sua própria conta de armazenamento, recomendamos usar essa opção.
- **Azure Data Lake Storage**: especifique sua própria conta do Azure Data Lake Storage para armazenar os dados e ter controle total de onde os dados são armazenados. Para obter mais informações, leia [Usar sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md).

:::image type="content" source="media/data-storage-environment.png" alt-text="Escolha a opção preferida para armazenar seus dados.":::

## <a name="step-3-connect-to-microsoft-dataverse"></a>Etapa 3: Conecte ao Microsoft Dataverse

A etapa **Microsoft Dataverse** permite conectar o Customer Insights com o seu ambiente Dataverse. Compartilhe dados com o Dataverse para usá-los com aplicativos de negócios baseados no Dataverse, como o Dynamics 365 Marketing ou aplicativos baseados em modelo no Power Apps.


Deixe este campo vazio se você não tiver seu próprio ambiente do Dataverse e criaremos um para você.

Para obter mais informações, leia [Trabalhar com dados do Customer Insights no Microsoft Dataverse](customer-insights-dataverse.md).

:::image type="content" source="media/dataverse-provisioning.png" alt-text="compartilhamento de dados com o Microsoft Dataverse habilitado automaticamente para novos ambientes de rede.":::

### <a name="step-4-finalize-the-settings"></a>Etapa 4: Finalize a configuração

Na etapa **Revisão**, repasse todas as configurações especificadas. Quando tudo parecer correto, selecione **Criar** para configurar o ambiente.

Você pode alterar algumas das configurações posteriormente. Para obter mais informações, consulte [Gerenciar ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabalhe com seu novo ambiente

Reveja os seguintes artigos para ajudá-lo a começar a configurar o Customer Insights:

- [Adicionar mais usuários e atribuir permissões](permissions.md).
- [Ingerir suas fontes de dados](data-sources.md) e executá-las por meio do [processo de unificação de dados](data-unification.md) para obter [perfis de cliente unificados](customer-profiles.md).
- [Enriquecer os perfis de cliente unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Criar segmentos](segments.md) para agrupar clientes e [métricas](measures.md) para revisar os KPIs.
- [Configurar conexões](connections.md) e [exportações](export-destinations.md) para processar subconjuntos de seus dados em outros aplicativos.

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Como administrador, você pode optar por copiar a configuração de um ambiente existente ao criar um novo.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de tela das opções de configuração nas configurações do ambiente.":::

Você verá uma lista de todos os ambientes disponíveis da sua organização, dos quais é possível copiar dados.

As seguintes configurações são copiadas:

- Fontes de dados importadas via Power Query
- Configuração de unificação de dados
- Segmentos
- Medidas
- Relações
- Atividades
- Índice de filtro e pesquisa
- Exportações
- Atualizar agenda
- Enriquecimentos
- Modelos de previsão
- Atribuições de função

## <a name="set-up-a-copied-environment"></a>Configurar um ambiente copiado

Ao copiar a configuração do ambiente, você precisa passar por algumas etapas extras para confirmar as credenciais:

- Perfis do cliente. Primeiro, autentique e ingira suas fontes de dados e execute a unificação de dados para recriar os perfis dos clientes.
- Credenciais da fonte de dados. É preciso fornecer as credenciais de cada fonte de dados para autenticá-las e atualizá-las manualmente.
- Fontes de dados da pasta do Common Data Model e do Dataverse. Você precisa criar essas fontes de dados manualmente com o mesmo nome do ambiente de origem.
- Segredos de conexão que são usados para exportações e enriquecimentos. Você precisa autenticar novamente as conexões e, em seguida, reativar os enriquecimentos e as exportações.

Você verá uma mensagem de confirmação quando o ambiente copiado for criado. Selecione **Ir para fontes de dados** para ver a lista de fontes de dados.

Todas as fontes de dados mostrarão um status **Credenciais Necessárias**. Edite as fontes de dados e insira as credenciais para atualizá-las.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de fontes de dados que foram copiadas e precisam de autenticação.":::

Após atualizar as fontes de dados, vá para **Dados** > **Unificar**. Aqui você encontrará configurações do ambiente de origem. Edite-os conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade unificada do cliente.

Quando a unificação de dados estiver concluída, vá para **Medidas** e **Segmentos** para atualizá-los também.

Antes de reativar as exportações e os enriquecimentos, acesse **Administrador** > **Conexões** para autenticar novamente as conexões no seu novo ambiente.

[!INCLUDE [footer-include](includes/footer-banner.md)]
