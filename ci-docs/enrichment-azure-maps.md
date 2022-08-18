---
title: Enriquecer perfis dos clientes com dados de localização do Azure Mapas (versão preliminar)
description: Informações gerais sobre o enriquecimento próprio do Azure Mapas.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: f14b4fc20a9a1d8842f42f9e0e656b3d8dcddcf4
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9238028"
---
# <a name="enrich-customer-profiles-with-location-data-from-azure-maps-preview"></a>Enriquecer perfis dos clientes com dados de localização do Azure Mapas (versão preliminar)

O Azure Mapas fornece dados e serviços centrados no local para oferecer experiências com base em dados geoespaciais com inteligência de local interna. Os serviços de enriquecimento de dados do Azure Mapas melhoram a precisão de informações de localização sobre os clientes. Ele traz recursos como normalização de endereço e extração de latitude e longitude para o Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura ativa do Azure Mapas. Para obter uma assinatura, [inscreva-se ou obtenha uma avaliação gratuita](https://azure.microsoft.com/services/azure-maps/).

- Uma [conexão](connections.md) do Azure Mapas é [configurada](#configure-the-connection-for-azure-maps) por um administrador.

## <a name="configure-the-connection-for-azure-maps"></a>Configure a conexão para o Azure Mapas

Você deve ser [administrador](permissions.md#admin) no Customer Insights e ter uma chave de API ativa do Azure Mapas.

1. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administração** > **Conexões** e selecione **Configurar** no bloco do Azure Mapas.

   :::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Página de configuração de conexão do Azure Mapas.":::

1. Insira um nome para a conexão e uma chave de API válida do Azure Mapas.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Salvar**.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** em **Localização** do bloco do Microsoft Azure Mapas.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Bloco do Azure Mapas.":::

1. Revise a visão geral e selecione **Avançar**.

1. Selecionar a conexão. Contate um administrador se nenhuma conexão estiver disponível.

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer com dados da Microsoft. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

1. Defina que tipo de campos de seus perfis unificados usar para correspondência: o endereço principal e/ou secundário. Você pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis para ambos os endereços separadamente. Por exemplo, para um endereço residencial e um endereço comercial. Selecione **Avançar**

1. Mapeie os campos para os dados de localização do Azure Mapas. Os campos **Rua 1** e **CEP** são obrigatórios para o endereço principal e/ou secundário selecionado. Para maior precisão de correspondência, adicione mais campos.

   :::image type="content" source="media/enrichment-azure-maps-attributes.png" alt-text="Mapeamento de atributos do Azure Mapas.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Revise as **Configurações Avançadas**, que oferecem flexibilidade máxima para lidar com casos de uso avançados. No entanto, os seguintes valores padrão normalmente não precisam ser alterados.

   - **Tipo de endereços**: a melhor correspondência de endereço será retornada, mesmo se estiver incompleta. Para obter apenas endereços completos (por exemplo, endereços que incluem o número da casa), desmarque todas as caixas de seleção, exceto **Endereços de Ponto**.
   - **Idioma**: os endereços retornam no idioma baseado na região do endereço. Para aplicar um idioma de endereço padronizado, selecione o idioma no menu suspenso. Por exemplo, a seleção de **Inglês** retorna **Copenhagen, Denmark** em vez de **København, Danmark**.
   - **Número máximo de resultados**: número de resultados por endereço.

1. Selecione **Avançar**

1. Forneça um **Nome** para o enriquecimento e o **Nome da entidade de saída**.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Executar** para iniciar o processo de enriquecimento ou feche para voltar para a página **Enriquecimentos**.

## <a name="view-enrichment-results"></a>Exibir resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes enriquecidos por campo** apresenta um detalhamento da cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
