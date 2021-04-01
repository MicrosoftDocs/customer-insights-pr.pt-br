---
title: Exportar dados do Customer Insights para o AdRoll
description: Saiba como configurar a conexão com o AdRoll.
ms.date: 02/15/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 6fedd549c2e7de362f36e3fb23d363200bb92a04
ms.sourcegitcommit: d24e52150fe5a4fab45128e12d6a03637771d9b9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2021
ms.locfileid: "5697060"
---
# <a name="connector-for-adroll-preview"></a>Conector para AdRoll (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o AdRoll e use-os para publicidade. 

## <a name="prerequisites"></a>Pré-requisitos

-   Você deve ter uma [conta do AdRoll](https://www.adroll.com/) e as credenciais de administrador correspondentes.
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="connect-to-adroll"></a>Conectar-se ao AdRoll

1. Vá para **Administrador** > **Exportar destinos**.

1. Em **AdRoll**, selecione **Configurar**.

1. Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.

   :::image type="content" source="media/AdRoll_config.PNG" alt-text="Painel de configuração para conexão do AdRoll.":::

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o AdRoll.

1. Selecione **Autenticar com o AdRoll** e forneça suas credenciais de administrador do AdRoll. 

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Insira sua **ID de Anunciante do AdRoll** [Anunciável no AdRoll](https://help.adroll.com/hc/en-us/articles/212011838-Advertiser-Profiles).

1. Selecione **Próximo** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. É necessário exportar os segmentos para o AdRoll.

1. Selecione os segmentos que você deseja exportar. Selecione um segmento com pelo menos 100 membros. Você não poderá exportar segmentos menores. Além disso, o tamanho máximo de um segmento para exportação é de 250.000 membros por exportação. 

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitações conhecidas

- É possível exportar até 250.000 perfis por vez para o AdRoll.
- Não é possível exportar segmentos com menos de 100 perfis para o AdRoll. 
- A exportação para o AdRoll é limitada a segmentos.
- Exportar até 250.000 perfis para AdRoll pode levar até 10 minutos para a conclusão. 
- O número de perfis que você pode exportar para o AdRoll depende e está limitado ao seu contrato com o AdRoll.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao AdRoll, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o AdRoll cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
