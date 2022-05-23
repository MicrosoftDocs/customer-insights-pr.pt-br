---
title: Remover duplicidades antes de unificar os dados
description: A segunda etapa no processo de unificação é selecionar qual registro manter quando duplicidades forem encontradas.
recommendations: false
ms.date: 04/22/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: 27dff3551ab411a12c273536d7431d651c48573e
ms.sourcegitcommit: 6a5f4312a2bb808c40830863f26620daf65b921d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2022
ms.locfileid: "8741605"
---
# <a name="remove-duplicates-before-unifying-data"></a>Remover duplicidades antes de unificar os dados

[!INCLUDE [m3-prod-trial-note](includes/m3-prod-trial-note.md)]

Esta etapa na unificação permite, opcionalmente, configurar regras para lidar com registros duplicados em uma entidade. *Eliminação de duplicação* identifica registros duplicados e os mescla em um registro. Os registros de origem são vinculados ao registro mesclado com IDs alternativas. Se as regras não forem configuradas, as regras definidas pelo sistema serão aplicadas.

## <a name="include-enriched-entities-preview"></a>Incluir entidades enriquecidas (versão preliminar)

Se você enriqueceu entidades no nível da fonte de dados para ajudar a melhorar seus resultados de unificação, selecione-as. Para obter mais informações, consulte [Enriquecimento de fontes de dados](data-sources-enrichment.md).

1. Na página **Registros duplicados**, selecione **Usar entidades enriquecidas** na parte superior.

1. No painel **Usar entidades enriquecidas**, selecione uma ou mais entidades enriquecidas.

1. Selecione **Concluído**.

## <a name="define-deduplication-rules"></a>Definir regras de eliminação de duplicação

1. Na página **Registros duplicados**, selecione uma entidade e, em seguida, selecione **Adicionar regra** para definir as regras de eliminação de duplicação.

   :::image type="content" source="media/m3_duplicates_showmore.png" alt-text="Captura de tela da página Registros duplicados com Mostrar mais realçado":::

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

## <a name="deduplication-output-as-an-entity"></a>Saída de eliminação de duplicação como uma entidade

O processo de eliminação de duplicação cria uma nova entidade sem duplicação para cada uma das entidades de origem. Essas entidades podem ser encontradas juntamente com **ConflationMatchPairs:CustomerInsights** na seção **Sistema** na página **Entidades**, com o nome **Deduplication_DataSource_Entity**.

Uma entidade de saída de eliminação de duplicação contém as seguintes informações:

- IDs/chaves
  - Campos Chave primária e ID Alternativa. O campo ID Alternativa consiste em todas as IDs alternativas identificadas para um registro.
  - O campo Deduplication_GroupId mostra o grupo ou cluster identificado em uma entidade que agrupa todos os registros semelhantes com base nos campos de eliminação de duplicação especificados. Ele é usado para fins de processamento do sistema. Se não houver regras de eliminação de duplicação manual especificadas e as regras de eliminação de duplicação definidas pelo sistema se aplicarem, talvez você não encontre esse campo na entidade de saída de eliminação de duplicação.
  - Deduplication_WinnerId: este campo contém a ID do vencedor dos grupos ou clusters identificados. Se a Deduplication_WinnerId for igual ao valor da chave primária para um registro, isso significa que o registro é o registro vencedor.
- Campos usados para definir as regras de eliminação de duplicação.
- Campos de regra e pontuação para denotar quais das regras de eliminação de duplicação foram aplicadas e a pontuação retornada pelo algoritmo de correspondência.

[!INCLUDE[footer-include](includes/footer-banner.md)]
