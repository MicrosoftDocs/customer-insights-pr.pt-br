---
title: Adicionar código ao seu site
description: Como adicionar um trecho de código para capturar eventos do Dynamics 365 Customer Insights em seu site.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 09/27/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: ad835f762226d62fdb0f544627f2a76ff09a1ffd
ms.sourcegitcommit: f1e3cc51ea4cf68210eaf0210ad6e14b15ac4fe8
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/27/2021
ms.locfileid: "7558779"
---
# <a name="install-the-web-sdk-on-a-website"></a>Instalar o SDK da Web em um site

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo descreve como um administrador instala o kit de ferramentas de desenvolvimento de software (SDK) da Web em um site. Você começará a ver eventos em seu espaço de trabalho pouco tempo depois de instrumentar seu site. Para obter mais informações, consulte [Gerenciar espaços de trabalho e ambientes](manage-environments-workspaces.md). Para capturar eventos em aplicativos móveis, consulte [Visão geral dos recursos de desenvolvedor](developer-resources.md).


### <a name="prerequisites"></a>Pré-requisitos

* Você deve ter permissões de administrador para o espaço de trabalho a fim de armazenar os dados.
* Seu site ou projeto deve ser hospedado online para enviar dados de atividades. Os dados enviados de um arquivo local não serão aceitos pelo servidor.


## <a name="add-web-sdk-to-your-website"></a>Adicionar o SDK da Web a seu site

Vá para **Administração** > **Espaço de trabalho**  e, em seguida, selecione **Guia de instalação**. Há duas opções para instalar o SDK da Web. A primeira é usar o link de download e a segunda é instalar um pacote do gerenciador de pacotes do nó (NPM).

### <a name="option-1-using-the-download-link"></a>Opção 1: usando o link de download

1. Selecione **Copiar código** para copiar o trecho de código. Por padrão, a chave de ingestão do seu espaço de trabalho está incorporada no trecho de código.
  :::image type="content" source="media/copy-code.png" alt-text="Captura de tela da página do trecho de código.":::

1. Adicione o código copiado a seu site, próximo à <head> marca e antes de qualquer outro script ou marcas CSS.
1. Publique seu site atualizado e aguarde alguns minutos para capturar o tráfego da Web de entrada.
1. Para ver os dados, selecione seu espaço de trabalho no alternador de espaço de trabalho no painel de navegação. Em seguida, selecione um dos relatórios na seção **Descobrir**.

### <a name="option-2-using-the-npm-package-recommended-for-javascript-based-web-apps"></a>Opção 2: usando o pacote do NPM (recomendado para aplicativos Web baseados em JavaScript)

1. Acesse nossa [página da Web do NPM](https://www.npmjs.com/package/engagementinsights-web) e siga as instruções para instalar e configurar o pacote do NPM do SDK da Web.
1. Publique seu site atualizado e aguarde alguns minutos para capturar o tráfego da Web de entrada.
1. Para ver os dados, selecione seu espaço de trabalho no alternador de espaço de trabalho no painel de navegação. Em seguida, selecione um dos relatórios na seção **Descobrir**.

## <a name="configuration-options"></a>Opções de configuração

Você pode alterar as seguintes opções de configuração no trecho de código:

- **ingestionKey**: a chave de ingestão usada para enviar eventos ao seu espaço de trabalho. Você pode alterar a chave de ingestão para enviar eventos para um espaço de trabalho diferente. Uma chave de ingestão é exclusiva para cada espaço de trabalho.
- **autoCapture**: especifica se exibições de página e interações com o site são capturadas. Há duas opções:
    - **exibir**: defina como *verdadeiro* para capturar exibições de página. As exibições de página são capturadas como [eventos](glossary.md#event) de *Exibição*, um tipo de [evento base](glossary.md#base-event).
    - **clicar**: defina como *verdadeiro* para capturar interações com visitantes no site. As interações são capturadas como [eventos](glossary.md#event) de *Ação*, um tipo de [evento base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
