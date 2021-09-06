---
title: Exportar dados do Customer Insights para o Microsoft Advertising
description: Saiba como configurar a conexão e exportar para o Microsoft Advertising.
ms.date: 05/12/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8f8a4cbb9590f9c5311789154319283530e0a10343cccbe9c7aec99765b4fbf2
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7031440"
---
# <a name="export-segments-to-microsoft-advertising-preview"></a>Exportar segmentos para o Microsoft Advertising (versão preliminar)

Exporte segmentos do Customer Insights para o Microsoft Advertising para criar públicos-alvo de Correspondência de Clientes. Use esses públicos-alvo para suas campanhas publicitárias.

## <a name="prerequisites"></a>Pré-requisitos

-   Uma [conta do Microsoft Advertising](https://ads.microsoft.com/) e as credenciais de administrador correspondentes.
-   Você aceitou os termos de uso da Correspondência de Clientes. 
-   [Segmentos configurados](segments.md) nos insights de público-alvo.
-   Os perfis de cliente unificados nos segmentos exportados contêm um campo com um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Você pode exportar até 500.000 perfis por vez para o Microsoft Advertising.
- A exportação para o Microsoft Advertising está limitada a segmentos.
- Exportar até 500.000 perfis para o Microsoft Advertising pode levar até 10 minutos para a conclusão. 


## <a name="set-up-the-connection-to-microsoft-advertising"></a>Configurar a conexão com o Microsoft Advertising

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Microsoft Advertising** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. O padrão é administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão ao Microsoft Advertising.

1. Selecione **Autenticar com Microsoft Advertising** e forneça suas credenciais de administrador do Microsoft Advertising.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Microsoft Advertising. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Selecione os segmentos a serem exportados. Os públicos-alvo da Correspondência de Clientes no Microsoft Advertising são criados automaticamente com o nome dos segmentos selecionados para exportação. Cada segmento resultará em um público-alvo separado da Correspondência de Clientes. 

1. Insira sua **ID do cliente e ID da conta do Microsoft Advertising**. Você pode encontrar a ID do cliente (`cid`) e a ID da conta (`aid`) nos parâmetros da URL quando você estiver conectado ao Microsoft Advertising.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo em seu perfil de cliente unificado com o endereço de email de um cliente. A exportação de segmentos para o Microsoft Advertising é necessária.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Microsoft Advertising, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados que podem ser confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Microsoft Advertising atenda a todas as obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
