---
title: Enriquecimento com o enriquecimento de terceiros da HERE Technologies
description: Informações gerais sobre o enriquecimento de terceiros da HERE Technologies.
ms.date: 10/27/2020
ms.reviewer: jodahl
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 7082fcfec099c3c9436b233c193be23625f6691a
ms.sourcegitcommit: a9b2cf598f256d07a48bba8617347ee90024a1dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4668664"
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

1. Selecione **Adicionar dados** e escolha se deseja mapear os campos para o endereço principal e/ou secundário. Você pode especificar um mapeamento de campo para ambos os endereços (por exemplo, um endereço residencial e um comercial) e enriquecer os perfis para ambos os endereços separadamente. Selecione **Avançar**.

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
