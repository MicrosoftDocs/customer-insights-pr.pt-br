---
title: Remover duplicidades antes de unificar os dados
description: A segunda etapa no processo de unificação é selecionar qual registro manter quando duplicidades forem encontradas.
recommendations: false
ms.date: 08/01/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: sstabbert
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 3f84c1c149f0befcbe489ccdd8a666ce6d5d798a
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304459"
---
# <a name="remove-duplicates-before-unifying-data"></a>Remover duplicidades antes de unificar os dados

Esta etapa opcional na unificação permite que você configure regras para eliminar registros duplicados **dentro** de uma entidade. A eliminação de duplicação identifica vários registros para um cliente e seleciona o melhor registro a ser mantido (com base nas preferências básicas de mesclagem) ou mescla os registros em um (com base nas preferências avançadas de mesclagem). Os registros de origem são vinculados ao registro mesclado com IDs alternativas. Se as regras não forem configuradas, as regras definidas pelo sistema serão aplicadas.

## <a name="default-deduplication"></a>Eliminação de duplicação padrão

As regras definidas pelo sistema serão aplicadas se nenhuma regra de eliminação de duplicação for adicionada.

- A eliminação de duplicação da chave primária é feita.
  Para quaisquer registros com a mesma chave primária, o registro **Mais preenchido** (aquele com o menor número de valores nulos) é o vencedor.
- Quaisquer regras de correspondência entre entidades serão aplicadas à entidade.
  Por exemplo: na etapa de correspondência, se a entidade A for comparada com a entidade B em *FullName* e *DateofBirth*, a eliminação de duplicação por *FullName* e *DateofBirth* da entidade A também é feita. Como *FullName* e *DateofBirth* são chaves válidas para identificar um cliente na entidade A, essas chaves também são válidas para identificar clientes duplicados na entidade A.

## <a name="include-enriched-entities-preview"></a>Incluir entidades enriquecidas (versão preliminar)

Se você enriqueceu entidades no nível da fonte de dados para ajudar a melhorar seus resultados de unificação, selecione-as. Para obter mais informações, consulte [Enriquecimento de fontes de dados](data-sources-enrichment.md).

1. Na página **Registros duplicados**, selecione **Usar entidades enriquecidas** na parte superior.

1. No painel **Usar entidades enriquecidas**, selecione uma ou mais entidades enriquecidas.

1. Selecione **Concluído**.

## <a name="define-deduplication-rules"></a>Definir regras de eliminação de duplicação

1. Na página **Registros duplicados**, selecione uma entidade e, em seguida, selecione **Adicionar regra** para definir as regras de eliminação de duplicação.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Captura de tela da página de registros duplicados com entidade realçada e Adicionar regra exibida"  lightbox="media/m3_duplicates_showmore.png":::

   1. No painel **Adicionar regra**, insira as seguintes informações:
      - **Selecionar campo**: escolha na lista de campos disponíveis da entidade na qual você deseja verificar se há duplicidades. Escolha campos que provavelmente são exclusivos para cada cliente. Por exemplo, um endereço de email ou a combinação de nome, cidade e número de telefone.
      - **Normalizar**: selecione uma das opções de normalização a seguir para os atributos selecionados.
        - **Numerais**: converte outros sistemas de numeração, como numerais romanos, em numerais arábicos. *VIII* torna-se *8*.
        - **Símbolos**: remove todos os símbolos e caracteres especiais. *Head&Shoulder* torna-se *HeadShoulder*.
        - **Texto em minúsculas: converte todos os caracteres em minúsculas**. *TODAS EM MAIÚSCULAS e Capitalização de Título* torna-se *todas em maiúsculas e capitalização de título*.
        - **Tipo (telefone, nome, endereço, organização)**: padroniza nomes, títulos, números de telefone, endereços etc.
        - **Unicode em ASCII**: converte a notação Unicode em caracteres ASCII. */u00B2* torna-se *2*.
        - **Espaço em branco**: remove todos os espaços. *Hello   World* torna-se *Olá, Mundo*.
      - **Precisão**: defina o nível de precisão a ser aplicado a esta condição.
        - **Básico**: escolha entre *Baixo (30%)*, *Médio (60%)*, *Alto (80%)* e *Exato (100%)*. Selecione **Exato** para corresponder apenas os registros com 100% de correspondência.
        - **Personalizado**: defina uma porcentagem de correspondência para os registros. O sistema só fará a corresponderá dos registros que ultrapassarem esse limite.
      - **Nome**: nome da regra.

      :::image type="content" source="media/m3_duplicates_add.png" alt-text="Captura de tela do painel Adicionar regra para remover duplicidades.":::

   1. Opcionalmente, selecione **Adicionar** > **Adicionar condição** para adicionar mais condições à regra. As condições são conectadas a um operador lógico AND e, portanto, somente serão executadas se todas as condições forem atendidas.

   1. Opcionalmente, selecione **Adicionar** > **Adicionar exceção** para [adicionar exceções à regra](match-entities.md#add-exceptions-to-a-rule). As exceções são usadas para lidar com casos raros de falsos positivos e falsos negativos.

   1. Selecione **Concluído** para criar a regra.

1. Opcionalmente, [adicione mais regras](#define-deduplication-rules).

1. Selecione uma entidade e, em seguida, **Editar preferências de mesclagem**.

1. No painel **Preferências de mesclagem**:
   1. Escolha uma das três opções para determinar qual registro manter se uma duplicidade for encontrada:
      - **Mais preenchido**: identifica o registro com mais campos de atributos preenchidos como o registro vencedor. É a opção de mesclagem padrão.
      - **Mais recente**: identifica o registro vencedor com base na maior recência. Requer uma data ou um campo numérico para definir o nível de atualização.
      - **Menos recente**: identifica o registro vencedor com base na menor recência. Requer uma data ou um campo numérico para definir o nível de atualização.

      Em caso de empate, o registro vencedor é aquele com o MAX(PK) ou o maior valor de chave primária.

   1. Opcionalmente, para definir preferências de mesclagem em atributos individuais de uma entidade, selecione **Avançado** na parte inferior do painel. Por exemplo, você pode manter o email mais recente E o endereço mais completo de diferentes registros. Expanda a entidade para ver todos os seus atributos e defina qual opção usar para atributos individuais. Se você escolher uma opção baseada em recência, também precisará especificar um campo de data/hora que defina a recência.

      :::image type="content" source="media/m3_adv_merge.png" alt-text="Painel Preferências de mesclagem avançada mostrando email recente e endereço completo":::

   1. Selecione **Concluído** para aplicar suas preferências de mesclagem.

1. Depois de definir as regras de eliminação de duplicação e as preferências de mesclagem, selecione **Avançar**.
  
> [!div class="nextstepaction"]
> [Próxima etapa para uma única entidade: Unificar campos](merge-entities.md)

> [!div class="nextstepaction"]
> [Próxima etapa para várias entidades: Condições correspondentes](match-entities.md)

[!INCLUDE[footer-include](includes/footer-banner.md)]
