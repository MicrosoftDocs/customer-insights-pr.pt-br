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
ms.openlocfilehash: b935be08199f20e83bceb3317985b0e1dc120016
ms.sourcegitcommit: 6b07c9c3102761be162e4842f3c9fbc19f948a9b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2021
ms.locfileid: "6095684"
---
# <a name="manage-predictions"></a><span data-ttu-id="630c9-103">Gerenciar previsões</span><span class="sxs-lookup"><span data-stu-id="630c9-103">Manage predictions</span></span>

<span data-ttu-id="630c9-104">Este artigo discute algumas tarefas que a maioria dos cenários de previsão compartilham.</span><span class="sxs-lookup"><span data-stu-id="630c9-104">This article discusses some tasks that most prediction scenarios share.</span></span>

## <a name="troubleshoot-a-failed-prediction"></a><span data-ttu-id="630c9-105">Solucionar uma previsão com falha</span><span class="sxs-lookup"><span data-stu-id="630c9-105">Troubleshoot a failed prediction</span></span>

1. <span data-ttu-id="630c9-106">Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="630c9-106">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="630c9-107">Selecione as reticências verticais ao lado da previsão para a qual deseja exibir os logs de erros.</span><span class="sxs-lookup"><span data-stu-id="630c9-107">Select the vertical ellipses next to the prediction you want to view error logs for.</span></span>

1. <span data-ttu-id="630c9-108">Selecione **Logs**.</span><span class="sxs-lookup"><span data-stu-id="630c9-108">Select **Logs**.</span></span>

1. <span data-ttu-id="630c9-109">Revise todos os erros.</span><span class="sxs-lookup"><span data-stu-id="630c9-109">Review all the errors.</span></span> <span data-ttu-id="630c9-110">Há vários tipos de erros que podem ocorrer e eles descrevem qual condição causou o erro.</span><span class="sxs-lookup"><span data-stu-id="630c9-110">There are several types of errors that can occur, and they describe what condition caused the error.</span></span> <span data-ttu-id="630c9-111">Por exemplo, um erro causado por dados insuficientes para gerar uma previsão de forma precisa é geralmente resolvido ao carregar dados adicionais no Customer Insights.</span><span class="sxs-lookup"><span data-stu-id="630c9-111">For example, an error that there's not enough data to accurately predict is typically resolved by loading additional data into Customer Insights.</span></span>

## <a name="input-data-usability-report"></a><span data-ttu-id="630c9-112">Relatório de usabilidade de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="630c9-112">Input data usability report</span></span>

<span data-ttu-id="630c9-113">O relatório de usabilidade de dados de entrada fornece uma visão consolidada dos erros e avisos que suas previsões predefinidas podem estar gerando.</span><span class="sxs-lookup"><span data-stu-id="630c9-113">The input data usability report provides a consolidated view of the errors and warnings that your out-of-box predictions may be generating.</span></span> <span data-ttu-id="630c9-114">Ele também fornece recomendações sobre como melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="630c9-114">It also gives recommendations how to improve the model performance.</span></span>

<span data-ttu-id="630c9-115">O relatório é disponibilizado depois que um modelo conclui seu processo de treinamento.</span><span class="sxs-lookup"><span data-stu-id="630c9-115">The report is available after a model has completed its training process.</span></span> <span data-ttu-id="630c9-116">Ele é criado para cada modelo separadamente, independentemente de ter sido concluído com sucesso ou não.</span><span class="sxs-lookup"><span data-stu-id="630c9-116">It's created for each model separately, regardless if it completed successfully or not.</span></span>

> [!NOTE]
> <span data-ttu-id="630c9-117">No momento, esse recurso funciona somente para o modelo de Rotatividade da Transações.</span><span class="sxs-lookup"><span data-stu-id="630c9-117">Currently, this feature only works for the Transaction Churn model.</span></span>

### <a name="view-the-input-data-usability-report"></a><span data-ttu-id="630c9-118">Exibir o relatório de usabilidade de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="630c9-118">View the input data usability report</span></span>

<span data-ttu-id="630c9-119">Depois que um modelo pronto para uso tiver concluído sua etapa de treinamento, exiba o relatório:</span><span class="sxs-lookup"><span data-stu-id="630c9-119">After an out-of-box model has completed its training step, view the report:</span></span>
- <span data-ttu-id="630c9-120">Selecione as reticências ao lado do nome do modelo e escolha **Relatório de usabilidade de dados de entrada**.</span><span class="sxs-lookup"><span data-stu-id="630c9-120">Select the ellipses next to the model name and choose **Input data usability report**.</span></span>
- <span data-ttu-id="630c9-121">Selecione o status de um modelo em **Ver Relatório de usabilidade de dados de entrada** no painel lateral.</span><span class="sxs-lookup"><span data-stu-id="630c9-121">Select the status of a model select **See Input data usability report** in the side pane.</span></span>
- <span data-ttu-id="630c9-122">Selecione um dos modelos na lista e, em seguida, selecione **Relatório de usabilidade de dados de entrada** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="630c9-122">Selecting one of the models in the list and select **Input data usability report** in the command bar.</span></span>
- <span data-ttu-id="630c9-123">Abra a página de resultados do modelo e selecione **Relatório de usabilidade de dados de entrada** na barra de comando.</span><span class="sxs-lookup"><span data-stu-id="630c9-123">Open the model results page and select **Input data usability report** in the command bar.</span></span>

### <a name="information-in-the-input-data-usability-report"></a><span data-ttu-id="630c9-124">Informações no relatório de usabilidade de dados de entrada</span><span class="sxs-lookup"><span data-stu-id="630c9-124">Information in the input data usability report</span></span>

<span data-ttu-id="630c9-125">As colunas a seguir no relatório contêm informações úteis para aprimorar os dados do modelo.</span><span class="sxs-lookup"><span data-stu-id="630c9-125">The following columns in the report contain helpful information to improve the data for the model.</span></span>

:::image type="content" source="media/input-data-usability-report.png" alt-text="Exemplo de um relatório de usabilidade de dados de entrada mostrando uma tabela com erros, avisos e recomendações.":::

- <span data-ttu-id="630c9-127">Nome: nome descritivo do erro, aviso ou recomendação.</span><span class="sxs-lookup"><span data-stu-id="630c9-127">Name: Descriptive name of the error, warning, or recommendation.</span></span>
- <span data-ttu-id="630c9-128">Etapa: fase de modelagem, treinamento ou pontuação, a que se referem as informações.</span><span class="sxs-lookup"><span data-stu-id="630c9-128">Step: Model phase, train or score, the information refers to.</span></span>
- <span data-ttu-id="630c9-129">Estado: severidade da informação (erro, aviso, recomendação).</span><span class="sxs-lookup"><span data-stu-id="630c9-129">State: Severity of the information (error, warning, recommendation).</span></span>
- <span data-ttu-id="630c9-130">Nome da coluna: coluna em uma entidade que deve ser modificada para melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="630c9-130">Column name: Column in an entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="630c9-131">Nome da entidade: nome da entidade que deve ser modificada para melhorar o desempenho do modelo.</span><span class="sxs-lookup"><span data-stu-id="630c9-131">Entity name: Name of the entity that needs to be modified to improve the model performance.</span></span>
- <span data-ttu-id="630c9-132">Detalhes: detalhes sobre o erro, aviso ou recomendação.</span><span class="sxs-lookup"><span data-stu-id="630c9-132">Details: Details about the error, warning, or recommendation.</span></span>

## <a name="refresh-a-prediction"></a><span data-ttu-id="630c9-133">Atualizar uma previsão</span><span class="sxs-lookup"><span data-stu-id="630c9-133">Refresh a prediction</span></span>

<span data-ttu-id="630c9-134">As previsões serão atualizadas automaticamente no mesmo [cronograma de atualização dos dados](system.md#schedule-tab) conforme definido nas configurações.</span><span class="sxs-lookup"><span data-stu-id="630c9-134">Predictions will automatically refresh on the same [schedule your data refreshes](system.md#schedule-tab) as configured in settings.</span></span> <span data-ttu-id="630c9-135">Você também pode atualizá-las manualmente.</span><span class="sxs-lookup"><span data-stu-id="630c9-135">You can refresh them manually too.</span></span>

1. <span data-ttu-id="630c9-136">Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="630c9-136">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="630c9-137">Selecione os três pontos verticais ao lado da previsão que deseja atualizar.</span><span class="sxs-lookup"><span data-stu-id="630c9-137">Select the vertical ellipses next to the prediction you want to refresh.</span></span>

1. <span data-ttu-id="630c9-138">Selecione **Atualizar**.</span><span class="sxs-lookup"><span data-stu-id="630c9-138">Select **Refresh**.</span></span>

## <a name="delete-a-prediction"></a><span data-ttu-id="630c9-139">Excluir uma previsão</span><span class="sxs-lookup"><span data-stu-id="630c9-139">Delete a prediction</span></span>

<span data-ttu-id="630c9-140">A exclusão de uma previsão também remove sua entidade de saída.</span><span class="sxs-lookup"><span data-stu-id="630c9-140">Deleting a prediction also removes its output entity.</span></span>

1. <span data-ttu-id="630c9-141">Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.</span><span class="sxs-lookup"><span data-stu-id="630c9-141">Go to **Intelligence** > **Predictions** and select the **My predictions** tab.</span></span>

1. <span data-ttu-id="630c9-142">Selecione os três pontos verticais ao lado da previsão que deseja excluir.</span><span class="sxs-lookup"><span data-stu-id="630c9-142">Select the vertical ellipses next to the prediction you want to delete.</span></span>

1. <span data-ttu-id="630c9-143">Selecione **Excluir**.</span><span class="sxs-lookup"><span data-stu-id="630c9-143">Select **Delete**.</span></span>
