---
title: Recursos novos e futuros
description: Informações sobre novos recursos, melhorias e correções de bugs.
ms.date: 03/02/2022
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 0e25ed4e4e25b130fda410d4ba1c78caded7f0f9
ms.sourcegitcommit: b7189b8621e66ee738e4164d4b3ce2af0def3f51
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2022
ms.locfileid: "8088271"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>O que há de novo no recurso de insights do público-alvo do Dynamics 365 Customer Insights



Estamos animados para anunciar nossas atualizações mais recentes! Este artigo resume os recursos de recursos de versão preliminar pública, aprimoramentos de disponibilidade geral e atualizações de recursos. Para ver os planos de recurso a longo prazo, consulte os [Planos de lançamento do Dynamics 365 e do Power Platform](/dynamics365/release-plans/).

Distribuímos atualizações por região. Portanto, determinadas regiões podem ver recursos antes de outras. A menos que especificado de forma diferente, você não precisa tomar medidas e atualizaremos o aplicativo automaticamente, sem tempo de inatividade.

> [!TIP]
> Para enviar e votar em solicitações de recursos e sugestões de produto, acesse o [portal de ideias do aplicativo do Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).


## <a name="january-2022-updates"></a>Atualizações de janeiro de 2022

As atualizações de janeiro de 2022 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="sentiment-analysis-of-your-customers-feedback"></a>Análise de sentimento dos comentários do cliente

O Customer Insights fornece um novo recurso baseado em IA para sintetizar o sentimento do cliente e identificar aspectos de negócios específicos como oportunidades para melhorias direcionadas. Ao analisar os comentários escritos por seus clientes, você pode obter insights precisos com um baixo custo. Análise de sentimentos baseada em modelos de Processamento de Linguagem Natural (NLP) que geram dois insights derivados para cada ID do cliente. Uma pontuação de sentimento (de -5 a 5) e uma lista de aspectos de negócios aplicáveis. 

Para obter mais informações, consulte [Analisar sentimento nos comentários do cliente (versão preliminar)](sentiment-analysis.md).


## <a name="december-2021-updates"></a>Atualizações de dezembro de 2021

As atualizações em dezembro de 2021 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="forward-customer-insights-logs-to-azure-monitor"></a>Encaminhar logs do Customer Insights para o Azure Monitor

O Customer Insights fornece uma integração direta com o Azure Monitor. Esse recurso inclui eventos operacionais e de auditoria. Os logs de recursos do Azure Monitor permitem monitorar e enviar logs para o Armazenamento do Azure, o Azure Log Analytics ou transmiti-los para os Hubs de Eventos do Azure.

Para obter mais informações, confira [Encaminhamento de logs no Dynamics 365 Customer Insights com o Azure Monitor (versão preliminar)](diagnostics.md).

### <a name="enrich-customer-profiles-with-engagement-data"></a>Enriquecer perfis de clientes com dados de engajamento

Use dados do Microsoft Office 365 para enriquecer os perfis das contas dos clientes com insights sobre engajamentos por meio de aplicativos do Office 365. Os dados de engajamento consistem em atividades de email e reunião, que são agregadas no nível da conta. Por exemplo, o número de emails de uma conta comercial ou o número de reuniões com a conta. Nenhum dado sobre usuários individuais é compartilhado. Este enriquecimento está disponível nas seguintes regiões: Reino Unido, Europa, América do Norte.

Para obter mais informações, consulte [Enriquecer perfis de clientes com dados de engajamento (versão preliminar)](enrichment-office.md).

### <a name="advanced-data-unification-features"></a>Recursos avançados de unificação de dados

#### <a name="enable-conflict-resolution-policies-at-the-individual-attribute-level"></a>Habilitar políticas de resolução de conflitos no nível de atributo individual

Ao eliminar a duplicação de registros de clientes em uma entidade, não convém escolher um registro completo como vencedor. Agora permitimos que você mescle os melhores campos de vários registros com base em regras de cada atributo. Por exemplo, você pode manter o email mais recente E o endereço mais completo de diferentes registros. 

Agora você pode definir regras de mesclagem separadas para atributos individuais ao eliminar a duplicação e mesclar registros em uma única entidade. Anteriormente, só permitíamos que você selecionasse uma única regra de mesclagem (mantendo registros com base na integridade dos dados de recência) que era aplicada no nível do registro a todos os atributos. Isso não é ideal quando alguns dos dados que você deseja manter são encontrados no registro A, e outros bons dados são encontrados no registro B.

Para mais informações, confira [Definir a eliminação de duplicação em uma entidade correspondente](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="custom-rules-for-matching"></a>Regras personalizadas para correspondência

Há momentos em que você precisa especificar uma exceção às regras gerais para NÃO corresponder registros. Isso pode acontecer quando vários indivíduos compartilham informações suficientes para que o sistema os corresponda como um único indivíduo. Por exemplo, gêmeos com o mesmo sobrenome, que moram na mesma cidade e compartilham a data de nascimento.

As exceções garantem que a unificação incorreta de dados possa ser resolvida nas regras de unificação. Você pode adicionar várias exceções a uma regra.

Para obter mais informações, confira [Adicionar exceções a uma regra](match-entities.md#add-exceptions-to-a-rule).

#### <a name="provide-additional-conflict-resolution-policies-and-enable-grouping-of-attributes"></a>Fornecer políticas adicionais de resolução de conflitos e habilitar o agrupamento de atributos

Esse recurso permite tratar um grupo de campos como uma unidade. Por exemplo, quando nossos registros contêm os campos Endereço1, Endereço2, Cidade, Estado e CEP. Provavelmente não convém mesclar Endereço2 em um registro diferente para que isso torne nossos dados mais completos.

Agora você pode combinar um grupo de campos relacionados e aplicar uma única política de mesclagem ao grupo. 

Para obter mais informações, confira [Combinar um grupo de campos](merge-entities.md#combine-a-group-of-fields).


## <a name="november-2021-updates"></a>Atualizações de novembro de 2021

As atualizações em novembro de 2021 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="segment-membership-now-available-in-dataverse"></a>Associação ao segmento agora disponível no Dataverse

As informações de associação ao segmento para perfis de clientes agora estão disponíveis no Dataverse juntamente com os perfis e insights dos clientes. Os aplicativos de ação e os aplicativos baseados em modelo do Dynamics 365 podem usar esses dados para pesquisar detalhes da associação ao segmento para um determinado cliente.

### <a name="activities-support-contact-level-details-for-business-accounts"></a>As atividades oferecem suporte a detalhes no nível do contato para contas comerciais

Agora você pode configurar, exibir e filtrar atividades para contatos nas linhas do tempo de atividades da sua conta comercial para entender melhor quais contatos de conta participaram de atividades específicas.

## <a name="october-2021-updates"></a>Atualizações de outubro de 2021

As atualizações em outubro de 2021 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="b-to-b"></a>B2B

A partir de outubro de 2021, você pode trabalhar com contas comerciais e seus contatos relacionados no Customer Insights. Antes, o aplicativo era voltado principalmente para consumidores individuais. Várias áreas de recursos foram atualizadas para oferecer suporte a cenários B2B em cima de um novo tipo de ambiente. Para obter uma visão geral dos recursos B2B com suporte, consulte [Trabalhe com contas comerciais em insights de público-alvo](work-with-business-accounts.md).

As seções a seguir destacam algumas das principais áreas que foram adaptadas para oferecer suporte a contas comerciais e consumidores individuais.

#### <a name="export-segments-based-on-business-accounts"></a>Exportar segmentos com base em contas comerciais

Todas as exportações de segmento em insights de público-alvo estão disponíveis no contexto de contas comerciais. A maioria das exportações de segmento requerem configuração extra e [informações de contato projetadas](segment-builder.md#create-a-new-segment) nos segmentos subjacentes para serem válidas para contas comerciais. Para obter mais informações, consulte [Exportar segmentos](export-destinations.md#export-segments).

#### <a name="use-the-linkedin-ads-export-with-business-accounts"></a>Usar a exportação de Anúncios do LinkedIn com contas comerciais

A exportação de Anúncios do LinkedIn agora está disponível para segmentação de empresa e contato no contexto das contas comerciais. Ao selecionar a segmentação da empresa como seu foco principal de exportação do LinkedIn, você pode exportar segmentos criados em contas comerciais sem a necessidade de projetar informações de contato. Para obter mais informações, consulte os documentos sobre [Exportação de Anúncios do LinkedIn](export-linkedin-ads.md) e a diferença entre [segmentação de contato](https://business.linkedin.com/marketing-solutions/ad-targeting/contact-targeting) e [segmentação da empresa](https://business.linkedin.com/marketing-solutions/ad-targeting/account-targeting). 

#### <a name="create-measures-based-on-business-accounts-and-their-hierarchy"></a>Criar medidas com base em contas comerciais e sua hierarquia

O construtor de medidas permite criar medidas em torno de contas comerciais e, opcionalmente, usar as informações de hierarquia. As informações de hierarquia são usadas para acumular um cálculo de medida em uma conta e em todas as suas subcontas relacionadas. Por exemplo, você pode criar medidas como a receita total para cada grupo de contas comerciais identificadas por sua hierarquia. Para obter mais informações, consulte [Definir e gerenciar medidas](measures.md).

#### <a name="create-segments-based-on-business-accounts-and-their-hierarchy"></a>Criar segmentos com base em contas comerciais e sua hierarquia

O construtor de segmento permite que você crie segmentos de contas comerciais que, opcionalmente, incluem informações de contato para cada conta em um segmento. Se você configurou a hierarquia de contas, pode usar as informações da hierarquia de contas na criação do segmento. Para obter mais informações, consulte [Criar um novo segmento](segment-builder.md#create-a-new-segment).

#### <a name="retain-your-business-accounts-with-deep-insights-to-their-churn-tendency"></a>Mantenha suas contas comerciais com insights profundos sobre a tendência de rotatividade

O modelo de previsão de rotatividade de clientes agora também oferece suporte a contas comerciais. Você pode avaliar o risco da rotatividade não apenas para uma conta, mas para uma combinação de uma conta e uma categoria de produto ou serviço que os clientes compram de você. Esse acréscimo ajuda a entender se uma conta tem maior probabilidade de parar de comprar de você em geral ou apenas em uma determinada categoria de bens ou serviços. Para ajudá-lo ainda mais a usar este modelo de IA, ele também lista os motivos pelos quais uma conta provavelmente será objeto de rotatividade. Para mais informações, consulte [Previsão de rotatividade de transações (versão preliminar)](predict-transactional-churn.md).

#### <a name="see-contacts-of-a-business-account-in-customer-view"></a>Ver os contatos de uma conta comercial na exibição do Customer

Se as contas comerciais forem mapeadas para contas relacionadas, o aplicativo Customer Insights mostra esses contatos relacionados como parte da exibição de detalhes do cliente. Para obter mais informações, consulte [Perfis do cliente](customer-profiles.md).


## <a name="september-2021-updates"></a>Atualizações de setembro de 2021

As atualizações em setembro de 2021 incluem novos recursos, atualizações de desempenho e correções de bugs.

### <a name="activities"></a>Atividades

- **Melhorias no cronograma de atividades** Ampliamos os filtros para a linha do tempo de atividades nos perfis dos clientes. Além disso, você pode usar a nova bandeja de filtro para filtrar por tipo de atividade e por data. As datas podem ser filtradas em diferentes condições. Para mais informações, consulte [Visualoizar cronogramas de atividades em perfis de clientes](activities.md#view-activity-timelines-on-customer-profiles).

### <a name="relationships"></a>Relações

- **Suporte de relacionamento multi-hop** Use relacionamentos multi-hop ao configurar atividades e definir relacionamentos entre entidades. Os relacionamentos multi-hop usam uma entidade intermediária para conectar duas entidades. Ao configurar uma atividade, você pode usar uma relação multi-hop para conectar sua entidade de atividade a uma entidade intermediária e depois a uma entidade de cliente. Você pode combinar relacionamentos multi-hop com relacionamentos multi-path. Para obter mais informações, consulte [Relacionamento multi-hop](relationships.md#multi-hop-relationship).

- **Suporte de relacionamento multi-path** Use relacionamentos multi-path ao configurar atividades e definir relacionamentos entre entidades. Relacionamentos multi-path relacionam uma entidade de origem a mais de uma entidade. Ao configurar uma atividade, você pode usar uma relação multi-path para conectar sua entidade de atividade com mais de uma entidade de cliente. Você pode combinar relacionamentos multi-path com relacionamentos multi-hop. Para obter mais informações, consulte [Relacionamento multi-path](relationships.md#multi-path-relationship).

## <a name="august-2021-updates"></a>Atualizações de agosto de 2021

As atualizações em julho e agosto de 2021 incluem um novo recurso, atualizações de desempenho e correções de bugs.

### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos para o Klaviyo** Ampliamos nossos [destinos de exportação para incluir o Klaviyo](export-klaviyo.md). Agora você pode exportar segmentos para criar campanhas, fazer marketing por email e usar grupos de clientes específicos com o Klaviyo. 


## <a name="june-2021-updates"></a>Atualizações de junho de 2021

As atualizações em junho de 2021 incluem vários recursos, upgrades de desempenho e correções de bugs.

### <a name="data-ingestion"></a>Ingestão de dados

- **Aprimoramento nas atualizações de progresso de unificação de dados** Agora você pode ver atualizações dinâmicas de status aprimoradas e mais granulares nas etapas do [processo de unificação de dados](data-unification.md). Esse recurso permite que você acompanhe o progresso detalhado para entender o fluxo do processo e agir se alguma etapa precisar de atenção.

### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos e outros dados para o Salesforce Marketing Cloud** Ampliamos nossos destinos de exportação para incluir o [Salesforce Marketing Cloud](export-salesforce.md). Agora você pode exportar segmentos e outros tipos de dados para o Salesforce Marketing Cloud por meio de uma exportação de SFTP de marca. A importação de dados pode ser totalmente automatizada no Salesforce e usada para criar campanhas de marketing mais eficientes.  
 
- **Exportar segmentos para o ActiveCampaign** Ampliamos nossos destinos de exportação para incluir o [Active Campaign](export-active-campaign.md). Agora você pode exportar segmentos para gerar campanhas, executar marketing por email e trabalhar com grupos específicos de clientes no ActiveCampaign.
 
- **Exportar segmentos para o Sendinblue** Ampliamos nossos destinos de exportação para incluir o [Sendinblue](export-sendinblue.md). Agora você pode exportar segmentos para gerar campanhas, executar marketing por email e trabalhar com grupos específicos de clientes com o Sendinblue.
 
### <a name="ux-updates"></a>Atualizações de experiência do usuário 

- **Nova página Clientes e página de detalhes do perfil** Reformulamos a página Clientes e as páginas de detalhes do perfil para melhorar a experiência do usuário e o desempenho. Essas alterações permitem que você exiba, classifique, pesquise e filtre clientes. Os filtros agora são representados na URL para compartilhar os resultados da pesquisa com outros usuários de forma simples. Os resultados da pesquisa também podem ser salvos como um segmento.    
  A página de detalhes de perfis de clientes agora agrupa dados em várias subseções, como dados demográficos, IDs e outros atributos de perfil para facilitar a leitura. Outras seções na página de detalhes do perfil agora são mais interativas. Por exemplo, a seção de atividades agora permite filtragem e classificação.


## <a name="may-2021-updates"></a>Atualizações de maio de 2021

As atualizações em maio de 2021 incluem vários recursos, atualizações de desempenho e correções de bugs.

### <a name="data-ingestion"></a>Ingestão de dados

- **Exibir ou modificar metadados ou definição de entidade ao anexar dados de seu Azure Data Lake Storage** Agora você pode ver e editar metadados ou definição de entidade em insights de público-alvo ao anexar dados de uma pasta do Common Data Model em seu Azure Data Lake Storage. Esse recurso fornece feedback em tempo real, validação de modelo e verificação de erros. Ele permite que você edite model.json e manifest.json perfeitamente.

### <a name="extensibility"></a>Extensibilidade

- **Exportações de segmento aprimoradas, programação personalizada e duplicação** Agora é possível [ver todas as exportações para um segmento específico](export-destinations.md#view-exports-and-export-details) em uma lista. Esta nova visão ajuda a gerenciar como um segmento específico é usado e adaptar as existentes ou criar exportações.    
  Você pode [definir agendas de atualização personalizadas](export-destinations.md#schedule-and-run-exports) para exportações individuais ou várias exportações de uma vez. Até agora, todas as exportações eram executadas a cada atualização do sistema.    
  Em vez de criar uma exportação do zero, você pode começar com base em uma existente para economizar tempo.

- **Exportar segmentos para o Microsoft Advertising** Estendemos nossos destinos de exportação para incluir o Microsoft Advertising. Crie públicos-alvo de Correspondência de Clientes no Microsoft Advertising com seus dados de perfil de cliente unificados e use esses públicos-alvo para suas campanhas de publicidade. Para obter mais informações, consulte [Exportar segmentos para o Microsoft Advertising](export-microsoft-advertising.md).

- **Exportar segmentos para LinkedIn Ads** Ampliamos nossos destinos de exportação para incluir anúncios do LinkedIn e permitir que você desbloqueie o Contact Targeting, bem como o Company Targeting, por meio do LinkedIn, exportando seus dados de perfil de cliente unificados. Para obter mais informações, consulte [Exportar segmentos para o LinkedIn Ads](export-linkedin-ads.md).


- **Exportar segmentos para o Omnisend** Estendemos nossos destinos de exportação para incluir o Omnisend. Use os segmentos criados nos insights do público-alvo para gerar campanhas, fornecer marketing de emails e usar grupos específicos de clientes com o Omnisend. Para obter mais informações, consulte [Exportar segmentos para o Omnisend](export-omnisend.md)

### <a name="predictions"></a>Previsões

- **Relatório de usabilidade de dados de entrada** O relatório de usabilidade de dados de entrada fornece uma visão consolidada dos erros e avisos que suas previsões predefinidas podem estar gerando. Ele também fornece recomendações sobre como melhorar o desempenho do modelo.    
  O relatório é disponibilizado depois que um modelo conclui seu processo de treinamento. É criado para cada modelo de forma separada, independentemente de ter sido concluído com êxito ou não.
  Atualmente, esse recurso está disponível apenas para o modelo de Rotatividade da Transação. Para obter mais informações, consulte [Relatório de usabilidade de dados de entrada](manage-predictions.md#input-data-usability-report).

### <a name="relationships"></a>Relações

- **Visualizador de relacionamento** A exibição do visualizador de relacionamento permite que você veja todos os relacionamentos existentes entre entidades e sua cardinalidade. Os relacionamentos agora são organizados em grupos: relacionamentos criados pelo usuário, sistema e herdados. Você também pode exportar uma exibição como uma imagem. Para obter mais informações, consulte [Exibir relacionamentos](relationships.md#view-relationships). 

## <a name="april-2021-updates"></a>Atualizações de abril de 2021

As atualizações em abril de 2021 incluem vários recursos, atualizações de desempenho e correções de bugs.

### <a name="data-unification"></a>Unificação de dados
 
- **Experiência de mesclagem aprimorada para unificação dos dados**    
  
   Agora temos uma melhor experiência de usuário na configuração de mesclagem do processo de unificação de dados. As alterações incluem ordenação intuitiva dos campos mesclados e estatísticas detalhadas sobre campos combinados e singleton.

- **Reordenamento de entidades e configuração de todos os registros de origem na entidade Cliente**  
      
   Agora você pode reordenar e remover entidades de um plano de fusão existente no processo de unificação de dados. Isso proporciona flexibilidade para reordenar as entidades no processo de correspondência de acordo com as necessidades de negócios. Além disso, habilitamos a inclusão de todos os registros não correspondentes na entidade final *Cliente*, que permite estabelecer a definição do conjunto de dados do perfil do cliente.

### <a name="enrichments"></a>Enriquecimentos

 - **Novo enriquecimento: endereços aprimorados**    
  
   Estamos felizes em apresentar um novo enriquecimento para aprimorar os endereços nos dados dos seus clientes. Os endereços dos seus dados podem ser não estruturados, incompletos ou incorretos. Este recurso usa os modelos da Microsoft para normalizar e enriquecer seus endereços no formato de Common Data Model para melhor a precisão e os insights.
 
   Para saber mais, veja [Enriquecimento de perfis de clientes com endereços aprimorados](enrichment-enhanced-addresses.md).

- **Experiência de configuração guiada para enriquecimentos**    
  
   Nós revisitamos a experiência de configuração para enriquecimentos com uma experiência simples e guiada. Agora você tem um claro processo passo a passo para criar e editar enriquecimentos.
 
   Além disso, separamos a configuração de conexões para enriquecimentos de terceiros para permitir que a mesma conexão seja usada por vários enriquecimentos. Somente os administradores podem configurar novas conexões, mas as conexões criadas estão disponíveis para os administradores e os colaboradores.    

   Para obter mais informações, consulte [Visão geral das conexões](connections.md).

- **Vários enriquecimentos do mesmo tipo**    
  
   Agora os usuários podem criar e gerenciar vários enriquecimentos do mesmo tipo de enriquecimento. Por exemplo, agora você pode criar dois enriquecimentos separados de endereço para enriquecer dois segmentos de clientes diferentes. Há limites em relação a quantos enriquecimentos do mesmo tipo podem ser criados e eles variam de acordo com o tipo de enriquecimento.
  
   Para obter mais informações, consulte [Enriquecimento para perfis de clientes](enrichment-hub.md).

## <a name="march-2021-updates"></a>Atualizações de março de 2021

As atualizações em março de 2021 incluem vários recursos, atualizações de desempenho e correções de bugs.

### <a name="activities"></a>Atividades

- **Assistente de atividade e tipos semânticos**

   Melhoramos e atualizamos nossa experiência de mapeamento de atividades para orientar e simplificar a criação do mapeamento de atividades. Nesta nova experiência, os usuários obtêm uma experiência guiada para ajudar na conclusão de cada etapa do processo. Na etapa de mapeamento de atividades, além de escolher entre muitos tipos de atividades, o usuário pode escolher mapear semanticamente os dados de *Assinatura* e/ou *SalesOrderLine* para esquemas padrão do setor, que podem ser usados para consumo downstream.   

   Para obter mais informações, consulte [Atividades do cliente](activities.md).

### <a name="data-ingestion"></a>Ingestão de dados

- **Conectar-se a fontes de dados locais usando fluxos de dados e gateways do Power Platform** Temos o prazer de anunciar a versão preliminar dos fluxos de dados e da conectividade local do Power Platform usando gateways no Customer Insights com um ambiente associado do Power Platform ou do Dataverse. Quaisquer novas fontes de dados criadas em um ambiente do Customer Insights com um ambiente vinculado do Dataverse terão como padrão os fluxos de dados do Power Platform trazendo a conectividade de dados local e um conjunto avançado de conectores e recursos de transformação.

### <a name="extensibility"></a>Extensibilidade

- **Exportações organizadas em conexões e exportações** Alteramos o nome da página **Destinos de exportação** para **Conexões** e adicionamos uma página separada para **Exportações**. Como parte desta atualização, faremos a transição de exportações existentes em pares de uma conexão e uma exportação usando essa conexão. Os administradores agora têm mais clareza sobre os dados de saída na página **Conexões**. Todas as funções de usuário têm acesso à página **Exportações**, mas apenas os administradores podem optar por permitir que os colaboradores editem exportações específicas com conexões compartilhadas.     
  Para obter mais informações, consulte [Visão geral de conexões](connections.md) e [Visão geral de exportações](export-destinations.md).

- **Exportar segmentos para o Campaign Monitor** Estendemos nossos destinos de exportação para incluir o Campaign Monitor. Agora você pode exportar segmentos do Customer Insights para listas do Campaign Monitor e usá-los como linha de base para suas campanhas de marketing.    
   Para obter mais informações, consulte [Exportar para o Campaign Monitor](export-campaign-monitor.md).

- **Exportar segmentos para o Constant Contact** Estendemos nossos destinos de exportação para incluir o Constant Contact. Agora você pode exportar segmentos do Customer Insights para listas do Constant Contact e usá-los como linha de base para suas campanhas de marketing.   
   Para obter mais informações, consulte [Exportar para o Constant Contact](export-constant-contact.md).

- **Exportar segmentos para o RollWorks** Estendemos nossos destinos de exportação para incluir o RollWorks. Agora você pode exportar segmentos do Customer Insights para públicos-alvo de RollWorks e usá-los como a linha de base para sua publicidade B2B.    
   Para obter mais informações, consulte [Exportar para o RollWorks](export-rollworks.md).

- **Exportar segmentos para o Snapchat** Estendemos nossos destinos de exportação para incluir o Snapchat. Agora você pode exportar segmentos do Customer Insights para públicos do Snapchat e usá-los como linha de base para sua publicidade.     
   Para obter mais informações, consulte [Exportar para o Snapchat](export-snapchat.md).

### <a name="predictions"></a>Previsões

- **Usar filtros de produto em recomendações preditivas de produtos** Adicionamos a capacidade de usar filtros de produto no nosso modelo de recomendação de produtos. Agora você pode criar uma previsão que use apenas um subconjunto dos seus produtos.    
   Para obter mais informações, consulte [Configurar filtros de produto](predict-product-recommendation.md#configure-product-filters).

- **Criar segmentos com base em previsões do modelo** Adicionamos uma maneira rápida de criar segmentos usando os resultados de um modelo de previsão. Na página de resultados do modelo, você pode facilmente criar um novo segmento selecionando a nova opção **Criar segmento**.    
  Para obter mais informações, consulte [Criar um segmento com base em um modelo de previsão](prediction-based-segment.md).

- **Explicações para recomendações de produtos** Adicionamos informações explicando os principais fatores aprendidos pelo modelo de IA para gerar recomendações de produtos e o grau em que esses fatores contribuem para as recomendações de produtos. Essas informações foram adicionadas à tela de resultados do modelo.    
   Para mais informações, consulte [Analisar um status de previsão e resultados](predict-product-recommendation.md#review-a-prediction-status-and-results).

## <a name="february-2021-updates"></a>Atualizações de fevereiro de 2021

As atualizações em fevereiro de 2021 incluem vários recursos, atualizações de desempenho e correções de bugs.

#### <a name="extensibility"></a>Extensibilidade

- **Exportar segmentos para o AdRoll**

  Estendemos nossos destinos de exportação para incluir o AdRoll. Agora você pode exportar segmentos do Customer Insights para públicos-alvo do AdRoll e usá-los como a linha de base para sua publicidade. Para obter mais informações, consulte [Conector para AdRoll](export-adroll.md).

#### <a name="segments"></a>Segmentos
 
- **Duplicar um segmento**
  
  Para criar um novo segmento com base em um existente, agora você pode duplicar um segmento e editar o segmento duplicado para refiná-lo ainda mais. 

- **Adicionar outros atributos a um segmento**

  Agora você pode incluir atributos em sua saída do segmento, mesmo se esses atributos não fizerem parte do perfil do cliente. Por exemplo, inclua as IDs de assinatura em um segmento, mesmo que ele faça parte da entidade de assinatura que tenha uma relação M:1 com a entidade do cliente. Contanto que o atributo pertença a uma entidade relacionada à entidade do cliente, agora é possível incluir esses atributos.  

#### <a name="predictions"></a>Previsões

- **Criar recomendações de produto preditivas**

  Entender o que os clientes estão interessados em comprar é uma das primeiras etapas necessárias para melhorar a receita comercial e ganhar a fidelidade do cliente por meio da personalização e do envolvimento. Fornecer recomendações de produtos que não estejam alinhados aos interesses de seu cliente pode criar uma sensação de desconexão entre o cliente e sua empresa e, em última análise, limitar a receita potencial e a experiência geral de um cliente. 

  Usando seus próprios dados, agora você pode criar previsões para quais produtos seus clientes provavelmente comprarão no futuro. Para obter mais informações, consulte [Previsão de recomendação de produto](predict-product-recommendation.md).

#### <a name="system-administration"></a>Administrador do sistema

- **O ambiente de cópia oferece suporte a mais tipos de fontes de dados**

  Os administradores podem copiar as configurações do ambiente para um novo ambiente na mesma organização. Este recurso amplia a funcionalidade do ambiente de cópia para casos em que as fontes de dados com base em um data lake gerenciado do Microsoft Dataverse ou uma pasta Common Data Model são usados.

## <a name="january-2021-updates"></a>Atualizações de janeiro de 2021

As atualizações em janeiro de 2021 incluem vários recursos, upgrades de desempenho e correções de bugs.

#### <a name="extensibility"></a>Extensibilidade

- **Funcionalidade estendida e desempenho aprimorado para exportação de SFTP** Agora você pode exportar todas as entidades de saída do Customer Insights para um host SFTP. Anteriormente, a exportação era limitada a entidades de segmento. Além disso, o desempenho da exportação de SFTP permite mais volume de dados em menos tempo, dependendo do desempenho do seu host SFTP.    
  Para obter mais informações, consulte [Conector para SFTP (versão preliminar)](export-sftp.md).  

#### <a name="segments"></a>Segmentos

- **Segmentos sugeridos com tecnologia de aprendizado de máquina para melhorar as métricas** Existe uma nova maneira de descobrir e criar segmentos. O sistema usa um modelo de IA para sugerir segmentos que podem ajudar a melhorar um KPI (medida) que você já está rastreando. Mostramos a influência dos atributos que você seleciona em uma medida ou em outro atributo principal. Essas informações ajudam a encontrar segmentos potenciais que apresentam oportunidades.    
  Para obter mais informações, consulte [Segmentos sugeridos (versão preliminar)](suggested-segments.md).

#### <a name="data-unification"></a>Unificação de dados

- **Experiência de correspondência aprimorada** Na área de unificação de dados, a experiência de correspondência foi atualizada. Ela permite que você configure e visualize as regras de correspondência, incluindo estatísticas detalhadas para explicar melhor como a correspondência funciona. Existem opções para desativar uma regra de correspondência para que não fique mais ativa, enquanto mantém a configuração, regras de correspondência de arrastar e soltar e muito mais.
  Para obter mais informações, consulte [Corresponder entidades](match-entities.md).

- **A saída de duplicação do processo de correspondência está disponível como uma entidade** A saída do processo de duplicação do processo de correspondência agora é gravada em uma entidade separada para análise posterior. Essa entidade consiste nos campos usados no processo de duplicação e no registro do vencedor e nos registros alternativos correspondentes que são mesclados com o registro do vencedor.
  Para obter mais informações, consulte [Saída de duplicação como uma entidade](match-entities.md#deduplication-output-as-an-entity).

#### <a name="system-administration"></a>Administrador do sistema

- **Compartilhe dados perfeitamente com o Microsoft Dataverse** Agora você pode compartilhar a saída do Customer Insights com os aplicativos Microsoft Dataverse usando o Data Lake gerenciado do Microsoft Dataverse. Depois de associar um ambiente do Dataverse ao Customer Insights, você tem a opção de ativar o compartilhamento de dados.
  Para obter mais informações, consulte [Gerenciar ambientes](manage-environments.md).




[!INCLUDE[footer-include](../includes/footer-banner.md)]