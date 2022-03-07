---
title: Corresponder entidades para unificação de dados
description: Corresponda entidades para criar perfis de clientes unificados.
ms.date: 02/23/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 2155042d86cda0cffee1588760a06d6c7eb7077e
ms.sourcegitcommit: fcc94f55dc2dce84eae188d582801dc47696c9cc
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2021
ms.locfileid: "6085608"
---
# <a name="match-entities"></a>Corresponder entidades

A fase de correspondência especifica como combinar seus conjuntos de dados em um conjunto de dados de perfil de cliente unificado. Depois de concluir a [etapa de mapeamento](map-entities.md) no processo de unificação de dados, você estará pronto para fazer a correspondência de suas entidades. A fase de correspondência requer pelo menos duas entidades mapeadas.

A página de correspondência tem três seções: 
- Principais métricas que resumem o número de registros correspondentes
- Ordem de correspondência e regras para a correspondência entre entidades
- Regras para eliminação de duplicação de entidades correspondentes

## <a name="specify-the-match-order"></a>Especifique a ordem de correspondência

Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Definir ordem** para iniciar a fase de correspondência.

Cada correspondência unifica duas ou mais entidades em uma única entidade consolidada. Ao mesmo tempo, ela mantém os registros exclusivos do cliente. Por exemplo, selecionamos duas entidades: **eCommerce:eCommerceContacts** como a entidade principal e **LoyaltyScheme:loyCustomers** como entidade secundária. A ordem das entidades especifica a ordem na qual o sistema tentará fazer a correspondência dos registros.

:::image type="content" source="media/match-page.png" alt-text="Captura de tela da página Corresponder na área Unificar do processo de unificação de dados.":::
  
A correspondência da entidade principal *eCommerce:eCommerceContacts* é feita com a próxima entidade *LoyaltyScheme:loyCustomers*. Se você tiver mais de duas entidades, será feita a correspondência conjunto de dados resultante da primeira etapa de correspondência com a entidade seguinte.

> [!IMPORTANT]
> A entidade que você escolhe como sua entidade principal servirá como base para o conjunto de dados de perfis unificado. Entidades adicionais selecionadas durante a fase de correspondência serão adicionadas a essa entidade. Isso não significa que a entidade unificada incluirá *todos* os dados incluídos nesta entidade.
>
> Há duas considerações que podem ajudá-lo a escolher a hierarquia de suas entidades:
>
> - Escolha a entidade com os dados de perfil mais completos e confiáveis sobre seus clientes como entidade principal.
> - Escolha a entidade que tenha vários atributos em comum com outras entidades (por exemplo, nome, número de telefone ou endereço de email) como entidade principal.

Depois que especificar a ordem de correspondência, você verá os pares de correspondência definidos na seção **Detalhes dos registros correspondentes** em **Dados** > **Unificar** > **Corresponder**. As principais métricas estarão vazias até que o processo de correspondência seja concluído.

## <a name="define-rules-for-match-pairs"></a>Definir regras para pares de correspondência

As regras de correspondência especificam a lógica pela qual um par específico de entidades será correspondido.

O aviso **Precisa de regras** próximo ao nome de uma entidade sugere que nenhuma regra de correspondência foi definida para um par de correspondência. 

:::image type="content" source="media/match-rule-add.png" alt-text="Captura de tela da seção Detalhes dos registros correspondentes com o controle para adicionar regras destacado.":::

1. Selecione **Adicionar regras** em uma entidade na seção **Detalhes dos registros correspondentes** para definir regras de correspondência.

1. No painel **Criar regra**, configure as condições para a regra.

   :::image type="content" source="media/match-rule-conditions.png" alt-text="Captura de tela de uma regra de correspondência aberta com condições adicionadas.":::

   - **Entidade/Campo (primeira linha)**: escolha uma entidade relacionada e um atributo para especificar uma propriedade de registro que provavelmente seja exclusiva de um cliente. Por exemplo, um número de telefone ou endereço de email. Evite a correspondência por atributos de tipo de atividade. Por exemplo, um ID de compra provavelmente não encontrará correspondência em outros tipos de registro.

   - **Entidade/Campo (segunda linha)**: escolha um atributo relacionado ao atributo da entidade especificada na primeira linha.

   - **Normalizar**: selecione uma das opções de normalização a seguir para os atributos selecionados. 
     - Espaço em branco: remove todos os espaços. *Hello   World* torna-se *Olá, Mundo*.
     - Símbolos: remove todos os símbolos e caracteres especiais. *Head&Shoulder* torna-se *HeadShoulder*.
     - Texto em minúsculas: converte todos os caracteres em minúsculas. *TODAS EM MAIÚSCULAS e Capitalização de Título* torna-se *todas em maiúsculas e capitalização de título*.
     - Unicode para ASCII: converte a notação Unicode em caracteres ASCII. */u00B2* torna-se *2*.
     - Numerais: converte outros sistemas de numeração, como numerais romanos, em numerais arábicos. *VIII* torna-se *8*.
     - Tipos semânticos: padroniza nomes, títulos, números de telefone, endereços, etc. 

   - **Precisão**: defina o nível de precisão a ser aplicado a esta condição. 
     - **Básico**: escolha entre *Baixo*, *Médio*, *Alto* e *Exato*. Selecione **Exata** para corresponder apenas aos registros que correspondem a 100%. Selecione um dos outros níveis para corresponder aos registros que não são 100% idênticos.
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

As regras de correspondência representam conjuntos de condições. Para fazer a correspondência das entidades com base em vários atributos, adicione mais regras

1.  Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Adicionar regra** na entidade à qual você deseja adicionar regras.

2. Siga as etapas em [Definir regras para pares de correspondência](#define-rules-for-match-pairs).

> [!NOTE]
> A ordem das regras é importante. O algoritmo de correspondência tenta fazer a correspondência com base em sua primeira regra e continua para a segunda regra somente se nenhuma correspondência for identificada com a primeira regra.

### <a name="change-the-entity-order-in-match-rules"></a>Alterar a ordem da entidade nas regras de correspondência

Você pode reorganizar entidades para regras de correspondência para alterar a ordem em que são processadas. As regras que estiverem em conflito devido a um pedido alterado serão removidas. Você deve recriar as regras removidas com uma configuração atualizada.

1. Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Editar**.

1. No painel **Editar regra**, selecione o controle **Mover para cima/para baixo** ou arraste e solte as entidades para alterar a ordem.

   :::image type="content" source="media/reorder-match-rules.png" alt-text="Opções para modificar a ordem em que as entidades são processadas na fase de correspondência.":::

1. Selecione **Concluído** para salvar a regra.

## <a name="define-deduplication-on-a-match-entity"></a>Definir a eliminação de duplicação em uma entidade correspondente

Além de [regras para a correspondência entre entidades](#define-rules-for-match-pairs), você também pode especificar regras de eliminação de duplicação. *Eliminação de duplicação* é outro processo durante a correspondência de registros. Ela identifica registros duplicados e os mescla em um único registro. Os registros de origem são vinculados ao registro mesclado com IDs alternativas.

Os registro com eliminação de duplicação serão usados no processo de correspondência entre entidades. A eliminação de duplicação ocorre em entidades individuais e pode ser configurada para cada entidade usada em pares de correspondência.

A especificação de regras de eliminação de duplicação não é obrigatória. Se nenhuma regra desse tipo for configurada, as regras definidas pelo sistema serão aplicadas. Elas combinam todos os registros em um único registro antes de passar os dados da entidade para a correspondência entre entidades para o aprimoramento do desempenho.

### <a name="add-deduplication-rules"></a>Adicionar regras de eliminação de duplicação

1. Acesse **Dados** > **Unificar** > **Corresponder**.

1. Na seção **Duplicações mescladas**, selecione **Definir entidades**. Caso as regras de eliminação de duplicação já tenham sido criadas, selecione **Editar**.

1. No painel **Mesclar preferências**, escolha as entidades às quais deseja aplicar a eliminação de duplicação.

1. Especifique como combinar os registros duplicados e escolha uma das três opções:
   - **Mais preenchido**: identifica o registro com mais campos de atributos preenchidos como o registro vencedor. Esta é a opção de mesclagem padrão.
   - **Mais recente**: identifica o registro vencedor com base na maior recência. Requer uma data ou um campo numérico para definir a recência.
   - **Menos recente**: identifica o registro vencedor com base na menor recência. Requer uma data ou um campo numérico para definir a recência.
 
   > [!div class="mx-imgBorder"]
   > ![Etapa 1 das regras de eliminação de duplicação](media/match-selfconflation.png "Etapa 1 das regras de eliminação de duplicação")
 
1. Depois que as entidades forem selecionadas e a preferência de mesclagem for definida, selecione **Adicionar regra** para definir as regras de eliminação de duplicação no nível da entidade.
   - **Selecionar campo** lista todos os campos disponíveis dessa entidade. Escolha o campo em que deseja verificar se há duplicidades. Escolha campos que provavelmente são exclusivos para cada cliente. Por exemplo, um endereço de email ou a combinação de nome, cidade e número de telefone.
   - Especifique as configurações de normalização e precisão.
   - Defina mais condições adicionais selecionando **Adicionar condição**.
 
   > [!div class="mx-imgBorder"]
   > ![Etapa 2 das regras de eliminação de duplicação](media/match-selfconflation-rules.png "Etapa 2 das regras de eliminação de duplicação")

  É possível criar várias regras de eliminação de duplicação para uma entidade. 

1. A execução do processo de correspondência agora agrupa os registros com base nas condições definidas nas regras de eliminação de duplicação. Após o agrupamento dos registros, a política de mesclagem é aplicada para identificar o registro vencedor.

1. Esse registro vencedor é então transmitido para a correspondência entre entidades, juntamente com os registros não vencedores (por exemplo, IDs alternativas) para melhorar a qualidade da correspondência.

1. Quaisquer regras de correspondência personalizadas definidas substituem as regras de eliminação de duplicação. Se uma regra de eliminação de duplicação identificar registros correspondentes e uma regra de correspondência personalizada for definida para nunca corresponder esses registros, esses dois registros não serão correspondidos.

1. Depois que [executar o processo de correspondência](#run-the-match-process), você verá as estatísticas de eliminação de duplicação nos blocos de métricas principais.

### <a name="deduplication-output-as-an-entity"></a>Saída de eliminação de duplicação como uma entidade

O processo de eliminação de duplicação cria uma entidade para cada entidade dos pares de correspondência para identificar os registros com eliminação de duplicação. Essas entidades podem ser encontradas juntamente com **ConflationMatchPairs:CustomerInsights** na seção **Sistema** na página **Entidades**, com o nome **Deduplication_DataSource_Entity**.

Uma entidade de saída de eliminação de duplicação contém as seguintes informações:
- IDs/chaves
  - Campo de chave primária e seu campo de IDs alternativas. O campo de IDs alternativas consiste em todas as IDs alternativas identificadas para um registro.
  - O campo Deduplication_GroupId mostra o grupo ou cluster identificado em uma entidade que agrupa todos os registros semelhantes com base nos campos de eliminação de duplicação especificados. Ele é usado para fins de processamento do sistema. Se não houver regras de eliminação de duplicação manual especificadas e as regras de eliminação de duplicação definidas pelo sistema se aplicarem, talvez você não encontre esse campo na entidade de saída de eliminação de duplicação.
  - Deduplication_WinnerId: este campo contém a ID do vencedor dos grupos ou clusters identificados. Se a Deduplication_WinnerId for igual ao valor da chave primária para um registro, isso significa que o registro é o registro vencedor.
- Campos usados para definir as regras de eliminação de duplicação.
- Campos de regra e pontuação para denotar quais das regras de eliminação de duplicação foram aplicadas e a pontuação retornada pelo algoritmo de correspondência.
   
## <a name="run-the-match-process"></a>Executar o processo de correspondência

Com as regras de correspondência definidas, incluindo as regras de correspondência entre entidades e de eliminação de duplicação, você poderá executar o processo de correspondência. 

Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Executar** para iniciar o processo. O algoritmo de correspondência levará algum tempo para ser concluir o processo e você não poderá alterar a configuração até que ele seja concluído. Para fazer alterações, você pode cancelar a execução. Selecione o status do trabalho e selecione **Cancelar trabalho** no painel **Detalhes do progresso**.

Você encontrará o resultado de uma execução com êxito, a entidade unificada do perfil do cliente, na página **Entidades**. Sua entidade de cliente unificada é chamada **Clientes** na seção **Perfis**. A primeira execução de correspondência com êxito cria a entidade unificada *Cliente*. Todas as execuções de correspondência subsequentes expandem essa entidade.

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

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

:::image type="content" source="media/match-rules-management.png" alt-text="Captura de tela do menu suspenso com opções de regra de correspondência.":::

- **Altere a ordem das suas regras** se você definiu várias regras. Você pode reordenar as regras de correspondência selecionando as opções **Mover para Cima** e **Mover para Baixo** ou arrastando e soltando.

- **Altere as condições da regra** selecionando **Editar** e escolha campos diferentes.

- **Desative uma regra** para reter uma regra de correspondência enquanto a exclui do processo de correspondência.

- **Duplique suas regras** se você definiu uma regra de correspondência e deseja criar uma regra semelhante com modificações, selecione **Duplicar**.

- **Exclua uma regra** selecionando o símbolo **Excluir**.

## <a name="specify-custom-match-conditions"></a>Especificar condições de correspondência personalizadas

Você pode especificar condições que determinados registros sempre devem corresponder ou nunca corresponder. Essas regras podem ser carregadas para substituir o processo de correspondência padrão. Por exemplo, se houver John Doe I e John Doe II em nossos registros, o sistema pode combiná-los como uma pessoa. As regras de correspondência personalizadas permitem que você especifique que os perfis se refiram a pessoas diferentes. 

1. Acesse **Dados** > **Unificar** > **Corresponder** e selecione **Correspondência personalizada** na seção **Detalhes dos registros correspondentes**.

  :::image type="content" source="media/custom-match-create.png" alt-text="Captura de tela da seção de regras de correspondência com o controle Correspondência personalizada destacado.":::

1. Se não houver nenhuma regra de correspondência personalizadas definida, você verá um novo painel **Correspondência personalizada** com mais detalhes.

1. Selecione **Preencher o modelo** para obter um arquivo de modelo que pode especificar quais registros de quais entidades devem sempre corresponder ou nunca. Você precisará preencher separadamente os registros "sempre corresponder" e "nunca corresponder" em dois arquivos diferentes.

1. O modelo contém campos para especificar os valores da chave primária e da entidade a serem usados na correspondência personalizada. Por exemplo, se você quiser que a chave primária *12345* da entidade *Vendas* sempre corresponda à chave primária *34567* da entidade *Contato*, preencha no modelo:
    - Entity1: Sales
    - Entity1Key: 12345
    - Entity2: Contact
    - Entity2Key: 34567

   O mesmo arquivo de modelo pode especificar registros de correspondência personalizados de várias entidades.
   
   Se você deseja especificar a correspondência personalizada para eliminação de duplicação em uma entidade, forneça a mesma entidade como Entidade1 e Entidade2 e defina os diferentes valores de chave primária.

1. Depois de adicionar todas as substituições que você deseja aplicar, salve o arquivo de modelo.

1. Vá para **Dados** > **Fontes de dados** e ingira os arquivos de modelo como novas entidades. Depois de ingerido, você pode usá-los para especificar a configuração de Correspondência.

1. Após o upload dos arquivos e entidades estarem disponíveis, selecione a opção **Correspondência personalizada** novamente. Você verá opções para especificar as entidades que deseja incluir. Selecione as entidades obrigatórias no menu suspenso.

   :::image type="content" source="media/custom-match-overrides.png" alt-text="Captura de tela da caixa de diálogo para escolher substituições para um cenário de correspondência personalizado.":::

1. Selecione as entidades para as quais você deseja usar **Sempre corresponder** e **Nunca corresponder**, selecione **Concluído**.

1. Selecione **Salvar** na página **Corresponder** para aplicar a configuração de correspondência personalizada.

1. Selecione **Executar** na página **Corresponder** para iniciar o processo de correspondência. Outras regras de correspondência especificadas serão substituídas pela configuração de correspondência personalizada.

> [!TIP]
> Acesse **Dados** > **Entidades** e examine a entidade **ConflationMatchPair** para confirmar se as substituições foram aplicadas.

## <a name="next-step"></a>Próxima etapa

Depois de concluir o processo de correspondência de pelo menos um par de correspondência, você pode resolver possíveis contradições em seus dados, percorrendo o tópico [**Mesclar**](merge-entities.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
