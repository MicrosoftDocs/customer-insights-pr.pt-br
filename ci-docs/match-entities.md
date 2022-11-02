---
title: Condições de correspondência para a unificação de dados
description: Corresponda entidades para criar perfis de clientes unificados.
recommendations: false
ms.date: 10/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: bbd2c5f441b85460250c11f02358ea67260278d6
ms.sourcegitcommit: 52ea58c872b10f1e6f9d120be93df93cca1a12dd
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/26/2022
ms.locfileid: "9721507"
---
# <a name="match-conditions-for-data-unification"></a>Condições de correspondência para a unificação de dados

Esta etapa na unificação define a ordem de correspondência e as regras de correspondência entre entidades. Ela requer pelo menos duas entidades.

> [!NOTE]
> Depois de criar suas condições de correspondência e selecionar **Avançar**, você não pode remover uma entidade ou atributo selecionado. Se necessário, selecione **Voltar** para revisar as entidades e atributos selecionados antes de continuar.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="include-enriched-entities-preview"></a>Incluir entidades enriquecidas (versão preliminar)

Se você enriqueceu entidades no nível da fonte de dados para ajudar a melhorar seus resultados de unificação, selecione-as. Para obter mais informações, consulte [Enriquecimento de fontes de dados](data-sources-enrichment.md). Se você tiver selecionado entidades enriquecidas na página **Registros duplicados**, não será necessário selecioná-las novamente.

1. Na página **Condições correspondentes**, selecione **Usar entidades enriquecidas** na parte superior.

1. No painel **Usar entidades enriquecidas**, selecione uma ou mais entidades enriquecidas.

1. Selecione **Concluído**.

## <a name="specify-the-match-order"></a>Especifique a ordem de correspondência

Cada correspondência unifica duas ou mais entidades em uma única entidade consolidada. Ao mesmo tempo, ela mantém os registros exclusivos do cliente. A ordem de correspondência indica a ordem em que o sistema tenta corresponder os registros.

> [!IMPORTANT]
> A primeira entidade é chamada de entidade primária, que serve como base para seus perfis unificados. As entidades adicionais selecionadas serão adicionadas a essa entidade.
>
> Considerações importantes:
>
> - Escolha a entidade com os dados de perfil mais completos e confiáveis sobre seus clientes como a entidade principal.
> - Escolha a entidade que tem vários atributos em comum com outras entidades (por exemplo, nome, número de telefone ou endereço de email) como a entidade principal.

1. Na página **Condições correspondentes**, use as setas para cima e para baixo para mover as entidades na ordem desejada ou arraste e solte-as. Por exemplo, selecione **eCommerceCustomers** como a entidade principal e **loyCustomers** como a segunda entidade.

1. Para ter todos os registros na entidade como um cliente exclusivo independentemente de uma correspondência ser encontrada ou não, selecione **Incluir todos os registros**. Quaisquer registros nessa entidade que não corresponderem a registros em outra entidade serão incluídos no perfil unificado. Os registros que não têm correspondência são chamados de singletons.
  
A entidade principal *Contacts:eCommerce* corresponde à próxima entidade *CustomerLoyalty:Loyalty*. O conjunto de dados que resulta da primeira etapa de correspondência é combinado com a entidade a seguir, se você tiver mais de duas entidades.

:::image type="content" source="media/m3_match.png" alt-text="Captura de tela da ordem de correspondência selecionada para as entidades." lightbox="media/m3_match.png":::

## <a name="define-rules-for-match-pairs"></a>Definir regras para pares de correspondência

As regras de correspondência especificam a lógica pela qual um par específico de entidades será correspondido. Uma regra consiste em uma ou mais condições.

O aviso ao lado de um nome de entidade significa que nenhuma regra de correspondência está definida para um par de correspondência.

1. Selecione **Adicionar regra** para um par de entidades a fim de definir regras de correspondência.

1. No painel **Adicionar regra**, configure as condições para a regra.

   :::image type="content" source="media/m3_add_rule.png" alt-text="Captura de tela do painel Adicionar regra.":::

   - **Selecionar Entidade/Campo (primeira linha)**: escolha uma entidade e um atributo que provavelmente é exclusivo de um cliente. Por exemplo, um número de telefone ou endereço de email. Evite a correspondência por atributos de tipo de atividade. Por exemplo, um ID de compra provavelmente não encontrará correspondência em outros tipos de registro.

   - **Selecionar Entidade/Campo (segunda linha)**: escolha um atributo relacionado ao atributo da entidade especificada na primeira linha.

   - **Normalizar**: selecione uma das opções de normalização a seguir para os atributos selecionados.
     - **Numerais**: converte outros sistemas de numeração, como numerais romanos, em numerais arábicos. *VIII* torna-se *8*.
     - **Símbolos**: remove todos os símbolos e caracteres especiais. *Head&Shoulder* torna-se *HeadShoulder*.
     - **Texto em minúsculas**: converte todos os caracteres em minúsculas. *TODAS EM MAIÚSCULAS e Capitalização de Título* torna-se *todas em maiúsculas e capitalização de título*.
     - **Tipo (telefone, nome, endereço, organização)**: padroniza nomes, títulos, números de telefone, endereços e organizações.
     - **Unicode em ASCII**: converte a notação Unicode em caracteres ASCII. */u00B2* torna-se *2*.
     - **Espaço em branco**: remove todos os espaços. *Hello   World* torna-se *Olá, Mundo*.

   - **Precisão**: defina o nível de precisão a ser aplicado a esta condição.
     - **Básico**: escolha entre *Baixo (30%)*, *Médio (60%)*, *Alto (80%)* e *Exato (100%)*. Selecione **Exato** para corresponder apenas os registros com 100% de correspondência.
     - **Personalizado**: defina uma porcentagem de correspondência para os registros. O sistema só fará a corresponderá dos registros que ultrapassarem esse limite.

   - **Nome**: nome da regra.

1. Para corresponder entidades somente se os atributos atenderem a várias condições, selecione **Adicionar** > **Adicionar condição** para adicionar mais condições a uma regra de correspondência. As condições são conectadas a um operador lógico AND e, portanto, somente serão executadas se todas as condições forem atendidas.

1. Opcionalmente, considere opções avançadas, como [exceções](#add-exceptions-to-a-rule) ou [condições de correspondência personalizadas](#specify-custom-match-conditions).

1. Selecione **Concluído** para finalizar a regra.

1. Opcionalmente, [adicione mais regras](#add-rules-to-a-match-pair).

1. Clique em **Avançar**.

> [!div class="nextstepaction"]
> [Próxima etapa: Unificar campos](merge-entities.md)

### <a name="add-rules-to-a-match-pair"></a>Adicionar regras a um par de correspondência

As regras de correspondência representam conjuntos de condições. Para fazer a correspondência das entidades com base em vários atributos, adicione mais regras.

1. Selecione **Adicionar regra** na entidade à qual você deseja adicionar regras.

1. Siga as etapas em [Definir regras para pares de correspondência](#define-rules-for-match-pairs).

> [!NOTE]
> A ordem das regras é importante. O algoritmo de correspondência tentará fazer a correspondência de um determinado registro do cliente com base na primeira regra e avançará para a segunda regra somente se nenhuma correspondência for identificada com a primeira.

## <a name="advanced-options"></a>Opções avançadas

### <a name="add-exceptions-to-a-rule"></a>Adicionar exceções a uma regra

Na maioria dos casos, a correspondência de entidades resulta em perfis de cliente exclusivos com dados consolidados. Para gerenciar casos raros de falsos positivos e falsos negativos, defina exceções para uma regra de correspondência. As exceções são aplicadas após o processamento das regras de correspondência e evitam a correspondência de todos os registros que atendem aos critérios de exceção.

Por exemplo, se sua regra de correspondência combinar sobrenome, cidade e data de nascimento, o sistema identificará gêmeos com o mesmo sobrenome que moram na mesma cidade com o mesmo perfil. Você poderá especificar uma exceção que não corresponda aos perfis se o nome nas entidades combinadas não for o mesmo.

1. No painel **Editar regra**, selecione **Adicionar** > **Adicionar exceção**.

1. Especifique os critérios de exceção.

1. Selecione **Concluído** para salvar a regra.

### <a name="specify-custom-match-conditions"></a>Especificar condições de correspondência personalizadas

Especifique as condições que substituem a lógica de correspondência padrão. Há quatro opções disponíveis:

|Opção  |Description |Exemplo  |
|---------|---------|---------|
|Sempre corresponder     | Define valores para as chaves primárias que sempre são correspondidas.         |  Sempre corresponda a linha com a chave primária *12345* à linha com a chave primária *54321*.       |
|Nunca corresponder     | Define valores para as chaves primárias que nunca correspondem.        | Nunca corresponda a linha com a chave primária *12345* com a linha com a chave primária *54321*.        |
|Bypass            | Define valores que o sistema deve sempre ignorar na fase de correspondência. |  Ignorar os valores *11111* e *Desconhecido* durante a correspondência.        |
|Mapeamento de alias    | Definição de valores que o sistema deve considerar como o mesmo valor.         | Considerar *Joe* igual a *Joseph*.        |

1. Selecione **Personalizado**.

   :::image type="content" source="media/m3_match_custom.png" alt-text="Botão Personalizado":::

1. Escolha o **Tipo personalizado** e selecione **Baixar modelo**. Renomeie o modelo sem usar espaços. Use um modelo separado para cada opção de correspondência.

1. Abra o arquivo de modelo baixado e preencha os detalhes. O modelo contém campos para especificar os valores da chave primária e da entidade a serem usados na correspondência personalizada. Os nomes das entidades diferenciam maiúsculas de minúsculas. Por exemplo, se você quiser que a chave primária *12345* da entidade *Vendas* sempre corresponda à chave primária *34567* da entidade *Contato*, preencha no modelo:
   - Entity1: Sales
   - Entity1Key: 12345
   - Entity2: Contact
   - Entity2Key: 34567

   O mesmo arquivo de modelo pode especificar registros de correspondência personalizados de várias entidades.

   > [!NOTE]
   > Se você deseja especificar a correspondência personalizada para eliminação de duplicação em uma entidade, forneça a mesma entidade como Entidade1 e Entidade2 e defina os diferentes valores de chave primária. Você deve definir pelo menos uma regra de desduplicação para a entidade usar a correspondência personalizada.

1. Depois de adicionar todas as substituições, salve o arquivo de modelo.

1. Vá para **Dados** > **Fontes de dados** e ingira os arquivos de modelo como novas entidades.

1. Após carregar os arquivos, selecione a opção **Personalizado** novamente. Selecione as entidades necessárias no menu suspenso e selecione **Concluído**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de tela da caixa de diálogo para escolher substituições para um cenário de correspondência personalizado.":::

1. A aplicação da correspondência personalizada depende da opção de correspondência que você deseja usar.

   - Para **Sempre corresponder** ou **Nunca corresponder**, prossiga para a próxima etapa.
   - Para **Bypass** ou **Mapeamento de alias**, selecione **Editar** em uma regra de correspondência existente ou crie uma. Na lista suspensa Normalizações, escolha a opção **Bypass personalizado** ou **Mapeamento de alias** e selecione **Concluído**.

1. Selecione **Concluído** no painel **Personalizado** para aplicar a configuração de correspondência personalizada.

   Cada arquivo de modelo ingerido é sua própria fonte de dados. Se forem descobertos registros que precisam de tratamento de correspondência especial, atualize a fonte de dados apropriada. A atualização será usada durante o próximo processo de unificação. Por exemplo, você identifica gêmeos com quase o mesmo nome que vivem no mesmo endereço que foi mesclado como uma pessoa. Atualize a fonte de dados para identificar os gêmeos como registros separados e exclusivos.

> [!div class="nextstepaction"]
> [Próxima etapa: Unificar campos](merge-entities.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
