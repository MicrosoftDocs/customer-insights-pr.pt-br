---
title: Enriquecimento com o enriquecimento de terceiros da HERE Technologies
description: Informações gerais sobre o enriquecimento de terceiros da HERE Technologies.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 8e8d6bfea4e0df54682501f60759c24c893444af
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597727"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquecimento de perfis de clientes com a HERE Technologies (versão preliminar)

A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização. Com os serviços de enriquecimento de dados da HERE Technologies, você pode criar uma compreensão mais precisa da localização de seus clientes com normalização de endereço, extração de latitude e longitude e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar os enriquecimentos da HERE Technologies, os seguintes pré-requisitos devem ser atendidos:

- Você tem uma assinatura ativa da HERE Technologies. Para obter uma assinatura, você pode [se inscrever aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [entre contato com a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente. [Saiba mais sobre o enriquecimento de localização da HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Você tem a chave de API da HERE Technologies.

- Você tem as permissões de [Administrador](permissions.md#administrator).

## <a name="configuration"></a>Configuração

1. Vá para **Dados** > **Enriquecimento**.

1. Selecione **Enriquecer meus dados** no bloco da HERE Technologies.

   > [!div class="mx-imgBorder"]
   > ![Bloco da HERE Technologies](media/HERE-tile.png "Bloco da HERE Technologies")

1. Insira uma **chave de API da HERE Technologies** ativa. Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**. 

1. Confirme as duas entradas selecionando **Conectar-se à HERE**.

1.  Selecione **Adicionar dados** e escolha o **Conjunto de dados do cliente** que deseja enriquecer com dados de localização de Tecnologias HERE. Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. Escolha se deseja mapear os campos para o endereço principal e/ou secundário. Você pode especificar um mapeamento de campo para ambos os endereços (por exemplo, um endereço residencial e um comercial) e enriquecer os perfis para ambos os endereços separadamente. Selecione **Avançar**.

1. Defina quais campos de seus perfis unificados devem ser usados para procurar dados de localização correspondentes da HERE Technologies. Os campos **Rua 1** e **CEP** são obrigatórios para o endereço principal e/ou secundário selecionado. Para uma maior precisão de correspondência, mais campos podem ser adicionados.

   > [!div class="mx-imgBorder"]
   > ![Página de configuração de enriquecimento da HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuração de enriquecimento da HERE Technologies")

1. Selecione **Aplicar** para completar o mapeamento de campo.

## <a name="enrichment-results"></a>Resultados de enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados do cliente e dos tempos de resposta da API da HERE Technologies.

Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a HERE Technologies cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]