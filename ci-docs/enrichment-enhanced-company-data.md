---
title: Dados da empresa aprimorados
description: Enriqueça e normalize os dados da empresa com os modelos da Microsoft.
ms.date: 04/22/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 6aa38afa7f92b512d19b4967fc1652b5e43ad094
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645521"
---
# <a name="enrichment-of-company-profiles-with-enhanced-company-data"></a>Enriquecimento dos perfis da empresa com dados da empresa aprimorados

Use os modelos da Microsoft e os dados da empresa compilados para corrigir, complementar e padronizar os perfis da sua empresa. Usaremos o [Formato Common Data Model](/common-data-model/schema/core/applicationcommon/account) para melhor precisão e insights.

Você também pode [aprimorar os dados da empresa em fontes de dados](data-sources-enrichment.md) para melhorar a precisão da correspondência no processo de unificação de dados. 

Para empresas públicas nos Estados Unidos, há disponíveis informações como receita, cotação de ações, setor e muito mais.  

## <a name="how-we-enhance-company-data"></a>Como aprimorar os dados da empresa

Nosso modelo passa por um processo de duas etapas para aprimorar um perfil de empresa. Primeiro, ele normaliza o nome da empresa. Por exemplo, *Microsoft Corp* será corrigido e padronizado para *Microsoft Corporation*. Ele tenta encontrar uma correspondência nos dados da empresa compilados da Microsoft. Se uma correspondência for encontrada, enriqueceremos o perfil da empresa com informações dos dados da empresa compilados, incluindo o nome da empresa.


### <a name="example"></a>Exemplo

As informações da sua empresa podem não seguir um formato padronizado e conter erros de ortografia. O modelo tenta corrigir esses problemas e criar informações consistentes.

```Input
Microsft
```

```Output
- AccountName: Microsoft Corporation
- MainPhoneNumber: 8006427676
- Website: https://www.microsoft.com/
- Street1: One Microsoft Way
- City: Redmond
- StateOrProvince: Washington
- County: King
- ZipOrPostalCode: 98052
- CountryOrRegion: United States
```

## <a name="limitations"></a>Limitações

Existem algumas limitações com os dados aprimorados. Não há suporte aos itens na lista abaixo pelo modelo.

1.  Confirme a identidade da empresa. Não verificamos se a entrada é uma organização existente ou se uma empresa usa a saída como seu nome padrão.
2.  Cobre as empresas de forma abrangente globalmente. Os dados compilados da Microsoft têm cobertura global, mas oferecem a maior parte da cobertura na Austrália, no Canadá, no Reino Unido e nos Estados Unidos.
3.  Padronize os endereços da empresa globalmente. Atualmente, oferecemos suporte à padronização de endereços nestes países ou regiões: Austrália, Canadá, França, Alemanha, Itália, Japão, Reino Unido e Estados Unidos.
4.  Garanta a precisão ou atualização dos dados. Como as informações comerciais mudam com frequência, não podemos garantir que os dados da empresa aprimorados fornecidos sejam sempre exatos ou atualizados.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento**.

1. Selecione **Enriquecer meus dados** no bloco **Dados da empresa aprimorados**.

   :::image type="content" source="media/enhanced-company-data-tile.png" alt-text="Bloco de enriquecimento no centro de enriquecimento para dados da empresa.":::

1. Selecione os **Conjunto de dados do cliente** e escolha a entidade que contém os endereços que deseja enriquecer. Você pode selecionar a entidade *Cliente* para enriquecer endereços em todos os seus perfis de clientes ou selecione uma entidade de segmento para enriquecer endereços somente em perfis de clientes contidos naquele segmento.

1. Selecione os tipos de campos dos perfis de sua empresa que devem ser usados para fazer a correspondência com os dados da empresa compilados da Microsoft. Esta seleção afetará os campos de mapeamento aos quais você tem acesso na próxima etapa.

1.  Mapeie os campos da empresa a partir de sua entidade de cliente unificada. Quanto mais identificadores de chave e campos você mapear, maior será a probabilidade de uma taxa de correspondência mais alta.

    :::image type="content" source="media/enhanced-company-data-mapping.png" alt-text="Etapa de mapeamento de dados ao configurar o enriquecimento de uma empresa.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento para a entidade de saída.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

## <a name="enrichment-results"></a>Resultados de enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). A duração do processamento depende do tamanho dos dados do cliente.

Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.

Você pode ver um exemplo dos dados enriquecidos no bloco **Versão preliminar de clientes enriquecidos**. Selecione **Ver mais** e, depois, a guia **Dados** para acessar uma visão detalhada de cada perfil enriquecido.

### <a name="overview-card"></a>Cartão de visão geral

O cartão de visão geral mostra detalhes sobre a cobertura do enriquecimento. 

* **Empresas processadas e alteradas**: o número de perfis de empresas que foram enriquecidas com êxito.

* **Empresas processadas e não alteradas**: o número de perfis de empresas que foram reconhecidas, mas não foram alteradas. Isso geralmente acontece quando os dados de entrada são válidos e não podem ser aprimorados pelo enriquecimento.

* **Empresas não processadas e não alteradas**: o número de perfis de empresas de clientes que não foram reconhecidas. Isso normalmente acontece para dados de entrada que são inválidos ou não são compatíveis com o enriquecimento.

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]