---
title: Segmentos sugeridos com base em atividade (versão preliminar)
description: Deixe o Aprendizado de Máquina ajudá-lo a encontrar segmentos novos e interessantes com base na atividade do cliente.
ms.date: 05/11/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
manager: shellyha
searchScope:
- ci-segment-suggestions
- customerInsights
ms.openlocfilehash: df4f5f4b5c9a3ad66d57a6b349e18a0d714aff62
ms.sourcegitcommit: 8a28e9458b857adf8e90e25e43b9bc422ebbb2cd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/18/2022
ms.locfileid: "9170575"
---
# <a name="suggested-segments-based-on-activity-preview"></a>Segmentos sugeridos com base em atividade (versão preliminar)

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
Se fornecer serviços de saúde pública e seu objetivo for minimizar as despesas para pacientes individuais, você poderia tentar reduzir as consultas recorrentes fornecendo o melhor atendimento possível no menor número de consultas possível. Nesse caso, seu objetivo é manter baixa a frequência de visitas e reduzir os custos recorrentes para os pacientes. Ou você pode identificar segmentos de pacientes que tenham consultas frequentes e altos custos recorrentes e analisar esses casos para melhorar o tratamento do indivíduo.

## <a name="required-data"></a>Dados obrigatórios

As sugestões são geradas com base nos dados de entrada selecionados.

- Perfis do cliente: todos os clientes ou membros de um segmento específico.

- Período: mês passado, ano passado ou qualquer período de tempo personalizado.

- Tipo de atividade: compras, transações de varejo, transações online, casos de atendimento ao cliente, assinaturas e assim por diante.  

- Entidade no Customer Insights que contém os dados da atividade: a entidade UnifiedActivity ou a entidade para uma atividade específica.

- Dimensões a serem incluídas: atualidade, frequência ou dimensão monetária, dependendo dos requisitos de negócios.

## <a name="generate-suggested-segments"></a>Gerar segmentos sugeridos

1. Acesse **Segmentos** e selecione a guia **Sugestões (versão preliminar)**.

1. Selecione **Encontre novas sugestões** e escolha **Ver ou prever o comportamento do cliente**. Selecione **Iniciar**.

   :::image type="content" source="media/suggested-segments-activity-wizard.png" alt-text="Primeira etapa do assistente de configuração para um segmento sugerido com base na atividade.":::

1. Forneça os dados de entrada necessários e selecione **Avançar**.

   - Escolha os clientes: inclua todos os clientes ou um segmento específico.
   - Escolha a atividade: selecione o tipo de atividade e as entidades que a descrevem.
   - Preferências: defina o período a ser considerado, os fatores para sugestões e mapeie os atributos.

1. Revise sua entrada e selecione **Executar** para executar o modelo e gerar sugestões.

Dependendo da quantidade de perfis de clientes e atividades selecionadas, pode levar alguns minutos para isso ser concluído.

Depois de gerar as sugestões, você pode filtrá-las pela dimensão ou pelo valor em que tem mais interesse.

## <a name="manage-suggested-segments"></a>Gerenciar segmentos sugeridos

Acesse **Segmentos** e selecione a guia **Sugestões (versão preliminar)**. Na seção **Sugestões baseadas em atividade**, selecione um segmento sugerido para exibir as ações disponíveis.

- **Veja a sugestão** para exibir os detalhes desse segmento, como a extensão de cada dimensão em comparação com o grupo-alvo. Ele também destaca o número de membros potenciais no segmento e o percentual correspondente do total de clientes.
- **Crie o segmento** para salvar o sugerido como um segmento. Ele será exibido na guia **Todos os segmentos** e poderá ser [atualizado ou excluído](segments.md). Você não pode editar os detalhes do segmento. Porém, você pode alterar os critérios de entrada para as sugestões e gerar outras sugestões.
- **Edite as sugestões** para modificar os atributos configurados que substituirão as sugestões atuais.
- **Atualize as sugestões** para atualizar as sugestões enquanto mantêm os atributos configurados.

[!INCLUDE [footer-include](includes/footer-banner.md)]
