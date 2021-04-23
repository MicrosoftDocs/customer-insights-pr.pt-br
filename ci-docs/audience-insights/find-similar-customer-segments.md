---
title: Encontrar clientes semelhantes com IA
description: Encontrar segmentos de clientes semelhantes com inteligência artificial.
ms.date: 06/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: f588f45ed11efffbb335003642a4b92810153017
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5596761"
---
# <a name="similar-customers-preview"></a>Clientes Semelhantes (versão preliminar)

Esse recurso permite encontrar clientes semelhantes em sua base de clientes usando inteligência artificial. Você precisa ter pelo menos um segmento criado para usar esse recurso. A expansão dos critérios de um segmento existente ajuda a encontrar clientes semelhantes a esse segmento.

> [!NOTE]
> *Encontrar clientes semelhantes* usa meios automatizados para avaliar dados e fazer previsões com base nesses dados e, portanto, tem a capacidade de ser usado como um método de criação de perfil, pois esse termo é definido pelo Regulamento Geral sobre a Proteção de Dados ("RGPD"). O uso desse recurso pelo cliente para processar dados pode estar sujeito ao RGPD ou a outras leis ou regulamentos. Você é responsável por garantir que o uso do Dynamics 365 Customer Insights, incluindo as previsões, esteja em conformidade com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

## <a name="finding-similar-customers"></a>Encontrando clientes semelhantes

1. Nos insights de público-alvo, vá para **Segmentos** e selecione o segmento no qual deseja basear seu novo segmento. Esse é o seu *segmento de origem*.

1. Na barra de ação, selecione **Encontrar clientes semelhantes**.

1. Revise o nome sugerido para o seu novo segmento e altere-o, se necessário.

1. Revise os campos que definem seu novo segmento. Esses campos definem a base na qual o sistema tentará encontrar clientes semelhantes ao seu segmento de origem. O sistema selecionará os campos recomendados por padrão.
  Os campos que podem reduzir significativamente o desempenho do modelo são excluídos automaticamente:
  
   - Campos com os seguintes tipos de dados: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campos com cardinalidade (o número de elementos em um campo) menor que 2 ou maior que 30

1. Escolha se você deseja incluir **Todos os cliente** ou apenas clientes em um **Segmento existente específico** no seu novo segmento.

1. Excluir clientes no seu segmento de origem selecionando a caixa de seleção **Excluir todos no segmento de origem**.

1. Por padrão, o sistema sugere incluir apenas 20% do tamanho do público-alvo em sua saída. Edite esse limite, conforme necessário. Aumentar o limite reduzirá a precisão.

1. Selecione **Executar** na parte inferior da página, para iniciar uma tarefa de classificação binária (um método de aprendizado de máquina) que analisa o conjunto de dados.

## <a name="view-the-similar-segment"></a>Ver o segmento semelhante

Depois de processar o segmento semelhante, você encontrará o novo segmento listado na página **Segmentos**.

> [!div class="mx-imgBorder"]
> ![Segmento de clientes semelhante](media/expanded-segment.png "Segmento de clientes semelhante")

Selecione **Exibir** na barra de ação para abrir os detalhes do segmento. Essa exibição contém informações sobre a distribuição de resultados entre [pontuações de similaridade](#about-similarity-scores). Você também encontrará os valores da pontuação de similaridade na **Visualização Membros do segmento**.

## <a name="use-the-output-of-a-similar-segment"></a>Use a saída de um segmento semelhante

Você pode [trabalhar com a saída de um segmento semelhante](segments.md), como você faz com outros segmentos. Por exemplo, exporte o segmento ou crie uma medida.

## <a name="refresh-and-edit-a-similar-segment"></a>Atualize e edite um segmento semelhante

Para atualizar um segmento semelhante, selecione-o na página **Segmentos** e selecione **Atualizar** na barra de ação.

A edição de um segmento semelhante reprocessará seus dados. O segmento criado anteriormente é atualizado com dados atualizados.    
Para editar um segmento semelhante, selecione-o na página **Segmentos** e selecione **Editar** na barra de ação. Aplique suas alterações e selecione **Executar** para iniciar o processamento.

## <a name="delete-a-similar-segment"></a>Excluir um segmento semelhante

Selecione o segmento na página **Segmentos** e selecione **Excluir** na barra de ação. Em seguida, confirme a exclusão.

## <a name="about-similarity-scores"></a>Sobre pontuações de similaridade

O modelo de machine learning de classificação binário atribui uma pontuação aos clientes no segmento semelhante. A pontuação é baseada na semelhança com os clientes no segmento de origem.

- Pontuações de similaridade abaixo de 0,55 são clientes classificados pelo sistema como *não similar* para clientes no segmento de origem
- As pontuações de similaridade entre 0,55 - 0,7 são classificados como *um pouco semelhante*
- As pontuações de similaridade entre 0,7 - 0,85 são classificados como *um pouco semelhante*
- Pontuações de similaridade entre 0,85 - 1 são clientes classificados pelo sistema como *muito parecido*

Clientes com pontuações de similaridade abaixo de 0,4 não são incluídos na saída do modelo. O sistema não os considera semelhantes o suficiente para o segmento de origem.


[!INCLUDE[footer-include](../includes/footer-banner.md)]