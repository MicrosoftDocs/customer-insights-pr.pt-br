---
title: Enriquecer perfis de clientes unificados
description: Use recursos para enriquecer os dados do cliente.
ms.date: 11/02/2020
ms.reviewer: kishorem
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6b73aa93ec1a98f2b8d20d02e88bc6304f887078
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269454"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimento para perfis de clientes (visualização)

Use dados de fontes como a Microsoft e outros parceiros para enriquecer os dados de seus clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do hub de enriquecimento":::

Em insights de público-alvo, acesse **Dados** > **Enriquecimento** para trabalhar com as opções de enriquecimento.    
Você precisa ter permissões de Colaborador ou Administrador para criar ou editar enriquecimentos. Para obter mais informações, consulte [Permissões](permissions.md).

Na guia **Descobrir**, você encontrará os seguintes enriquecimentos:

- [Marcas](enrichment-microsoft-graph.md) fornecidas pelo Microsoft Graph
- [Interesses](enrichment-microsoft-graph.md) fornecidos pelo Microsoft Graph
- [Dados da empresa](enrichment-leadspace.md) fornecidos pela Leadspace
- [Dados demográficos](enrichment-experian.md) fornecidos pela Experian
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados](enrichment-SFTP-custom-import.md) via SFTP

Na guia **Meus enriquecimentos**, você pode ver os enriquecimentos configurados e editar suas propriedades.

## <a name="manage-existing-enrichments"></a>Gerenciar enriquecimentos existentes

Vá para **Meus enriquecimentos** para ver todos os enriquecimentos configurados. Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.

Selecione um enriquecimento para ver as opções disponíveis. Como alternativa, você pode selecionar as reticências (...) em um item da lista para ver as opções.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerenciar enriquecimentos na lista de enriquecimentos":::

- **Exibir** detalhes de enriquecimento com o número de perfis de clientes enriquecidos.
- **Editar** a configuração de enriquecimento.
- **Executar** o enriquecimento para atualizar os perfis dos clientes com os dados mais recentes.
- **Desativar** um enriquecimento existente para impedi-lo de atualizar automaticamente a cada atualização agendada. Os dados da última atualização bem-sucedida continuarão disponíveis. **Ativar** um enriquecimento inativo para reiniciar a atualização automática a cada atualização agendada.
- **Exclua** um enriquecimento.

Você pode executar ou desativar vários enriquecimentos de uma vez, selecionando-os na lista. As opções de exibição e edição não estão disponíveis como ação em massa e funcionam apenas para um enriquecimento de cada vez.


[!INCLUDE[footer-include](../includes/footer-banner.md)]