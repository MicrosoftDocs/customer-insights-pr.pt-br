---
title: Analisar o sentimento de comentários do cliente (versão preliminar)
description: Saiba como a usar um modelo de análise de sentimento em comentários do cliente no Dynamics 365 Customer Insights.
ms.date: 09/14/2022
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 61ce9fb18efa6152dddb2e31f4fd0366a31ac2c7
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610444"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analisar o sentimento de comentários do cliente (versão preliminar)

A análise de sentimento permite sintetizar o sentimento do cliente e identificar aspectos comerciais como oportunidades de melhoria. Esse recurso do Customer Insights ajuda você a entender o que funciona bem e o que você precisa resolver. Isso pode ajudar você a promover ações comerciais que permitem experiências que resultam em alta satisfação e fidelidade do cliente.

## <a name="overview"></a>Visão geral

O recurso de análise de sentimento gera dois insights derivados por ID do cliente. Uma pontuação de sentimento (de -5 a 5) e uma lista de aspectos comerciais aplicáveis (áreas do negócio) que, juntos, ajudam você a entender melhor os comentários do cliente.

Essa análise ajudará a:
- Obter uma visão geral dos sentimentos do cliente em relação a uma marca ou organização
- Identificar clientes com sentimento negativo para focar suas campanhas e participações e otimizá-las para um retorno maior  
- Identificar aspectos comercias com problemas apontados pelos clientes  
- Segmentar os clientes com base em seu sentimento para executar campanhas personalizadas com vendas, marketing e esforços de suporte direcionados
- Otimizar as operações comerciais abordando áreas de preocupação ou oportunidades que foram mencionadas pelos clientes
- Reconhecer aspectos comerciais que estão indo bem e recompensar clientes satisfeitos por meio de programas de fidelidade e de promoções

Este modelo fornece uma lista de palavras que afetaram a decisão dos modelos de atribuir uma determinada pontuação de sentimento ou aspecto comercial aos comentários.  

Usamos dois **Modelos de processamento de linguagem natural (NLP)**: o primeiro atribui a cada comentário uma pontuação de sentimento. O segundo modelo associa cada comentário a todos os aspectos comerciais aplicáveis. Os modelos são treinados em dados públicos de fontes em redes sociais e nos setores de varejo, restaurantes, produtos de consumo e automotivo.
  
Os aspectos comerciais predefinidos para o modelo associar aos dados de comentários incluem:
- Gerenciamento de contas
- Finalização de compra e pagamento
- Suporte ao cliente
- Retirada na loja
- Envio e recuperação de embalagens
- Pré-venda
- Preço
- Privacidade e segurança
- Promoções e recompensas
- Recibo e garantia
- Devolução, troca e cancelamento
- Precisão de processamento
- Qualidade do site/aplicativo

> [!NOTE]
> No momento, só oferecemos suporte à análise de sentimento nos comentários do cliente em inglês. Ofereceremos suporte a mais idiomas no futuro. Se os comentários em outros idiomas forem carregados, o modelo ainda retornará resultados. No entanto, esses resultados não serão precisos.

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [permissões de Colaborador](permissions.md)
- Dados de feedback de texto [unificados](data-unification.md). É altamente recomendável que você [configure suas entidades de dados de comentários como entidades de atividade do tipo semântico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tipo de feedback).
- A ID Unificada do Cliente (UCID) da unificação de dados para fazer a correspondência de registros de dados de comentários de texto com um cliente individual.
- ID dos Comentários
- Carimbo de data/hora dos comentários
- Texto de comentários

O Customer Insights pode processar até 10 milhões de registros de comentários para uma única execução de modelo. O modelo pode analisar comentários de até 128 palavras. Se um comentário for mais longo, a análise considerará somente as primeiras 128 palavras.

> [!NOTE]
> Somente uma entidade de comentários pode ser configurada. Se houver várias entidades de feedback, combine-as no Power Query antes da ingestão de dados.

## <a name="configure-a-sentiment-analysis"></a>Configurar uma análise de sentimento

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Criar**, selecione **Usar modelo** no bloco **Análise de sentimento do cliente (versão preliminar)**.

1. Selecione **Introdução**.

1. **Nomeie** a análise e forneça o **Nome da entidade de saída do aspecto comercial** e o **Nome da entidade de saída da pontuação de sentimento**.

1. Selecione **Avançar**

1. Selecione **Adicionar dados** para **Feedback do cliente**.

1. Selecione o tipo de atividade semântica **Feedback** que contém os dados de feedback. Se a atividade não foi configurada, selecione **aqui** e crie-a.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Etapa de configuração para selecionar atividades de comentários para análise de sentimento.":::

1. Selecione as atividades a serem usadas para essa análise de sentimento e selecione **Avançar**.

1. Mapeie os atributos em seus dados para os atributos do modelo. 

1. Selecione **Salvar**.

1. Selecione **Avançar** A etapa **Revisar e executar** mostra um resumo da configuração e oferece a chance de fazer alterações antes de criar a análise.

1. Selecione **Editar** em qualquer uma das etapas para revisar e fazer alterações.

1. Se estiver satisfeito com as seleções, selecione **Salvar e executar** para iniciar a execução do modelo. Selecione **Concluído**. A guia **Minhas previsões** é exibida enquanto a previsão está sendo criada. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

[!INCLUDE [progress-details](includes/progress-details-pane.md)]

## <a name="view-analysis-results"></a>Visualizar resultados da análise

1. Vá para **Inteligência** > **Previsões**.

1. Na guia **Minhas previsões**, selecione a previsão que deseja visualizar.

Há dois guias de resultados:

### <a name="sumary-tab"></a>Guia Resumo

Há quatro seções principais de dados na página de resultados.

- **Pontuação média de sentimento**: as pontuações de sentimento ajudam você a entender o sentimento geral de todos os clientes.
  - **Negativo** (-5 > 2)
  - **Neutro**: (-1 > 1)
  - **Positivo** (2 > 5)
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representação visual do sentimento geral do cliente.":::

- **Distribuição de clientes por pontuação de sentimento**: os clientes são categorizados em grupos negativos, neutros e positivos com base em suas pontuações de sentimento. Passe o mouse sobre as barras no histograma para ver o número de clientes e a pontuação média de sentimento em cada grupo. Esses dados podem ajudar você a [criar segmentos de clientes](prediction-based-segment.md) com base em suas pontuações de sentimento.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gráfico de barras mostrando o sentimento do cliente nos três grupos de sentimento.":::

- **Pontuação média de sentimento ao longo do tempo**: o sentimento do cliente pode mudar ao longo do tempo. Fornecemos tendências sobre os sentimentos de seus clientes para o intervalo de tempo de seus dados. Essa exibição ajuda você a medir o efeito de promoções sazonais, lançamentos de produtos ou outras intervenções com limite de tempo sobre o sentimento do cliente. Veja o gráfico selecionando o ano de interesse no menu suspenso.

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gráfico de histórico com a pontuação de sentimento ao longo do tempo representada como uma linha.":::

- **Sentimento em todos os aspectos do negócio**: o sentimento médio em todos os aspectos de negócios ajuda a avaliar quais aspectos de seus negócios já satisfazem os clientes ou exigem mais atenção. Os registros de comentários que não se alinham a nenhum dos aspectos comerciais com suporte são categorizados em **Outros**. Classifique os dados selecionando qualquer coluna.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista de aspectos comerciais com o valor do sentimento associado e o número de clientes que o mencionam.":::

  Selecione o nome de um aspecto comercial para ver como um aspecto comercial é identificado pelo modelo:

  - **Palavras influentes**: principais palavras que influenciaram a identificação do modelo de IA de um aspecto comercial nos comentários do cliente.
    **Mostrar palavras ofensivas**: permite que você inclua palavras ofensivas na lista dos dados originais de comentários do cliente. Por padrão, essa opção está desativada.  O mascaramento de palavras ofensivas é fornecido por um modelo de IA e pode não detectar todas as palavras ofensivas. Se você detectar uma palavra ofensiva que não foi filtrada conforme o esperado, informe-nos.

    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista de palavras influentes com a alternância para mostrar ou ocultar palavras ofensivas.":::

  - **Exemplos de comentários**: registros de comentários reais em seus dados. As palavras são codificadas por cores de acordo com sua influência na identificação de um aspecto comercial.

### <a name="influential-words-analysis-tab"></a>Guia Análise de palavras influentes

Há três seções de informações adicionais que explicam como o modelo de sentimento funciona.
  
- **Principais palavras que contribuem para o sentimento positivo**: as principais palavras que influenciaram a identificação do sentimento positivo do modelo de IA nos comentários do cliente.  

- **Principais palavras que contribuem para o sentimento negativo**: as principais palavras que influenciaram a identificação do sentimento negativo do modelo de IA nos comentários do cliente.

- **Exemplos de comentários**: os registros de comentários reais, um com um sentimento negativo e outro com um sentimento positivo. As palavras nos registros de comentários são destacadas de acordo com sua contribuição para a pontuação de sentimento atribuída. As palavras que contribuem para uma pontuação de sentimento positiva estão destacadas em verde. As palavras que contribuem para uma pontuação negativa estão destacadas em vermelho.
   Selecione **Ver mais** para carregar mais amostras de feedback.
  
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemplos de análise de sentimento em comentários do cliente.":::

**Mostrar palavras ofensivas**: permite que você inclua palavras ofensivas na lista dos dados originais de comentários do cliente. Por padrão, essa opção está desativada.  O mascaramento de palavras ofensivas é fornecido por um modelo de IA e pode não detectar todas as palavras ofensivas. Se você detectar uma palavra ofensiva que não foi filtrada conforme o esperado, informe-nos.

## <a name="act-on-analysis-results"></a>Agir com base nos resultados da análise

Para criar segmentos de clientes na página de resultados da análise de sentimento, selecione **Criar segmentos** na parte superior da página de resultados do modelo.

## <a name="potential-bias"></a>Possível desvio

Como acontece com qualquer recurso que usa inteligência artificial preditiva, pode haver um possível desvio nos dados que usa para prever o sentimento do cliente. Por exemplo, se coletar comentários somente de forma digital, você poderá perder comentários de clientes que fazem negócios com você pessoalmente, o que pode afetar os resultados do recurso.

Como esse recurso usa meios automatizados para avaliar dados e fazer previsões com base nesses dados, ele tem, portanto, a capacidade de ser usado como um método de criação de perfil, conforme esse termo é definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD"). O uso desse recurso para processar dados pode estar sujeito ao GDPR ou a outras leis ou regulamentos. Você é responsável por garantir que seu uso do Dynamics 365 Customer Insights, incluindo a análise de sentimento, esteja em conformidade com todas as leis e regulamentos aplicáveis, incluindo as leis relacionadas à privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

[!INCLUDE [footer-include](includes/footer-banner.md)]

