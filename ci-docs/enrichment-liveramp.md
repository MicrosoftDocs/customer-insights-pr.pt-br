---
title: Enriquecer perfis dos clientes com dados de identidade da LiveRamp (versão preliminar)
description: Enriqueça perfis de clientes com dados do LiveRamp.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 49bf558209ca91ab9d8db945862a57adccee1f6b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196334"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquecer perfis dos clientes com dados de identidade da LiveRamp (versão preliminar)

O LiveRamp fornece resolução de identidade offline determinada e consolidação de dados do cliente. Você pode mapear identificadores pessoais em seus dados de cliente para o gráfico de identidade da AbiliTec e receber IDs da AbiliTec. Você pode usar essas IDs para uma unificação melhor dos dados de seus clientes.

## <a name="supported-countriesregions"></a>Países/regiões com suporte

Atualmente, oferecemos suporte ao enriquecimento de perfis de clientes com dados do LiveRamp apenas nos Estados Unidos.

## <a name="prerequisites"></a>Pré-requisitos

- Você tem uma assinatura ativa da LiveRamp. Para obter uma assinatura, entre em contato com a equipe da sua conta LiveRamp ou pelo email [dynamics@liveramp.com](mailto:dynamics@liveramp.com) para saber mais.

- Uma assinatura ativa da AbiliTec com uma ID do cliente e segredo para acessar a API. Para obter mais informações, consulte [Hub dos desenvolvedores da API da AbiliTec](https://developers.liveramp.com/abilitec-api/).

- Uma [conexão](connections.md) da LiveRamp é [configurada](#configure-the-connection-for-liveramp) por um administrador.

## <a name="configure-the-connection-for-liveramp"></a>Configurar a conexão para LiveRamp

Você deve ser um [administrador](permissions.md#admin) no Customer Insights e ter uma ID do cliente e um segredo ativos da LiveRamp.

1. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administrador** > **Conexões** e selecione **Configurar** no bloco da LiveRamp.

   :::image type="content" source="media/liveramp-connection.png" alt-text="Painel de configuração para configurar a conexão com o serviço do LiveRamp da AbiliTec. ":::

1. Insira um nome para a conexão e uma ID de cliente e um segredo válidos da LiveRamp.

1. Revise e forneça seu consentimento para a [Conformidade e privacidade dos dados](#data-privacy-and-compliance) selecionando **Eu concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Salvar**.

### <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao LiveRamp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o LiveRamp atenda às obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, revise a [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** em **Identidade** do bloco da LiveRamp.

   :::image type="content" source="media/liveramp-tile.png" alt-text="Bloco de identidade na página de visão geral do enriquecimento. ":::

1. Revise a visão geral e selecione **Avançar**.

1. Selecionar a conexão. Contate um administrador se nenhuma conexão estiver disponível.

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer com dados de identidade da LiveRamp. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

1. Defina que tipo de campos de seus perfis unificados devem usar para fazer a correspondência de dados de identidade da LiveRamp. Pelo menos um dos campos **Nome e endereço**, **Email** ou **Telefone** é obrigatório. Para maior precisão de correspondência, adicione outros campos. Selecione **Avançar**

1. Mapeie os campos para os dados de identificação da LiveRamp.

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opções de mapeamento de dados para o enriquecimento do LiveRamp.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o enriquecimento e o **Nome da entidade de saída**.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Executar** para iniciar o processo de enriquecimento ou feche para voltar para a página **Enriquecimentos**.

## <a name="view-enrichment-results"></a>Exibir resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

O **Número de clientes enriquecidos por campo** apresenta um detalhamento da cobertura de cada campo enriquecido.

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Use as IDs da AbiliTec para consolidar os perfis dos clientes em uma visão baseada em pessoa.
[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
