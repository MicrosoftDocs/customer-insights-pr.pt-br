---
title: Enriqueça os perfis dos clientes com o Microsoft Graph
description: Use dados proprietários do Microsoft Graph para enriquecer os dados de seus clientes com afinidades de marca e interesse.
ms.date: 09/28/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 4f93a2337815f76b98185ecb3755e08443031748
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405021"
---
# <a name="enrich-customer-profiles-with-brand-and-interest-affinities-preview"></a>Enriquecer perfis de clientes com afinidades de marca e interesse (versão prévia)

Use dados proprietários do Microsoft Graph para enriquecer os dados de seus clientes com afinidades de marca e interesse. Essas afinidades são determinadas com base em dados de pessoas com dados demográficos semelhantes aos de seus clientes. Essas informações ajudam a entender e segmentar melhor seus clientes com base em suas afinidades com marcas e interesses específicos.

Em insights de público-alvo, acesse **Dados** > **Enriquecimento** para [configurar e exibir enriquecimentos](enrichment-hub.md).

Para configurar o enriquecimento das afinidades da marca, vá para a guia **Descobrir** e selecione **Enriquecer meus dados** no bloco **Marcas**.

Para configurar o enriquecimento das afinidades do interesse, vá para a guia **Descobrir** e selecione **Enriquecer meus dados** no bloco **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Blocos de Marcas e Interesses](media/BrandsInterest-tile-Hub.png "Blocos de Marcas e Interesses")

## <a name="about-microsoft-graph"></a>Sobre o Microsoft Graph

Usamos dados de pesquisa online do Microsoft Graph para encontrar afinidades por marcas e interesses em vários segmentos demográficos (definidos por idade, sexo ou local). O volume de pesquisa online de uma marca ou interesse determina quanta afinidade um segmento demográfico, em comparação com outros segmentos, tem com essa marca ou interesse.

[Saiba mais sobre o Microsoft Graph](https://docs.microsoft.com/graph/overview).

## <a name="affinity-score-and-confidence"></a>Pontuação de afinidade e confiança

A **pontuação de afinidade** é calculada em uma escala de 100 pontos, com 100 representando o segmento que tem maior afinidade por uma marca ou interesse.

A **confiança de afinidade** também é calculada em uma escala de 100 pontos. Indica o nível de confiança do sistema de que um segmento tem uma afinidade pela marca ou interesse. O nível de confiança é baseado no tamanho do segmento e na granularidade do segmento. O tamanho do segmento é determinado pela quantidade de dados que temos para um determinado segmento. A granularidade do segmento é determinada por quantos atributos (idade, sexo, local) estão disponíveis em um perfil.

Não normalizamos as pontuações para o seu conjunto de dados. Consequentemente, talvez você não veja todos os valores possíveis de pontuação de afinidade para o seu conjunto de dados. Por exemplo, pode não haver perfil de cliente enriquecido com pontuação de afinidade 100 em seus dados. Isso é possível se não houver clientes no segmento demográfico com pontuação 100 para uma determinada marca ou interesse.

> [!TIP]
> Ao [criar segmentos](segments.md) usando pontuações de afinidade, revise a distribuição de pontuações de afinidade para o seu conjunto de dados antes de decidir sobre os limites de pontuação apropriados. Por exemplo, uma pontuação de afinidade de 10 pode ser considerada significativa em um conjunto de dados que possui uma pontuação de afinidade mais alta de apenas 25 para uma determinada marca ou interesse.

## <a name="supported-countriesregions"></a>Países/regiões com suporte

Atualmente, oferecemos suporte para as seguintes opções de país/região: Austrália, Canadá (inglês), França, Alemanha, Reino Unido ou Estados Unidos (inglês).

Para selecionar um país, abra o **Enriquecimento de marcas** ou **Enriquecimento de interesse** e selecione **Alterar** ao lado de **País/Região**. No painel **Configurações de país/região**, escolha uma opção e selecione **Aplicar**.

### <a name="implications-related-to-country-selection"></a>Implicações relativas à seleção de país

- Quando [escolher suas próprias marcas](#define-your-brands-or-interests), forneceremos sugestões com base no país/região selecionado.

- Ao [escolher um setor](#define-your-brands-or-interests), identificaremos as marcas ou interesses mais relevantes com base no país/região selecionado.

- Quando [mapear seus campos](#map-your-fields), se o campo País/Região não estiver mapeado, usaremos os dados do Microsoft Graph do país/região selecionado para enriquecer perfis de clientes. Também usaremos essa seleção para enriquecer perfis de clientes que não têm dados de país/região disponíveis.

- Ao [enriquecer perfis](#refresh-enrichment), enriqueceremos todos os perfis de clientes para os quais temos dados do Microsoft Graph disponíveis para as marcas e interesses selecionados, incluindo perfis que não estão no país/região selecionado. Por exemplo, se você selecionou Alemanha, enriqueceremos os perfis localizados nos Estados Unidos se tivermos dados do Microsoft Graph disponíveis para as marcas e interesses selecionados nos Estados Unidos.

## <a name="configure-enrichment"></a>Configurar Enriquecimento

A configuração do enriquecimento de marcas ou interesses consiste em duas etapas:

### <a name="define-your-brands-or-interests"></a>Definir suas marcas ou interesses

Selecione uma das seguintes opções:

- **Setor**: o sistema identifica as principais marcas ou interesses relevantes para o seu setor e enriquece os dados dos seus clientes com eles.
- **Escolher seus próprios**: selecione até cinco itens da lista de marcas ou interesses mais relevantes para sua organização.

Para adicionar uma marca ou interesse, insira-a na área de entrada para obter sugestões com base nos termos correspondentes. Se não listarmos uma marca ou interesse que você procura, envie-nos seus comentários usando o link **Sugerir**.

### <a name="map-your-fields"></a>Mapear seus campos

Mapeie os campos da sua entidade unificada do cliente para pelo menos dois atributos para definir o segmento demográfico que você deseja que utilizemos para enriquecer os dados do cliente. Selecione **Editar** para definir o mapeamento dos campos e selecione **Aplicar** quando terminar. Selecione **Salvar** para concluir o mapeamento de campo.

Os seguintes formatos e valores têm suporte; os valores não diferenciam maiúsculas de minúsculas:

- **Data de nascimento**: recomendamos que a data de nascimento seja convertida no tipo DateTime durante a ingestão de dados. Como alternativa, pode ser uma string no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ssZ".
- **Gênero**: Masculino, Feminino, Desconhecido
- **Código postal**: CEPs de cinco dígitos para os EUA, código postal padrão em todos os outros lugares
- **Cidade**: nome da cidade em inglês
- **Estado/Província**: abreviação de duas letras para os EUA e o Canadá. Abreviação de duas ou três letras para a Austrália. Não aplicável à França, à Alemanha ou ao Reino Unido.
- **País/Região**:

  - EUA: Estados Unidos da América, Estados Unidos, EUA, América
  - CA: Canadá, CA
  - GB: Reino Unido, Reino Unido, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha
  - AU: Austrália, AU, Common Wealth of Australia
  - FR: França, FR, República Francesa
  - DE: Alemanha, Alemanha, Deutschland, Allemagne, DE, República Federal da Alemanha, República da Alemanha

## <a name="refresh-enrichment"></a>Atualizar enriquecimento

Execute o enriquecimento depois de configurar marcas, interesses e o mapeamento de campo para dados demográficos. Para iniciar o processo, selecione **Executar** na página de configuração de marca ou interesse. Além disso, você pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma atualização agendada.
Dependendo do tamanho dos dados do cliente, pode levar alguns minutos para que uma execução de enriquecimento seja concluída.

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="enrichment-results"></a>Resultados de enriquecimento

Depois de executar o processo de enriquecimento, vá para **Meus enriquecimentos** para revisar o número total de clientes enriquecidos e um detalhamento de marcas ou interesses nos perfis de clientes enriquecidos.

:::image type="content" source="media/my-enrichments.png" alt-text="Visualização dos resultados após a execução do processo de enriquecimento":::

Revise os dados enriquecidos selecionando **Exibir Dados enriquecidos** no gráfico. Dados enriquecidos para marcas vão para a entidade **BrandAffinityFromMicrosoft**. Os dados para interesses estão na entidade **InterestAffinityFromMicrosoft**. Você também encontrará essas entidades listadas no grupo **Enriquecimento** em **Dados** > **Entidades**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Veja dados de enriquecimento no cartão do cliente

As afinidades de marca e interesse também podem ser visualizadas em cartões de clientes individuais. Vá para **Clientes** e selecione um perfil do cliente. No cartão do cliente, você encontrará gráficos das marcas ou interesses pelos quais as pessoas no perfil demográfico desse cliente têm afinidade.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos":::

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Crie [Segmentos](segments.md), [Medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.
