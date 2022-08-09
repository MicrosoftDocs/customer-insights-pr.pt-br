---
title: Conector do Power BI (versão prévia)
description: Saiba como usar o conector do Dynamics 365 Customer Insights no Power BI.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: stefanie-msft
ms.author: sthe
manager: shellyha
ms.openlocfilehash: 656a695b8b3f1ec2b5fbaad69feba7f1f0b73dee
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196656"
---
# <a name="power-bi-connector-preview"></a>Conector do Power BI (versão prévia)

Crie visualizações para seus dados com o Microsoft Power BI Desktop. Gere insights adicionais e crie relatórios com seus dados de cliente unificados.

## <a name="prerequisites"></a>Pré-requisitos

- Perfis unificados de cliente.
- A versão mais recente do [Microsoft Power BI Desktop](https://powerbi.microsoft.com/desktop/) está instalado no seu computador. [Saiba mais sobre o Power BI Desktop](/power-bi/desktop-what-is-desktop).

## <a name="configure-the-connector-for-power-bi"></a>Configure o conector do Power BI

1. No Power BI Desktop, selecione **Arquivo** > **Obter Dados**.

1. Selecione **Ver mais** e procure **Dynamics 365 Customer Insights**

1. Selecione **Conectar**.

1. **Entre** com a mesma conta organizacional usada no Customer Insights e selecione **Conectar**.
   > [!NOTE]
   > A conta indicada nesta etapa é usada para buscar dados do Customer Insights e não precisa ser a mesma usada para se conectar ao Power BI. Para redefinir a conta que é usada para a busca de dados, abra o Power BI e vá para **Arquivo** > **Opções** > **Configurações** > **Configurações da fonte de dados**. Na lista de fontes de dados, selecione **Fazer logon no Dynamics 365 Customer Insights** e, em seguida, selecione **Limpar permissões**.  

1. Na caixa de diálogo **Navegador**, visualize a lista de todos os ambientes aos quais você tem acesso. Expanda um ambiente e abra qualquer uma das pastas (entidades, medidas, segmentos, enriquecimentos). Por exemplo, abra a pasta **Entidades** para ver todas as entidades que você pode importar.

   :::image type="content" source="media/power-bi-navigator.png" alt-text="Navegador de Conector do Power BI.":::

1. Marque as caixas de seleção ao lado das entidades para incluir e **Carregar**. É possível selecionar várias entidades de vários ambientes.

   Uma caixa de diálogo de carregamento é exibida enquanto as entidades são carregadas. Depois que todas as entidades selecionadas forem carregadas, use os recursos do Power BI para visualizar os dados.

## <a name="large-data-sets"></a>Grandes conjuntos de dados

O conector Customer Insights para Power BI foi criado para funcionar com conjuntos de dados que contêm até 1 milhão de perfis de clientes. A importação de conjuntos de dados maiores pode funcionar, mas é demorada e pode atingir o tempo limite devido a limitações do Power BI. Para obter mais informações, consulte [Power BI: recomendações para grandes conjuntos de dados](/power-bi/admin/service-premium-what-is#large-datasets).

### <a name="work-with-a-subset-of-data"></a>Trabalhe com um subconjunto de dados

Considere trabalhar com um subconjunto de seus dados. Por exemplo, crie [segmentos](segments.md) em vez de exportar todos os registros de cliente para o Power BI.

## <a name="troubleshooting"></a>Solução de Problemas

### <a name="customer-insights-environment-doesnt-show-in-power-bi"></a>O ambiente do Customer Insights não é exibido no Power BI

Ambientes com mais de um [relacionamento](relationships.md) definido entre duas entidades idênticas no Customer Insights não estarão disponíveis no conector do Power BI.

Identifique e remova os relacionamentos duplicados.

1. Vá para **Dados** > **Relacionamentos** no ambiente ausente no Power BI.
1. Identifique os relacionamentos duplicados:
   - Verifique se há mais de um relacionamento definido entre as duas entidades iguais.
   - Verifique se há um relacionamento criado entre duas entidades que estão incluídas no processo de unificação. Existe um relacionamento implícito definido entre todas as entidades incluídas no processo de unificação.
1. Remova todos os relacionamentos duplicados identificados.

Após a remoção dos relacionamentos duplicados, tente configurar o conector do Power BI novamente.

### <a name="errors-on-date-fields-when-loading-entities-in-power-bi-desktop"></a>Erros nos campos de data ao carregar entidades no Power BI Desktop

Ao carregar entidades que contêm campos com um formato de data como MM/DD/AAAA, você poderá encontrar erros devido a formatos de localidade incompatíveis. Essa incompatibilidade ocorre quando o arquivo do Power BI Desktop está definido para outra localidade diferente de inglês (Estados Unidos), porque os campos de data no Customer Insights são salvos no formato dos EUA.

O arquivo do Power BI Desktop tem uma única configuração de local, que é aplicada durante a recuperação de dados. Para corrigir os erros de data, [defina a localidade do arquivo .BPI](/power-bi/fundamentals/supported-languages-countries-regions#choose-the-language-or-locale-of-power-bi-desktop) como Inglês (Estados Unidos).

[!INCLUDE [footer-include](includes/footer-banner.md)]
