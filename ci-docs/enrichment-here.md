---
title: Enriquecimento com o enriquecimento de terceiros da HERE Technologies
description: Informações gerais sobre o enriquecimento de terceiros da HERE Technologies.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 171ead92427924083a13e2a3d52e7a7da417c801
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953659"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquecimento de perfis de clientes com a HERE Technologies (versão preliminar)

A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização. Os serviços de enriquecimento de dados da HERE Technologies melhoram a precisão das informações de localização sobre seus clientes. Ela fornece normalização de endereço, extração de latitude e longitude e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

- Você tem uma assinatura ativa da HERE Technologies. Para obter uma assinatura, [inscreva-se aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [entre em contato com a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente. [Saiba mais sobre o enriquecimento de localização da HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Uma [conexão](connections.md) da HERE é [configurada](#configure-the-connection-for-here-technologies) por um administrador.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar a conexão para a HERE Technologies

Você deve ser [administrador](permissions.md#admin) no Customer Insights e ter uma chave de API ativa da HERE Technologies.

1. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da HERE technologies.

1. Insira um nome para a conexão e uma chave de API válida da HERE Technologies.

1. Revise e forneça seu consentimento para a [Conformidade e privacidade dos dados](#data-privacy-and-compliance) selecionando **Eu concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Salvar**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Página de configuração de conexão da HERE Technologies.":::

### <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a HERE Technologies cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** em **Localização** do bloco da HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Bloco da HERE Technologies.":::

1. Revise a visão geral e selecione **Avançar**.

1. Selecionar a conexão. Entre em contato com um administrador se não houver um disponível.

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer com dados da HERE Technologies. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

1. Defina que tipo de campos de seus perfis unificados usar para correspondência: o endereço principal e/ou secundário. Você pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis para ambos os endereços separadamente. Por exemplo, para um endereço residencial e um endereço comercial. Selecione **Avançar**

1. Mapeie os campos para os dados da HERE Technologies. Os campos **Rua 1** e **CEP** são obrigatórios para o endereço principal e/ou secundário selecionado. Para maior precisão de correspondência, adicione mais campos.

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o enriquecimento e o **Nome da entidade de saída**.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Executar** para iniciar o processo de enriquecimento ou feche para voltar para a página **Enriquecimentos**.

## <a name="enrichment-results"></a>Resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes enriquecidos por campo** apresenta um detalhamento da cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
