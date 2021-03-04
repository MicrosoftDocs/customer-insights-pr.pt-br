---
title: Conector LiveRamp
description: Saiba como exportar dados para o LiveRamp.
ms.date: 12/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 64d781f52e8124fc3e83a7b84f468830c5249cfd
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270144"
---
# <a name="liverampreg-connector-preview"></a>Conector do LiveRamp&reg; (versão preliminar)

Ative seus dados no LiveRamp para conectar-se a mais de 500 plataformas nos ecossistemas digital, social e de TV. Trabalhe com seus dados no LiveRamp para segmentar, suprimir e personalizar campanhas publicitárias.

## <a name="prerequisites"></a>Pré-requisitos

- Você precisa de uma assinatura do LiveRamp para usar esse conector.
- Para obter uma assinatura, [entre em contato com a LiveRamp](https://liveramp.com/contact/) diretamente. [Saiba mais sobre o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="connect-to-liveramp"></a>Conectar-se ao LiveRamp

1. Nos insights de público-alvo, vá para **Administrador** > **Destinos de exportação**.

1. No bloco **LiveRamp**, selecione **Configurar**.

1. Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.

1. Forneça um **Nome do usuário** e uma **Senha** para sua conta do LiveRamp Secure FTP (SFTP).
Essas credenciais podem ser diferentes das credenciais do LiveRamp Onboarding.

1. Selecione **Verificar** para testar a conexão com o LiveRamp.

1. Após a verificação bem-sucedida, forneça seu consentimento para **Privacidade e conformidade de dados** marcando a caixa de seleção **Concordo**.

1. Selecione **Avançar** para configurar o conector LiveRamp.

## <a name="configure-the-connector"></a>Configurar o conector

1. No campo **Escolha seu identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar ao LiveRamp para resolução de identidade.

1. Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.

1. Selecione **Adicionar atributo** para mapear atributos adicionais para enviar ao LiveRamp.

   > [!TIP]
   > Enviar mais atributos de identificador de chave para o LiveRamp provavelmente resultará em uma taxa de correspondência mais alta.

1. Selecione os segmentos que você deseja exportar para o LiveRamp.

1. Selecione **Salvar**.

> [!div class="mx-imgBorder"]
> ![Conector LiveRamp com mapeamento de atributos](media/export-liveramp-segments.png "Conector LiveRamp com mapeamento de atributos")

## <a name="export-the-data"></a>Exportar os dados

A exportação começará em breve se todos os pré-requisitos para exportação tiverem sido concluídos. A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).
Depois que a exportação for concluída com êxito, você poderá entrar no LiveRamp Onboarding para ativar e distribuir seus dados.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Liveramp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Liveramp cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]