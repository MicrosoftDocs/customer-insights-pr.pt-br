---
title: Exportar segmentos para o LiveRamp (versão preliminar)
description: Saiba como configurar a conexão e a exportação para o LiveRamp.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 3e30a16dcb276fa6c951ad0b42ed0a4792f87ce3
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9050749"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segmentos para o LiveRamp&reg; (versão preliminar)

Ative seus dados no LiveRamp para se conectar a mais de 500 plataformas em ecossistemas digitais, sociais e de TV. Trabalhe com seus dados no LiveRamp para segmentar, suprimir e personalizar campanhas publicitárias.

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

- Você precisa de uma assinatura do LiveRamp para usar esse conector.
- Para obter uma assinatura, [entre em contato com a LiveRamp](https://liveramp.com/contact/) diretamente. [Saiba mais sobre o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="set-up-connection-to-liveramp"></a>Configurar conexão com o LiveRamp

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **LiveRamp** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça um **Nome do usuário** e uma **Senha** para sua conta do LiveRamp Secure FTP (SFTP).
Essas credenciais podem ser diferentes das credenciais do LiveRamp Onboarding.

1. Selecione **Verificar** para testar a conexão com o LiveRamp.

1. Após a verificação bem-sucedida, forneça seu consentimento para **Privacidade e conformidade de dados** marcando a caixa de seleção **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do LiveRamp. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. No campo **Escolha seu identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar ao LiveRamp para resolução de identidade.
   > [!div class="mx-imgBorder"]
   > ![Conector LiveRamp com mapeamento de atributos.](media/export-liveramp-segments.png "Conector LiveRamp com mapeamento de atributos")

1. Mapeie os atributos correspondentes da sua entidade *Cliente* para o identificador de chave selecionado.

1. Selecione **Adicionar atributo** para mapear mais atributos para enviar para o LiveRamp.

   > [!TIP]
   > Enviar mais atributos de identificador de chave para o LiveRamp provavelmente resultará em uma taxa de correspondência mais alta.

1. Selecione os segmentos que você deseja exportar para o LiveRamp.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Liveramp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Liveramp cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.

[!INCLUDE [footer-include](includes/footer-banner.md)]
