---
title: Enriqueça perfis de clientes com dados de localização do Azure Mapas
description: Informações gerais sobre o enriquecimento próprio do Azure Mapas.
ms.date: 08/31/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: cbeac7e25d83df152c38d1c59cc6734a3d1fee97
ms.sourcegitcommit: 23c8973a726b15050e368cc6e0aab78b266a89f6
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/08/2021
ms.locfileid: "7618553"
---
# <a name="enrichment-of-customer-profiles-with-azure-maps-preview"></a>Enriquecimento de perfis de clientes com o Azure Mapas (versão preliminar)

O Azure Mapas fornece dados e serviços centrados na localização para fornecer experiências baseadas em dados geoespaciais com inteligência de localização interna. Os serviços de enriquecimento de dados do Azure Mapas melhoram a precisão de informações de localização sobre os clientes. Ele traz recursos como normalização de endereço e extração de latitude e longitude para o Dynamics 365 Customer Insights.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o enriquecimento de dados do Azure Mapas, é necessário atender aos seguintes pré-requisitos:

- Você tem uma assinatura ativa do Azure Mapas. Para obter uma assinatura, você pode [inscrever-se ou obter uma avaliação gratuita](https://azure.microsoft.com/services/azure-maps/).

- Uma [conexão](connections.md) do Azure Mapas está disponível, *ou* você tem permissões de [administrador](permissions.md#administrator) e uma chave de API ativa do Azure Mapas.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento**. 

1. No bloco **Localização**, selecione **Enriquecer meus dados**.

   :::image type="content" source="media/azure-maps-tile.png" alt-text="Bloco do Azure Mapas.":::

1. Selecione uma [conexão](connections.md) na lista suspensa. Entre em contato com um administrador se nenhuma conexão do Azure Mapas estiver disponível. Se você for um administrador, poderá [configurar a conexão para o Azure Mapas](#configure-the-connection-for-azure-maps). 

1. Selecione **Avançar** para confirmar a seleção.

1. Escolha o **Conjunto de dados do cliente** a ser enriquecido com dados de localização do Azure Mapas. Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de clientes unificados, ou selecionar uma entidade de segmento para enriquecer somente perfis de clientes contidos nesse segmento.

    :::image type="content" source="media/enrichment-azure-maps-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. Escolha se deseja mapear campos para o endereço principal e/ou secundário. Você pode especificar um mapeamento de campo para ambos os endereços e enriquecer os perfis para ambos os endereços separadamente (por exemplo, um endereço residencial e um comercial). Selecione **Avançar**

1. Defina que campos de perfis unificados devem ser usados para procurar dados de localização correspondentes no Azure Mapas. Os campos **Rua 1** e **CEP** são obrigatórios para o endereço principal ou secundário selecionado. Para maior precisão de correspondência, você pode adicionar mais campos.

   :::image type="content" source="media/enrichment-azure-maps-configuration.png" alt-text="Página de configuração de enriquecimento do Azure Mapas.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Avalie se você deseja modificar **Configurações Avançadas**. Isso visa fornecer flexibilidade máxima para lidar com casos de uso avançados, mas os valores padrão serão adequados na maioria dos casos:
   - **Tipo de endereços**: o comportamento padrão é que o enriquecimento retornará a melhor correspondência de endereço, mesmo se estiver incompleto. Para obter apenas endereços completos (por exemplo, endereços que incluem o número da casa), desmarque todas as caixas de seleção, exceto **Endereços de Ponto**. 
   - **Idioma**: por padrão, os endereços são retornados no idioma da região à qual o endereço foi determinado como pertencente. Para aplicar um idioma de endereço padronizado, selecione o idioma no menu suspenso. Por exemplo, selecionar **inglês** retornará **Copenhague, Dinamarca** em vez de **København, Danmark**.

1. Forneça um nome para o enriquecimento.

1. Revise suas opções e selecione **Salvar enriquecimento**.

## <a name="configure-the-connection-for-azure-maps"></a>Configure a conexão para o Azure Mapas

Você precisa ser um administrador em insights de público-alvo para configurar conexões. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administração** > **Conexões** e selecione **Configurar** no bloco do Azure Mapas.

1. Na caixa **Nome de exibição**, insira um nome para a conexão.

1. Forneça uma chave válida de API do Azure Mapas.

1. Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Salvar**.

:::image type="content" source="media/enrichment-azure-maps-connection.png" alt-text="Página de configuração de conexão do Azure Mapas.":::

## <a name="enrichment-results"></a>Resultados de enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados do cliente e dos tempos de resposta da API.

Após a conclusão do processo de enriquecimento, você poderá revisar os dados de perfis de clientes recém-enriquecidos em **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o Azure Mapas, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o Azure Mapas cumpra obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, acesse [Declaração de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
