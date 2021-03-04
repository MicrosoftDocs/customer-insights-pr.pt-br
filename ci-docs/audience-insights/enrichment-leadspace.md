---
title: Enriquecimento de perfis de empresa com a Leadspace de enriquecimento de terceiros
description: Informações gerais sobre o enriquecimento de terceiros da Leadspace.
ms.date: 11/24/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 12eed91a7ca4ef7fde0d53cca4a1dfd398b4634f
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269408"
---
# <a name="enrichment-of-company-profiles-with-leadspace-preview"></a>Enriquecimento de perfis de empresa com Leadspace (versão preliminar)

Leadspace é uma empresa de ciência de dados que fornece uma Plataforma de Dados de Clientes B2B. Ela permite que os clientes com perfis de cliente unificados para as empresas possam enriquecer seus dados. Os enriquecimentos incluem atributos adicionais, como tamanho da empresa, localização, setor e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o Leadspace, os seguintes pré-requisitos devem ser atendidos:

- Você tem uma licença da Leadspace ativa e a “chave perpétua” (referida como **token da Leadspace**). Entre em contato diretamente com [Leadspace](https://www.leadspace.com/products/leadspace-on-demand/) para obter detalhes sobre o produto.
- Você tem as permissões de [Administrador](permissions.md#administrator).
- Você ter [perfis unificados de clientes](customer-profiles.md) para empresas.

## <a name="configuration"></a>Configuração

1. Nos insights de público-alvo, vá para **Dados** > **Enriquecimento**.

1. Selecione **Enriquecer meus dados** no bloco da Leadspace.

   :::image type="content" source="media/leadspace-tile.png" alt-text="Captura de tela do bloco da Leadspace.":::

1. Selecione **Introdução** e digite um **token da Leadspace** ativo (chave perpétua). Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**. Confirme as duas entradas selecionando **Conectar-se à Leadspace**.

1. Selecione **Mapear dados** e escolha o conjunto de dados que deseja enriquecer com dados da empresa do Leadspace. Você pode selecionar a entidade *Cliente* para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.

   :::image type="content" source="media/enrichment-leadspace-select-segment.png" alt-text="Escolha entre enriquecimento do segmento e do perfil do cliente.":::

1. Clique em **Próximo** e defina quais campos de seus perfis unificados devem ser usados para procurar dados da empresa correspondentes na Leadspace. O campo **Nome da empresa** é obrigatório. Para uma maior precisão de correspondência, podem ser adicionados até dois outros campos, **Site da empresa** e **Local da empresa**.

   :::image type="content" source="media/enrichment-leadspace-mapping.png" alt-text="Painel de mapeamento de campo da Leadspace.":::
   
1. Selecione **Aplicar** para completar o mapeamento de campo.

1. Selecione **Executar** para enriquecer os perfis da empresa. O tempo de duração de um enriquecimento depende do número de perfis de clientes unificados.

## <a name="enrichment-results"></a>Resultados de enriquecimento

Depois de atualizar o enriquecimento, você pode revisar os dados da empresa recém-enriquecidos em [Meus enriquecimentos](enrichment-hub.md). Você pode encontrar o horário da última atualização e o número de perfis aprimorados.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

Para obter mais informações, consulte [APIs da Leadspace](https://support.leadspace.com/hc/en-us/sections/201997649-API).

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Leadspace, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Leadspace cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]