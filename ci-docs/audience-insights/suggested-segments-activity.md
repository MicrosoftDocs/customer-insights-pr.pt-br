---
title: Segmentos sugeridos com base na atividade.
description: Deixe o Aprendizado de Máquina ajudá-lo a encontrar segmentos novos e interessantes com base na atividade do cliente.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
ms.openlocfilehash: 14d9d4f0df6b5835f21fb63447d05853ee98a757
ms.sourcegitcommit: 8341fa964365c185b65bc4b71fc0c695ea127dc0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/14/2021
ms.locfileid: "6034047"
---
# <a name="suggested-segments-based-on-activity-data-preview"></a>Segmentos sugeridos com base em dados de atividade (versão preliminar)

Descubra segmentos interessantes dos seus clientes com base nos dados de atividade do cliente que são ingeridos no Customer Insights. Exemplos de dados de atividades são transações, duração da chamada de suporte, compras ou devoluções. Para sugerir segmentos, os dados de atividades são analisados quanto à atualidade, frequência e valor monetário (ou duração). Alternativamente, você pode gerar [segmentos sugeridos para melhorar uma medida ou entender melhor o que influencia um atributo](suggested-segments.md).

:::image type="content" source="media/suggested-segments-tab.png" alt-text="Guia Segmentos sugeridos mostrando sugestões para segmentos baseados em atividades e em atributos.":::

## <a name="categorize-customers-by-activity"></a>Categorizar clientes por atividade

Com os [dados de atividade](activities.md) disponíveis no Customer Insights, podemos gerar sugestões que representam grupos de clientes:

- maioria de clientes ativos 
- clientes que fizeram mais compras 
- clientes que geraram mais receita 
- clientes que não têm estado ativos recentemente 
- clientes que interagem com sua empresa frequentemente  

Se tiver uma empresa de varejo, você pode descobrir quais clientes geram mais receita e recompensá-los com um cupom. Ou você pode identificar clientes ocasionais e convidá-los a participar de um programa de recompensas para que visitem sua empresa mais frequentemente.
Se você estiver no ramo de assistência médica fornecendo assistência médica pública e sua meta for reduzir as despesas de pacientes individuais. Uma forma de fazer isso seria reduzir as visitas recorrentes, dando o melhor atendimento possível no menor número de visitas possível. Nesse caso, seu objetivo é manter baixa a frequência de visitas e reduzir os custos recorrentes para os pacientes. Ou você pode identificar segmentos de pacientes que tenham consultas frequentes e altos custos recorrentes e analisar esses casos para melhorar o tratamento do indivíduo. 

## <a name="required-data"></a>Dados obrigatórios

As sugestões são geradas com base nos dados de entrada selecionados. 

- Perfis do cliente: todos os clientes ou membros de um segmento específico. 

- Período: mês passado, ano passado ou qualquer período de tempo personalizado.

- Tipo de atividade: compras, transações de varejo, transações online, casos de atendimento ao cliente, assinaturas e assim por diante.  

- Entidade no Customer Insights que contém os dados da atividade: a entidade UnifiedActivity ou a entidade para uma atividade específica. 

- Dimensões a serem incluídas: atualidade, frequência ou dimensão monetária, dependendo dos requisitos de negócios.

## <a name="generate-suggested-segments"></a>Gerar segmentos sugeridos

1. Vá para **Segmentos**.

1. Selecione a guia **Sugestões (versão preliminar)**.

1. Selecione **Encontre novas sugestões** e escolha **Ver ou prever o comportamento do cliente**. Selecione **Iniciar** para executar a experiência guiada.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeira etapa do assistente de configuração para um segmento sugerido com base na atividade.":::

1. Forneça os dados de entrada necessários e selecione **Avançar** para continuar.

   - Escolha os clientes: inclua todos os clientes ou um segmento específico.
   - Escolha a atividade: selecione o tipo de atividade e as entidades que a descrevem.
   - Preferências: defina o período a ser considerado, os fatores para sugestões e mapeie os atributos.

1. Revise sua entrada e selecione **Executar** para executar o modelo e gerar sugestões.

1. Dependendo da quantidade de perfis de clientes e atividades selecionadas, pode levar alguns minutos para isso ser concluído. 

Depois de gerar as sugestões, você pode filtrá-las pela dimensão ou pelo valor em que tem mais interesse. 

## <a name="view-details-of-a-suggested-segment"></a>Exibir detalhes do segmento sugerido

Assim que as sugestões forem geradas, você as encontrará listadas em **Segmentos** > **Sugestões (versão preliminar)** na seção **Sugestões baseadas em atividades**.

:::image type="content" source="media/suggested-segments-details.png" alt-text="Painel lateral expandido exibindo os dados detalhados de um segmento sugerido.":::

Selecione **Ver sugestão** em um segmento sugerido para ver os detalhes desse segmento. O painel lateral dá os detalhes, como a extensão de cada dimensão em comparação com o grupo-alvo. Ele também destaca o número de membros potenciais no segmento e o percentual correspondente do total de clientes. Se você quiser manter a sugestão como um segmento, selecione **Criar segmento**.    

## <a name="save-a-suggestion-as-a-segment"></a>Salvar uma sugestão como um segmento

1. Vá para **Segmentos** > **Sugestões (versão preliminar)**.

1. Selecione o segmento que você quer salvar. 

1. No painel lateral, selecione **Criar segmento**. 

1. Depois de salvar o segmento, ele aparecerá na lista de segmentos na guia **Todos os segmentos**. Agora, ele pode ser [atualizado ou excluído assim como qualquer outro segmento](segments.md). Você não pode editar os detalhes do segmento. Porém, você pode alterar os critérios de entrada para as sugestões e gerar outras sugestões.

## <a name="refresh-or-edit-a-set-of-suggestions"></a>Atualize ou edite um conjunto de sugestões

1. Acesse **Segmentos** > **Sugestões (versão preliminar)** e procure o segmento na seção **Sugestões baseadas em atividades**.

1. Selecione **Atualizar sugestões** para atualizar as sugestões, mantendo os atributos configurados. Ou selecione **Editar sugestões** para modificar os atributos configurados. O sistema irá executar o processo novamente, gerar sugestões de segmento com base nos dados mais recentes e substituir as sugestões atuais.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
