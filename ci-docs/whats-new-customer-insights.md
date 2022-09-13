---
title: Novidades do Dynamics 365 Customer Insights
description: Informações sobre novos recursos, melhorias e correções de bugs.
ms.date: 08/31/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: skumm
manager: shellyha
ms.openlocfilehash: acba06cba5fb5cbf0bca5aeb30b603003555fc32
ms.sourcegitcommit: 3ab8f1c0ba5874095a19f0b6367b9a4432f72ed1
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/06/2022
ms.locfileid: "9409343"
---
# <a name="whats-new-in-dynamics-365-customer-insights"></a>Novidades do Dynamics 365 Customer Insights

Estamos animados para anunciar nossas atualizações mais recentes! Este artigo resume os recursos de recursos de versão preliminar pública, aprimoramentos de disponibilidade geral e atualizações de recursos. Para ver os planos de recurso a longo prazo, consulte os [Planos de lançamento do Dynamics 365 e do Power Platform](/dynamics365/release-plans/).

Distribuímos atualizações por região. Portanto, determinadas regiões podem ver recursos antes de outras. A menos que seja especificado de forma diferente, você não precisará tomar nenhuma medida. Atualizaremos o aplicativo automaticamente sem nenhum tempo de inatividade.

> [!TIP]
> Para enviar e votar em solicitações de recursos e sugestões de produto, acesse o [portal de ideias do aplicativo do Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="august-2022-updates"></a>Atualizações de agosto de 2022

As atualizações de agosto de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="contact-unification-in-b-to-b-environments"></a>Unificação de contatos em ambientes B-to-B

Os ambientes B-to-B no Customer Insights agora oferecem suporte a uma experiência aprimorada de unificação de dados.

Agora você pode unificar contatos, além de contas, para obter uma visão completa de seus contatos comerciais. Os contatos unificados são associados a contas unificadas e agora estão listados nos cartões dos clientes. 

Para obter mais informações, consulte [Criar um perfil de contato unificado](data-unification-contacts.md).

### <a name="create-and-export-of-segments-based-on-unified-contacts"></a>Criar e exportar segmentos com base em contatos unificados

Graças à nova unificação de contatos, você pode criar segmentos de contatos usando critérios de contatos, contas ou ambos. Esses segmentos podem ser exportados para ativação em outros serviços.

Para obter mais informações, consulte a [Visão geral de exportações](export-destinations.md).

### <a name="deployment-regions-aligned-with-microsoft-dataverse"></a>Regiões de implantação alinhadas com o Microsoft Dataverse

Ao criar um novo ambiente do Customer Insights, você pode selecionar a região onde deseja que o serviço seja implantado e hospedado. Atualizamos a seleção de região para estar alinhada com o Microsoft Dataverse e o Power Platform.

Agora você pode selecionar facilmente a mesma região que o ambiente existente do Microsoft Dataverse ou a conta do Azure Data Lake Storage (se você escolher essa opção), sujeito à disponibilidade do Customer Insights nessa região.

Para mais informações, consulte [Criar um novo ambiente](create-environment.md) e [Disponibilidade do produto por geografia](https://dynamics.microsoft.com/availability-reports/).

## <a name="july-2022-updates"></a>Atualizações de julho de 2022

As atualizações de julho de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="export-to-moengage"></a>Exportar para o MoEngage

Exporte segmentos de perfis unificados de cliente para o MoEngage e use-os para marketing por email no MoEngage.

Para obter mais informações, consulte [Exportar segmentos para o MoEngage](export-moengage.md).

### <a name="ssh-support-for-sftp-based-exports"></a>Suporte de SSH para exportações baseadas em SFTP

Escolha se deseja autenticar por meio de SSH ou nome de usuário/senha para conexões com destinos de exportação SFTP.

Para obter mais informações, consulte [Exportar dados para hosts SFTP](export-sftp.md).

### <a name="personalize-experiences-with-data-about-known-and-unknown-users"></a>Personalize experiências com dados sobre usuários conhecidos e desconhecidos

Gerenciar dados dos clientes não é um novo desafio, mas está se tornando cada vez mais difícil à medida que os usuários navegam pelos diversos canais digitais que as marcas oferecem. Um usuário que é conhecido (autenticado) em um canal torna-se desconhecido (não autenticado) em outro se não estiver conectado. Geralmente, o problema é que os usuários não autenticados (desconhecidos) não têm uma ID comum. Ela pode ser usada para associar atributos de perfil significativos e gerar perfis unificados de cliente. O Customer Insights ajuda a resolver esse problema ingerindo dados de métodos de rastreamento em seus sistemas de origem.

Para obter mais informações, consulte [Personalizar suas experiências com dados sobre usuários conhecidos e desconhecidos](unknown-to-known.md).

## <a name="june-2022-updates"></a>Atualizações de junho de 2022

As atualizações em junho de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="updated-user-experience-for-data-sources-and-data-ingestion"></a>Experiência do usuário atualizada para fontes de dados e ingestão de dados

A importação de dados de uma ampla variedade de fontes de dados é a base para a consolidação dos dados de seus clientes no Dynamics 365 Customer Insights. Revisamos a experiência do usuário para a importação e a conexão de fontes de dados. Essa atualização tem como objetivo facilitar a ingestão de dados para o Customer Insights.

Para obter mais informações, consulte [Visão geral de fontes de dados](data-sources.md).

### <a name="export-to-inmobi"></a>Exportar para a InMobi

A InMobi ajuda as marcar a entender, identificar, envolver e adquirir novos clientes. Você pode exportar segmentos e outros dados para o serviço da InMobi por meio de contas do Armazenamento de Blobs do Azure.

Para obter mais informações, consulte [Exportar para a InMobi (versão preliminar)](export-inmobi.md)

### <a name="lockbox-support-in-customer-insights"></a>Suporte ao Sistema de Proteção de Dados no Customer Insights

O Sistema de Proteção de Dados do Cliente fornece uma interface para revisar e aprovar (ou rejeitar) solicitações de acesso a dados. Essas solicitações ocorrem quando o acesso aos dados do cliente é necessário para resolver um caso de suporte.

Para obter mais informações, consulte [Acessar dados do cliente com segurança com o Sistema de Proteção de Dados do Cliente (Versão preliminar)](security-overview.md#securely-access-customer-data-with-customer-lockbox-preview).

### <a name="connect-to-your-data-using-azure-private-link"></a>Conectar seus dados usando o Link Privado do Azure

O Link Privado do Azure permite que o Customer Insights conecte sua conta do Azure Data Lake Storage por um ponto de extremidade privado em sua rede virtual. Para dados em uma conta de armazenamento, que não está exposta à Internet pública, o Link Privado permite a conexão com essa rede restrita.

Para obter mais informações, consulte [Usar Link Privado no Customer Insights](security-overview.md#set-up-an-azure-private-link).

## <a name="may-2022-updates"></a>Atualizações de maio de 2022

As atualizações de maio de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="updated-data-unification-experience"></a>Experiência de unificação de dados atualizada

 A unificação de dados permite unificar fontes de dados díspares em um único conjunto de dados mestre que fornece uma visão unificada desses dados. Os dados podem ser unificados em uma única entidade ou em várias entidades. Primeiro você [seleciona entidades e campos de origem](map-entities.md), [remove registros duplicados](remove-duplicates.md), especifica regras para [condições correspondentes](match-entities.md) e define quais [campos devem ser incluídos nos perfis de clientes unificados](merge-entities.md).

Para obter mais informações, consulte [Visão geral da unificação de dados](data-unification.md).

### <a name="refreshed-home-page-in-customer-insights"></a>Home page atualizada no Customer Insights

A **Página Inicial** orienta você no processo de configuração dos principais recursos e fornece uma visão geral dos segmentos, medidas e dados de enriquecimento. Atualizamos a experiência para fornecer informações mais relevantes rapidamente.

Para obter mais informações, consulte [Explorar o Customer Insights](home.md).

### <a name="track-usage-of-a-segment"></a>Acompanhar o uso de um segmento

Agora você pode [acompanhar o uso de um segmento](segments.md#track-usage-of-a-segment) em aplicativos, que são baseados na mesma organização do Dataverse que está conectada ao Customer Insights. Para [Segmentos do Customer Insights usados nas jornadas do cliente do Dynamics 365 Marketing](/dynamics365/marketing/real-time-marketing-ci-profile), o sistema informa sobre o uso desse segmento.

### <a name="export-to-criteo"></a>Exportar para a Criteo

A Criteo é uma plataforma online que ajuda os usuários a gerenciar a publicidade digital. Agora você pode exportar segmentos de perfis de cliente unificados para gerar campanhas, fornecer marketing de emails e usar grupos específicos de clientes com a Criteo.

Para obter mais informações, consulte [Exportar segmentos para a Criteo (versão preliminar)](export-criteo.md).

### <a name="refined-documentation-structure-for-environment-creation"></a>Estrutura de documentação refinada para criação de ambiente

Revisamos os documentos de ajuda relacionados à criação e gerenciamento de ambientes no Customer Insights. Agora, os artigos estão agrupados no nó Ambientes no Sumário. Os artigos reestruturados fornecem mais orientações para as diferentes formas de configurar ambientes e têm uma estrutura mais clara. Se você tiver comentários para compartilhar, informe-nos por meio dos controles no final dos artigos de ajuda.

Para obter mais informações, consulte [Como criar um novo ambiente](create-environment.md).

## <a name="april-2022-updates"></a>Atualizações de abril de 2022

As atualizações de abril de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="dun--bradstreet-enrichment-preview"></a>Enriquecimento da Dun & Bradstreet (Versão preliminar)

A Dun & Bradstreet fornece dados comerciais, análises e insights para empresas. Ela permite que os clientes com perfis de cliente unificados para as empresas possam enriquecer seus dados. Os enriquecimentos incluem atributos como número DUNS, porte da empresa, localização, setor e muito mais.

Para obter mais informações, consulte [Enriquecimento de perfis de empresas com a Dun & Bradstreet (Versão preliminar)](enrichment-dnb.md).

### <a name="define-the-measure-type-when-creating-a-new-measure"></a>Definir o tipo de medida ao criar uma nova medida

Agora você pode distinguir entre medidas para perfis individuais e medidas em toda a sua empresa. Enquanto as medidas de negócios são exibidas na home page do Customer Insights, as medidas do cliente são expostas nas visualizações detalhadas do cliente.

Para obter mais informações, consulte [Usar o construtor de medidas para criar medidas do zero](measure-builder.md).

### <a name="consolidation-of-customer-insights-documentation"></a>Consolidação da documentação do Customer Insights

Revisitamos nossos artigos de documentação e removemos menções de recursos de insights de participação e insights de público-alvo. A partir de agora, vamos nos referir consistentemente ao nome de produto Customer Insights quando escrevermos sobre os principais recursos do aplicativo. Essa mudança também leva a uma reestruturação significativa do sumário, da estrutura de URLs e dos caminhos de arquivos no repositório de documentação subjacente. Todos os seus favoritos ou links existentes continuam funcionando e redirecionam para as URLs atualizadas.

Se quiser nos contar sua percepção dessa mudança ou identificar algo que não esteja funcionando como esperado, informe-nos [enviando comentários para esta página](https://github.com/MicrosoftDocs/customer-insights/issues/new?title=&body=%0A%0A%5BEnter%20feedback%20here%5D%0A%0A%0A---%0A%23%23%23%23%20Document%20Details%0A%0A%E2%9A%A0%20*Do%20not%20edit%20this%20section.%20It%20is%20required%20for%20docs.microsoft.com%20%E2%9E%9F%20GitHub%20issue%20linking.*%0A%0A*%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Version%20Independent%20ID%3A%20d323ba46-f96e-1972-bc52-9b88f7d9cdfa%0A*%20Content%3A%20%5BNew%20and%20upcoming%20features%20-%20Dynamics%20365%20Customer%20Insights%5D(https%3A%2F%2Fdocs.microsoft.com%2Fen-us%2Fdynamics365%2Fcustomer-insights%2Fwhats-new-customer-insights)%0A*%20Content%20Source%3A%20%5Bci-docs%2Fwhats-new-customer-insights.md%5D(https%3A%2F%2Fgithub.com%2FMicrosoftDocs%2Fcustomer-insights%2Fblob%2Fmain%2Fci-docs%2Fwhats-new-customer-insights.md)%0A*%20Service%3A%20**customer-insights**%0A*%20Sub-service%3A%20**audience-insights**%0A*%20GitHub%20Login%3A%20%40m-hartmann%0A*%20Microsoft%20Alias%3A%20**mhart**).

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

Para obter mais informações, consulte [Habilitar o compartilhamento de dados com o Dataverse a partir do seu próprio Azure Data Lake Storage (Versão Preliminar)](customer-insights-dataverse.md#enable-data-sharing-with-dataverse-from-your-own-azure-data-lake-storage-preview).

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
  
Durante o período de transição, os eventos capturados ainda serão transmitidos para o Data Lake conectado. Depois que essa funcionalidade for desativada, o compartilhamento de dados será interrompido e nenhum novo evento será enviado para o armazenamento conectado.
Contate diretamente a equipe da sua conta Microsoft se tiver dúvidas sobre o fim da versão preliminar do recurso. A equipe da sua conta manterá você atualizado sobre os próximos lançamentos. 

## <a name="january-2022-updates"></a>Atualizações de janeiro de 2022

As atualizações de janeiro de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Análise de sentimento dos comentários do cliente

O Customer Insights fornece um novo recurso baseado em IA para sintetizar o sentimento do cliente e identificar aspectos de negócios específicos como oportunidades para melhorias direcionadas. Ao analisar os comentários escritos por seus clientes, você pode obter insights precisos com um baixo custo. Análise de sentimentos baseada em modelos de Processamento de Linguagem Natural (NLP) que geram dois insights derivados para cada ID do cliente. Uma pontuação de sentimento (de -5 a 5) e uma lista de aspectos de negócios aplicáveis. 

Para obter mais informações, consulte [Analisar sentimento nos comentários do cliente (versão preliminar)](sentiment-analysis.md).


[!INCLUDE [footer-include](includes/footer-banner.md)]