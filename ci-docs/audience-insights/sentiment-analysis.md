---
title: Análise semântica de comentários do cliente
description: Saiba como a usar um modelo de análise de sentimento em comentários do cliente no Dynamics 365 Customer Insights.
ms.date: 12/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: wmelewong
ms.author: wameng
manager: shellyha
ms.openlocfilehash: 05e530a1bc96c5fd9c7a3bc0197563d8fe330387
ms.sourcegitcommit: cb71e39de9b891c24bd5cd9c014eb3eeb537ac24
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/10/2022
ms.locfileid: "7951072"
---
# <a name="analyze-sentiment-in-customer-feedback-preview"></a>Analisar o sentimento nos comentários do cliente (versão preliminar)

Os clientes esperam produtos, serviços e experiências de alta qualidade nos dias de hoje. Especialmente os clientes que compartilham seus comentários. É muito desafiador para as organizações analisar um volume crescente de dados sem diminuir a precisão e aumentar o custo de mão de obra. O Dynamics 365 Customer Insights oferece um modelo de análise de sentimento para comentários do cliente que permite que as organizações analisem seus dados com mais precisão e a um custo menor.

A análise de sentimento permite sintetizar o sentimento do cliente e identificar aspectos comerciais como oportunidades de melhoria. Esse recurso do Customer Insights ajuda você a entender o que funciona bem e o que você precisa resolver. Concentre-se nas áreas do negócio mais relevantes e impactantes para melhorar a experiência de seus clientes. Em última análise, isso pode ajudar você a promover ações comerciais que permitem experiências que resultam em alta satisfação e fidelidade do cliente.

## <a name="overview"></a>Visão geral

O recurso de análise de sentimento gera dois insights derivados por ID do cliente. Uma pontuação de sentimento (de -5 a 5) e uma lista de aspectos comerciais aplicáveis (áreas do negócio) juntos ajudam você a entender melhor os comentários do cliente. 

Essas informações podem ajudar você a alcançar os seguintes resultados: 
- Obter uma visão geral dos sentimentos do cliente em relação a uma marca ou organização
- Identificar clientes com sentimento negativo para focar suas campanhas e participações e otimizá-las para um retorno maior  
- Identificar aspectos comercias com problemas apontados pelos clientes  
- Segmentar os clientes com base em seu sentimento para executar campanhas personalizadas com vendas, marketing e esforços de suporte direcionados
- Otimizar as operações comerciais abordando áreas de preocupação ou oportunidades que foram mencionadas pelos clientes
- Reconhecer aspectos comerciais que estão indo bem e recompensar clientes satisfeitos por meio de programas de fidelidade e de promoções

Para garantir que você possa confiar nos resultados dos modelos, fornecemos informações transparentes sobre como os modelos tomam decisões. Você receberá uma lista de palavras que afetaram a decisão dos modelos de atribuir uma determinada pontuação de sentimento ou aspecto comercial aos comentários.  

Usamos dois **Modelos de processamento de linguagem natural (NLP)**: o primeiro atribui a cada comentário uma pontuação de sentimento. O segundo modelo associa cada comentário a todos os aspectos comerciais aplicáveis. Os modelos são treinados em dados públicos de fontes em redes sociais e nos setores de varejo, restaurantes, produtos de consumo e automotivo.    
  
- Os aspectos comerciais predefinidos para o modelo associar aos dados de comentários incluem:
-   Gerenciamento de contas
-   Finalização de compra e pagamento
-   Suporte ao cliente
-   Retirada na loja
-   Envio e recuperação de embalagens
-   Pré-venda
-   Preço
-   Privacidade e segurança
-   Promoções e recompensas
-   Recibo e garantia
-   Devolução, troca e cancelamento
-   Precisão de processamento
-   Qualidade do site/aplicativo

> [!NOTE]
> No momento, só oferecemos suporte à análise de sentimento nos comentários do cliente em inglês. Ofereceremos suporte a mais idiomas no futuro. Se os comentários em outros idiomas forem carregados, o modelo ainda retornará resultados. No entanto, esses resultados não serão precisos. 

## <a name="prerequisites"></a>Pré-requisitos

A análise de sentimento é baseada em dados de comentários de texto que passaram pelo [processo de unificação de dados](data-unification.md). É altamente recomendável que você [configure suas entidades de dados de comentários como entidades de atividade do tipo semântico](map-entities.md#select-primary-key-and-semantic-type-for-attributes) (tipo de feedback) com antecedência. 

Para configurar um modelo de análise de sentimento, você precisa de, pelo menos, [Permissões de colaborador](permissions.md).

O Customer Insights pode processar até 10 milhões de registros de comentários para uma única execução de modelo. O modelo pode analisar comentários de até 128 palavras. Se um comentário for mais longo, a análise considerará somente as primeiras 128 palavras.

### <a name="data-requirements"></a>Requisitos de dados
  
Os atributos de dados a seguir são necessários:
- A ID Unificada do Cliente (UCID) para fazer a correspondência de registros de dados de comentários de texto com um cliente individual. Essa ID é resultado do [processo de unificação de dados](data-unification.md).
- ID dos Comentários
- Carimbo de data/hora dos comentários
- Texto de comentários   

> [!TIP]
> A análise de sentimento requer os comentários de texto de seus clientes. Somente uma entidade de comentários pode ser configurada atualmente. Se houver várias entidades de comentários, você poderá uni-las no Power Query antes do início da ingestão de dados.

## <a name="configure-a-sentiment-analysis"></a>Configurar uma análise de sentimento 

1. No Customer Insights, acesse **Inteligência** > **Previsões**.

1. No bloco **Análise de sentimento do cliente**, selecione **Usar modelo**.

1. No painel **Análise de sentimento do cliente (versão preliminar)**, selecione **Introdução**.

1. Na etapa **Nome do modelo**, forneça um **Nome** para sua análise. 

1. Forneça o **Nome da entidade de saída do aspecto comercial** e o **Nome da entidade de saída da pontuação de sentimento**. Em seguida, selecione **Avançar**.

1. Na etapa **Dados necessários**, selecione **Adicionar dados**.

   :::image type="content" source="media/sentiment-add-data.png" alt-text="Adicione um fluxo de dados no modelo de análise de sentimento.":::

1. No painel **Adicionar dados**, escolha o tipo semântico **Comentários** na lista.

   :::image type="content" source="media/sentiment-add-feedback-activities.png" alt-text="Etapa de configuração para selecionar atividades de comentários para análise de sentimento.":::

1. Selecione as atividades a serem usadas para essa análise de sentimento e selecione **Avançar**.
 
1. Mapeie os atributos em seus dados para os atributos do modelo. Selecione **Salvar** para aplicar as seleções. 

1. Você verá o status do mapeamento de dados. Selecione **Avançar** para continuar. 

1. Na etapa **Revisar os detalhes do seu modelo**, valide a configuração da análise de sentimento. Você pode voltar para qualquer parte da configuração de previsão. Selecione **Salvar e Executar** para iniciar a análise. 

   :::image type="content" source="media/sentiment-model-review-config.png" alt-text="Etapa de revisão do modelo de sentimento mostrando todos os itens configurados.":::

1. Selecione **Concluído** para sair da experiência de configuração. O processo pode levar várias horas para ser concluído, dependendo da quantidade de dados usada. 

## <a name="review-analysis-status"></a>Revisar o status da análise

1.  Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.
2.  Selecione a previsão que você deseja revisar.
- **Nome da previsão**: nome da previsão fornecido ao criá-la.
- **Tipo de previsão**: tipo de modelo usado para a previsão.
- **Entidade de saída**: nome da entidade que armazenará a saída da previsão. Acesse **Dados** > **Entidades** para encontrar a entidade com esse nome.
- **Campo previsto:** este campo é preenchido apenas para alguns tipos de previsões e não é usado na previsão do valor de permanência do cliente.
- **Status**: status da execução da previsão.
  - **Enfileirada**: a previsão está aguardando a conclusão de outros processos.
  - **Atualizando**: a previsão está em execução no momento para criar resultados que fluirão para a entidade de saída.
  - **Falha**: a execução da previsão falhou. Analisar os logs para obter mais detalhes.
  - **Êxito**: a previsão teve êxito. Selecione Exibir nas elipses verticais para revisar os resultados da previsão.
- **Editado**: a data em que a configuração da previsão foi alterada.
- **Última atualização**: a data em que a previsão atualizou os resultados na entidade de saída.

## <a name="manage-sentiment-analysis"></a>Gerenciar análise de sentimento

Você pode otimizar, solucionar problemas, atualizar ou excluir previsões. Revise um relatório de usabilidade de dados de entrada para descobrir como fazer uma previsão mais rápida e confiável. Para obter mais informações, consulte [Gerenciar previsões](manage-predictions.md).

## <a name="review-analysis-results"></a>Revisar resultados da análise
 
1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**. 
1. Selecione o nome da previsão da qual você deseja revisar os resultados. Nesse caso, selecione a análise de sentimento que deseja revisar. 

### <a name="summary-tab"></a>Guia Resumo

Há quatro seções principais de dados na página de resultados. 

- **Pontuação média de sentimento**: ajuda você a entender o sentimento geral de todos os clientes. As pontuações de sentimento são agrupadas em três categorias: 
  1.    Negativo (-5 > 2)
  2.    Neutro (-1 > 1)
  3.    Positivo (2 > 5) 
  
  :::image type="content" source="media/overall-customer-sentiment.png" alt-text="Representação visual do sentimento geral do cliente.":::

- **Distribuição de clientes por pontuação de sentimento**: os clientes são categorizados em grupos negativos, neutros e positivos com base em suas pontuações de sentimento. Passe o mouse sobre as barras no histograma para ver o número de clientes e a pontuação média de sentimento em cada grupo. Esses dados podem ajudar você a [criar segmentos de clientes](segments.md) com base em suas pontuações de sentimento.  

  :::image type="content" source="media/distribution-customer-sentiment.png" alt-text="Gráfico de barras mostrando o sentimento do cliente nos três grupos de sentimento.":::

- **Pontuação média de sentimento ao longo do tempo**: o sentimento do cliente pode mudar ao longo do tempo. Fornecemos tendências sobre os sentimentos de seus clientes para o intervalo de tempo de seus dados. Essa exibição pode ajudar você a medir o efeito de promoções sazonais, lançamentos de produtos ou outras intervenções com limite de tempo sobre o sentimento do cliente. Veja o gráfico selecionando o ano de interesse no menu suspenso. 

  :::image type="content" source="media/sentiment-score-over-time.png" alt-text="Gráfico de histórico com a pontuação de sentimento ao longo do tempo representada como uma linha.":::
 
- **Sentimento em todos os aspectos comerciais**: esta tabela lista o sentimento médio entre os aspectos comerciais. Ele pode ajudar você a avaliar quais aspectos do seu negócio já satisfazem os clientes ou os aspectos que exigem mais atenção. Os registros de comentários que não se alinham a nenhum dos aspectos comerciais com suporte são categorizados em **Outros**. A tabela é classificada em ordem alfabética por padrão. Você pode modificar a classificação selecionando um cabeçalho da tabela.

  :::image type="content" source="media/sentiment-across-business-aspects.png" alt-text="Lista de aspectos comerciais com o valor do sentimento associado e o número de clientes que o mencionam.":::
 
  Selecione o nome de um aspecto comercial para ver informações adicionais sobre como um aspecto comercial é identificado pelo modelo. Há duas partes neste painel: 

  - **Palavras influentes**: mostra as principais palavras que influenciaram a identificação do modelo de IA de um aspecto comercial nos comentários do cliente. 
    **Mostrar palavras ofensivas**: permite que você inclua palavras ofensivas na lista dos dados originais de comentários do cliente. Por padrão, essa opção está desativada.  O mascaramento de palavras ofensivas é fornecido por um modelo de IA e pode não detectar todas as palavras ofensivas. Continuamos iterando e treinando o classificador para obter um desempenho ideal. Se você detectar uma palavra ofensiva que não foi filtrada conforme o esperado, informe-nos. 
    
    :::image type="content" source="media/offensive-words-sentiment.png" alt-text="Lista de palavras influentes com a alternância para mostrar ou ocultar palavras ofensivas.":::
 
  - **Exemplos de comentários**: mostra os registros de comentários reais em seus dados. As palavras são codificadas por cores de acordo com sua influência na identificação de um aspecto comercial. 


### <a name="influential-words-analysis-tab"></a>Guia Análise de palavras influentes

Há três seções de informações adicionais que explicam como o modelo de sentimento funciona.
  
1. **Principais palavras que contribuem para o sentimento positivo**: mostra as principais palavras que influenciaram a identificação do sentimento positivo do modelo de IA nos comentários do cliente.  
2. **Principais palavras que contribuem para o sentimento negativo**: mostra as principais palavras que influenciaram a identificação do sentimento negativo do modelo de IA nos comentários do cliente.  
3. **Exemplos de comentários**: mostra os registros de comentários reais, um com um sentimento negativo e outro com um sentimento positivo. As palavras nos registros de comentários são destacadas de acordo com sua contribuição para a pontuação de sentimento atribuída. As palavras que contribuem para uma pontuação de sentimento positiva estão destacadas em verde. As palavras que contribuem para uma pontuação negativa estão destacadas em vermelho.
   Selecione **Ver mais** para carregar mais exemplos de comentários que fornecem mais informações e contexto de como o modelo de sentimento funciona.
   
   :::image type="content" source="media/sentiment-feedback-samples.png" alt-text="Exemplos de análise de sentimento em comentários do cliente.":::
 
**Mostrar palavras ofensivas**: permite que você inclua palavras ofensivas na lista dos dados originais de comentários do cliente. Por padrão, essa opção está desativada.  O mascaramento de palavras ofensivas é fornecido por um modelo de IA e pode não detectar todas as palavras ofensivas. Continuamos iterando e treinando o classificador para obter um desempenho ideal. Se você detectar uma palavra ofensiva que não foi filtrada conforme o esperado, informe-nos. 

## <a name="act-on-analysis-results"></a>Agir com base nos resultados da análise

Você pode facilmente começar a criar segmentos de clientes na página de resultados da análise de sentimento selecionando **Criar segmentos** na parte superior da página de resultados do modelo.

:::image type="content" source="media/create-segment-model.png" alt-text="Barra de comandos com opções nos modelos previsão.":::
 
## <a name="potential-bias"></a>Possível desvio

Como acontece com qualquer recurso que usa inteligência artificial preditiva, você deve estar ciente do possível desvio nos dados que usa para prever o sentimento do cliente. Por exemplo, se coletar comentários somente de forma digital, você poderá perder comentários de clientes que fazem negócios com você pessoalmente, o que pode afetar os resultados do recurso.

Como esse recurso usa meios automatizados para avaliar dados e fazer previsões com base nesses dados, ele tem, portanto, a capacidade de ser usado como um método de criação de perfil, conforme esse termo é definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD"). O uso desse recurso para processar dados pode estar sujeito ao GDPR ou a outras leis ou regulamentos. Você é responsável por garantir que seu uso do Dynamics 365 Customer Insights, incluindo a análise de sentimento, esteja em conformidade com todas as leis e regulamentos aplicáveis, incluindo as leis relacionadas à privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

[!INCLUDE[footer-include](../includes/footer-banner.md)]

