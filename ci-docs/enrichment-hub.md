---
title: Enriquecer perfis de clientes unificados
description: Use recursos para enriquecer os dados do cliente.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.custom: intro-internal
searchScope:
- ci-enrichments
- ci-enrichment-details
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 3bbe8b829a6698da55d84709dbab6c36aa76792a
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954027"
---
# <a name="enrichment-for-customer-profiles-preview"></a>Enriquecimento para perfis de clientes (visualização)

Use dados de fontes como a Microsoft e outros parceiros para enriquecer os dados de seus clientes.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do hub de enriquecimento.":::

Vá para **Dados** > **Enriquecimento** para trabalhar com opções de enriquecimento.  

Você precisa ter permissões de Colaborador ou Administrador para criar ou editar enriquecimentos. Para obter mais informações, consulte [Permissões](permissions.md).

Na guia **Descobrir**, você encontrará todas as opções de enriquecimento suportadas.

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

- [AbiliTec Identity](enrichment-liveramp.md) fornecido pelo LiveRamp AbiliTec
- [Marcas](enrichment-microsoft.md) fornecidas pela Microsoft
- [Dados demográficos](enrichment-experian.md) fornecidos pela Experian
- [Endereços aprimorados](enrichment-enhanced-addresses.md) fornecidos pela Microsoft
- [Interesses](enrichment-microsoft.md) fornecidos pela Microsoft
- [Dados de localização](enrichment-azure-maps.md) fornecidos por Microsoft Azure Mapas
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados do SFTP](enrichment-SFTP-custom-import.md) via SFTP

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

- [Dados de engajamento da conta](enrichment-office.md) fornecido pela Microsoft
- [Dados da empresa](enrichment-dnb.md) fornecidos pela Dun & Bradstreet
- [Dados de empresas](enrichment-leadspace.md) fornecidos pela Leadspace
- [Endereços aprimorados](enrichment-enhanced-addresses.md) fornecidos pela Microsoft
- [Dados aprimorados da empresa](enrichment-enhanced-company-data.md) fornecidos pela Microsoft
- [Dados de localização](enrichment-azure-maps.md) fornecidos por Microsoft Azure Mapas
- [Dados de localização](enrichment-here.md) fornecidos pela HERE Technologies
- [Dados personalizados do SFTP](enrichment-SFTP-custom-import.md) via SFTP

---

Na guia **Meus enriquecimentos**, você pode ver os enriquecimentos configurados e editar suas propriedades. Você também pode criar [segmentos](segments.md) ou [medidas](measures.md) de enriquecimentos.

## <a name="manage-existing-enrichments"></a>Gerenciar enriquecimentos existentes

Acesse a guia **Meus enriquecimentos** para ver todos os enriquecimentos configurados. Cada enriquecimento é representado como uma linha que inclui informações adicionais sobre o enriquecimento.

Selecione o enriquecimento para ver as opções disponíveis. Você também pode selecionar as reticências verticais (&vellip;) em um item de lista para ver as opções. Se configurou vários enriquecimentos, você poderá usar a caixa de pesquisa para encontrá-los rapidamente.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerenciar enriquecimentos na lista de enriquecimentos.":::

- **Exibir** detalhes de enriquecimento com o número de perfis de clientes enriquecidos.
- **Editar** a configuração de enriquecimento.
- **Executar** o enriquecimento para atualizar os perfis dos clientes com os dados mais recentes.
- **Desativar** um enriquecimento existente para impedi-lo de atualizar automaticamente a cada atualização agendada. Os dados da última atualização bem-sucedida continuarão disponíveis. **Ativar** um enriquecimento inativo para reiniciar a atualização automática a cada atualização agendada.
- **Exclua** o enriquecimento.

Execute ou desative vários enriquecimentos de uma vez, selecionando-os na lista. As opções de exibição e edição não estão disponíveis como ação em massa. Elas só funcionam para um enriquecimento de cada vez.

## <a name="enrichments-and-connections"></a>Enriquecimentos e conexões

Os enriquecimentos de terceiros são configurados usando [conexões](connections.md), as quais um administrador configura com credenciais e fornece consentimento para a transferências de dados. As conexões podem ser usadas por administradores e colaboradores para configurar enriquecimentos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Vários enriquecimentos do mesmo tipo

A entidade a ser enriquecida é especificada durante a configuração de enriquecimento, o que permite que você enriqueça somente um subconjunto de seus perfis. Por exemplo, enriqueça dados somente para um segmento específico. Você pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma conexão. Alguns enriquecimentos terão limites para o número de enriquecimentos do mesmo tipo que podem ser criados. Os limites e uso atual podem ser vistos em cada bloco na guia **Descobrir** da página **Enriquecimento**.

## <a name="enrich-data-sources-before-unification"></a>Enriquecer as fontes de dados antes da unificação

Você pode enriquecer os dados do cliente antes da unificação de dados para ajudar a aumentar a qualidade de uma correspondência de dados. Para obter mais informações, consulte [enriquecimento de fonte de dados](data-sources-enrichment.md).

## <a name="run-or-refresh-enrichments"></a>Executar ou atualizar enriquecimentos

1. Para iniciar o processo de enriquecimento, selecione **Executar**. Ou permita que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). A duração do processamento depende do tamanho dos dados do cliente.

1. Opcionalmente, [veja o andamento do processo de enriquecimento](#see-the-progress-of-the-enrichment-process).

1. Após a conclusão do processo de enriquecimento, vá para **Meus enriquecimentos** para revisar os dados de perfis de clientes enriquecidos recentemente, a hora da última atualização e o número de perfis enriquecidos.

1. Selecione o enriquecimento para ver os [resultados de enriquecimento](#enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Veja o andamento do processo de enriquecimento

Você pode encontrar detalhes sobre o processamento de um enriquecimento, incluindo o status e possíveis problemas durante ou após a conclusão de uma atualização. Entenda quais processos estão envolvidos para atualizar um enriquecimento e quanto tempo levou para executar os processos. O status de enriquecimento é compatível com Experian, Leadspace, HERE Technologies, SFTP Import e Azure Mapas.

1. Vá para **Dados** > **Enriquecimento**.
1. Na guia **Meus enriquecimentos**, selecione o status do enriquecimento para abrir um painel lateral.
1. No painel **Detalhes de progresso**, expanda a seção **Enriquecimentos**.
1. No enriquecimento em que você deseja ver o progresso, selecione **Ver detalhes**.
1. No painel **Detalhes da tarefa**, selecione **Mostrar detalhes** para ver os processos envolvidos na atualização do enriquecimento e o status.

## <a name="enrichment-results"></a>Resultados de enriquecimento

Após concluir a execução de enriquecimento, revise os resultados do enriquecimento.

1. Vá para **Dados** > **Enriquecimento**.
1. Na guia **Meus enriquecimentos**, selecione o enriquecimento sobre o qual deseja obter informações.

Todos os enriquecimentos mostram informações básicas, como o número de perfis enriquecidos e o número de perfis enriquecidos ao longo do tempo. O bloco **Visualização de clientes enriquecidos** mostra uma amostra da entidade de enriquecimento gerada. Para ter uma exibição detalhada, selecione **Ver mais** e selecione a guia **Dados**.

:::image type="content" source="media/enrichments-results.png" alt-text="Página de resultados do enriquecimento.":::

Se disponível, o **Número de clientes enriquecidos por campo** apresenta um detalhamento da cobertura de cada campo enriquecido.

Alguns enriquecimentos também mostram informações específicas do tipo de enriquecimento. Para obter mais informações, consulte a documentação relacionada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
