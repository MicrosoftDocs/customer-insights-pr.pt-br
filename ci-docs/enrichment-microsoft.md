---
title: Enriqueça os perfis dos clientes com dados de marcas e interesses da Microsoft
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
ms.openlocfilehash: 61262980cafdcd130430e200e466ce7da6cc4d07
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953751"
---
# <a name="enrich-customer-profiles-with-affinities-and-share-of-voice-preview"></a>Enriquecer os perfis dos clientes com afinidades e share of voice (versão preliminar)

Use dados proprietários da Microsoft para enriquecer os dados dos seus clientes com afinidades de marca, afinidades de interesse e share of voice (SoV). Essas afinidades e o SoV são baseados nos dados das pessoas com demografias semelhantes às dos seus clientes. Essas informações ajudam você a entender e segmentar melhor seus clientes com base nas afinidades ou no SoV com marcas e interesses específicos que eles têm.

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

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

   - Para configurar o enriquecimento de afinidades de marca e de SoV, selecione **Enriquecer meus dados** no bloco **Marcas**.

   - Para configurar o enriquecimento de afinidades de interesse e de SoV, selecione **Enriquecer meus dados** no bloco **Interesses**.

   > [!div class="mx-imgBorder"]
   > ![Blocos de marcas e interesses.](media/BrandsInterest-tile-Hub.png "Blocos de Marcas e Interesses")

1. Revise a visão geral e selecione **Avançar**.

1. Para alterar seu país ou região, selecione **Alterar** ao lado de **País/Região**. No painel **Configurações de país/região**, escolha um [país/região com suporte](#supported-countriesregions) e selecione **Aplicar**.

   > [!NOTE]
   > Ao escolher suas próprias marcas, o sistema oferece sugestões com base no país/região selecionado. Ao escolher um setor, você obterá as marcas ou os interesses mais relevantes com base no país/região selecionado.

1. Escolha até cinco marcas ou interesses usando uma ou ambas as opções:

   - **Setor**: selecione seu setor na lista suspensa e escolha entre as principais marcas ou interesses desse setor.
   - **Escolher seus próprios**: insira uma marca ou interesse que seja relevante para sua organização e escolha uma das sugestões correspondentes. Se não listarmos uma marca ou interesse que você procura, envie-nos seus comentários usando o link **Sugerir**.

1. Selecione **Avançar** e revise suas preferências de enriquecimento padrão e atualize-as conforme necessário.

   :::image type="content" source="media/affinity-enrichment-preferences.png" alt-text="Captura de tela da janela de preferências de enriquecimento.":::

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer com dados da Microsoft. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

1. Selecione **Avançar**

1. Mapeie seus campos de sua entidade de cliente unificada para os dados da Microsoft.

   > [!NOTE]
   > Pelo menos os atributos Data de Nascimento ou Sexo são obrigatórios. País/Região e pelo menos Cidade (e Estado/Província) ou CEP são obrigatórios. Recomendamos que a data de nascimento seja convertida no tipo DateTime durante a ingestão de dados. Alternativamente, pode ser uma cadeia de caracteres no formato [ISO 8601](https://www.iso.org/iso-8601-date-and-time-format.html) "aaaa-MM-dd" ou "aaaa-MM-ddTHH:mm:ss".

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento. O **Nome da entidade de saída** é selecionado automaticamente.

   :::image type="content" source="media/enrichment-interests-summary.png" alt-text="Revisão de interesses e página de nomenclatura.":::

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Executar** para iniciar o processo de enriquecimento ou feche para voltar para a página **Enriquecimentos**.

   Ao enriquecer perfis, enriqueceremos todos os perfis de clientes dos quais obtemos dados para as marcas e interesses selecionados, incluindo perfis que não estão no país ou na região selecionada. Por exemplo, se você selecionou Alemanha, enriqueceremos perfis localizados nos Estados Unidos se tivermos dados disponíveis para as marcas e os interesses selecionados nos EUA.

## <a name="enrichment-results"></a>Resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

:::image type="content" source="media/my-enrichments.png" alt-text="Visualização dos resultados após a execução do processo de enriquecimento.":::

Os resultados incluem os gráficos **Nível de afinidade** ou **Compartilhamento de Voz**.

As entidades criadas dos enriquecimentos estão listadas no grupo **Enriquecimento** em **Dados** > **Entidades**. Dados enriquecidos para marcas vão para as entidades **BrandAffinityFromMicrosoft** e **BrandShareOfVoiceFromMicrosoft**. Os dados para interesses estão nas entidades **InterestAffinityFromMicrosoft** e **InterestShareOfVoiceFromMicrosoft**.

## <a name="see-enrichment-data-on-the-customer-card"></a>Veja dados de enriquecimento no cartão do cliente

O SoV de marca e interesse também pode ser exibido em cartões de clientes individuais. Vá para **Clientes** e selecione um perfil do cliente. No cartão do cliente, você encontrará gráficos para o SoV de marca ou de interesse com base nas pessoas nesse perfil demográfico do cliente.

:::image type="content" source="media/enrichment-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos.":::

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]


[!INCLUDE [footer-include](includes/footer-banner.md)]
