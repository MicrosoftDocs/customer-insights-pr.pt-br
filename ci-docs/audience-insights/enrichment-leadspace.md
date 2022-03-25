---
title: Enriquecimento de perfis de empresa com a Leadspace de enriquecimento de terceiros
description: Informações gerais sobre o enriquecimento de terceiros da Leadspace.
ms.date: 09/30/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 0db0c984f6bf9f7ded0704b6fa0caf39c7dace3a
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376770"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecimento de perfis de empresa com a Leadspace (versão preliminar)

A Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B. Ela habilita ambientes com perfis de clientes unificados com base em contas para enriquecer seus dados. Enriqueça *Perfis de clientes* com atributos como tamanho da empresa, localização ou setor. Enriqueça *Perfis de contato* com atributos como cargo, personalidade ou verificação de email.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a Leadspace, os seguintes pré-requisitos devem ser atendidos:

- Você ter uma licença da Leadspace ativa.
- Você tem [perfis de clientes unificados](customer-profiles.md) com base em contas.
- Uma conexão da Leadspace já ter sido configurada por um administrador ou você ter permissões de [administrador](permissions.md#admin) e a "chave perpétua" (chamada de **token da Leadspace**). Contate a [Leadspace](https://www.leadspace.com/leadspace-microsoft-dynamics-365/) diretamente para obter detalhes sobre seu produto.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Nos insights de público-alvo, vá para **Dados** > **Enriquecimento**.

1. Selecione **Enriquecer meus dados** no bloco da Leadspace e selecione **Começar agora**.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de tela do bloco da Leadspace.":::

1. Selecione uma [conexão](connections.md) na lista suspensa. Contate um administrador se nenhuma conexão estiver disponível. Se for administrador, você poderá criar uma conexão selecionando **Adicionar conexão** e escolhendo **Leadspace**. 

1. Selecione **Conectar-se à Leadspace** para confirmar a conexão.

1. Selecione **Avançar** e escolha o **Conjunto de dados do cliente** que você deseja enriquecer com os dados de empresas da Leadspace. Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.

    :::image type="content" source="media/enrichment-Leadspace-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. Selecione **Avançar** e defina quais tipos de campos de seus perfis unificados serão usados para procurar dados de empresas correspondentes da Leadspace. O campo **Nome da empresa** é obrigatório. Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Site da empresa** e **Local da empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo Leadspace.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Marque a caixa de seleção se tiver *Perfis de contato* que você gostaria de enriquecer. Os insights do público-alvo mapearão automaticamente os campos obrigatórios.

   :::image type="content" source="media/enrichment-leadspace-contacts.png" alt-text="Enriquecimento de registros de contato Leadspace.":::
 
1. Forneça um nome para o enriquecimento e selecione **Salvar enriquecimento** depois de revisar suas escolhas.


## <a name="configure-the-connection-for-leadspace"></a>Configurar a conexão para a Leadspace 

Você deve ser um administrador para configurar as conexões. Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da Leadspace.

1. Selecione **Começar**. 

1. Insira um nome para a conexão na caixa **Nome de exibição**.

1. Forneça um token da Leadspace válido.

1. Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** selecionando **Eu concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Salvar**.
   
   :::image type="content" source="media/enrichment-Leadspace-connection.png" alt-text="Página de configuração de conexão da Leadspace.":::

## <a name="enrichment-results"></a>Resultados de enriquecimento

Depois de atualizar o enriquecimento, você pode revisar os dados da empresa recém-enriquecidos em [Meus enriquecimentos](enrichment-hub.md). Você pode encontrar o horário da última atualização e o número de perfis aprimorados.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

Para obter mais informações, consulte [APIs da Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Próximas etapas


[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Leadspace, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Leadspace cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
