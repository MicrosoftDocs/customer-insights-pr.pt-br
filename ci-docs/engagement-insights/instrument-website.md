---
title: Adicionar código ao seu site
description: Como adicionar um trecho de código para capturar eventos no seu site.
author: britl
ms.reviewer: mhart
ms.author: britl
ms.date: 04/30/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: b5467da775a621c436bd9ddedb272506acc1e2b31dcf7c87feb5dd11e2daae2b
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7035080"
---
# <a name="install-the-code-snippet-on-a-website"></a>Instalar o trecho de código em um site

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Este artigo descreve como um administrador instala o trecho de código em um site. Você começará a ver eventos no espaço de trabalho pouco depois de adicionar o script ao seu site. Para obter mais informações, consulte [Gerenciar espaços de trabalho e ambientes](manage-environments-workspaces.md). Para capturar eventos em aplicativos móveis, consulte [Visão geral dos recursos de desenvolvedor](developer-resources.md).


### <a name="prerequisites"></a>Pré-requisitos

* Você deve ter permissões de administrador para o espaço de trabalho a fim de armazenar os dados.
* Seu site ou projeto deve ser hospedado online para enviar dados de atividades. Os dados enviados de um arquivo local não serão aceitos pelo servidor.


## <a name="add-code-to-your-website"></a>Adicionar código ao seu site
1.  Vá para **Administração** > **Espaço de trabalho**  e, em seguida, selecione **Guia de instalação**.
1. Selecione **Copiar código** para copiar o trecho de código. Por padrão, a chave de ingestão do seu espaço de trabalho está incorporada no trecho de código.
:::image type="content" source="media/copy-code.png" alt-text="Captura de tela da página do trecho de código.":::
3. Adicione o trecho de código copiado ao seu site, próximo à <head> marca e antes de qualquer outro script ou marcas CSS.
4.  Publique seu site atualizado e aguarde alguns minutos para capturar o tráfego da Web de entrada.
5.  Para ver os dados, selecione seu espaço de trabalho no alternador de espaço de trabalho no painel de navegação. Em seguida, selecione um dos relatórios na seção **Descobrir**.

## <a name="configuration-options"></a>Opções de configuração

Você pode alterar as seguintes opções de configuração no trecho de código:

- **ingestionKey**: a chave de ingestão usada para enviar eventos ao seu espaço de trabalho. Você pode alterar a chave de ingestão para enviar eventos para um espaço de trabalho diferente. Uma chave de ingestão é exclusiva para cada espaço de trabalho. 
- **autoCapture**: especifica se exibições de página e interações com o site são capturadas. Há duas opções:
    - **exibir**: defina como *verdadeiro* para capturar exibições de página. As exibições de página são capturadas como [eventos](glossary.md#event) de *Exibição*, um tipo de [evento base](glossary.md#base-event).
    - **clicar**: defina como *verdadeiro* para capturar interações com visitantes no site. As interações são capturadas como [eventos](glossary.md#event) de *Ação*, um tipo de [evento base](glossary.md#base-event).

[!INCLUDE[footer-include](../includes/footer-banner.md)]
