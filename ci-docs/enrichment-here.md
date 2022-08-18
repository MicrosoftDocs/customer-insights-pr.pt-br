---
title: Enriquecer perfis de clientes com a HERE Technologies (versão preliminar)
description: Informações gerais sobre o enriquecimento de terceiros da HERE Technologies.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 86a070342193dd7afda38823d90f4bd28c8b862e
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237844"
---
# <a name="enrich-customer-profiles-with-here-technologies-preview"></a>Enriquecer perfis de clientes com a HERE Technologies (versão preliminar)

A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização. Os serviços de enriquecimento de dados da HERE Technologies melhoram a precisão das informações de localização sobre seus clientes. Ela fornece normalização de endereço, extração de latitude e longitude e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

- Você tem uma assinatura ativa da HERE Technologies. Para obter uma assinatura, [inscreva-se aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [entre em contato com a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente. [Saiba mais sobre o enriquecimento de localização da HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Uma [conexão](connections.md) da HERE é [configurada](#configure-the-connection-for-here-technologies) por um administrador.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar a conexão para a HERE Technologies

Você deve ser [administrador](permissions.md#admin) no Customer Insights e ter uma chave de API ativa da HERE Technologies.

1. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da HERE technologies.

1. Insira um nome para a conexão e uma chave de API válida da HERE Technologies.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Salvar**.

   :::image type="content" source="media/enrichment-HERE-connection.png" alt-text="Página de configuração de conexão da HERE Technologies.":::

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** em **Localização** do bloco da HERE Technologies.

   :::image type="content" source="media/HERE-tile.png" alt-text="Bloco da HERE Technologies.":::

1. Revise a visão geral e selecione **Avançar**.

1. Selecionar a conexão. Contate um administrador se nenhuma conexão estiver disponível.

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer com dados da HERE Technologies. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

1. Defina que tipo de campos de seus perfis unificados usar para correspondência: o endereço principal e/ou secundário. Você pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis para ambos os endereços separadamente. Por exemplo, para um endereço residencial e um endereço comercial. Selecione **Avançar**

1. Mapeie os campos para os dados da HERE Technologies. Os campos **Rua 1** e **CEP** são obrigatórios para o endereço principal e/ou secundário selecionado. Para maior precisão de correspondência, adicione mais campos.

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o enriquecimento e o **Nome da entidade de saída**.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Executar** para iniciar o processo de enriquecimento ou feche para voltar para a página **Enriquecimentos**.

## <a name="view-enrichment-results"></a>Exibir resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes enriquecidos por campo** apresenta um detalhamento da cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
