---
title: Enriquecimento de aprimoramento de endereço
description: Enriqueça e normalize as informações de endereço de perfis de clientes com modelos da Microsoft.
ms.date: 04/21/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: e0ca731f944da9a7eaae7c2dc2d7568b6386089f
ms.sourcegitcommit: d84d664e67f263bfeb741154d309088c5101b9c3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/24/2021
ms.locfileid: "6305418"
---
# <a name="enrichment-of-customer-profiles-with-enhanced-addresses"></a>Enriquecimento de perfis de clientes com endereços aprimorados

Os endereços dos seus dados podem ser não estruturados, incompletos ou incorretos. Use os modelos da Microsoft para normalizar e enriquecer seus endereços no [formato de Common Data Model](/common-data-model/schema/core/applicationcommon/address) para ter melhor precisão e insights.

## <a name="how-we-enhance-addresses"></a>Como aprimoramos os endereços

Nosso modelo passa por um processo de duas etapas para aprimorar endereços. Primeiro, ele analisa o endereço para identificar seus componentes e os coloca em um formato estruturado. Em seguida, usamos a IA para corrigir, completar e padronizar os valores no endereço.

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

Os endereços avançados só funcionam com os valores que já existem nos dados de endereço processados. O que o modelo não faz: 

1. Verificar se o endereço é válido.
2. Verificar se algum dos valores, como CEPs ou nomes de ruas, é válido.
3. Alterar valores que não reconhece.

O modelo usa técnicas com base em aprendizado de máquina para aprimorar os endereços. Embora apliquemos um limite de alta confiança para quando o modelo altera um valor de entrada, como acontece com qualquer modelo baseado em aprendizado de máquina, a precisão de 100% não é garantida.

## <a name="supported-countries-or-regions"></a>Países ou regiões com suporte

Atualmente, damos suporte a endereços de enriquecimento nestes países ou regiões: 

- Austrália
- Canadá
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

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Crie [segmentos](segments.md) e [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para fornecer experiências personalizadas aos seus clientes.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
