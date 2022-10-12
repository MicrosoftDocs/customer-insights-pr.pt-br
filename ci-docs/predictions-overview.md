---
title: Visão geral das previsões
description: Cenários de previsão e opções cobertos pelo aplicativo Dynamics 365 Customer Insights.
ms.date: 09/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: overview
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: f8c61d7530126890d26ce482a27a0f97a39e836c
ms.sourcegitcommit: be341cb69329e507f527409ac4636c18742777d2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2022
ms.locfileid: "9610176"
---
# <a name="predictions-overview"></a>Visão geral das previsões

O Dynamics 365 Customer Insights é fornecido com várias opções que aproveitam a IA e o aprendizado de máquina para prever dados.

## <a name="out-of-box-models"></a>Modelos prontos para uso

A maneira mais fácil de começar com dados de previsão são os modelos predefinidos, geralmente chamados de modelos prontos para uso. Eles exigem apenas determinados dados e estrutura para gerar insights rapidamente. Os seguintes modelos estão disponíveis:

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

- [Valor da permanência do cliente](predict-customer-lifetime-value.md): prevê a receita potencial de um cliente durante toda a interação com uma empresa.
- [Recomendação de produto](predict-product-recommendation.md): sugere conjuntos de recomendações de produtos preditivos com base no comportamento de compra e clientes com padrões de compra semelhantes.
- [Rotatividade da assinatura](predict-subscription-churn.md): prevê se um cliente está em risco por não usar mais os produtos ou serviços de assinatura de sua empresa.
- [Rotatividade transacional](predict-transactional-churn.md): prevê se um cliente individual não comprará mais seus produtos ou serviços em determinado período.
- [Análise de sentimento](sentiment-analysis.md): analisa o sentimento dos comentários do cliente e identifica os aspectos comerciais que são frequentemente mencionados.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

- [Rotatividade transacional](predict-transactional-churn.md): prevê se uma conta de cliente não comprará mais seus produtos ou serviços em determinado período.

---

> [!TIP]
> Recomendamos que você atualize regularmente os modelos prontos para uso com dados atualizados para garantir que eles informem com precisão seu caso de uso comercial. Os dados são atualizados ad hoc quando o sistema ingere fontes de dados novas ou atualizadas. No entanto, os modelos só serão pontuados novamente nesse caso e continuarão usando os dados de treinamento existentes.
>
> Para configurar uma **Atualização da agenda**, defina o cronograma de retreinamento do modelo durante a configuração. O modelo será treinado e pontuado novamente conforme o cronograma, que pode ser alterado a qualquer momento.

## <a name="azure-machine-learning-integration"></a>Integração do Azure Machine Learning

Se uma organização já usa cenários de aprendizado de máquina com base em experimentos do Azure Machine Learning, o recurso de modelos personalizados no Customer Insights ajuda a conectar os pontos. Crie fluxos de trabalho que ajudem você a escolher os dados dos quais deseja gerar insights e mapeie os resultados para seus perfis de cliente unificados. Para obter mais informações, consulte [Modelos personalizados de aprendizado de máquina](custom-models.md).

## <a name="manage-existing-predictions"></a>Gerenciar previsões existentes

Vá para a página **Inteligência** > **Previsões**. Na guia **Minhas previsões**, veja as previsões que você criou, seu tipo de previsão, nome da entidade de saída, status, a última vez que a previsão foi editada e a última vez que os dados foram atualizados. Você pode classificar a lista de previsões por qualquer coluna.

Selecione uma previsão para exibir as ações disponíveis.

:::image type="content" source="media/predictions.png" alt-text="Página Minhas previsões.":::

- **Editar** a previsão para alterar suas propriedades.
- [**Atualizar**](#refresh-a-prediction) a previsão para incluir os dados mais recentes.
- **Visualizar** os detalhes da previsão.
- [**Relatório de usabilidade de dados de entrada**](#view-the-input-data-usability-report) para visualizar erros, avisos e recomendações.
- **Excluir** a previsão.

### <a name="refresh-a-prediction"></a>Atualizar uma previsão

As previsões podem ser atualizadas em uma programação automática ou manualmente sob demanda. Para atualizar manualmente todas as previsões, selecione **Atualizar tudo**. Para atualizar manualmente uma previsão, selecione-a e então **Atualizar**. Para [agendar uma atualização automática](schedule-refresh.md), acesse **Administrador** > **Sistema** > **Agenda**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

### <a name="view-the-input-data-usability-report"></a>Exibir o relatório de usabilidade de dados de entrada

O relatório de usabilidade de dados de entrada fornece uma visão consolidada dos erros e avisos que suas previsões predefinidas podem estar gerando. Isso também fornece recomendações sobre como melhorar o desempenho do modelo.

O relatório é disponibilizado depois que um modelo conclui seu processo de treinamento. É criado para cada modelo de forma separada, independentemente de o treinamento ter sido concluído com êxito ou não.

Na guia **Minhas previsões**, selecione o previsão e escolha **Relatório de usabilidade de dados de entrada**. Ou na visualização de detalhes de previsão, selecione **Relatório de usabilidade de dados de entrada**.

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo de um relatório de usabilidade de dados de entrada mostrando uma tabela com erros, avisos e recomendações.":::

O relatório inclui:

- **Nome:** nome descritivo do erro, aviso ou recomendação.
- **Etapa:** fase de modelagem, treinamento ou pontuação, a que se referem as informações.
- **Estado:** gravidade das informações (erro, aviso, recomendação).
- **Nome da coluna:** coluna em uma entidade que deve ser modificada para melhorar o desempenho do modelo.
- **Nome da entidade:** nome da entidade que deve ser modificada para melhorar o desempenho do modelo.
- **Detalhes:** detalhes sobre o erro, aviso ou recomendação.

[!INCLUDE [footer-include](includes/footer-banner.md)]
