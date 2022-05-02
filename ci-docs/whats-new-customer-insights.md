---
title: Recursos novos e futuros
description: Informações sobre novos recursos, melhorias e correções de bugs.
ms.date: 04/05/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: 25c6e2897d836854408871b2c74afa16ecba7435
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645684"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novidades do Dynamics 365 Customer Insights

Estamos animados para anunciar nossas atualizações mais recentes! Este artigo resume os recursos de recursos de versão preliminar pública, aprimoramentos de disponibilidade geral e atualizações de recursos. Para ver os planos de recurso a longo prazo, consulte os [Planos de lançamento do Dynamics 365 e do Power Platform](/dynamics365/release-plans/).

Distribuímos atualizações por região. Portanto, determinadas regiões podem ver recursos antes de outras. A menos que especificado de forma diferente, você não precisa tomar medidas e atualizaremos o aplicativo automaticamente, sem tempo de inatividade.

> [!TIP]
> Para enviar e votar em solicitações de recursos e sugestões de produto, acesse o [portal de ideias do aplicativo do Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="march-2022-updates"></a>Atualizações de março de 2022

As atualizações de março de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="liveramp-abilitec-enrichment-preview"></a>Enriquecimento do LiveRamp AbiliTec (versão preliminar)

O LiveRamp fornece resolução de identidade e consolidação de dados do cliente. Você pode mapear identificadores pessoais em seus dados de cliente para o gráfico de identidade da AbiliTec e receber IDs da AbiliTec. Você pode usar essas IDs para uma unificação melhor dos dados de seus clientes.

Para obter mais informações, consulte [Enriquecer perfis com dados de identidade do LiveRamp (versão preliminar)](enrichment-liveramp.md).

### <a name="organize-segments-and-measures-with-tags-and-filters"></a>Organize segmentos e medidas com marcas e filtros
Se a sua organização mantém muitos segmentos ou medidas, encontrar o certo às vezes pode parecer um desafio. Esse novo recurso permite organizar listas usando marcas e colunas. Ele ajuda a encontrar dados de forma rápida e fácil e a personalizar as exibições.

Para obter mais informações, consulte [Trabalhar com marcas e colunas](work-with-tags-columns.md).

### <a name="enable-data-sharing-with-dataverse-when-using-your-own-storage-account"></a>Habilitar o compartilhamento de dados com o Dataverse usando sua própria conta de armazenamento

Se o seu ambiente usar o Azure Data Lake Storage para armazenar dados do Customer Insights, o compartilhamento de dados com o Microsoft Dataverse precisará de configurações adicionais.
Anteriormente, você só podia habilitar o compartilhamento de dados com o Dataverse quando os dados estavam armazenados em nosso data lake gerenciado. 

Para obter mais informações, consulte [Habilitar o compartilhamento de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage (Versão Preliminar)](manage-environments.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

### <a name="new-export-destinations-iterable-and-braze"></a>Novos destinos de exportação: Iterable e Braze

Continuamos a expandir nosso ecossistema de destinos de exportação com novas conexões. Agora você pode exportar segmentos para o Iterable e o Braze para usar seus serviços de ativação.

Para obter mais informações, consulte [Exportar segmentos para o Iterable (versão preliminar)](export-iterable.md) e [Exportar segmentos para o Braze (versão preliminar)](export-braze.md).

### <a name="improvements-to-marketo-and-google-ads-export"></a>Melhorias na exportação do Marketo e do Google Ads

A alteração de APIs nos serviços conectados leva a atualizações para que os conectores sejam executados de maneira confiável e sem problemas. Lançamos algumas atualizações para as exportações para os serviços Marketo e Google Ads:

- Google Ads: a nova versão do conector de exportação do Google Ads simplifica a experiência de autenticação e agora permite que você crie públicos-alvo do Google Ads automaticamente. 
- Marketo: a nova versão do conector de exportação do Marketo oferece suporte à ID do Marketo, permitindo que você evite a duplicação de dados, atualize registros existentes e crie registros no Marketo. 


## <a name="february-2022-updates"></a>Atualizações de fevereiro de 2022

As atualizações de fevereiro de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="general-availability-for-prediction-models"></a>Disponibilidade geral para modelos de previsão

Os modelos de previsão prontos para uso, incluindo **rotatividade de assinaturas**, **rotatividade transacional** e **valor da permanência do cliente (CLV)** tornam-se geralmente disponíveis como parte do Customer Insights. 

Para obter mais informações, consulte [Visão geral de previsões](predictions-overview.md).

### <a name="new-data-source-integration-with-azure-synapse-analytics-preview"></a>Nova fonte de dados: Integração com Azure Synapse Analytics (versão preliminar)

Azure Synapse Analytics é um serviço de análise empresarial que acelera o tempo para a obtenção de insights em data warehouses e sistemas de big data.

Organizações que já usam o Azure Synapse Analytics podem ingerir esses dados no Customer Insights. 

Para obter mais informações, consulte [Conectar uma fonte de dados do Azure Synapse (versão preliminar)](connect-synapse.md).

### <a name="liveramp-enrichment-preview"></a>Enriquecimento do LiveRamp (versão preliminar)

O LiveRamp fornece resolução de identidade e consolidação de dados do cliente. Você pode mapear identificadores pessoais em seus dados de cliente para o gráfico de identidade da AbiliTec e receber IDs da AbiliTec. Você pode usar essas IDs para uma unificação melhor dos dados de seus clientes.

Para obter mais informações, consulte [Enriquecer perfis com dados de identidade do LiveRamp (versão preliminar)](enrichment-liveramp.md).

### <a name="enrichment-for-data-sources-preview"></a>Enriquecimento de fontes de dados (versão preliminar)

Use dados de fontes como a Microsoft e outros de parceiros para enriquecer os dados de clientes antes da unificação de dados. Os enriquecimentos da fonte de dados ajudam a produzir dados mais completos e de qualidade que podem ajudar a alcançar melhores resultados depois de unificar seus dados.

Para obter mais informações, consulte [Enriquecimento de fontes de dados (versão preliminar)](data-sources-enrichment.md).

### <a name="change-owner-of-environment"></a>Alterar proprietário do ambiente

Embora vários usuários possam ter permissões de administrador no Customer Insights, apenas um usuário é o proprietário de um ambiente. Uma experiência aprimorada permite que você altere os proprietários de um ambiente e reivindique a propriedade se um antigo proprietário deixar a organização. 

Para mais informações, consulte [Alterar o proprietário de um ambiente](manage-environments.md#change-the-owner-of-an-environment).

### <a name="data-preparation-process-lists-corruption-reason-for-corrupted-records"></a>O processo de preparação de dados indica o motivo da corrupção para registros corrompidos

A preparação de dados agora mostra o motivo do problema para todos os campos com dados corrompidos. As informações são fornecidas no nível de registro individual para facilitar a identificação. 

Para obter mais informações, consulte [Fontes de dados corrompidos](entities.md#corrupted-data-sources).

### <a name="end-of-preview-for-reporting-features-in-the-engagement-insights-capability"></a>Fim da versão preliminar para recursos de relatório no recurso de insights de engajamento

A versão preliminar do recurso de insights de participação do Dynamics 365 Customer Insights terminou em 15 de fevereiro de 2022.  
Essa alteração significa que a experiência da avaliação do Customer Insights não inclui mais a possibilidade de criar funis nem outras funcionalidades de relatórios.

Convidamos você a explorar e avaliar os muitos outros recursos do [Customer Insights](https://dynamics.microsoft.com/ai/customer-insights/), a plataforma de dados de clientes da Microsoft (CDP).    
 
Por um período de transição, os participantes existentes da versão preliminar ainda terão acesso a alguns recursos e funcionalidades da versão preliminar:

- Obter código para instrumentar um site ou aplicativo móvel 
- Ver eventos e as propriedades de eventos 
- Aprimore perfis unificados com eventos ingeridos e refinados para se beneficiar do valor total dos dados de seus clientes
  
Durante o período de transição, os eventos capturados ainda serão transmitidos para o Data Lake conectado. Depois que essa funcionalidade for desativada, o compartilhamento de dados será interrompido e nenhum novo evento será enviado ao armazenamento conectado.
Contate diretamente a equipe da sua conta Microsoft se tiver dúvidas sobre o fim da versão preliminar do recurso. A equipe da sua conta manterá você atualizado sobre os próximos lançamentos. 

## <a name="january-2022-updates"></a>Atualizações de janeiro de 2022

As atualizações de janeiro de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Análise de sentimento dos comentários do cliente

O Customer Insights fornece um novo recurso baseado em IA para sintetizar o sentimento do cliente e identificar aspectos de negócios específicos como oportunidades para melhorias direcionadas. Ao analisar os comentários escritos por seus clientes, você pode obter insights precisos com um baixo custo. Análise de sentimentos baseada em modelos de Processamento de Linguagem Natural (NLP) que geram dois insights derivados para cada ID do cliente. Uma pontuação de sentimento (de -5 a 5) e uma lista de aspectos de negócios aplicáveis. 

Para obter mais informações, consulte [Analisar sentimento nos comentários do cliente (versão preliminar)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]