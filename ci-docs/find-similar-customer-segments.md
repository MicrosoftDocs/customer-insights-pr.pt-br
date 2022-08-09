---
title: Encontrar clientes semelhantes com IA (versão preliminar) (contém vídeo)
description: Encontrar segmentos de clientes semelhantes com inteligência artificial.
ms.date: 03/25/2022
ms.subservice: audience-insights
ms.topic: conceptual
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-segment-builder
- ci-segment-insights
- customerInsights
ms.openlocfilehash: 09fe36a4da45d114cbfccf8dad1e7b80b4b7e320
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170713"
---
# <a name="find-similar-customers-with-ai-preview"></a>Encontrar clientes semelhantes com IA (versão preliminar)

Encontre clientes semelhantes em sua base de clientes usando a inteligência artificial. Você precisa de pelo menos um segmento criado para usar este recurso. Expandir os critérios de um segmento existente ajuda a encontrar clientes que sejam semelhantes a esse segmento.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOFou]

> [!NOTE]
> *Encontrar clientes semelhantes* usa meios automatizados para avaliar os dados e fazer previsões com base nesses dados. Portanto, ele tem a possibilidade de ser usado como um método de criação de perfil, conforme o termo é definido pelo Regulamento Geral sobre a Proteção de Dados (RGPD). O uso desse recurso pelo cliente para processar dados pode estar sujeito ao RGPD ou a outras leis ou regulamentos. Você é responsável por garantir que o uso do Dynamics 365 Customer Insights, incluindo as previsões, esteja em conformidade com todas as leis e regulamentos aplicáveis, incluindo leis relacionadas a privacidade, dados pessoais, dados biométricos, proteção de dados e confidencialidade das comunicações.

## <a name="find-similar-customers"></a>Localizar clientes semelhantes

1. Vá para **Segmentos** e selecione o segmento no qual deseja basear o novo segmento. Esse é o seu *segmento de origem*.

1. Selecione **Encontrar clientes semelhantes**.

1. Revise o nome sugerido para o seu novo segmento e altere-o, se necessário.

1. Opcionalmente, adicione [marcas](work-with-tags-columns.md#manage-tags) ao novo segmento.

1. Revise os campos que definem seu novo segmento. Esses campos definem a base na qual o sistema tentará encontrar clientes semelhantes ao seu segmento de origem. O sistema seleciona os campos recomendados por padrão. Se necessário, adicione mais campos.
  Os campos que podem reduzir significativamente o desempenho do modelo são excluídos automaticamente:
  
   - Campos com os seguintes tipos de dados: StringType, BooleanType, CharType, LongType, IntType, DoubleType, FloatType, ShortType
   - Campos com cardinalidade (o número de elementos em um campo) menor que 2 ou maior que 30

1. Escolha de deseja incluir **Todos os clientes**, exceto o segmento de origem ou somente os clientes em um **segmento diferente** em seu novo segmento.

1. Por padrão, o sistema sugere incluir apenas 20% do tamanho do público-alvo em sua saída. Edite esse limite, conforme necessário. Aumentar o limite reduzirá a precisão.

1. Inclua clientes em seu segmento de origem marcando a caixa de seleção **Incluir membros do segmento de origem além dos clientes com atributos semelhantes**.

1. Selecione **Executar** na parte inferior da página para iniciar uma [tarefa de classificação binária](#about-similarity-scores) (um método de aprendizado de máquina) que analisa o conjunto de dados.

## <a name="view-the-similar-segment"></a>Ver o segmento semelhante

Após o processamento do segmento semelhante, você encontrará o novo segmento listado na página **Segmentos** com o tipo **Expansão**.

Selecione **Exibir** para ver a distribuição do resultado nas [pontuações de similaridade](#about-similarity-scores) e os valores da pontuação de similaridade em **Visualização dos membros do segmento**.

:::image type="content" source="media/expanded-segment.png" alt-text="Segmento de clientes semelhante.":::

## <a name="manage-a-similar-segment"></a>Gerenciar um segmento semelhante

[Trabalhe e gerencie um segmento semelhante](segments.md#manage-existing-segments) da mesma maneira que faz com outros segmentos. Por exemplo, exporte o segmento ou crie uma medida.

Edite, atualize, renomeie, baixe e exclua um segmento semelhante. Editar um segmento semelhante reprocessa seus dados. O segmento criado anteriormente é atualizado com dados atualizados.

## <a name="about-similarity-scores"></a>Sobre pontuações de similaridade

O modelo de machine learning de classificação binário atribui uma pontuação aos clientes no segmento semelhante. A pontuação é baseada na semelhança com os clientes no segmento de origem.

- Pontuações de similaridade abaixo de 0,55 são clientes classificados pelo sistema como *não similar* para clientes no segmento de origem
- As pontuações de similaridade entre 0,55 - 0,7 são classificados como *um pouco semelhante*
- As pontuações de similaridade entre 0,7 - 0,85 são classificados como *um pouco semelhante*
- Pontuações de similaridade entre 0,85 - 1 são clientes classificados pelo sistema como *muito parecido*

Clientes com pontuações de similaridade abaixo de 0,4 não são incluídos na saída do modelo. O sistema não os considera semelhantes o suficiente para o segmento de origem.

[!INCLUDE [footer-include](includes/footer-banner.md)]
