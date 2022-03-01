---
title: Conector do Power BI
description: Saiba como usar o conector do Dynamics 365 Customer Insights no Power BI.
ms.date: 09/21/2020
ms.reviewer: sthe
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: d497ca779a337c512a7254524f597cff226bcb45
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405014"
---
# <a name="connector-for-power-bi-preview"></a>Conector do Power BI (versão prévia)

Crie visualizações para seus dados com o Power BI Desktop. Gere insights adicionais e crie relatórios com seus dados de cliente unificados.

## <a name="prerequisites"></a>Pré-requisitos

- Você deve ter perfis de clientes unificados.
- A versão mais recente do [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) foi instalada no seu computador. [Saiba mais sobre o Power BI Desktop](https://docs.microsoft.com/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configure o conector do Power BI

1. No Power BI Desktop, selecione **Arquivo** > **Obter Dados**.

1. Selecione **Ver mais** e procure **Dynamics 365 Customer Insights**

1. Selecione o resultado e selecione **Conectar**.

1. **Entre** com a mesma conta organizacional usada no Customer Insights e selecione **Conectar**.
   > [!NOTE]
   > A conta indicada nesta etapa é usada para buscar dados do Customer Insights e não precisa ser a mesma usada para se conectar ao Power BI. Para redefinir a conta que é usada para a busca de dados, abra o Power BI e vá para **Arquivo** > **Opções** > **Configurações** > **Configurações da fonte de dados**. Na lista de fontes de dados, selecione **Fazer logon no Dynamics 365 Customer Insights** e, em seguida, selecione **Limpar permissões**.  

1. Na caixa de diálogo **Navegador**. você vê a lista de todos os ambientes aos quais tem acesso. Expanda um ambiente e abra qualquer uma das pastas (entidades, medidas, segmentos, enriquecimentos). Por exemplo, abra a pasta **Entidades** para ver todas as entidades que você pode importar.

   ![Navegador de Conector do Power BI](media/power-bi-navigator.png "Navegador de Conector do Power BI")

1. Marque as caixas de seleção ao lado das entidades para incluir e **Carregar**. É possível selecionar várias entidades de vários ambientes.

1. Você verá uma caixa de diálogo de carregamento enquanto suas entidades são carregadas. Depois que todas as entidades selecionadas forem carregadas, você poderá usar os recursos do Power BI para visualizar os dados.

## <a name="large-data-sets"></a>Grandes conjuntos de dados

O conector Customer Insights para Power BI foi criado para funcionar com conjuntos de dados que contêm até 1 milhão de perfis de clientes. Importar conjuntos de dados maiores pode funcionar, mas é demorado. Além disso, o processo pode atingir um tempo limite devido a limitações do Power BI. Para obter mais informações, consulte [Power BI: recomendações para grandes conjuntos de dados](https://docs.microsoft.com/power-bi/admin/service-premium-what-is#large-datasets). 

### <a name="work-with-a-subset-of-data"></a>Trabalhe com um subconjunto de dados

Considere trabalhar com um subconjunto de seus dados. Por exemplo, você pode criar [segmentos](segments.md) em vez de exportar todos os registros de clientes para o Power BI.
