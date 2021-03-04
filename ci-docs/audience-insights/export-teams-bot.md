---
title: Bot para Microsoft Teams
description: Procure perfis de clientes unificados no Microsoft Teams com a ajuda de um bot.
ms.date: 04/21/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 03299610fd41a7e142e3c9723fad56ce7f90e083
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267938"
---
# <a name="teams-bot-for-dynamics-365-customer-insights-preview"></a><span data-ttu-id="f7773-103">Bot do Teams para Dynamics 365 Customer Insights (versão preliminar)</span><span class="sxs-lookup"><span data-stu-id="f7773-103">Teams bot for Dynamics 365 Customer Insights (preview)</span></span>

<span data-ttu-id="f7773-104">Conecte-se com o Microsoft Teams para permitir que um bot procure perfis de clientes unificados nos canais do Teams.</span><span class="sxs-lookup"><span data-stu-id="f7773-104">Connect with Microsoft Teams to let a bot look up unified customer profiles in Teams channels.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f7773-105">![Bot do Teams mostrando um registro de cliente](media/teams-bot.png "Bot do Teams mostrando um registro de cliente")</span><span class="sxs-lookup"><span data-stu-id="f7773-105">![Teams bot showing a customer record](media/teams-bot.png "Teams bot showing a customer record")</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f7773-106">Pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="f7773-106">Prerequisites</span></span>

<span data-ttu-id="f7773-107">Para instalar e configurar o bot, os seguintes pré-requisitos devem ser atendidos:</span><span class="sxs-lookup"><span data-stu-id="f7773-107">To set up and configure the bot, the following prerequisites must be met:</span></span>

- <span data-ttu-id="f7773-108">Há pelo menos uma [fonte de dados adicionada](data-sources.md).</span><span class="sxs-lookup"><span data-stu-id="f7773-108">There's at least one [data source added](data-sources.md).</span></span>
- <span data-ttu-id="f7773-109">O [processo de unificação](data-unification.md) foi concluído.</span><span class="sxs-lookup"><span data-stu-id="f7773-109">The [unification process](data-unification.md) is complete.</span></span>
- <span data-ttu-id="f7773-110">Os campos são adicionados ao [índice de pesquisa e filtro](search-filter-index.md).</span><span class="sxs-lookup"><span data-stu-id="f7773-110">Fields are added to the [search and filter index](search-filter-index.md).</span></span>
- <span data-ttu-id="f7773-111">O Customer Insights e o Teams estão na mesma organização.</span><span class="sxs-lookup"><span data-stu-id="f7773-111">Customer Insights and Teams are in the same organization.</span></span>

## <a name="configure-the-bot"></a><span data-ttu-id="f7773-112">Configurar o bot</span><span class="sxs-lookup"><span data-stu-id="f7773-112">Configure the bot</span></span>

1. <span data-ttu-id="f7773-113">Nos insights de público-alvo, vá para **Administrador** > **Destinos de Exportação**.</span><span class="sxs-lookup"><span data-stu-id="f7773-113">In audience insights, go to **Admin** > **Export Destinations**.</span></span>
1. <span data-ttu-id="f7773-114">No bloco do Microsoft Teams, selecione **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="f7773-114">On the Microsoft Teams tile, select **Set up**.</span></span>
1. <span data-ttu-id="f7773-115">Você é redirecionado para a área **Aplicativos** no Teams.</span><span class="sxs-lookup"><span data-stu-id="f7773-115">You're redirected to the **Apps** area in Teams.</span></span> <span data-ttu-id="f7773-116">Você também pode abrir o Teams e selecionar **Aplicativos** no canto inferior esquerdo ou [obtê-lo do AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) diretamente.</span><span class="sxs-lookup"><span data-stu-id="f7773-116">You can also open Teams and select **Apps** in the bottom-left corner or [get it from AppSource](https://go.microsoft.com/fwlink/?linkid=2124104) directly.</span></span>
1. <span data-ttu-id="f7773-117">Procure **Customer Insights** e selecione o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="f7773-117">Search for **Customer Insights** and select the app.</span></span>
1. <span data-ttu-id="f7773-118">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="f7773-118">Select **Add**.</span></span>
1. <span data-ttu-id="f7773-119">Depois de entrar no Customer Insights no Teams, você verá uma mensagem de boas-vindas e poderá começar.</span><span class="sxs-lookup"><span data-stu-id="f7773-119">After signing in to Customer Insights in Teams, you'll see a welcome message and can get started.</span></span>

## <a name="things-you-can-do-with-the-bot"></a><span data-ttu-id="f7773-120">O que você pode fazer com o bot</span><span class="sxs-lookup"><span data-stu-id="f7773-120">Things you can do with the bot</span></span>

<span data-ttu-id="f7773-121">O bot fornece recursos de pesquisa para perfis unificados de clientes.</span><span class="sxs-lookup"><span data-stu-id="f7773-121">The bot provides lookup capabilities for unified customer profiles.</span></span>

- <span data-ttu-id="f7773-122">Insira **pesquisar** seguido por um nome, endereço de email ou qualquer outro campo no perfil unificado do cliente que seja adicionado ao índice de pesquisa e filtro.</span><span class="sxs-lookup"><span data-stu-id="f7773-122">Enter **search** followed by a name, email address, or any other field on the unified customer profile that is added to the search and filter index.</span></span>

  <span data-ttu-id="f7773-123">Você receberá um cartão com até 15 campos do perfil do cliente resultante.</span><span class="sxs-lookup"><span data-stu-id="f7773-123">You'll get a card with up to 15 fields from the resulting customer profile.</span></span> <span data-ttu-id="f7773-124">Várias correspondências retornam uma lista de resultados onde você pode selecionar um perfil.</span><span class="sxs-lookup"><span data-stu-id="f7773-124">Multiple matches return a list of results where you can select a profile.</span></span> <span data-ttu-id="f7773-125">Você pode adicionar o termo de pesquisa entre aspas duplas para procurar uma correspondência exata.</span><span class="sxs-lookup"><span data-stu-id="f7773-125">You can add the search term in double quotes to look up an exact match.</span></span>

- <span data-ttu-id="f7773-126">Se a sua organização mantiver vários ambientes do Customer Insights na mesma organização, você poderá inserir **switchinstance** para escolher a qual ambiente deseja conectar o bot.</span><span class="sxs-lookup"><span data-stu-id="f7773-126">If your organization maintains multiple Customer Insights environments in the same organization, you can enter **switchinstance** to choose which environment you want to connect the bot to.</span></span>

- <span data-ttu-id="f7773-127">Insira **ajuda** para ver uma lista dos comandos disponíveis para o bot.</span><span class="sxs-lookup"><span data-stu-id="f7773-127">Enter **help** to see a list of available commands for the bot.</span></span>  


[!INCLUDE[footer-include](../includes/footer-banner.md)]