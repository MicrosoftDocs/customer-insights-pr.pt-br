---
title: Enriquecer perfis de clientes com dados da Microsoft
description: Use dados proprietários da Microsoft para enriquecer os dados dos seus clientes com afinidades e share of voice.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-MS
ms.author: kishorem
manager: shellyha
searchScope:
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 12704ec46832e9463e6115db6c4df64e72bf4f97
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8372659"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enriquecer os perfis dos clientes com afinidades e share of voice (versão preliminar)

Use dados proprietários da Microsoft para enriquecer os dados dos seus clientes com afinidades de marca, afinidades de interesse e share of voice (SoV). Essas afinidades e o SoV são baseados nos dados das pessoas com demografias semelhantes às dos seus clientes. Essas informações ajudam você a entender e segmentar melhor seus clientes com base nas afinidades ou no SoV com marcas e interesses específicos que eles têm.

Em insights de público-alvo, acesse **Dados** > **Enriquecimento** para [configurar e exibir enriquecimentos](enrichment-hub.md).

Para configurar o enriquecimento de afinidades de marca e de SoV, acesse a guia **Descobrir** e selecione **Enriquecer meus dados** no bloco **Marcas**.

Para configurar o enriquecimento de afinidades de interesse e de SoV, acesse a guia **Descobrir** e selecione **Enriquecer meus dados** no bloco **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Blocos de marcas e interesses.](media/BrandsInterest-tile-Hub.png "Blocos de Marcas e Interesses")

## <a name="how-we-determine-affinities-and-sov"></a>Como determinamos afinidades e SoV

Usamos dados de pesquisa online da Microsoft para encontrar afinidades e SoV para marcas e interesses em vários segmentos demográficos (definidos por idade, sexo ou localização). O volume de pesquisa online para uma marca ou interesse constitui a base para determinar a afinidade ou o SoV. No entanto, cada um fornece uma perspectiva diferente para entender seus clientes.

- A afinidade é uma comparação entre segmentos demográficos. Você pode usar essas informações para identificar os segmentos demográficos que tenham maior afinidade com uma determinada marca ou interesse, em comparação com outros segmentos.

- O share of voice é uma comparação entre suas marcas ou interesses selecionados. Você pode usar essas informações para identificar qual marca ou interesse tem o maior share of voice para um determinado segmento demográfico, em comparação com outras marcas ou interesses selecionados.

## <a name="affinity-level-and-score"></a>Nível e pontuação de afinidade

Em cada perfil de cliente enriquecido, fornecemos dois valores relacionados: nível de afinidade e pontuação de afinidade. Esses valores ajudam a determinar o grau de afinidade para o segmento demográfico do perfil, uma marca ou interesse, em comparação a outros segmentos demográficos.

O *nível de afinidade* consiste em quatro níveis e *pontuação de afinidade* é calculado em uma escala de 100 pontos que mapeia para os níveis de afinidade.


|Nível de afinidade |Pontuação de afinidade  |
|---------|---------|
|Muito alto     | 85 a 100       |
|Alto(a)     | 70 a 84        |
|Médio(a)     | 35 a 69        |
|Baixo(a)     | 1 a 34        |

Dependendo da granularidade que deseja para medir a afinidade, é possível usar o nível ou a pontuação de afinidade. A pontuação de afinidade oferece um controle mais preciso.

## <a name="share-of-voice-sov"></a>Share of voice (SoV)

Calculamos o SoV em uma escala de 100 pontos. O SoV total em todas as marcas ou interesses para cada perfil de cliente enriquecido chega a 100. Ao contrário das afinidades, o SoV é relativo às marcas e aos interesses que você seleciona. Por exemplo, os valores de SoV para 'Microsoft' podem ser diferentes se as marcas selecionadas forem ('Microsoft', 'GitHub') em comparação com ('Microsoft', 'LinkedIn').

## <a name="supported-countriesregions"></a>Países/regiões com suporte

Atualmente, oferecemos suporte para as seguintes opções de país/região: Austrália, Canadá (inglês), França, Alemanha, Reino Unido ou Estados Unidos (inglês).

Para selecionar um país ou região, abra **Enriquecimento de marcas** ou **Enriquecimento de interesses** e selecione **Alterar** ao lado de **País/Região**. No painel **Configurações de país/região**, escolha uma opção e selecione **Aplicar**.

### <a name="implications-related-to-country-selection"></a>Implicações relativas à seleção de país

- Ao [escolher suas próprias marcas](#define-your-brands-or-interests), o sistema oferece sugestões com base no país/região selecionado.

- Ao [escolher um setor](#define-your-brands-or-interests), você obterá as marcas ou os interesses mais relevantes com base no país/região selecionado.

- Ao [enriquecer perfis](#refresh-enrichment), enriqueceremos todos os perfis de clientes dos quais obtemos dados para as marcas e interesses selecionados, incluindo perfis que não estão no país ou na região selecionada. Por exemplo, se você selecionou Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados disponíveis para as marcas e os interesses selecionados nos EUA.

## <a name="configure-enrichment"></a>Configurar enriquecimento

Uma experiência guiada ajuda você na configuração dos enriquecimentos. 

### <a name="define-your-brands-or-interests"></a>Definir suas marcas ou interesses

Escolha até cinco marcas ou interesses usando uma ou ambas as opções:

- **Setor**: selecione seu setor na lista suspensa e escolha entre as principais marcas ou interesses desse setor.
- **Escolher seus próprios**: insira uma marca ou interesse que seja relevante para sua organização e escolha uma das sugestões correspondentes. Se não listarmos uma marca ou interesse que você procura, envie-nos seus comentários usando o link **Sugerir**.

### <a name="review-enrichment-preferences"></a>Revisar preferências de enriquecimento

Revise as preferências de enriquecimento padrão e atualize-as conforme necessário.

:::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de tela da janela de preferências de enriquecimento.":::

### <a name="select-entity-to-enrich"></a>Selecione a entidade a ser enriquecida

Selecione **Entidade enriquecida** e escolha o conjunto de dados que deseja enriquecer com os dados da Microsoft. Você pode selecionar a entidade Cliente para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.

### <a name="map-your-fields"></a>Mapear seus campos

Mapeie os campos da entidade de cliente unificada para definir o segmento demográfico que deseja que o sistema use para enriquecer os dados de clientes. Mapeie País/Região e pelo menos os atributos de Data de Nascimento ou Sexo. Além disso, é necessário mapear pelo menos uma Cidade (e Estado/Província) ou CEP. Selecione **Editar** para definir o mapeamento dos campos e selecione **Aplicar** quando terminar. Selecione **Salvar** para concluir o mapeamento de campo.

Os seguintes formatos e valores têm suporte (os valores não diferenciam maiúsculas de minúsculas):

- **Data de nascimento**: recomendamos que a data de nascimento seja convertida no tipo DateTime durante a ingestão de dados. Alternativamente, pode ser uma cadeia de caracteres no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ss".
- **Sexo**: masculino, feminino, desconhecido.
- **CEP**: CEPs de cinco dígitos para os Estados Unidos, CEP padrão em todos os outros lugares.
- **Cidade**: nome da cidade em inglês.
- **Estado/Província**: abreviação de duas letras para os EUA e o Canadá. Abreviação de duas ou três letras para a Austrália. Não aplicável à França, à Alemanha ou ao Reino Unido.
- **País/Região**:

  - EUA: Estados Unidos da América, Estados Unidos, EUA, América
  - CA: Canadá, CA
  - GB: Reino Unido, Reino Unido, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha
  - AU: Austrália, AU, Comunidade das Nações da Austrália
  - FR: França, FR, República Francesa
  - DE: Alemanha, Alemanha, Deutschland, Allemagne, DE, República Federal da Alemanha, República da Alemanha

## <a name="review-and-name-the-enrichment"></a>Revise e nomeie o enriquecimento

Por último, você pode revisar as informações e fornecer um nome para o enriquecimento.

:::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisão de interesses e página de nomenclatura.":::

## <a name="refresh-enrichment"></a>Atualizar enriquecimento

Execute o enriquecimento depois de configurar marcas, interesses e o mapeamento de campo para dados demográficos. Para iniciar o processo, selecione **Executar** na página de configuração de marca ou interesse. Além disso, você pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma atualização agendada.

Dependendo do tamanho dos dados do cliente, pode levar alguns minutos para que uma execução de enriquecimento seja concluída.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultados de enriquecimento

Depois de executar o processo de enriquecimento, vá para **Meus enriquecimentos** para revisar o número total de clientes enriquecidos e um detalhamento de marcas ou interesses nos perfis de clientes enriquecidos.

:::image type="content" source="media/my-enrichments.png" alt-text="Visualização dos resultados após a execução do processo de enriquecimento.":::

Você encontrará um gráfico com o número de perfis de clientes enriquecidos ao longo do tempo e visualizações das entidades enriquecidas. Revise os dados enriquecidos selecionando **Ver mais** nos gráficos de **Nível de afinidade** ou de **Share of Voice**. Dados enriquecidos para marcas vão para as entidades **BrandAffinityFromMicrosoft** e **BrandShareOfVoiceFromMicrosoft**. Os dados para interesses estão nas entidades **InterestAffinityFromMicrosoft** e **InterestShareOfVoiceFromMicrosoft**. Você também encontrará essas entidades listadas no grupo **Enriquecimento** em **Dados** > **Entidades**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Veja dados de enriquecimento no cartão do cliente

O SoV de marca e interesse também pode ser exibido em cartões de clientes individuais. Vá para **Clientes** e selecione um perfil do cliente. No cartão do cliente, você encontrará gráficos para o SoV de marca ou de interesse com base nas pessoas nesse perfil demográfico do cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos.":::

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
