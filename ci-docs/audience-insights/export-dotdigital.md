---
title: Exportar dados do Customer Insights para o DotDigital
description: Saiba como configurar a conexão com o DotDigital.
ms.date: 11/14/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ed6bd40e8575fc90258f79f60abffe54f136d274
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644434"
---
# <a name="connector-for-dotdigital-preview"></a>Conector para DotDigital (versão preliminar)

Exporte segmentos de perfis de clientes unificados para catálogos de endereços do DotDigital e use-os para campanhas, marketing por email e para criar segmentos de clientes com o DotDigital. 

## <a name="prerequisites"></a>Pré-requisitos

-   Você deve ter uma [conta do DotDigital](https://dotdigital.com/) e as credenciais de administrador correspondentes.
-   Há catálogos de endereços existentes no DotDigital e as IDs correspondentes. A ID pode ser encontrada na URL ao selecionar e abrir um catálogo de endereços. Para obter mais informações, consulte [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="connect-to-dotdigital"></a>Conectar-se ao DotDigital

1. Vá para **Administrador** > **Exportar destinos**.

1. Em **DotDigital**, selecione **Configurar**.

1. Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.

   :::image type="content" source="media/DotDigital_config.PNG" alt-text="Painel de configuração da exportação para o DotDigital.":::

1. Insira seu **nome de usuário e senha do DotDigital**.

1. Insira sua **[ID do catálogo de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o DotDigital.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Próximo** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**, **Nome completo**, **Gênero** e **Código postal**.

1. Selecione os segmentos que você deseja exportar. Você pode exportar até 1 milhão de perfis de clientes no total para o DotDigital.

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab). No DotDigital, agora você pode encontrar seus segmentos nos [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis por exportação para o DotDigital.
- A exportação para o DotDigital é limitada a segmentos.
- A exportação de segmentos com um total de 1 milhão de perfis pode levar até 3 horas devido a limitações do provedor. 
- O número de perfis que você pode exportar para o DotDigital depende e está limitado ao seu contrato com o DotDigital.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao DotDigital, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o DotDigital cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
