---
title: Recursos novos e futuros
description: Informações sobre novos recursos, melhorias e correções de bugs.
ms.date: 11/02/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: midevane
manager: shellyha
ms.openlocfilehash: 07b4bee0445f9cd7d53a37cd405af839feb07ae3
ms.sourcegitcommit: 4004eadac7a65e50e0a409cb925958523c2b6348
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2020
ms.locfileid: "4649990"
---
# <a name="whats-new-in-the-audience-insights-capability-of-dynamics-365-customer-insights"></a>O que há de novo no recurso de insights do público-alvo do Dynamics 365 Customer Insights

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Estamos animados para anunciar nossas atualizações mais recentes! Este artigo resume os recursos de recursos de versão preliminar pública, aprimoramentos de disponibilidade geral e atualizações de recursos. Para ver os planos de recurso a longo prazo, consulte os [Planos de lançamento do Dynamics 365 e do Power Platform](https://docs.microsoft.com/dynamics365/release-plans/).

Você também pode assistir ao vídeo a seguir para saber mais sobre os recursos planejados para os últimos seis meses.

> [!VIDEO https://www.youtube.com/embed/jQh-7pscH30]

Distribuímos atualizações por região. Portanto, determinadas regiões podem ver recursos antes de outras. A menos que especificado de forma diferente, você não precisa tomar medidas e atualizaremos o aplicativo automaticamente, sem tempo de inatividade.

> [!TIP]
> Para enviar e votar em solicitações de recursos e sugestões de produto, acesse o [portal de ideias do aplicativo do Dynamics 365](https://experience.dynamics.com/ideas/categories/?forum=79a8c474-4e35-e911-a971-000d3a4f3343&forumName=Dynamics%20365%20Customer%20Insights).

## <a name="november-2020-updates"></a>Atualizações de novembro de 2020

As atualizações em novembro de 2020 incluem vários recursos, atualizações de desempenho e correções de bugs.

### <a name="new-and-updated-features-in-november-2020"></a>Recursos novos e atualizados em novembro de 2020

#### <a name="data-enrichment"></a>Enriquecimento de dados

- **Traga seus próprios dados de enriquecimento por meio de importação personalizada de protocolo de transferência de arquivos seguro (SFTP)**
  
  A importação personalizada de SFTP permite importar dados de enriquecimento que não precisam passar pelo processo de unificação de dados. Saiba mais sobre a importação personalizada de SFTP.

  Para mais informações, consulte [Enriquecer os perfis dos clientes com dados personalizados (versão preliminar)](enrichment-SFTP-custom-import.md).
 
- **Enriqueça os dados do seu cliente com dados de localização da HERE Technologies**

  Com os serviços de enriquecimento de dados da HERE Technologies, você pode criar uma compreensão mais precisa da localização de seus clientes com normalização de endereço, extração de latitude e longitude e muito mais. Saiba mais sobre como enriquecer com HERE Technologies.

  Para mais informações, consulte [Enriquecimento dos perfis dos clientes com HERE Technologies](enrichment-here.md).

#### <a name="data-unification"></a>Unificação de dados

- **Flexibilidade para permitir a criação de perfis de dados em entidades e campos selecionados de sua conta de armazenamento**

  Você pode indicar quais entidades e campos de dados de uma pasta do Common Data Model em sua conta do Azure Data Lake storage você deseja habilitar a criação de perfil de dados como parte do processo de ingestão de dados.

  Para mais informações, consulte [Conectar-se a uma pasta do Common Data Model](connect-common-data-model.md#connect-to-a-common-data-model-folder).

#### <a name="extensibility"></a>Extensibilidade

- **Ative seus segmentos por meio do Google Ads**

  Exporte segmentos de para listas de público-alvo do Google Ads e use essas listas para anunciar na Pesquisa do Google, Rede de Display do Google, YouTube e Gmail. Saiba mais sobre como ativar seus segmentos por meio do Google Ads.

  Para obter mais informações, consulte [Conector para Google Ads](export-google-ads.md).

- **Ative seus segmentos por meio do Marketo**

  Exporte segmentos para públicos do Marketo e use esses públicos para automação de marketing. Saiba mais sobre como ativar seus segmentos por meio do Marketo. 

  Para obter mais informações, consulte [Conector para Marketo](export-marketo.md).

- **Ative seus segmentos por meio do DotDigital**

  Exporte segmentos para DotDigital e use-os para fins de marketing. Saiba mais sobre como ativar seus segmentos por meio do DotDigital. 

  Para obter mais informações, consulte [Conector para DotDigital](export-dotdigital.md).

#### <a name="predictions"></a>Previsões

- **Previsão de rotatividade transacional**

  O recurso de previsão de rotatividade de transações permite que você, sem a ajuda de um cientista de dados, preveja a probabilidade de um cliente parar de comprar produtos ou serviços.  Usando a pontuação de previsão, você pode combinar outras informações sobre seus clientes, como valor do cliente, para criar segmentos de alto risco de rotatividade ou clientes de alto valor. Use este segmento para atingir clientes diretamente por meio de atividades de marketing, suporte ao cliente e outros cenários para reduzir o risco de rotatividade.
 
  Configure a definição de rotatividade como uma janela baseada no tempo específica para o seu negócio e defina quando os clientes são considerados rotativos. Por exemplo, um supermercado pode querer considerar um cliente cancelado se ele não tiver comprado nada nos últimos 30 dias.
 
  Conforme você continua criando a previsão, nós o orientaremos sobre quais dados são necessários e permitiremos que você mapeie os dados sobre seu negócio para os campos necessários para prever a rotatividade de seus clientes. Você também pode definir uma programação para retreinar o modelo com base em novas informações em seu sistema para se adaptar às mudanças nas circunstâncias de negócios.
 
  Para mais informações, consulte [Previsão de rotatividade transacional (versão preliminar)](predict-transactional-churn.md).

#### <a name="system-administration"></a>Administrador do sistema

- **Redefinir ambiente**

  Redefina tudo em um ambiente de uma instância selecionada para começar do zero.

  Para obter mais informações, consulte [Redefinir um ambiente existente](manage-environments.md#reset-an-existing-environment).


- **Conecte-se à sua conta do Azure Data Lake storage usando uma entidade de serviço**

  Grave a saída de dados e leia os dados de sua conta de armazenamento usando uma entidade de serviço do Azure. As conexões de conta de armazenamento existentes podem continuar a usar a chave da conta. Eles também oferecem uma opção de atualização para usar a entidade de serviço no futuro. Novas conexões serão baseadas no método de autenticação da entidade de serviço para sua conta de armazenamento.

  Para mais informações, consulte [Conectar-se a uma conta Azure Data Lake Storage Gen2 com uma entidade de serviço do Azure para insights do público-alvo](connect-service-principal.md).

## <a name="october-2020-updates"></a>Atualizações de outubro de 2020

As atualizações em outubro de 2020 incluem vários recursos, atualizações de desempenho e correções de bugs.

### <a name="new-and-updated-features-in-october-2020"></a>Recursos novos e atualizados em outubro de 2020

#### <a name="extensibility"></a>Extensibilidade

- **Exportar para o Mailchimp**

Exporte segmentos para listas de público existentes no Mailchimp para fornecer uma experiência de email personalizada para seus clientes.

Para obter mais informações, consulte [Conector para Mailchimp](export-mailchimp.md).

#### <a name="data-enrichment"></a>Enriquecimento de dados

- **Desduplique os registros de origem em uma entidade Match**

Especifique regras de desduplicação em entidades usadas no processo de correspondência para identificar registros duplicados. Mescle-os em um registro e vincule todos os registros de origem a este registro mesclado. Esse registro desduplicado será então usado no processo de correspondência entre entidades.

Para mais informações, consulte [Definir a desduplicação em uma entidade correspondente](match-entities.md#define-deduplication-on-a-match-entity).

#### <a name="system-administration"></a>Administrador do sistema

- **Orquestração: nova opção de atualização no Merge**

Até hoje, quando você executa o processo de mesclagem, o sistema executa todos os processos downstream que dependem da mesclagem e processos subsequentes. Agora, você pode verificar a saída do processo de mesclagem (a entidade de cliente unificada) antes de usá-lo no processamento downstream, como segmentos ou medidas.
Na página de mesclagem, agora você pode optar por executar apenas a etapa de mesclagem e executar apenas este processo. Para atualizar todos os processos downstream também, você pode escolher executar processos de mesclagem e downstream. 

## <a name="september-2020-updates"></a>Atualizações de setembro de 2020

As atualizações em setembro de 2020 incluem vários recursos, upgrades de desempenho e correções de bugs.

### <a name="new-and-updated-features-in-september-2020"></a>Recursos novos e atualizados em setembro de 2020

#### <a name="activities"></a>Atividades

- **Previsão inteligente de semântica de atributos**

Este novo recurso prevê os tipos semânticos de atributos de entrada que são passados para o processo de unificação de dados. Ele usa modelos aprendizado de máquina que aumentam a precisão e economizam tempo.

#### <a name="enrichments"></a>Enriquecimentos

- **Enriquecimento de dados demográficos da Experian**

O enriquecimento de dados demográficos da Experian agora está disponível na versão preliminar. A Experian é líder global em serviços de marketing e relatórios de crédito para consumidores e empresas. Com os [serviços de enriquecimento de dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage), você pode compreender melhor seus clientes enriquecendo os perfis desses clientes com dados demográficos, como número de pessoas na família, renda e muito mais.

Para usar esse recurso, você deve ter uma assinatura ativa da Experian.

Para obter mais informações, consulte [Enriquecer os perfis de clientes com dados demográficos da Experian](enrichment-experian.md)


#### <a name="system-administration"></a>Administrador do sistema

- **Painel de detalhes da tarefa**

O painel de detalhes da tarefa permite que você veja detalhes sobre as tarefas que o sistema executa. É uma maneira prática de identificar problemas com a configuração e encontrar soluções.
Analise as mensagens de erro para ver como tratar os possíveis problemas.
 
- **Processamento de informações adicionadas a páginas adicionais**

Esta melhoria adiciona informações sobre o status de suas entidades na página **Entidades** e **Clientes**.
 
Além disso, você pode encontrar detalhes sobre o andamento dos processos, junto com os detalhes da tarefa, em ambas as páginas.

- **Melhorias na página de status do sistema**

Melhoramos a estrutura da tabela de detalhes de status em **Sistema** > **Status** ao revisar as exportações de dados.
 
Além disso, os erros na coluna **Detalhes** agora são mais detalhados e acionáveis. 
 
- **Cancelar reverte o trabalho para o estado anterior**

Quando você cancela uma tarefa, por exemplo, no processo de correspondência, ela será revertida para o estado mais recente. Por exemplo, se o processo Corresponder foi concluído ontem e você o cancelou hoje, ele voltará ao estado de sucesso de ontem.


## <a name="august-2020-updates"></a>Atualizações de agosto de 2020

As atualizações em agosto de 2020 incluem vários recursos, upgrades de desempenho e correções de bugs.

### <a name="new-and-updated-features-in-august-2020"></a>Recursos novos e atualizados em agosto de 2020

#### <a name="data-unification"></a>Unificação de dados

- **Experiência aprimorada para o estágio de mapa durante a unificação de dados**

  A experiência para o estágio de mapa no processo de unificação de dados permite selecionar entidades, atributos e definir a semântica de uma maneira mais contínua.

  As alterações incluem:
  
  - menos interações necessárias para adicionar entidades e campos
  - recursos de pesquisa aprimorados na página do mapa
  - identificação visual e fácil do tipo de campo sugerido

#### <a name="enrichment"></a>Enriquecimento

- **Enriquecimento de afinidades de interesse disponível em mercados adicionais**

  Estamos estendendo a disponibilidade do enriquecimento de afinidades de interesse além dos Estados Unidos para cinco mercados adicionais: Canadá, Austrália, Reino Unido, França e Alemanha. Com essa extensão, você poderá enriquecer seus dados de cliente com interesses adicionais aplicáveis a esses mercados. Também enriqueceremos os perfis de clientes localizados nesses mercados usando dados proprietários locais do Microsoft Graph.
  Para obter mais informações, consulte [Enriquecer os perfis de clientes com afinidades de marca e de interesse](enrichment-microsoft-graph.md)


## <a name="july-2020-updates"></a>Atualizações de julho de 2020

As atualizações em julho de 2020 incluem vários recursos, upgrades de desempenho e correções de bugs.

### <a name="new-and-updated-features-in-july-2020"></a>Recursos novos e atualizados em julho de 2020

#### <a name="extensibility"></a>Extensibilidade

- **Gatilho do Power Automate para processo de unificação completo**

  Estendemos nossos gatilhos do Power Automate e permitimos que você crie uma notificação ou uma ação quando uma atualização do processo de unificação (mapear, combinar, mesclar) for concluída.    
  Para obter mais informações, consulte o [conector do Power Automate](export-power-automate.md)

#### <a name="enrichment"></a>Enriquecimento

- **Enriquecimento das afinidades de marca disponível em mercados adicionais**

  Estamos estendendo a disponibilidade do enriquecimento das afinidades de marca além dos Estados Unidos para cinco mercados adicionais: Canadá, Austrália, Reino Unido, França e Alemanha. Com essa extensão, você poderá enriquecer os dados de clientes com marcas locais nesses mercados. Também enriqueceremos os perfis de clientes localizados nesses mercados usando dados proprietários locais do Microsoft Graph.
  Para obter mais informações, consulte [Enriquecer os perfis de clientes com afinidades de marca e de interesse](enrichment-microsoft-graph.md)

## <a name="june-2020-updates"></a>Atualizações de junho de 2020

As atualizações em junho de 2020 incluem vários recursos, upgrades de desempenho e correções de bugs.

### <a name="new-and-updated-features-in-june-2020"></a>Recursos novos e atualizados em junho de 2020

#### <a name="enrichment"></a>Enriquecimento

- **Enriquecimento com dados da empresa do Leadspace**
  
  Defina campos em perfis de clientes unificados que são usados para consultar dados da empresa relacionados no Leadspace. Depois de executar o processo de enriquecimento, os perfis B2B são enriquecidos com atributos adicionais, incluindo tamanho, localização e setor da empresa e muito mais.    
  Essa colaboração permite que você melhore a qualidade de seus dados com entradas de serviços de terceiros. Para usar esse enriquecimento, você precisará de uma licença do Leadspace para acessar os dados de empresa B2B. O sistema usará essa licença para manter seus dados enriquecidos continuamente.    
  Para obter mais informações, consulte [Enriquecimento de perfis de empresas com o Leadspace](enrichment-leadspace.md).

- **Página do hub de enriquecimento**

  Todo o enriquecimento de dados disponível de provedores de enriquecimento próprios e terceirizados é configurado no mesmo lugar. A configuração do enriquecimento de dados é uma experiência contínua gerenciada a partir de um local comum.    
  Para obter mais informações, consulte [Enriquecimento para perfis de clientes](enrichment-hub.md).

- **Enriquecimento separado afinidade de interesse e de marca**

  As afinidades de interesse e de marca estão agora disponíveis como dois enriquecimentos independentes. Os enriquecimentos separados oferecem a flexibilidade de configurá-los e gerenciá-los individualmente, dependendo dos requisitos ou necessidades de seu negócio.    
  Para obter mais informações, consulte [Enriquecer os perfis de clientes com afinidades de marca e de interesse](enrichment-microsoft-graph.md).

#### <a name="extensibility"></a>Extensibilidade

- **URLs clicáveis para atividades unificadas no Complemento do cartão do cliente do Dynamics 365**

  As atividades unificadas no suplemento do cartão do cliente agora mostram URLs clicáveis se essas URLs foram definidas durante a configuração das atividades.    
  Para obter mais informações, consulte [Complemento do Cartão do Cliente](customer-card-add-in.md).

- **Afinidades de marca e de interesse disponíveis no Complemento do cartão do cliente do Dynamics 365**

  Um novo controle no Complemento do cartão do cliente do Dynamics 365 permite que você mostre enriquecimentos de marca e de interesse em seus contatos em aplicativos de interação com os clientes no Dynamics 365.    
  Para obter mais informações, consulte [Complemento do Cartão do Cliente](customer-card-add-in.md).

- **Gatilhos adicionais do Power Automate**

  Estendemos nossos gatilhos do Power Automate e adicionamos os seguintes gatilhos:
  - Receber uma notificação ou executar uma ação quando uma atualização completa automatizada (fontes de dados, unificação, segmentos, medidas, exportações) for concluída
  - Defina um limite para uma medida de negócios. Por exemplo, você pode criar uma notificação que é enviada quando o limite definido é passado. Além disso, o gatilho traz informações que permitem criar fluxos de trabalho mais complexos no Power Automate.    
  Para obter mais informações, consulte o [conector do Power Automate](export-power-automate.md)

- **Exportar para o Facebook Ads Manager**
  
  Este recurso permite exportar segmentos para Gerenciador de anúncios do Facebook. Os segmentos são exportados como públicos-alvo personalizados para usar perfis de clientes unificados em campanhas de marketing e anúncios do Facebook. Os públicos-alvo personalizados também podem ser usados para criar campanhas no Instagram por meio do Facebook Ads Manager.    
  Para obter mais informações, consulte [Conector para o FacebookAds Manager](export-facebook.md).

#### <a name="predictions"></a>Previsões

- **Previsão de rotatividade de assinaturas**

  Siga uma experiência guiada para criar previsão de rotatividade em áreas de assinatura, como serviços de nuvem, associação de clientes e outros setores. 

  O recurso de previsão de rotatividade de assinaturas permite prever a probabilidade de um cliente interromper o uso de produtos ou serviços baseados em assinatura sem envolver um cientista de dados. Usando a pontuação de previsão, você pode combinar outras informações sobre seus clientes para criar segmentos de alto risco de rotatividade. Com a ajuda desse segmento, você pode direcionar diretamente os clientes em marketing, suporte ao cliente e outros cenários para reduzir o risco de rotatividade de clientes específicos para melhorar a receita e reduzir custos.

  Dentro da experiência, você pode configurar a definição de rotatividade como uma janela baseada no tempo específica para o seu negócio. Por exemplo, uma empresa de streaming de vídeo que tem um processo de assinatura mensal pode querer considerar que um cliente abandonou o serviço após 15 dias do vencimento da assinatura.

  À medida que você continua na previsão, nós o orientaremos sobre quais dados são necessários e permitiremos que você mapeie os dados sobre sua empresa aos campos obrigatórios para prever a rotatividade de seus clientes. Conforme as informações de negócios mudam, você também pode definir uma programação para retreinar seu sistema com novas informações para se adaptar às mudanças nas circunstâncias de negócios.    
  Para obter mais informações, consulte [Previsão de rotatividades de assinaturas (versão preliminar)](predict-subscription-churn.md).

#### <a name="segments"></a>Segmentos

- **Localizar clientes semelhantes**
  
  Encontre clientes semelhantes em sua base de clientes usando a inteligência artificial. Um modelo de aprendizado de máquina de classificação binária atribui uma pontuação de similaridade aos clientes no segmento expandido. A pontuação é baseada na semelhança com os clientes no segmento de origem. Dependendo da pontuação de similaridade, os perfis de clientes são adicionados a um segmento recém-criado.

  Às vezes chamado de modelagem idêntica no marketing digital, ele usa um modelo de IA para ajudar a encontrar clientes que são semelhantes a outro segmento de seus clientes, levando em consideração atributos adicionais. Ele não permite apenas que você selecione os atributos. Ele também permite que você especifique o número máximo de clientes que devem estar nesse novo segmento. O modelo de IA, então, computará pontuações de similaridade para cada cliente com base em seus atributos selecionados e encontrará clientes com a pontuação de similaridade média mais alta. O segmento resultante incluirá clientes que se parecem com o cliente em seu segmento original.    
  Para obter mais informações, consulte [Clientes semelhantes](find-similar-customer-segments.md).

- **Diferenciadores e sobreposição de segmentos**

  A sobreposição de segmentos permite que você veja quantos e quais clientes são comuns a dois ou mais segmentos. Por exemplo, como um segmento de clientes com altos gastos se sobrepõe a um segmento de clientes com alta satisfação, ou como um segmento de clientes em rotatividade se sobrepõe a um segmento de clientes com baixa satisfação. Além disso, você pode analisar como a sobreposição muda com base em um atributo adicional de sua escolha.

  Os diferenciadores de segmentos revelam o que diferencia um segmento do resto de seus clientes ou de outro segmento. Tudo o que você precisa fazer é identificar um segmento e o sistema identificará os atributos e medidas do perfil que distinguem o segmento na forma de uma lista classificada de diferenciadores, do diferenciador mais forte ao mais fraco.    
  Para obter mais informações, consulte [Informações de segmentos (versão preliminar)](segment-insights.md).

- **Vida útil do segmento**
  
  Defina uma programação para ativar ou desativar um segmento.    
  Para obter mais informações, consulte [Gerenciar segmentos existentes](segments.md#manage-existing-segments).

## <a name="may-2020-updates"></a>Atualizações de maio de 2020

As atualizações em maio de 2020 incluem vários recursos, atualizações de desempenho e correções de bugs.

### <a name="new-and-updated-features-in-may-2020"></a>Recursos novos e atualizados em maio de 2020

#### <a name="data-ingestion"></a>Ingestão de dados

- **Ingestão de dados em tempo real: exibições de histórico**

  Ao usar nossa API para ingerir atualizações em tempo real, você verá até 30 dias de histórico agregado para essas atualizações. Você tem acesso a agregações de todas as chamadas de API bem-sucedidas ou com falha, incluindo resultado, sistema de origem e outros metadados úteis.    
  Para obter mais informações, consulte [Ingestão de dados em tempo real](real-time-data-ingestion.md).

- **Ingestão de dados em tempo real: atualizações de perfil**

  Essa extensão da ingestão de dados em tempo real permite ver, em segundos, alterações em campos específicos do perfil do usuário.    
  Além da funcionalidade em tempo real para atividades, o sistema suporta atualizações de baixa latência para campos de perfil. As atualizações em tempo real de campos de perfil têm uma data de validade e, portanto, não substituem as atualizações agendadas.    
  Para obter mais informações, consulte [Ingestão de dados em tempo real](real-time-data-ingestion.md).

#### <a name="extensibility"></a>Extensibilidade

- **Linha do tempo e paginação atualizadas no Complemento do Cartão do Cliente**

  A linha do tempo da solução Complemento do Cartão do Cliente corresponde à linha do tempo da atividade. A paginação da linha do tempo melhorou, mostrando até 50 atividades ao mesmo tempo. Ela também permite carregar atividades adicionais na linha do tempo.    
  Para obter mais informações, consulte [Complemento do Cartão do Cliente](customer-card-add-in.md).

- Gatilho do **Power Automate para alterações de segmento**

  Gatilhos para o Power Automate definem o que você pode criar de um fluxo. O gatilho recém-adicionado permite definir um limite para um segmento. Por exemplo, você pode criar uma notificação que é enviada quando o limite definido é passado.    
  Para obter mais informações, consulte o [conector do Power Automate](export-power-automate.md).

- **Suporte multilocatário para modelos personalizados**

  Configure fluxos de trabalho para modelos personalizados com um serviço Web de um locatário diferente do Azure Machine Learning. Você pode fazer logon no locatário Azure Machine Learning ao criar um novo fluxo de trabalho para modelos personalizados. Esse recurso é um complemento ao recurso existente de integração com seu próprio serviço Web personalizado do Azure Machine Learning.    
  Para obter mais informações, consulte [Modelos personalizados de aprendizado de máquina](custom-models.md).

#### <a name="segments"></a>Segmentos

- **Automação do caminho da entidade**

  Ao criar um segmento, os usuários precisam definir o caminho da entidade. Esse recurso é o primeiro passo para automatizar a definição do caminho da entidade para que você possa se concentrar nos critérios de segmentação que tem em mente.    
  Se a entidade pela qual você deseja segmentar clientes estiver diretamente relacionada à entidade cliente unificado, você não precisará mais definir o caminho da entidade. No entanto, se houver mais de um caminho de entidade possível, você ainda precisará defini-lo manualmente.

- **Ações em vários segmentos**
  
  Os usuários podem selecionar vários segmentos e executar ações neles, como atualizar os segmentos, com um único clique.    

- **Atualizar segmentos**

  Os usuários podem atualizar um único segmento ou selecionar apenas os segmentos que desejam atualizar.    

  
- **Melhorias nos segmentos compostos**

  Os usuários podem criar, editar e excluir segmentos que se baseiam em outros segmentos. Por exemplo, um segmento construído em outro segmento que foi construído em um terceiro segmento.    

- **Página lista de segmentos**

  O novo design da página de segmentos usa um formato de lista que permite ver mais segmentos de uma só vez. Um campo de pesquisa é adicionado para encontrar segmentos rapidamente. Agora, os usuários podem aplicar ações como fazer o download ou excluir em vários segmentos de uma vez. Uma nova experiência de tendência é apresentada para identificar rapidamente mudanças significativas nos segmentos.    
  Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

#### <a name="system-administration"></a>Administrador do sistema

- **Customer Insights disponível no Microsoft Dynamics 365 Online Government**

  Com cada vez mais canais para interações, os dados do cidadão são espalhados por vários sistemas, levando a dados em silos e uma visão fragmentada das informações sobre as interações do cidadão. Sem uma visão completa das interações de cada cidadão entre os canais, é impossível que os governos se modernizem em escala. A Microsoft está comprometida em apoiar as necessidades de tecnologia do governo para acompanhar as expectativas dos cidadãos em relação a experiências consistentes e responsivas.    
  Com a onda 1 da versão 2020, o Dynamics 365 Customer Insights estará disponível para o Government Community Cloud (GCC), um ambiente criado para atender às mais altas necessidades de conformidade dos órgãos governamentais dos Estados Unidos. As agências obtêm uma visão unificada dos cidadãos e usam a IA pré-criada para obter insights que melhoram as interações, capacitam os funcionários e transformam comunidades, reduzindo a complexidade da TI e atendendo aos padrões de conformidade e segurança dos Estados Unidos. O Dynamics 365 Government atende aos exigentes requisitos do Programa Federal de Gerenciamento de Riscos e Autorizações dos EUA (FedRAMP), permitindo que as agências federais dos Estados Unidos se beneficiem da economia de custos e da segurança rigorosa do Microsoft Cloud.

## <a name="april-2020-updates"></a>Atualizações de abril de 2020

As atualizações em abril de 2020 incluem vários recursos, atualizações de desempenho e correções de bugs.

### <a name="new-and-updated-features-in-april-2020"></a>Recursos novos e atualizados em abril de 2020

#### <a name="activities"></a>Atividades

- **Mapear entidade de atividade para o tipo de atividade padrão**
  
  Atualmente, a configuração e o armazenamento de atividades são baseados em um design estático para exibi-los em uma linha do tempo. O significado semântico das atividades, que tem potencial para vários casos de uso em modelos de IA, não é totalmente usado no momento. Pretendemos tornar a linha do tempo da atividade mais dinâmica, com base no tipo de atividade e no melhor entendimento semântico das atividades. Esse recurso tem como objetivo identificar o tipo de atividade, conforme definido no Common Data Model, para qualquer atividade ingerida.
  Para obter mais informações, consulte [Atividades do cliente](activities.md).

#### <a name="data-ingestion"></a>Ingestão de dados

- **Ingestão de dados em tempo real: atividades**
  
  Ingestão de dados em tempo real fornece dados imediatamente para consumo, até que a atualização programada subsequente extraia esses dados de fonte de dados.    
  Para obter mais informações, consulte [Ingestão de dados em tempo real](real-time-data-ingestion.md).

- **Melhorias na preparação de dados**
  
  Saiba mais sobre os dados ingeridos em uma entidade. Com o resumo dos dados, você pode entender as características de qualidade dos dados que podem ajudar a tomar as medidas apropriadas.    
  Para obter mais informações, consulte [Explorar dados da entidade](entities.md#exploring-a-specific-entitys-data).

- **Ingerir dados analíticos do Dynamics 365 com o Common Data Service**
  
  Common Data Service está disponível como uma forma de criar fontes de dados. Os clientes existentes do Dynamics 365 podem ingerir entidades analíticas do Common Data Service para o Customer Insights. Uma única fonte de dados pode usar simultaneamente o mesmo Common Data Service gerenciado em um ambiente de Customer Insights.    
  Para obter mais informações, consulte [Conecte-se aos dados em um data lake gerenciado pelo Common Data Service](connect-common-data-service-lake.md).

#### <a name="extensibility"></a>Extensibilidade

- **Exportar para LiveRamp**

  Ative seus dados no LiveRamp® para conectar-se a mais de 500 plataformas nos ecossistemas digital, social e de TV. Aproveite seus dados no LiveRamp para segmentar, suprimir e personalizar campanhas publicitárias.    
  Para obter mais informações, consulte o [conector do LiveRamp&reg;](export-liveramp.md).

- **Complemento de equipes do Customer Insights**
  
  O bot fornece recursos de pesquisa para perfis unificados de clientes. Ele exibirá um cartão com até 15 campos do perfil do cliente resultante. Várias correspondências retornam uma lista de resultados onde você pode selecionar um perfil.    
  Para obter mais informações, consulte [Bot de equipes do Customer Insights](export-teams-bot.md).

#### <a name="measures"></a>Medidas

- **Página lista de medidas**
  
  As melhorias na página de medidas incluem suporte para ações em uma única medida e em várias medidas ao mesmo tempo. Além disso, você encontrará um campo de pesquisa para localizar e rastrear medidas rapidamente.    
  Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

- **Melhorias em medidas compostas**
  
  Os usuários podem criar, editar e excluir medidas que se baseiam em outras medidas. Por exemplo, uma medida construída em outra medida que foi construída em uma terceira medida.

#### <a name="segments"></a>Segmentos

- **Operador adicional**
  
  O operador In-set permite a segmentação para clientes por vários valores possíveis de cadeia de caracteres. Antes da adição deste operador, você precisava construir esses segmentos com várias condições OR. O operador In-set permite fazer isso com uma única condição.    
  Para obter mais informações, consulte [Criar e gerenciar segmentos](segments.md).

#### <a name="system-administration"></a>Administrador do sistema

- **Copiar as configurações em um novo ambiente**
  
  Copie sua configuração de um ambiente para outro. Ao criar um novo ambiente, você pode selecionar um ambiente existente do qual deseja copiar a configuração. Atualmente, oferecemos suporte a fontes de dados, unificação de dados, relacionamentos, medidas e segmentos a serem copiados. Credenciais de fonte de dados e dados reais não são copiados.    
  Para obter mais informações, consulte [Gerenciar ambientes](manage-environments.md).
