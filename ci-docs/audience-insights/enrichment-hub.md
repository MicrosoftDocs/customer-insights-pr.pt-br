---
title: Enriquecer perfis de clientes unificados
description: Use recursos para enriquecer os dados do cliente.
ms.date: 07/01/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: d12c0a9dd65d31f9ae8a9cafeafab2767d57893e
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555247"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimento para perfis de clientes (visualização)

Use dados de fontes como a Microsoft e outros parceiros para enriquecer os dados de seus clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do hub de enriquecimento.":::

Em insights de público-alvo, acesse **Dados** > **Enriquecimento** para trabalhar com as opções de enriquecimento.  

Você precisa ter permissões de Colaborador ou Administrador para criar ou editar enriquecimentos. Para obter mais informações, consulte [Permissões](permissions.md).

Na guia **Descobrir**, você encontrará os seguintes enriquecimentos:

- [Marcas](enrichment-microsoft.md) fornecidas pela Microsoft
- [Interesses](enrichment-microsoft.md) fornecidos pela Microsoft
- [Endereços aprimorados](enrichment-enhanced-addresses.md) fornecidos pela Microsoft
- [Dados de empresas](enrichment-leadspace.md) fornecidos pela Leadspace
- [Dados demográficos](enrichment-experian.md) fornecidos pela Experian
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados](enrichment-SFTP-custom-import.md) via SFTP

Na guia **Meus enriquecimentos**, você pode ver os enriquecimentos configurados e editar suas propriedades.

## <a name="manage-existing-enrichments"></a>Gerenciar enriquecimentos existentes

Acesse a guia **Meus enriquecimentos** para ver todos os enriquecimentos configurados. Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.

Selecione o enriquecimento para ver as opções disponíveis. Você também pode selecionar as reticências (...) em um item da lista para ver as opções. Se configurou vários enriquecimentos, você poderá usar a caixa de pesquisa para encontrá-los rapidamente.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerenciar enriquecimentos na lista de enriquecimentos.":::

- **Exibir** detalhes de enriquecimento com o número de perfis de clientes enriquecidos.
- **Editar** a configuração de enriquecimento.
- **Executar** o enriquecimento para atualizar os perfis dos clientes com os dados mais recentes.
- **Desativar** um enriquecimento existente para impedi-lo de atualizar automaticamente a cada atualização agendada. Os dados da última atualização bem-sucedida continuarão disponíveis. **Ativar** um enriquecimento inativo para reiniciar a atualização automática a cada atualização agendada.
- **Exclua** o enriquecimento.

Execute ou desative vários enriquecimentos de uma vez, selecionando-os na lista. As opções de exibição e edição não estão disponíveis como ação em massa. Elas só funcionam para um enriquecimento de cada vez.

## <a name="enrichments-and-connections"></a>Enriquecimentos e conexões

Os enriquecimentos de terceiros são configurados usando [conexões](connections.md), as quais um administrador configura com credenciais e fornece consentimento para a transferências de dados. A conexão pode então ser usada pelos administradores e colaboradores para a configuração de enriquecimentos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Vários enriquecimentos do mesmo tipo

A entidade a ser enriquecida é especificada durante a configuração de enriquecimento, o que permite que você enriqueça somente um subconjunto de seus perfis. Por exemplo, enriqueça dados somente para um segmento específico. Você pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma conexão. Alguns enriquecimentos terão limites para o número de enriquecimentos do mesmo tipo que podem ser criados. Os limites e o uso atual podem ser vistos na página **Enriquecimento**.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
