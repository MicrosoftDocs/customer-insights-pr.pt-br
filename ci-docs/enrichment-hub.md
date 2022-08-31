---
title: Visão geral de enriquecimento de dados (versão preliminar)
description: Use os recursos da Microsoft e de outros serviços de terceiros para enriquecer os dados de seus clientes.
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
ms.openlocfilehash: fb747f7adc7d87f30f66c5d0ed20bbe238558fde
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304505"
---
# <a name="data-enrichment-preview-overview"></a>Visão geral de enriquecimento de dados (versão preliminar)

Use dados de fontes como a Microsoft e outros parceiros para enriquecer os dados de seus clientes. Os enriquecimentos de terceiros são configurados usando [conexões](connections.md), as quais um administrador configura com credenciais e fornece consentimento para a transferências de dados. As conexões podem ser usadas por administradores e colaboradores para configurar enriquecimentos.  

## <a name="multiple-enrichments-of-the-same-type"></a>Vários enriquecimentos do mesmo tipo

A entidade a ser enriquecida é especificada durante a configuração de enriquecimento, o que permite que você enriqueça somente um subconjunto de seus perfis. Por exemplo, enriqueça dados somente para um segmento específico. Você pode configurar vários enriquecimentos do mesmo tipo e reutilizar a mesma conexão. Alguns enriquecimentos terão limites para o número de enriquecimentos do mesmo tipo que podem ser criados. Os limites e uso atual podem ser vistos em cada bloco na guia **Descobrir** da página **Enriquecimento**.

## <a name="enrich-data-sources-before-unification"></a>Enriquecer as fontes de dados antes da unificação

Você pode enriquecer os dados do cliente antes da unificação de dados para ajudar a aumentar a qualidade de uma correspondência de dados. Para obter mais informações, consulte [enriquecimento de fonte de dados](data-sources-enrichment.md).

## <a name="create-an-enrichment"></a>Criar um enriquecimento

Você precisa ter [permissões](permissions.md) de Colaborador ou Administrador para criar ou editar enriquecimentos.

Vá para **Dados** > **Enriquecimento**. A guia **Descobrir** mostra todas as opções de enriquecimento com suporte.

:::image type="content" source="media/enrichment-hub-page.png" alt-text="Página do hub de enriquecimento.":::

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

## <a name="manage-existing-enrichments"></a>Gerenciar enriquecimentos existentes

Vá para **Dados** > **Enriquecimento**. Na guia **Meus enriquecimentos**, exiba os enriquecimentos configurados, seus status, o número de clientes enriquecidos e a última vez que os dados foram atualizados. Você pode classificar a lista de enriquecimentos por qualquer coluna ou usar a caixa de pesquisa para encontrar o enriquecimento que deseja gerenciar.

Selecione o enriquecimento para exibir as ações disponíveis.

:::image type="content" source="media/enrichment-hub-options-run.png" alt-text="Opções para gerenciar enriquecimentos na lista de enriquecimentos.":::

- **Exibir** detalhes de enriquecimento com o número de perfis de clientes enriquecidos.
- **Editar** a configuração de enriquecimento.
- [**Executar**](#run-or-refresh-enrichments) o enriquecimento para atualizar os perfis dos clientes com os dados mais recentes. Executar vários enriquecimentos de uma só vez selecionando-os na lista.
- **Ativar** ou **Desativar** um enriquecimento. Os enriquecimentos inativos não serão atualizados durante uma [atualização agendada](schedule-refresh.md).
- **Exclua** o enriquecimento.

Você também pode criar [segmentos](segments.md) ou [medidas](measures.md) de enriquecimentos.

## <a name="run-or-refresh-enrichments"></a>Executar ou atualizar enriquecimentos

Uma vez executados, os enriquecimentos podem ser atualizados em um agendamento automático ou atualizados manualmente sob demanda.

1. Para atualizar manualmente um ou mais enriquecimentos, selecione-os e escolha **Executar**. Para [agendar uma atualização automática](schedule-refresh.md), acesse **Administrador** > **Sistema** > **Agenda**. A duração do processamento depende do tamanho dos dados do cliente.

1. Opcionalmente, [veja o andamento do processo de enriquecimento](#see-the-progress-of-the-enrichment-process).

1. Após a conclusão do processo de enriquecimento, vá para **Meus enriquecimentos** para revisar os dados de perfis de clientes enriquecidos recentemente, a hora da última atualização e o número de perfis enriquecidos.

1. Selecione o enriquecimento para ver os [resultados de enriquecimento](#view-enrichment-results).

### <a name="see-the-progress-of-the-enrichment-process"></a>Veja o andamento do processo de enriquecimento

Você pode encontrar detalhes sobre o processamento de um enriquecimento, incluindo o status e possíveis problemas durante ou após a conclusão de uma atualização. Entenda quais processos estão envolvidos para atualizar um enriquecimento e quanto tempo levou para executar os processos. O status de enriquecimento é compatível com Experian, Leadspace, HERE Technologies, SFTP Import e Azure Mapas.

1. Vá para **Dados** > **Enriquecimento**.
1. Na guia **Meus enriquecimentos**, selecione o status do enriquecimento para abrir um painel lateral.
1. No painel **Detalhes de progresso**, expanda a seção **Enriquecimentos**.
1. No enriquecimento em que você deseja ver o progresso, selecione **Ver detalhes**.
1. No painel **Detalhes da tarefa**, selecione **Mostrar detalhes** para ver os processos envolvidos na atualização do enriquecimento e o status.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="view-enrichment-results"></a>Exibir resultados de enriquecimento

Após concluir a execução de enriquecimento, revise os resultados do enriquecimento.

1. Vá para **Dados** > **Enriquecimento**.
1. Na guia **Meus enriquecimentos**, selecione o enriquecimento que deseja exibir.

Todos os enriquecimentos mostram informações básicas, como o número de perfis enriquecidos e o número de perfis enriquecidos ao longo do tempo. O bloco **Visualização de clientes enriquecidos** mostra uma amostra da entidade de enriquecimento gerada. Para ter uma exibição detalhada, selecione **Ver mais** e selecione a guia **Dados**.

:::image type="content" source="media/enrichments-results.png" alt-text="Página de resultados do enriquecimento.":::

Se disponível, o **Número de clientes enriquecidos por campo** apresenta um detalhamento da cobertura de cada campo enriquecido.

Alguns enriquecimentos também mostram informações específicas do tipo de enriquecimento. Para obter mais informações, consulte a documentação relacionada.

[!INCLUDE [footer-include](includes/footer-banner.md)]
