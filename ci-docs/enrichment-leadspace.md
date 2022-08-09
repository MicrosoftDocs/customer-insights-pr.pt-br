---
title: Enriquecer perfis de empresas com a Leadspace (versão preliminar)
description: Informações gerais sobre o enriquecimento de terceiros da Leadspace.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 3f23fe7177f931db3e3179970915d0cd3c736f87
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196196"
---
# <a name="enrich-company-profiles-with-leadspace-preview"></a>Enriquecer perfis de empresas com a Leadspace (versão preliminar)

A Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B. Ela habilita ambientes com perfis de clientes unificados com base em contas para enriquecer seus dados. Enriqueça *Perfis de clientes* com atributos como tamanho da empresa, localização ou setor. Enriqueça *Perfis de contato* com atributos como cargo, personalidade ou verificação de email.

## <a name="prerequisites"></a>Pré-requisitos

- Uma licença ativa da Leadspace.
- [Perfis de cliente unificados](customer-profiles.md) com base em contas.
- Uma [conexão](connections.md) da Leadspace é [configurada](#configure-the-connection-for-leadspace) por um administrador. Contate a [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) diretamente para obter detalhes sobre seu produto.

## <a name="configure-the-connection-for-leadspace"></a>Configurar a conexão para a Leadspace

Você deve ser um [administrador](permissions.md#admin) no Customer Insights e ter a "chave perpétua" (conhecida como **token da Leadspace**).

1. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administrador** > **Conexões** e selecione **Configurar** no bloco da Leadspace.

   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuração de conexão da Leadspace.":::

1. Insira um nome para a conexão e um token válido da Leadspace.

1. Revise e forneça seu consentimento para a [Conformidade e privacidade dos dados](#data-privacy-and-compliance) selecionando **Eu concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Salvar**.

### <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Leadspace, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Leadspace cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** em **Dados da empresa** do bloca Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de tela do bloco da Leadspace.":::

1. Revise a visão geral e selecione **Avançar**.

1. Selecionar a conexão. Contate um administrador se nenhuma conexão estiver disponível.

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer com dados da empresa da Leadspace. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. Defina que tipo de campos de seus perfis unificados usar para correspondência: o endereço principal e/ou secundário. Você pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis para ambos os endereços separadamente. Por exemplo, para um endereço residencial e um endereço comercial. Selecione **Avançar**

1. Mapeie os campos para os dados da empresa da Leadspace. O campo **Nome da empresa** é obrigatório. Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Site da empresa** e **Local da empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo Leadspace.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Marque a caixa de seleção se tiver *Perfis de contato* que você gostaria de enriquecer. O Customer Insights mapeará automaticamente os campos obrigatórios.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Enriquecimento de registros de contato Leadspace.":::

1. Selecione **Avançar**

1. Forneça um **Nome** para o enriquecimento e o **Nome da entidade de saída**.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Executar** para iniciar o processo de enriquecimento ou feche para voltar para a página **Enriquecimentos**.

## <a name="view-enrichment-results"></a>Exibir resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

Para obter mais informações, consulte [APIs da Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
