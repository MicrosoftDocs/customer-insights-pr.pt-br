---
title: Insights de segmento para segmentos existentes
description: Obtenha insights sobre os segmentos existentes para ver diferenças e semelhanças.
ms.date: 06/10/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: JimsonChalissery
ms.author: jimsonc
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 1f90b0d18331584fce306da38bd31faea93ef97e
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732298"
---
# <a name="segment-insights-preview"></a>Insights do segmento (versão preliminar)

Descubra informações e insights adicionais sobre segmentos existentes. Descubra o que diferencia dois segmentos ou o que eles têm em comum.

## <a name="segment-overlap"></a>Sobreposição de segmentos

A análise de sobreposição de segmentos mostra quantos e quais clientes são comuns a dois ou mais segmentos. Por exemplo, como um segmento de clientes frequentes se sobrepõe a um segmento que contém clientes satisfeitos com seu serviço ou produto.
Você também pode analisar como a sobreposição muda para atributos específicos.

### <a name="run-an-overlap-analysis"></a>Executar uma análise de sobreposição

1. Vá para **Segmentos** e selecione a guia **Insights (versão preliminar)**.

1. Selecione **Novo** e escolha a opção **Sobreposição** no painel **Escolher Tipo de Insight**.

1. Escolha os segmentos de interesse e selecione **Avançar**.

1. Opcionalmente, escolha um ou mais campos de interesse para analisar sobreposições para cada valor de campo possível e selecione **Avançar**.

1. Forneça um nome para a análise de sobreposição, um nome de exibição opcional e uma descrição.

1. Selecione **Salvar** para iniciar a análise. A análise de sobreposição está pronta quando o status muda de Atualizando para Bem-sucedido.

### <a name="view-and-optimize-an-overlap-analysis"></a>Exibir e otimizar uma análise de sobreposição

Após concluir a análise, encontre detalhes sobre esse insight em **Segmentos** > **Insights (versão preliminar)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-overlap.png" alt-text="Detalhes de insight da sobreposição de segmentos.":::

Selecione um insight para ver os resultados da análise:

- O número de membros que se sobrepõem aos segmentos selecionados para análise.
- O número de membros incluídos em um dos segmentos, mas não no restante dos segmentos.
- Se você selecionou campos ao configurar a análise de sobreposição, encontre-os nas guias correspondentes. Você pode usar a lista suspensa de filtros para selecionar qualquer nível de atributo de interesse, e a tabela no fim da página mostrará os dados correspondentes.

## <a name="segment-differentiators"></a>Diferenciadores de segmento

Os diferenciadores de segmento ajudam a descobrir o que diferencia um segmento dos demais clientes ou de outro segmento. Você só precisa selecionar um segmento e o sistema identificará atributos e medidas do perfil que distinguem o segmento selecionado.

### <a name="run-a-differentiator-analysis"></a>Executar uma análise diferenciadora

1. Vá para **Segmentos** e selecione a guia **Insights (versão preliminar)**.

1. Selecione **Novo** e escolha a opção **Sobreposição** no painel **Escolher Tipo de Insight**.

1. Escolha o segmento que você deseja analisar como **Segmento primário** e selecione **Avançar**.

1. Escolha **Todos os clientes** ou um **Segmento secundário** para comparar com o segmento primário e selecione **Avançar**.

1. Opcionalmente, escolha um ou mais campos de interesse para concentrar a análise em atributos específicos e selecione **Avançar**.

1. Forneça um nome para a análise de sobreposição, um nome de exibição opcional e uma descrição.

1. Selecione **Salvar** para iniciar a análise. A análise de sobreposição está pronta quando o status muda de Atualizando para Bem-sucedido.

### <a name="view-and-optimize-a-differentiators-analysis"></a>Exibir e otimizar uma análise de diferenciadores

Após concluir a análise, encontre detalhes sobre esse insight em **Segmentos** > **Insights (versão preliminar)**.

> [!div class="mx-imgBorder"]
> :::image type="content" source="media/segment-differentiators.png" alt-text="Detalhes de insight do diferenciador de segmentos.":::

Selecione um insight para ver os resultados da análise. Uma análise diferenciadora inclui duas guias. A guia **Atributos** lista os atributos de perfil considerados como diferenciadores. A guia **Medidas** lista diferenciadores. Cada guia inclui os seguintes detalhes:

- Lista classificada de diferenciadores, ordenada pela pontuação da diferença.
- A **Pontuação da diferença** para cada diferenciador. A pontuação da diferença representa o grau de diferença de um atributo entre dois segmentos. Quanto maior a pontuação da diferença, mais os atributos diferem entre os dois segmentos. Selecione uma pontuação para abrir o painel **Pontuação da diferença** com as distribuições de valores desse atributo.

## <a name="manage-segment-insights"></a>Gerenciar insights de segmentos

Você pode usar as seguintes opções em insights na barra de comandos:

- **Voltar** para retornar à lista de insights
- **Atualizar** para executar a análise novamente
- **Excluir** para remover esse insight


[!INCLUDE[footer-include](../includes/footer-banner.md)]
