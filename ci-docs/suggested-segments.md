---
title: Segmentos sugeridos com tecnologia de aprendizado de máquina
description: Deixe o aprendizado de máquina ajudá-lo a encontrar segmentos novos e interessantes com base nos atributos do cliente.
ms.date: 10/15/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: 5c7c6cc8231f758713b989bbe782aa03a4b78fa9
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645662"
---
# <a name="suggested-segments-preview"></a>Segmentos sugeridos (versão preliminar)

Descubra segmentos interessantes de seus clientes com a ajuda de um modelo de IA. Este recurso com tecnologia de aprendizado de máquina sugere segmentos com base em medidas ou atributos do cliente. Ele pode ajudar a melhorar seus KPIs ou entender melhor a influência dos atributos no contexto de outros atributos. 

> [!NOTE]
> O recurso de segmentos sugeridos usa meios automatizados para avaliar dados e fazer previsões com base nesses dados e, portanto, tem a capacidade de ser usado como um método de criação de perfil, conforme esse termo é definido pelo Regulamento Geral de Proteção de Dados ("GDPR"). O uso desse recurso para processar dados pode estar sujeito ao GDPR ou a outras leis ou regulamentos. Você é responsável por garantir que o uso do Dynamics 365 Customer Insights, incluindo este recurso, esteja em conformidade com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

:::image type="content" source="media/suggested-segments.png" alt-text="Página de segmentos sugeridos que mostra detalhes de uma sugestão em um painel lateral.":::

## <a name="suggested-segments-to-improve-your-kpis"></a>Segmentos sugeridos para melhorar seus KPIs

Como um usuário do Customer Insights, você provavelmente tem uma série de [medidas criadas](measures.md) que ajudam a rastrear os KPIs (Indicadores Chave de Desempenho). É importante entender como certos atributos influenciam esse KPI para criar segmentos e executar uma campanha altamente direcionada.   
Por exemplo, você acompanha uma medida chamada *TotalSpendPerCustomer*. Como empresa, você gostaria de ver esse número crescer. Escolher uma medida como atributo primário permite que você selecione os atributos que deseja avaliar para influência. Digamos *camada de associação*, *período de adesão*, e *ocupação*. O Customer Insights pode então sugerir um segmento que informa quem é a maior influência dessa medida. Por exemplo, *Contadores* quem são membros *Ouro* e que estão com sua empresa há *pelo menos cinco anos* são os maiores influenciadores de *TotalSpendPerCustomer*. Você obterá um tamanho de segmento estimado para cada sugestão. Você pode usar essas informações para criar campanhas para os públicos-alvo.

## <a name="understand-what-influences-a-customer-attribute"></a>Entenda o que influencia um atributo do cliente

Você pode escolher um atributo de cliente em vez de uma medida como o atributo primário.. Com base na sua escolha de atributos de influência, o modelo de IA cria uma série de sugestões que mostram como os atributos selecionados influenciam o atributo primário.   
Por exemplo, você escolhe *Membro Rewards (Sim/Não)* como o atributo primário. *Tempo de uso*, *Ocupação*, e *Número de tíquetes de suporte* são definidos como outros atributos de influência. O modelo de IA pode sugerir segmentos que indicam principalmente profissionais de TI com tempo de uso superior a dois anos como membros de recompensa. Outra sugestão poderia destacar que contadores com tempo de uso superior a um ano e menos de três tíquetes de suporte são membros de recompensa. 

## <a name="artificial-intelligence-usage"></a>Uso de inteligência artificial

Usando o atributo primário e os atributos de influência, um algoritmo de árvore de decisão sugere segmentos interessantes. As sugestões são baseadas em regras ou padrões que foram escolhidos pelo algoritmo de IA. Apenas segmentos que diferem significativamente da população média são mostrados como sugestões. A comparação com a população média é baseada na medida selecionada ou no atributo primário.

### <a name="responsible-ai"></a>IA responsável

Os segmentos sugeridos permitem selecionar atributos para criar novos segmentos e processar os dados selecionados. Ao escolher atributos, incluindo atributos confidenciais como raça, orientação sexual ou gênero, você deve garantir que pode e deve processar esses dados. Você é responsável por cumprir todas as leis aplicáveis à sua organização e aderir aos princípios e políticas de privacidade da sua organização.

### <a name="different-results-for-primary-attributes-with-categorical-and-numeric-values"></a>Resultados diferentes para atributos principais com valores categóricos e numéricos

As sugestões de segmento são diferentes se você escolher um atributo numérico ou um atributo categórico como o atributo primário. Os valores em um atributo categórico contêm duas ou mais categorias ou tipos. Um atributo numérico contém dados quantitativos e tem um senso de medição associado a ele.

Com um atributo numérico como *rendimento anual* ou *período de adesão* como atributo primário, o sistema sugere segmentos que possuem um valor médio maior ou menor do atributo numérico quando comparado a todos os clientes.

Um atributo categórico como *satisfação do cliente* como o atributo primário, resulta em segmentos sugeridos que têm uma porcentagem maior ou menor de clientes pertencentes a uma determinada categoria, em comparação com a porcentagem de todos os clientes pertencentes a essa mesma categoria. Por exemplo, *satisfação do cliente* é escolhido como o atributo primário e consiste em três categorias (*Baixa*, *Média* e *Alta*). Para cada categoria, serão sugeridos segmentos com uma porcentagem maior ou menor de clientes pertencentes a essa categoria, em comparação com a proporção de todos os clientes na mesma categoria. Se 22% de todos os clientes têm um nível de satisfação *Alto*, então apenas os segmentos que têm uma proporção maior ou menor de clientes com um nível de satisfação *Alto* em comparação com 22% serão sugeridos para essa categoria. Da mesma forma, segmentos serão sugeridos para cada uma das outras categorias (*Baixa* e *Média*) se forem estatisticamente significativos.

> [!NOTE]
> Atualmente, oferecemos suporte apenas a atributos categóricos principais que tenham até 10 categorias. Se você deseja ver sugestões de segmento com base em um atributo primário com mais de 10 categorias, recomendamos agrupar algumas das categorias para reduzir o número de categorias para 10 ou menos. Essa limitação se aplica apenas a atributos primários. Para influenciar atributos categóricos, atualmente oferecemos suporte para no máximo 100 categorias.

## <a name="generate-suggested-segments"></a>Gerar segmentos sugeridos

1. Vá para **Segmentos**.

1. Selecione a guia **Sugestões (versão preliminar)**.

1. Selecione **Obter novas sugestões** para iniciar a experiência guiada.

1. Escolha uma medida ou um atributo de cliente como o atributo primário e selecione **Avançar**.

   :::image type="content" source="media/suggested-segments-primary-attribute.png" alt-text="Escolha do atributo primário para sugestões nos segmentos sugeridos.":::

1. Selecione os atributos de influência e **Salvar**.
   
   > [!TIP]
   > Selecionar vários atributos de influência aumenta as chances de avaliar como eles influenciam o atributo primário. Não inclua atributos que não influenciam o atributo primário. Por exemplo, se todos os seus clientes são de um país específico, não inclua o atributo *país* porque ele não terá nenhum impacto na saída.

1. Dependendo do número de perfis de clientes e atributos selecionados, pode levar alguns minutos para processar os atributos selecionados. 

## <a name="view-details-of-a-suggested-segment"></a>Exibir detalhes do segmento sugerido

Assim que o modelo de IA gerar as sugestões, você as encontrará listadas em **Segmentos** > **Sugestões (versão preliminar)**.
 
Selecione um segmento sugerido para revisar os detalhes dessa sugestão. Você também pode revisar os valores de atributo ou regras que o modelo de IA aprendeu para sugerir o segmento selecionado.

## <a name="save-a-suggestion-as-a-segment"></a>Salvar uma sugestão como um segmento

1. Vá para **Segmentos** > **Sugestões (versão preliminar)**.

1. Selecione o segmento que você quer salvar. 

1. No painel lateral, selecione **Salvar como segmento**. 

1. Depois de salvar o segmento, ele será mostrado na lista de segmentos na guia **Todos os segmentos**. Ele agora pode ser [atualizado, editado ou excluído como qualquer outro segmento](segments.md).

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Atualize ou edite um conjunto de sugestões

1. Vá para **Segmentos** > **Sugestões (versão preliminar)**.

1. Selecione **Atualizar sugestões** para atualizar as sugestões, mantendo os atributos configurados. Ou selecione **Editar atributos** para modificar os atributos configurados. O sistema executará novamente o modelo de IA, gerará sugestões de segmento com base nos dados mais recentes e substituirá as sugestões atuais.

## <a name="limitations"></a>Limitações

1. Incompatibilidade de tamanho estimado do segmento: se você escolher um atributo primário que contém valores vazios, isso pode afetar o tamanho estimado do segmento nas sugestões de segmento. Ao salvar esse segmento, o tamanho real do segmento pode ser diferente da estimativa original.
 
2. Atributos primários do tipo booleano não funcionam: atualmente, só oferecemos suporte a tipos de dados numéricos e de string como o atributo primário.

3. Os segmentos sugeridos não são distintos o suficiente: lembre-se de que os atributos selecionados e a distribuição dos valores desses atributos influenciam os resultados. Você pode alterar seus atributos de influência ou até mesmo seu atributo primário para obter resultados diferentes.



[!INCLUDE [footer-include](includes/footer-banner.md)]