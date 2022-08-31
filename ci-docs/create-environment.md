---
title: Criar um novo ambiente
description: Etapas para criar ambientes no Dynamics 365 Customer Insights.
ms.date: 08/15/2022
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
ms.openlocfilehash: 0a45e2fd2bdb7b85883a536f8b42ee650e54db7e
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304229"
---
# <a name="create-a-new-environment"></a>Criar um novo ambiente

Depois de [adquirir uma licença de assinatura do Dynamics 365 Customer Insights](paid-license.md), o administrador global do locatário do Microsoft 365 recebe um email que o convida a criar o ambiente. Acesse [https://home.ci.ai.dynamics.com/start](https://home.ci.ai.dynamics.com/start) para começar. Nesse cenário, comece com [Etapa 1: forneça informações básicas](#step-1-provide-basic-information).

Após a criação do primeiro ambiente, o administrador global do locatário do Microsoft 365 pode [adicionar usuários de sua organização como administradores](permissions.md). Esses administradores podem gerenciar usuários e ambientes. Se sua organização adquirir mais de uma licença do Customer Insights, [entre em contato com nossa equipe de suporte](https://go.microsoft.com/fwlink/?linkid=2079641) para aumentar o número de ambientes disponíveis. Para obter mais informações sobre capacidade e capacidade adicional, consulte o [guia de licenciamento do Dynamics 365](https://go.microsoft.com/fwlink/?LinkId=866544). Depois de ter a capacidade de criar ambientes adicionais, vá para [Iniciar o processo de criação do ambiente](#start-the-environment-creation-process).

> [!TIP]
> Se você está procurando avaliar o serviço, consulte [Configurar um ambiente de avaliação](trial-signup.md).

## <a name="prerequisites"></a>Pré-requisitos

[Permissões de administrador](permissions.md) no Customer Insights

## <a name="start-the-environment-creation-process"></a>Inicie o processo de criação do ambiente

1. Abra o seletor de ambiente e selecione **+ Novo**.
  
   :::image type="content" source="media/environment-picker.png" alt-text="Selecione o seletor de ambientes.":::

1. Siga a experiência guiada descrita nas seções a seguir para fornecer todas as informações necessárias para um novo ambiente.

## <a name="step-1-provide-basic-information"></a>Etapa 1: forneça informações básicas

1. Escolha se deseja criar um ambiente do zero ou copiar dados de outro ambiente. [Copiar dados de outro ambiente](#copy-the-environment-configuration) requer etapas adicionais.

   :::image type="content" source="media/environment-settings-dialog.png" alt-text="Caixa de diálogo para criar um ambiente do Customer Insights.":::

1. Forneça os detalhes a seguir:

   - **Nome**: o nome deste ambiente. Esse campo já estará preenchido se você copiou de um ambiente existente, mas é possível alterá-lo.
   - **Escolha seu negócio**: público principal para o novo ambiente: clientes individuais (B-to-C) ou [contas comerciais](work-with-business-accounts.md) (B-to-B). Se sua organização faz negócios principalmente com indivíduos, como um varejista ou uma cafeteria, escolha consumidores individuais. Caso seu público-alvo principal seja outras empresas, como uma montadora de automóveis ou uma empresa de papel, escolha contas comerciais.
   - **Tipo**: tipo de ambiente: produção ou área restrita. Os ambientes de área restrita não permitem atualização de dados agendada e são destinados à pré-implementação e teste. Os ambientes de sandbox usam o mesmo público-alvo primário que o ambiente de produção atualmente selecionado.
   - **Região**: a região na qual o serviço é implantado e hospedado. Para [usar sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md) ou [conectar-se a uma organização existente do Microsoft Dataverse](customer-insights-dataverse.md), o ambiente do Customer Insights deve estar na mesma região.

1. Selecione **Avançar**

## <a name="step-2-configure-data-storage"></a>Etapa 2: Configure o armazenamento de dados

1. Escolha onde armazenar os dados do Customer Insights:

   - **Armazenamento do Customer Insights**: o armazenamento de dados é gerenciado automaticamente. É a opção padrão e, a menos que haja requisitos específicos para armazenar dados em sua própria conta de armazenamento, recomendamos usar essa opção.
   - **Azure Data Lake Storage**: sua própria conta do Azure Data Lake Storage para armazenar os dados e ter controle total de onde os dados são armazenados. Siga as etapas em [Usar sua própria conta do Azure Data Lake Storage](own-data-lake-storage.md).

   :::image type="content" source="media/data-storage-environment.png" alt-text="Escolha a opção preferida para armazenar seus dados.":::

1. Selecione **Avançar**

## <a name="step-3-connect-to-microsoft-dataverse"></a>Etapa 3: Conecte ao Microsoft Dataverse

Se você tiver um ambiente do Dataverse, conecte o Customer Insights. Compartilhe dados com o Dataverse para usá-los com aplicativos de negócios baseados no Dataverse, como o Dynamics 365 Marketing ou aplicativos baseados em modelo no Power Apps.

1. Siga as etapas em [Trabalhar com dados do Customer Insights no Microsoft Dataverse](customer-insights-dataverse.md).

   :::image type="content" source="media/dataverse-provisioning.png" alt-text="compartilhamento de dados com o Microsoft Dataverse habilitado automaticamente para novos ambientes de rede.":::

1. Selecione **Avançar**

## <a name="step-4-finalize-the-settings"></a>Etapa 4: Finalize a configuração

Revise as configurações especificadas. Quando tudo parecer correto, selecione **Criar** para configurar o ambiente.

Para alterar algumas das configurações posteriormente, consulte [Gerenciar ambientes](manage-environments.md).

## <a name="work-with-your-new-environment"></a>Trabalhe com seu novo ambiente

Reveja os seguintes artigos para ajudá-lo a começar a configurar o Customer Insights:

- [Adicionar mais usuários e atribuir permissões](permissions.md).
- [Ingerir suas fontes de dados](data-sources.md) e executá-las por meio do [processo de unificação de dados](data-unification.md) para obter [perfis de cliente unificados](customer-profiles.md).
- [Enriquecer os perfis de cliente unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- [Criar segmentos](segments.md) para agrupar clientes e [métricas](measures.md) para revisar os KPIs.
- [Configurar conexões](connections.md) e [exportações](export-destinations.md) para processar subconjuntos de seus dados em outros aplicativos.

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Como administrador, se você optar por copiar a configuração de um ambiente existente, selecione na lista de todos os ambientes disponíveis em sua organização.

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de tela das opções de configuração nas configurações do ambiente.":::

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

### <a name="set-up-a-copied-environment"></a>Configurar um ambiente copiado

Ao copiar a configuração do ambiente, uma mensagem de confirmação é exibida quando o ambiente copiado foi criado. Execute as etapas a seguir para confirmar as credenciais.

1. Selecione **Ir para fontes de dados** para ver a lista de fontes de dados. Todas as fontes de dados mostrarão um status **Credenciais Necessárias**.

   :::image type="content" source="media/data-sources-copied.png" alt-text="Lista de fontes de dados que foram copiadas e precisam de autenticação.":::

1. Edite as fontes de dados e insira as credenciais para atualizá-las. As fontes de dados da pasta do Common Data Model e Dataverse devem ser criadas manualmente com o mesmo nome do ambiente de origem.

1. Após atualizar as fontes de dados, vá para **Dados** > **Unificar**. Aqui você encontrará configurações do ambiente de origem. Edite-os conforme necessário ou selecione **Unificar** > **Unificar perfis e dependências de clientes** para iniciar o processo de unificação de dados e criar a entidade unificada do cliente.

   > [!TIP]
   > Para contas e contatos, selecione **Unificar contas** > **Unificar perfis e dependências**.

1. Quando a unificação de dados estiver concluída, vá para **Medidas** e **Segmentos** para atualizá-los.

1. Acesse **Administrador** > **Conexões** para autenticar novamente as conexões no seu novo ambiente.

1. Acesse **Dados** > **Enriquecimento** e **Dados** > **Exportações** para reativá-los.

[!INCLUDE [footer-include](includes/footer-banner.md)]
