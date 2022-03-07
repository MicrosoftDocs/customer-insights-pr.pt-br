---
title: Enriquecimento de aprimoramento de endereços (contém vídeo)
description: Enriqueça e normalize as informações de endereço de perfis de clientes com modelos da Microsoft.
ms.date: 01/19/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
searchScope:
- ci-data-sources-enrichment
- ci-data-sources-enrichment-details
- ci-enrichments
- ci-enrichment-wizard
- customerInsights
ms.openlocfilehash: 067757019078d3a46b224ba259d2d097dfbbe381
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8353622"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enriquecimento de perfis de clientes com endereços aprimorados

Os endereços dos seus dados podem ser não estruturados, incompletos ou incorretos. Use os modelos da Microsoft para normalizar e enriquecer seus endereços no [formato de Common Data Model](/common-data-model/schema/core/applicationcommon/address) para ter melhor precisão e insights.

## <a name="how-we-enhance-addresses"></a>Como aprimoramos os endereços

Nosso modelo passa por um processo de duas etapas para aprimorar endereços. Primeiro, ele analisa o endereço para identificar componentes e coloca-os em um formato estruturado. Em seguida, usamos a IA para corrigir, completar e padronizar os valores no endereço.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWNewo]

### <a name="example"></a>Exemplo

As informações de endereço podem estar em um formato não padrão e conter erros de ortografia. O modelo pode corrigir esses problemas e criar endereços consistentes em perfis unificados de clientes.

```Input
4567 w main stret californa missouri 54321 us
```

```Output
- Street1: 4567 W Main St
- City: California
- StateOrProvince: MO
- ZipOrPostalCode: 54321
- CountryOrRegion: United States of America

- Address: 4567 W Main St, California, MO, 54321, United States of America
```

### <a name="limitations"></a>Limitações

Os endereços avançados só funcionam com os valores que já existem nos dados de endereço processados. O modelo não: 

1. Verifica se o endereço é um endereço válido.
2. Verifica se um dos valores, como CEPs ou nomes de rua, são válidos.
3. Altera valores não reconhecidos.

O modelo usa técnicas com base em aprendizado de máquina para aprimorar os endereços. Embora apliquemos um limite de alta confiança para quando o modelo altera um valor de entrada, como acontece com qualquer modelo baseado em aprendizado de máquina, a precisão de 100% não é garantida.

## <a name="supported-countries-or-regions"></a>Países ou regiões com suporte

Atualmente, damos suporte a endereços de enriquecimento nestes países ou regiões: 

- Austrália
- Canadá
- França
- Alemanha
- Itália
- Japão
- Reino Unido
- Estados Unidos

Os endereços devem conter um valor de país/região. Não processamos endereços para países ou regiões que não têm suporte e endereços que não tenham país ou região fornecidos.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento**.

1. Selecione **Enriquecer meus dados** no bloco **Endereços aprimorados**.

   :::image type="content" source="media/enhanced-addresses-tile.png" alt-text="Captura de tela do bloco Endereços aprimorados.":::

1. Selecione os **Conjunto de dados do cliente** e escolha a entidade que contém os endereços que deseja enriquecer. Você pode selecionar a entidade *Cliente* para enriquecer endereços em todos os seus perfis de clientes ou selecione uma entidade de segmento para enriquecer endereços somente em perfis de clientes contidos naquele segmento.

1. Selecione como os endereços serão formatados em seu conjunto de dados. Escolha **Endereço com um único atributo** se os endereços em seus dados usarem um único campo. Escolha **Endereço com vários atributos** se os endereços em seus dados usarem mais de um campo de dados.

   > [!NOTE]
   > País/região é obrigatório em endereços de atributo único e de vários atributos. Endereços que não contiverem valores de país/região válidos ou com suporte não serão enriquecidos.

1.  Mapeie os campos de endereço da sua entidade de cliente unificada.

    :::image type="content" source="media/enhanced-address-mapping.png" alt-text="Página de mapeamento de campo de endereço aprimorado.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento para a entidade de saída.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

## <a name="enrichment-results"></a>Resultados de enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). A duração do processamento depende do tamanho dos dados do cliente.

Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.

Você pode ver um exemplo dos dados enriquecidos no bloco **Versão preliminar de clientes enriquecidos**. Selecione **Ver mais** e, depois, a guia **Dados** para acessar uma visão detalhada de cada perfil enriquecido.

### <a name="overview-card"></a>Cartão de visão geral

O cartão de visão geral mostra detalhes sobre a cobertura do enriquecimento. 

* **Endereços processados e alterados**: o número de perfis de clientes com endereços que foram enriquecidos com êxito.

* **Endereços processados e não alterados**: o número de perfis de clientes com endereços que foram reconhecidos, mas não foram alterados. Isso geralmente acontece quando os dados de entrada são válidos e não podem ser aprimorados pelo enriquecimento.

* **Endereços não processados e não alterados**: o número de perfis com endereços que não foram reconhecidos. Geralmente para dados de entrada que são inválidos ou não são compatíveis com o enriquecimento.

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](../includes/footer-banner.md)]
