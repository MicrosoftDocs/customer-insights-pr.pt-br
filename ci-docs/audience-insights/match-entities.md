---
title: Corresponder entidades para unificação de dados
description: Corresponda entidades para criar perfis de clientes unificados.
ms.date: 02/07/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
searchScope:
- ci-match
- ci-merge
- ci-map
- customerInsights
ms.openlocfilehash: ab4ab0dba1bd91b1893cd4b16b8d51381d5b6ef8
ms.sourcegitcommit: 50d32a4cab01421a5c3689af789e20857ab009c4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/03/2022
ms.locfileid: "8376908"
---
# <a name="match-entities"></a>Corresponder entidades

A fase de correspondência especifica como combinar seus conjuntos de dados em um conjunto de dados de perfil de cliente unificado. Depois de concluir a [etapa de mapeamento](map-entities.md) no processo de unificação de dados, você estará pronto para fazer a correspondência de suas entidades. A fase de correspondência requer pelo menos duas entidades mapeadas.

A página de correspondência tem três seções: 
- Principais métricas que resumem o número de registros correspondentes
- Ordem de correspondência e regras para a correspondência entre entidades
- Regras para eliminação de duplicação de entidades correspondentes

## <a name="specify-the-match-order"></a>Especifique a ordem de correspondência

Cada correspondência unifica duas ou mais entidades em uma única entidade consolidada. Ao mesmo tempo, ela mantém os registros exclusivos do cliente. A ordem de correspondência indica a ordem em que o sistema tenta corresponder os registros.

> [!IMPORTANT]
> A entidade que você escolhe como sua entidade principal servirá como base para o conjunto de dados de perfis unificado. Entidades adicionais selecionadas durante a fase de correspondência serão adicionadas a essa entidade. Isso não significa que a entidade unificada incluirá *todos* os dados incluídos nesta entidade.
>
> Há duas considerações que podem ajudá-lo a escolher a hierarquia de suas entidades:
>
> - Escolha a entidade com os dados de perfil mais completos e confiáveis sobre seus clientes como entidade principal.
> - Escolha a entidade que tem vários atributos em comum com outras entidades (por exemplo, nome, número de telefone ou endereço de email) como entidade principal.

1. Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Definir ordem** para iniciar a fase de correspondência.
1. Selecione **Ordem da entidade**. Por exemplo, selecione **eCommerce:eCommerceContacts** como a entidade principal e **LoyaltyScheme:loyCustomers** como segunda entidade. 
1. Para definir todos os registros na entidade como um cliente exclusivo e correspondido a cada entidade a seguir, selecione **Incluir tudo**.
1. Selecione **Concluído**. 

Depois de especificar a ordem de correspondência, os pares de correspondência definidos são exibidos na seção **Detalhes dos registros correspondentes** em **Dados** > **Unificar** > **Corresponder**. As principais métricas ficam vazias até que o processo de correspondência seja concluído.

:::image type="content" source="media/match-page.png" alt-text="Captura de tela da página Corresponder na área Unificar do processo de unificação de dados.":::
  
A correspondência da entidade principal *eCommerce:eCommerceContacts* é feita com a próxima entidade *LoyaltyScheme:loyCustomers*. O conjunto de dados que resulta da primeira etapa de correspondência é combinado com a entidade a seguir, se você tiver mais de duas entidades.

## <a name="define-rules-for-match-pairs"></a>Definir regras para pares de correspondência

As regras de correspondência especificam a lógica pela qual um par específico de entidades será correspondido.

O aviso **Precisa de regras** próximo ao nome de uma entidade sugere que nenhuma regra de correspondência foi definida para um par de correspondência. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de tela da seção Detalhes dos registros correspondentes com o controle para adicionar regras destacado.":::

1. Selecione **Adicionar regra** abaixo de uma entidade na seção **Detalhes dos registros correspondentes** para definir as regras de correspondência.

1. No painel **Criar regra**, configure as condições para a regra.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de tela de uma regra de correspondência aberta com condições adicionadas.":::

   - **Entidade/Campo (primeira linha)**: escolha uma entidade relacionada e um atributo para especificar uma propriedade de registro que provavelmente seja exclusiva de um cliente. Por exemplo, um número de telefone ou endereço de email. Evite a correspondência por atributos de tipo de atividade. Por exemplo, um ID de compra provavelmente não encontrará correspondência em outros tipos de registro.

   - **Entidade/Campo (segunda linha)**: escolha um atributo relacionado ao atributo da entidade especificada na primeira linha.

   - **Normalizar**: selecione uma das opções de normalização a seguir para os atributos selecionados. 
     - Numerais: converte outros sistemas de numeração, como numerais romanos, em numerais arábicos. *VIII* torna-se *8*.
     - Símbolos: remove todos os símbolos e caracteres especiais. *Head&Shoulder* torna-se *HeadShoulder*.
     - Texto em minúsculas: converte todos os caracteres em minúsculas. *TODAS EM MAIÚSCULAS e Capitalização de Título* torna-se *todas em maiúsculas e capitalização de título*.
     - Tipo (telefone, nome, endereço, organização): padroniza nomes, títulos, números de telefone, endereços etc. 
     - Unicode para ASCII: converte a notação Unicode em caracteres ASCII. */u00B2* torna-se *2*.
     - Espaço em branco: remove todos os espaços. *Hello   World* torna-se *Olá, Mundo*.

   - **Precisão**: defina o nível de precisão a ser aplicado a esta condição. 
     - **Básico**: escolha entre *Baixo*, *Médio*, *Alto* e *Exato*. Selecione **Exato** para corresponder apenas os registros com 100% de correspondência. Selecione um dos outros níveis para corresponder aos registros que não são 100% idênticos.
     - **Personalizado**: defina uma porcentagem de correspondência para os registros. O sistema só fará a corresponderá dos registros que ultrapassarem esse limite.

1. Forneça um **Nome** para a regra.

1. [Adicione mais condições](#add-conditions-to-a-rule) ou selecione **Concluído** para finalizar a regra.

1. Opcionalmente, [adicione mais regras](#add-rules-to-a-match-pair).

1. Selecione **Salvar** para aplicar suas alterações.

### <a name="add-conditions-to-a-rule"></a>Adicionar condições a uma regra

Para fazer a correspondência das entidades somente se os atributos atenderem a várias condições, adicione mais condições a uma regra de correspondência. As condições são conectadas a um operador lógico AND e, portanto, somente serão executadas se todas as condições forem atendidas.

1. Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Editar** na regra à qual você deseja adicionar condições.

1. No painel **Editar regra**, selecione **Adicionar condição**.

1. Selecione **Concluído** para salvar a regra.

### <a name="add-rules-to-a-match-pair"></a>Adicionar regras a um par de correspondência

As regras de correspondência representam conjuntos de condições. Para fazer a correspondência das entidades com base em vários atributos, adicione mais regras.

1.  Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Adicionar regra** na entidade à qual você deseja adicionar regras.

2. Siga as etapas em [Definir regras para pares de correspondência](#define-rules-for-match-pairs).

> [!NOTE]
> A ordem das regras é importante. O algoritmo de correspondência tenta fazer a correspondência com base em sua primeira regra e continua para a segunda regra somente se nenhuma correspondência for identificada com a primeira regra.

### <a name="change-the-entity-order-in-match-rules"></a>Alterar a ordem da entidade nas regras de correspondência

Você pode reordenar as entidades de acordo com regras de correspondência para alterar a ordem em que elas são processadas. As regras que estiverem em conflito devido a um pedido alterado serão removidas. Você deve recriar as regras removidas com uma configuração atualizada.

1. Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Editar**.

1. No painel **Editar regra**, selecione o controle **Mover para cima/para baixo** ou arraste e solte as entidades para alterar a ordem.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opções para modificar a ordem em que as entidades são processadas na fase de correspondência.":::

1. Selecione **Concluído** para salvar a regra.

## <a name="define-deduplication-on-a-match-entity"></a>Definir a eliminação de duplicação em uma entidade correspondente

Além de [regras para a correspondência entre entidades](#define-rules-for-match-pairs), você também pode especificar regras de eliminação de duplicação. *Eliminação de duplicação* é outro processo durante a correspondência de registros. Ela identifica registros duplicados e os mescla em um registro. Os registros de origem são vinculados ao registro mesclado com IDs alternativas.

Os registros com duplicação eliminada são usados no processo de correspondência entre entidades. A eliminação de duplicação ocorre em entidades individuais e pode ser configurada para cada entidade usada em pares correspondentes.

A especificação de regras de eliminação de duplicação não é obrigatória. Se essas regras não estiverem configuradas, as regras definidas pelo sistema serão aplicadas. Elas combinam todos os registros em um único registro antes de passar os dados da entidade para a correspondência entre entidades para o aprimoramento do desempenho.

### <a name="add-deduplication-rules"></a>Adicionar regras de eliminação de duplicação

1. Acesse **Dados** > **Unificar** > **Corresponder**.

1. Na seção **Detalhes dos registros com duplicação eliminada**, selecione **Definir entidades**. Caso as regras de eliminação de duplicação já tenham sido criadas, selecione **Editar**.

1. No painel **Mesclar preferências**, escolha as entidades às quais deseja aplicar a eliminação de duplicação.

   1. Especifique como combinar os registros duplicados e escolha uma das três opções:
      - **Mais preenchido**: identifica o registro com mais campos de atributos preenchidos como o registro vencedor. É a opção de mesclagem padrão.
      - **Mais recente**: identifica o registro vencedor com base na maior recência. Requer uma data ou um campo numérico para definir o nível de atualização.
      - **Menos recente**: identifica o registro vencedor com base na menor recência. Requer uma data ou um campo numérico para definir o nível de atualização.

   1. Você também pode selecionar **Avançado** para definir regras de eliminação de duplicação em atributos individuais de uma entidade. Por exemplo, você pode manter o email mais recente E o endereço mais completo de diferentes registros. Expanda a entidade para ver todos os seus atributos e defina qual opção usar para atributos individuais. Se você escolher uma opção baseada em recência, também precisará especificar um campo de data/hora que defina a recência. 
 
      > [!div class="mx-imgBorder"]
      > ![Etapa 1 das regras de eliminação de duplicação.](media/match-selfconflation.png "Etapa 1 das regras de eliminação de duplicação")

   1. Selecione **Concluído** e aplique suas preferências de mesclagem para a eliminação de duplicação.
 
1. Depois que as entidades forem selecionadas e a preferência de mesclagem for definida, selecione **Adicionar regra** para definir as regras de eliminação de duplicação no nível da entidade.
   - **Selecionar campo** lista todos os campos disponíveis dessa entidade. Escolha o campo em que deseja verificar se há duplicidades. Escolha campos que provavelmente são exclusivos para cada cliente. Por exemplo, um endereço de email ou a combinação de nome, cidade e número de telefone.
   - Especifique as configurações de normalização e precisão.
   - Defina mais condições adicionais selecionando **Adicionar condição**.
 
   > [!div class="mx-imgBorder"]
   > ![Etapa 2 das regras de eliminação de duplicação.](media/match-selfconflation-rules.png "Etapa 2 das regras de eliminação de duplicação")

  É possível criar várias regras de eliminação de duplicação para uma entidade. 

1. A execução do processo de correspondência agora agrupa os registros com base nas condições definidas nas regras de eliminação de duplicação. Após o agrupamento dos registros, a política de mesclagem é aplicada para identificar o registro vencedor.

1. Esse registro vencedor é então transmitido para a correspondência entre entidades, juntamente com os registros não vencedores (por exemplo, IDs alternativas) para melhorar a qualidade da correspondência.

1. Quaisquer regras de correspondência personalizadas definidas substituem as regras de eliminação de duplicação. Se uma regra de eliminação de duplicação identificar registros correspondentes e uma regra de correspondência personalizada for definida para nunca corresponder esses registros, esses dois registros não serão correspondidos.

1. Depois de [executar o processo de correspondência](#run-the-match-process), você verá as estatísticas de eliminação de duplicação nos blocos de métricas principais.

### <a name="deduplication-output-as-an-entity"></a>Saída de eliminação de duplicação como uma entidade

O processo de eliminação de duplicação cria uma entidade para cada entidade dos pares de correspondência para identificar os registros com eliminação de duplicação. Essas entidades podem ser encontradas juntamente com **ConflationMatchPairs:CustomerInsights** na seção **Sistema** na página **Entidades**, com o nome **Deduplication_DataSource_Entity**.

Uma entidade de saída de eliminação de duplicação contém as seguintes informações:
- IDs/chaves
  - Campo de chave primária e seu campo de IDs alternativas. O campo de IDs alternativas consiste em todas as IDs alternativas identificadas para um registro.
  - O campo Deduplication_GroupId mostra o grupo ou cluster identificado em uma entidade que agrupa todos os registros semelhantes com base nos campos de eliminação de duplicação especificados. Ele é usado para fins de processamento do sistema. Se não houver regras de eliminação de duplicação manual especificadas e as regras de eliminação de duplicação definidas pelo sistema se aplicarem, talvez você não encontre esse campo na entidade de saída de eliminação de duplicação.
  - Deduplication_WinnerId: este campo contém a ID do vencedor dos grupos ou clusters identificados. Se a Deduplication_WinnerId for igual ao valor da chave primária para um registro, isso significa que o registro é o registro vencedor.
- Campos usados para definir as regras de eliminação de duplicação.
- Campos de regra e pontuação para denotar quais das regras de eliminação de duplicação foram aplicadas e a pontuação retornada pelo algoritmo de correspondência.
 
## <a name="include-enriched-entities-preview"></a>Incluir entidades enriquecidas (versão preliminar)

Se você enriqueceu entidades no nível fonte de dados, selecione-as antes de executar o processo de correspondência. As entidades enriquecidas podem melhorar seus resultados de unificação. Para obter mais informações, consulte [Enriquecimento de fontes de dados](data-sources-enrichment.md). 

A entidade enriquecida contém os campos de fonte de dados originais e os campos enriquecidos. Portanto, se você optar por trabalhar com a entidade enriquecida, a configuração existente não será afetada. No entanto, talvez seja necessário atualizar as regras de correspondência para usar os campos enriquecidos.

1. Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Usar entidades enriquecidas** no topo da página.

1. No painel **Usar entidades enriquecidas**, selecione uma ou mais entidades enriquecidas.

1. Selecione **Concluído**. Independentemente do local em que a entidade de origem é usada (como ordem de correspondência ou regras), ela é alterada automaticamente para a entidade enriquecida.
  
## <a name="run-the-match-process"></a>Executar o processo de correspondência

Com as regras de correspondência definidas, incluindo as regras de correspondência entre entidades e de eliminação de duplicação, você poderá executar o processo de correspondência. 

Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Executar** para iniciar o processo. O algoritmo de correspondência levará algum tempo para ser concluir o processo e você não poderá alterar a configuração até que ele seja concluído. Para fazer alterações, você pode cancelar a execução. Selecione o status do trabalho e selecione **Cancelar trabalho** no painel **Detalhes do progresso**.

Você encontrará o resultado de uma execução com êxito, a entidade unificada do perfil do cliente, na página **Entidades**. Sua entidade de cliente unificada é chamada **Clientes** na seção **Perfis**. A primeira execução de correspondência com êxito cria a entidade unificada *Cliente*. Todas as execuções de correspondência subsequentes expandem essa entidade.

[!INCLUDE [progress-details-include](../includes/progress-details-pane.md)]

## <a name="review-and-validate-your-matches"></a>Revise e valide suas correspondências

Acesse **Dados** > **Unificar** > **Corresponder** para avaliar a qualidade de seus pares de correspondência e refiná-los, se necessário.

Os blocos no topo da página mostram as métricas principais, resumindo o número de registros correspondentes e duplicados.

:::image type="content" source="media/match-KPIs.png" alt-text="Captura de tela recortada das métricas principais na página Corresponder com números e detalhes.":::

- **Registros de origem exclusivos** mostra o número de registros de origem individuais que foram processados na última execução de correspondências.
- **Registros com e sem correspondências** destaca quantos registros únicos permanecem após o processamento das regras de correspondência.
- **Somente registros com correspondência** mostra o número de correspondências em todos os seus pares de correspondência.

Você pode avaliar os resultados de cada par de correspondência e suas regras na tabela **Detalhes dos registros correspondentes**. Compare o número de registros que vieram de um par de correspondência com a porcentagem de registros correspondidos com êxito.

Revise as regras de um par de correspondência para ver a porcentagem de registros correspondidos com êxito no nível da regra. Selecione as reticências (...) e selecione **Visualização da correspondência** para exibir todos esses registros no nível da regra. Recomendamos que você examine alguns registros para verificar se a correspondência deles foi feita corretamente.

Experimente diferentes limites de precisão nas condições para encontrar o valor ideal.

  1. Selecione as reticências (...) para a regra que deseja experimentar e selecione **Editar**.

  2. Altere os valores de precisão nas condições que deseja revisar.

  3. Selecione **Visualizar** para exibir o número de registros com e sem correspondências para a condição selecionada.

## <a name="manage-match-rules"></a>Gerenciar regras de correspondência

Você pode reconfigurar e ajustar a maioria dos parâmetros de correspondência.

:::image type="content" source="media/match-rules-management.png" alt-text="Captura de tela do menu suspenso com as opções de regra de correspondência.":::

- **Altere a ordem das suas regras** se você definiu várias regras. Você pode reordenar as regras de correspondência selecionando as opções **Mover para Cima** e **Mover para Baixo** ou arrastando e soltando.

- **Altere as condições da regra** selecionando **Editar** e escolha campos diferentes.

- **Desative uma regra** para reter uma regra de correspondência enquanto a exclui do processo de correspondência.

- **Duplique suas regras** se você definiu uma regra de correspondência e deseja criar uma regra semelhante com modificações, selecione **Duplicar**.

- **Exclua uma regra** selecionando o símbolo **Excluir**.

## <a name="advanced-options"></a>Opções avançadas

### <a name="add-exceptions-to-a-rule"></a>Adicionar exceções a uma regra

Na maioria dos casos, a correspondência de entidades direciona a perfis de usuários únicos com dados consolidados. Para gerenciar dinamicamente casos raros de falsos positivos e falsos negativos, você pode definir exceções para uma regra de correspondência. As exceções são aplicadas após o processamento das regras de correspondência e evitam a correspondência de todos os registros que atendem aos critérios de exceção.

Por exemplo, se sua regra de correspondência combinar sobrenome, cidade e data de nascimento, o sistema identificará gêmeos com o mesmo sobrenome que moram na mesma cidade com o mesmo perfil. Você poderá especificar uma exceção que não corresponda aos perfis se o nome nas entidades combinadas não for o mesmo.

1. Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Editar** na regra à qual você deseja adicionar condições.

1. No painel **Editar regra**, selecione **Adicionar exceção**.

1. Especifique os critérios de exceção. 

1. Selecione **Concluído** para salvar a regra.

### <a name="specify-custom-match-conditions"></a>Especificar condições de correspondência personalizadas

Você pode especificar condições que substituem a lógica de correspondência padrão. Há quatro opções disponíveis: 

|Opção  |Description |Exemplo  |
|---------|---------|---------|
|Sempre corresponder     | Define valores que sempre correspondem.         |  Sempre corresponder *Mike* e *MikeR*.       |
|Nunca corresponder     | Define valores que nunca correspondem.        | Nunca corresponder *John* e *Jonathan*.        |
|Bypass personalizado     | Define valores que o sistema deve sempre ignorar na fase de correspondência. |  Ignorar os valores *11111* e *Desconhecido* durante a correspondência.        |
|Mapeamento de alias    | Definição de valores que o sistema deve considerar como o mesmo valor.         | Considerar *Joe* igual a *Joseph*.        |

1. Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Correspondência personalizada** na seção **Detalhes dos registros correspondentes**.

   :::image type="content" source="media/custom-match-create.png" alt-text="Captura de tela da seção de regras de correspondência com o controle Correspondência personalizada destacado.":::

1. No painel **Personalizado**, vá para a guia **Registros**.

1. Escolha a opção de correspondência personalizada da lista suspensa **Tipo personalizado** e selecione **Baixar modelo**. Você precisa de um modelo separado para cada opção de correspondência.

1. Abra o arquivo de modelo baixado e preencha os detalhes. O modelo contém campos para especificar os valores da chave primária e da entidade a serem usados na correspondência personalizada. Por exemplo, se você quiser que a chave primária *12345* da entidade *Vendas* sempre corresponda à chave primária *34567* da entidade *Contato*, preencha no modelo:
    - Entity1: Sales
    - Entity1Key: 12345
    - Entity2: Contact
    - Entity2Key: 34567

   O mesmo arquivo de modelo pode especificar registros de correspondência personalizados de várias entidades.
   
   Se você deseja especificar a correspondência personalizada para eliminação de duplicação em uma entidade, forneça a mesma entidade como Entidade1 e Entidade2 e defina os diferentes valores de chave primária.

1. Depois de adicionar todas as substituições, salve o arquivo de modelo.

1. Vá para **Dados** > **Fontes de dados** e ingira os arquivos de modelo como novas entidades.

1. Após o upload dos arquivos e entidades estarem disponíveis, selecione a opção **Correspondência personalizada** novamente. Você verá opções para especificar as entidades que deseja incluir. Selecione as entidades necessárias no menu suspenso e selecione **Concluído**.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de tela da caixa de diálogo para escolher substituições para um cenário de correspondência personalizado.":::

1. A aplicação da correspondência personalizada depende da opção de correspondência que você deseja usar. 

   - Para **Sempre corresponder** ou **Nunca corresponder**, prossiga para a próxima etapa.
   - Para **Bypass personalizado** ou **Mapeamento de alias**, selecione **Editar** em uma regra de correspondência existente ou crie uma. Na lista suspensa Normalizações, escolha a opção **Bypass personalizado** ou **Mapeamento de alias** e selecione **Concluído**.

1. Selecione **Salvar** na página **Corresponder** para aplicar a configuração de correspondência personalizada.

1. Selecione **Executar** na página **Corresponder** para iniciar o processo de correspondência. Outras regras de correspondência especificadas serão substituídas pela configuração de correspondência personalizada.

#### <a name="known-issues"></a>Problemas conhecidos

- A autocombinação não mostra os dados normalizados em entidades de eliminação de duplicação. No entanto, ela aplica a normalização internamente durante a eliminação de duplicação. É o comportamento esperado para todas as normalizações. 
- Se a configuração do tipo semântico for removida na fase de **Mapeamento** em que uma regra de correspondência usa Mapeamento de alias ou Bypass personalizado, a normalização não será aplicada. Ela só acontece se você desmarcar o tipo semântico após configurar a normalização na regra de correspondência, pois o tipo semântico será desconhecido.


## <a name="next-step"></a>Próxima etapa

Depois de concluir o processo de correspondência para pelo menos um par de correspondência, continue para a etapa de [**Mesclagem**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
