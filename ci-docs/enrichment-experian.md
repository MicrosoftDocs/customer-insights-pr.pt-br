---
title: Enriqueça os perfis dos clientes com dados demográficos da Experian (versão preliminar)
description: Informações gerais sobre o enriquecimento de terceiros da Experian.
ms.date: 08/08/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: fccb37cde3f05a70009c18b6c52db01a5ede094d
ms.sourcegitcommit: b1d06fe26934f12f0c5ed13e8ef1d37e52e67cc7
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/08/2022
ms.locfileid: "9237982"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriqueça os perfis dos clientes com dados demográficos da Experian (versão preliminar)

Experian é uma líder global em serviços de marketing e relatórios de crédito para consumidores e empresas. Com os serviços de enriquecimento de dados da Experian, você pode obter uma compreensão mais profunda de seus clientes, enriquecendo seus perfis de clientes com dados demográficos, como o tamanho da família, renda e muito mais.

## <a name="supported-countriesregions"></a>Países/regiões com suporte

No momento, oferecemos suporte ao enriquecimento de perfis de clientes somente nos Estados Unidos.

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura ativa da Experian Para obter uma assinatura, [contate a Experian](https://www.experian.com/marketing-services/contact) diretamente. [Saiba mais sobre o enriquecimento de dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Uma [conexão](connections.md) da Experian é [configurada](#configure-the-connection-for-experian) por um administrador.

- ID de Usuário, ID da Entidade e Número do Modelo da Experian para sua conta ST (Transporte Seguro) habilitada para SSH que a Experian criou para você.

## <a name="configure-the-connection-for-experian"></a>Configurar a conexão para a Experian

Você deve ser um [administrador](permissions.md#admin) no Customer Insights e ter uma ID de Usuário, ID de Entidade e Número do Modelo da Experian.

1. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administrador** > **Conexões** e selecione **Configurar** no bloco da Experian.

   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Painel de configuração de conexão da Experian":::

1. Insira um nome para a conexão e uma ID de Usuário, ID de Entidade e Número de Modelo válidos para o sua conta de Transporte Seguro da Experian.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Salvar**.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** em **Dados Demográficos** do bloco da Experian.

   :::image type="content" source="media/experian-tile.png" alt-text="Bloco da Experian na página de visão geral do enriquecimento. ":::

1. Revise a visão geral e selecione **Avançar**.

1. Selecionar a conexão. Contate um administrador se nenhuma conexão estiver disponível.

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer com dados demográficos da Experian. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. Defina que tipo de campos de seus perfis unificados devem usar para fazer a correspondência de dados demográficos da Experian. Pelo menos um dos campos **Nome e endereço**, **Telefone**, ou **E-mail** é necessário. Para maior precisão de correspondência, adicione outros campos. Selecione **Avançar**

1. Mapeie os campos para os dados demográficos da Experian.

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
