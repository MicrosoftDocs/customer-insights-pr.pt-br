---
title: Tarefas compartilhadas para cenários previsão
description: Saiba como gerenciar, solucionar problemas e refinar as previsões.
ms.date: 05/17/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: diegogranados117
ms.author: digranad
manager: shellyha
ms.openlocfilehash: dccb8dcca8f65f64973e46fed9d83034d58282e2
ms.sourcegitcommit: bcc47d15d4f0eacf008e4dbc09baac7f062b3ca8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2021
ms.locfileid: "6315864"
---
# <a name="manage-predictions"></a><span data-ttu-id="172f3-103">Gerenciar previsões</span><span class="sxs-lookup"><span data-stu-id="172f3-103">Manage predictions</span></span>

<span data-ttu-id="172f3-104">Este artigo discute algumas tarefas que a maioria dos cenários de previsão compartilham.</span><span class="sxs-lookup"><span data-stu-id="172f3-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="172f3-105">Solucionar uma previsão com falha</span><span class="sxs-lookup"><span data-stu-id="172f3-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="172f3-106">Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="172f3-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="172f3-107">Selecione as reticências verticais ao lado da previsão para a qual deseja exibir os logs de erros.</span><span class="sxs-lookup"><span data-stu-id="172f3-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="172f3-108">Selecione **Logs**.</span><span class="sxs-lookup"><span data-stu-id="172f3-108">Select **Logs**.</span></span>

1. <span data-ttu-id="172f3-109">Revise todos os erros.</span><span class="sxs-lookup"><span data-stu-id="172f3-109">Review all the errors.</span></span> <span data-ttu-id="172f3-110">Há vários tipos de erros que podem ocorrer e eles descrevem qual condição causou o erro.</span><span class="sxs-lookup"><span data-stu-id="172f3-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="172f3-111">Por exemplo, um erro causado por dados insuficientes para gerar uma previsão de forma precisa é geralmente resolvido ao carregar dados adicionais no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="172f3-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="172f3-112">Relatório de usabilidade de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="172f3-112">Input data usability report</span></span>

<span data-ttu-id="172f3-113">O relatório de usabilidade de dados de entrada fornece uma visão consolidada dos erros e avisos que suas previsões predefinidas podem estar gerando.</span><span class="sxs-lookup"><span data-stu-id="172f3-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="172f3-114">Ele também fornece recomendações sobre como melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="172f3-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="172f3-115">O relatório é disponibilizado depois que um modelo conclui seu processo de treinamento.</span><span class="sxs-lookup"><span data-stu-id="172f3-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="172f3-116">Ele é criado para cada modelo separadamente, independentemente de ter sido concluído com sucesso ou não.</span><span class="sxs-lookup"><span data-stu-id="172f3-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="172f3-117">Exibir o relatório de usabilidade de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="172f3-117">View the input data usability report</span></span>

<span data-ttu-id="172f3-118">Depois que um modelo pronto para uso tiver concluído sua etapa de treinamento, exiba o relatório:</span><span class="sxs-lookup"><span data-stu-id="172f3-118">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="172f3-119">Selecione as reticências ao lado do nome do modelo e escolha **Relatório de usabilidade de dados de entrada**.</span><span class="sxs-lookup"><span data-stu-id="172f3-119">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="172f3-120">Selecione o status de um modelo em **Ver Relatório de usabilidade de dados de entrada** no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="172f3-120">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="172f3-121">Selecione um dos modelos na lista e, em seguida, selecione **Relatório de usabilidade de dados de entrada** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="172f3-121">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="172f3-122">Abra a página de resultados do modelo e selecione **Relatório de usabilidade de dados de entrada** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="172f3-122">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="172f3-123">Informações no relatório de usabilidade de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="172f3-123">Information in the input data usability report</span></span>

<span data-ttu-id="172f3-124">As colunas a seguir no relatório contêm informações úteis para aprimorar os dados do modelo.</span><span class="sxs-lookup"><span data-stu-id="172f3-124">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo de um relatório de usabilidade de dados de entrada mostrando uma tabela com erros, avisos e recomendações.":::

- <span data-ttu-id="172f3-126">Nome: nome descritivo do erro, aviso ou recomendação.</span><span class="sxs-lookup"><span data-stu-id="172f3-126">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="172f3-127">Etapa: fase de modelagem, treinamento ou pontuação, a que se referem as informações.</span><span class="sxs-lookup"><span data-stu-id="172f3-127">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="172f3-128">Estado: severidade da informação (erro, aviso, recomendação).</span><span class="sxs-lookup"><span data-stu-id="172f3-128">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="172f3-129">Nome da coluna: coluna em uma entidade que deve ser modificada para melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="172f3-129">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="172f3-130">Nome da entidade: nome da entidade que deve ser modificada para melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="172f3-130">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="172f3-131">Detalhes: detalhes sobre o erro, aviso ou recomendação.</span><span class="sxs-lookup"><span data-stu-id="172f3-131">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="172f3-132">Atualizar uma previsão</span><span class="sxs-lookup"><span data-stu-id="172f3-132">Refresh a prediction</span></span>

<span data-ttu-id="172f3-133">As previsões serão atualizadas automaticamente no mesmo [cronograma de atualização dos dados](system.md#schedule-tab) conforme definido nas configurações.</span><span class="sxs-lookup"><span data-stu-id="172f3-133">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="172f3-134">Você também pode atualizá-las manualmente.</span><span class="sxs-lookup"><span data-stu-id="172f3-134">You can refresh them manually too.</span></span>

1. <span data-ttu-id="172f3-135">Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="172f3-135">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="172f3-136">Selecione os três pontos verticais ao lado da previsão que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="172f3-136">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="172f3-137">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="172f3-137">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="172f3-138">Excluir uma previsão</span><span class="sxs-lookup"><span data-stu-id="172f3-138">Delete a prediction</span></span>

<span data-ttu-id="172f3-139">A exclusão de uma previsão também remove sua entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="172f3-139">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="172f3-140">Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="172f3-140">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="172f3-141">Selecione os três pontos verticais ao lado da previsão que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="172f3-141">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="172f3-142">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="172f3-142">Select **Delete**.</span></span>
