---
title: Corresponder entidades para unificação de dados
description: Corresponda entidades para criar perfis de clientes unificados.
ms.date: 10/14/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
ms.reviewer: adkuppa
manager: shellyha
ms.openlocfilehash: 78549037f9c9e59329f5423c36eeb058128802c0
ms.sourcegitcommit: cf9b78559ca189d4c2086a66c879098d56c0377a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/03/2020
ms.locfileid: "4405050"
---
# <a name="match-entities"></a>Corresponder entidades

Após concluir a fase de mapeamento, você estará pronto para corresponder suas entidades. A fase de correspondência especifica como combinar seus conjuntos de dados em um conjunto de dados de perfil de cliente unificado. A fase de correspondência requer pelo menos [duas entidades mapeadas](map-entities.md).

## <a name="specify-the-match-order"></a>Especifique a ordem de correspondência

Vá para **Unificar** > **Corresponder** e selecione **Definir ordem** para iniciar a fase de correspondência.

Cada correspondência unifica duas ou mais entidades em uma única entidade, enquanto persiste cada registro de cliente exclusivo. No exemplo a seguir, selecionamos três entidades: **ContactCSV: TestData** como a entidade **Principal**, **WebAccountCSV: TestData** como a **Entidade 2** e **CallRecordSmall: TestData** como **Entidade 3**. O diagrama acima das seleções ilustra como a ordem de correspondência será executada.

> [!div class="mx-imgBorder"]
> ![Edite a ordem de correspondência de dados](media/configure-data-match-order-edit-page.png "Edite a ordem de correspondência de dados")
  
A entidade **Principal** é correspondida com a **Entidade 2**. O conjunto de dados resultante da primeira correspondência é correspondido com a **Entidade 3**.
Neste exemplo, selecionamos apenas duas correspondências, mas o sistema pode suportar mais.

> [!IMPORTANT]
> A entidade que você escolhe como sua entidade **Principal** servirá como base para o seu conjunto de dados mestre unificado. Entidades adicionais selecionadas durante a fase de correspondência serão adicionadas a essa entidade. Ao mesmo tempo, isso não significa que a entidade unificada incluirá *todos* os dados incluídos nesta entidade.
>
> Há duas considerações que podem ajudá-lo a escolher a hierarquia de suas entidades:
>
> - Qual entidade você acha que tem os dados mais completos e confiáveis sobre seus clientes?
> - A entidade que você acabou de identificar possui atributos que também são compartilhados por outras entidades (por exemplo, nome, número de telefone ou endereço de email)? Caso contrário, escolha sua segunda entidade mais confiável.

Selecione **Concluído** para salvar seu pedido de correspondência.

## <a name="define-rules-for-your-first-match-pair"></a>Definir regras para o seu primeiro par de correspondência

Depois de especificar a ordem da correspondência, você verá as correspondências definidas na página **Corresponder**. Os blocos na parte superior da tela ficarão vazios até que você execute a sua ordem de correspondência.

> [!div class="mx-imgBorder"]
> ![Definir regras](media/configure-data-match-need-rules.png "Definir regras")

O aviso **Precisa de Regras** sugere que nenhuma regra seja definida para um par de correspondência. As regras de correspondência especificam a lógica pela qual um par específico de entidades será correspondido.

1. Para definir sua primeira regra, abra o painel **Definição de Regra**, selecionando a linha de correspondência correspondente na tabela de correspondências (1) e, em seguida, selecionando **Criar nova regra** (2).

   > [!div class="mx-imgBorder"]
   > ![Criar nova regra](media/configure-data-match-new-rule2.png "Criar regra")

2. No painel **Editar regra**, configure as condições para essa regra. Cada condição é representada por duas linhas que incluem seleções obrigatórias.

   > [!div class="mx-imgBorder"]
   > ![Painel nova regra](media/configure-data-match-new-rule-condition.png "Painel nova regra")

   Entidade/Campo (primeiro) - Um atributo que será usado para correspondência da primeira entidade do par de correspondência. Os exemplos podem incluir um número de telefone ou endereço de email. Escolha um atributo que provavelmente seja exclusivo do cliente.

   > [!TIP]
   > Evite a correspondência com base nos atributos do tipo de atividade. Em outras palavras, se um atributo parece ser uma atividade, pode ser um critério ruim para correspondência.  

   Entidade/Campo (Segundo) - Um atributo que será usado para correspondência da segunda entidade do par de correspondência.

   Normalizar - **Método de normalização** : Várias opções de normalização estão disponíveis para os atributos selecionados. Por exemplo, remover pontuação ou remover espaços

   Para normalização do nome da Organização (Versão Prévia), você também pode selecionar **Tipo (Telefone, Nome, Organização)**

   > [!div class="mx-imgBorder"]
   > ![Normalização-B2B](media/match-normalization-b2b.png "Normalização-B2B")

   Nível de precisão - O nível de precisão que será usado para essa condição. A definição de um nível de precisão para uma condição de correspondência pode ter dois tipos: **Básico** e **Personalizado**.  
   - Básico: fornece quatro opções para você escolher: Baixa, Média, Alta e Exata. Selecione **Exata** para corresponder apenas aos registros que correspondem a 100%. Selecione um dos outros níveis para corresponder aos registros que não são 100% idênticos.
   - Personalizado: use o controle deslizante para definir a porcentagem personalizada que os registros precisam corresponder ou inserir um valor no campo **Personalizado**. O sistema corresponderá apenas aos registros que ultrapassam esse limite como pares de correspondência conflitantes. Os valores no controle deslizante estão entre 0 e 1. Então 0,64 representa 64%.

3. Selecione **Concluído** para salvar a regra.

### <a name="add-multiple-conditions"></a>Adicionar várias condições

Para corresponder às suas entidades somente se várias condições forem atendidas, adicione mais condições vinculadas por meio de um operador AND.

1. No painel **Editar regra**, selecione **Adicionar condição**. Você também pode excluir condições selecionando o botão remover ao lado de uma condição existente.

2. Selecione **Concluído** para salvar a regra.

## <a name="add-multiple-rules"></a>Adicione várias regras

Cada condição se aplica a um único par de atributos, enquanto as regras representam conjuntos de condições. Para que suas entidades correspondam a diferentes conjuntos de atributos, você pode adicionar mais regras.

1. Nos insights de público-alvo, vá para **Dados** > **Unificar** > **Corresponder**.

2. Selecione a entidade que você deseja atualizar e selecione **Adicionar regras**.

3. Siga o procedimento descrito em [Definir regras para o seu primeiro par de correspondência](#define-rules-for-your-first-match-pair).

> [!NOTE]
> A ordem das regras é importante. O algoritmo de correspondência tenta corresponder com base na sua primeira regra e continua na segunda regra somente se nenhuma correspondência for identificada na primeira regra.

## <a name="define-deduplication-on-a-match-entity"></a>Definir a eliminação de duplicação em uma entidade correspondente

Além de especificar regras de correspondência entre entidades conforme descrito nas seções acima, você também pode especificar regras de eliminação de duplicação. A *eliminação de duplicação* é um processo. Ela identifica os registros duplicados, mescla-os em um registro e vincula todos os registros de origem a esse registro mesclado com IDs alternativas ao registro mesclado.

Depois que um registro que passou por eliminação de duplicação for identificado, ele será usado no processo de correspondência entre entidades. A eliminação de duplicação é implementada no nível da entidade e pode ser aplicada a todas as entidades usadas no processo de correspondência.

### <a name="add-deduplication-rules"></a>Adicionar regras de eliminação de duplicação

1. Nos insights de público-alvo, vá para **Dados** > **Unificar** > **Corresponder**.

1. Na seção **Duplicações mescladas**, selecione **Definir entidades**.

1. Na seção **Mesclar preferências**, selecione as entidades às quais deseja aplicar a eliminação de duplicação.

1. Especifique como mesclar os registros duplicados e escolha uma das três opções de mesclagem:
   - *Mais preenchido*: identifica o registro com mais atributos preenchidos como o registro vencedor. Esta é a opção de mesclagem padrão.
   - *Mais recente*: identifica o registro vencedor com base na maior recência. Requer uma data ou um campo numérico para definir a recência.
   - *Menos recente*: identifica o registro vencedor com base na menor recência. Requer uma data ou um campo numérico para definir a recência.
 
   > [!div class="mx-imgBorder"]
   > ![Etapa 1 das regras de eliminação de duplicação](media/match-selfconflation.png "Etapa 1 das regras de eliminação de duplicação")
 
1. Depois que as entidades forem selecionadas e sua preferência de mesclagem for definida, selecione **Criar regra** para definir as regras de eliminação de duplicação no nível da entidade.
   - **Selecionar campo** lista todos os campos disponíveis dessa entidade nos quais você deseja realizar a eliminação de duplicação dos dados de origem.
   - Especifique as configurações de normalização e precisão de maneira semelhante à especificada na correspondência entre entidades.
   - Você pode definir condições adicionais selecionando **Adicionar condição**.
 
   > [!div class="mx-imgBorder"]
   > ![Etapa 2 das regras de eliminação de duplicação](media/match-selfconflation-rules.png "Etapa 2 das regras de eliminação de duplicação")

  É possível criar várias regras de eliminação de duplicação para uma entidade. 

1. A execução do processo de correspondência agora agrupa os registros com base nas condições definidas nas regras de eliminação de duplicação. Após o agrupamento dos registros, a política de mesclagem é aplicada para identificar o registro vencedor.

1. Esse registro vencedor é então passado para a correspondência entre entidades.

1. Quaisquer regras de correspondência personalizadas definidas para sempre corresponder e nunca corresponder anulam as regras de eliminação de duplicação. Se uma regra de eliminação de duplicação identificar registros correspondentes e uma regra de correspondência personalizada for definida para nunca corresponder esses registros, esses dois registros não serão correspondidos.

1. Depois de executar o processo de correspondência, você verá as estatísticas de eliminação de duplicação.
   
> [!NOTE]
> A especificação de regras de eliminação de duplicação não é obrigatória. Se nenhuma regra desse tipo for configurada, as regras definidas pelo sistema serão aplicadas. Elas recolhem todos os registros que compartilham a mesma combinação de valores (correspondência exata) da chave primária e os campos nas regras de correspondência em um único registro antes de passar os dados da entidade para a correspondência entre entidades a fim de obter desempenho e integridade do sistema aprimorados.

## <a name="run-your-match-order"></a>Execute sua ordem de correspondência

Depois de definir as regras de correspondência, incluindo as regras de correspondência entre entidades e de eliminação de duplicação, você poderá executar a ordem de correspondência. Na página **Correspondência**, selecione **Executar** para iniciar o processo. O algoritmo de correspondência pode levar algum tempo para ser concluído. Você não pode alterar as propriedades na página **Correspondência** até que o processo de correspondência seja concluído. Você encontrará a entidade unificada do perfil do cliente que foi criada na página **Entidades**. Sua entidade unificada do cliente é chamada **ConflationMatchPairs: CustomerInsights**.

Para fazer alterações adicionais e executar novamente a etapa, você pode cancelar uma correspondência em andamento. Selecione o texto **Atualizando...** e selecione **Cancelar o trabalho** na parte inferior do painel lateral exibido.

Quando o processo de correspondência estiver concluído, o texto **Atualizando...** será alterado para **Bem-sucedido** e você poderá usar todas as funcionalidades da página novamente.

O primeiro processo de correspondência resulta na criação de uma entidade mestre unificada. Todas as execuções de correspondências subsequentes resultam na expansão dessa entidade.

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="review-and-validate-your-matches"></a>Revise e valide suas correspondências

Avalie a qualidade de seus pares de correspondência e refine-a:

- Na página **Correspondência**, você encontrará dois blocos mostrando informações iniciais sobre seus dados.

  - **Clientes únicos**: mostra o número de perfis exclusivos que o sistema identificou.
  - **Registros correspondentes**: mostra o número de correspondências em todos os seus pares de correspondências.

- Na tabela **Ordem de correspondência**, é possível avaliar os resultados de cada par de correspondências comparando o número de registros provenientes desta entidade de par de correspondências com a porcentagem de registros correspondidos com êxito.

- Na seção **Regras** de uma entidade na tabela **Ordem de correspondência**, você encontrará a porcentagem de registros correspondidos com êxito no nível da regra. Ao selecionar o símbolo da tabela ao lado de uma regra, é possível visualizar todos esses registros no nível da regra. Recomendamos que você revise um subconjunto dos registros para validar se eles foram correspondidos corretamente.

- Experimente diferentes limites de precisão em torno de suas condições para identificar o valor ideal.

  1. Selecione as reticências (...) para a regra do par de correspondências com a qual você deseja experimentar e selecione **Editar**.

  2. Selecione a condição com a qual você deseja experimentar. Cada critério é representado por uma linha no painel **Regra de correspondência**.

  3. O que você verá na página **Visualização de critérios** depende do nível de precisão que você selecionou para uma condição. Encontre o número de registros correspondentes e não correspondentes para a condição selecionada.

     Obtenha uma compreensão abrangente dos efeitos de diferentes níveis de limite. Você pode comparar quantos registros serão correspondidos em cada um dos níveis de limite e visualizar os registros em cada opção. Selecione cada um dos blocos e revise os dados na seção da tabela.

## <a name="optimize-your-matches"></a>Otimize suas correspondências

Aumente a qualidade reconfigurando alguns dos seus parâmetros de correspondência:

- **Altere a ordem de correspondência** selecionando **Editar** e altere os campos da ordem de correspondência.

  > [!div class="mx-imgBorder"]
  > ![Edite a ordem de correspondência de dados](media/configure-data-match-order-edit.png "Edite a ordem de correspondência de dados")

- **Altere a ordem das suas regras** se você definiu várias regras. Você pode reordenar as regras de correspondência selecionando as opções **Mover para Cima** e **Mover para Baixo** na grade de regras de correspondência.

  > [!div class="mx-imgBorder"]
  > ![Alterar a ordem da regra](media/configure-data-change-rule-order.png "Alterar a ordem da regra")

- **Duplique suas regras** se você definiu uma regra de correspondência e quer criar uma regra semelhante com modificações. Faça isso selecionando **Duplicar**.

  > [!div class="mx-imgBorder"]
  > ![Duplicar uma regra](media/configure-data-duplicate-rule.png "Duplicar uma regra")

- **Edite suas regras** selecionando o símbolo **Editar**. Você pode aplicar as seguintes alterações:

  - Alterar atributos para uma condição: selecione novos atributos na linha de condição específica.
  - Altere o limite para uma condição: Ajuste o controle deslizante de precisão.
  - Altere o método de normalização para uma condição: Atualize o método de normalização.

## <a name="specify-your-custom-match-records"></a>Especifique seus registros de correspondência personalizados

Você pode especificar condições que determinados registros sempre devem corresponder ou nunca corresponder. Essas regras podem ser carregadas em massa para o processo de correspondência.

1. Selecione a opção **Correspondência personalizada** na tela **Ordem de correspondência**.

   > [!div class="mx-imgBorder"]
   > ![Criar uma correspondência personalizada](media/custom-match-create.png "Criar uma correspondência personalizada")

2. Se você não possui entidades carregadas, verá uma nova caixa de diálogo **Correspondência personalizada** que requer que você preencha alguns detalhes. Se você forneceu esses detalhes anteriormente, pule para a etapa 8.

   > [!div class="mx-imgBorder"]
   > ![Nova caixa de diálogo de correspondência personalizada](media/custom-match-new-dialog-box.png "Nova caixa de diálogo de correspondência personalizada")

3. Selecione **Preencher o modelo** para obter um arquivo de modelo que pode especificar quais registros de quais entidades devem sempre corresponder ou nunca. Você precisará preencher separadamente os registros "sempre corresponder" e "nunca corresponder" em dois arquivos diferentes.

4. O modelo contém campos para especificar os valores da chave primária e da entidade a serem usados na correspondência personalizada. Por exemplo, se você deseja que a chave primária 12345 da entidade Vendas corresponda sempre à chave primária 34567 da entidade Contato, precisará especificar o seguinte:
    - Entity1: Sales
    - Entity1Key: 12345
    - Entity2: Contact
    - Entity2Key: 34567

   O mesmo arquivo de modelo pode especificar registros de correspondência personalizados de várias entidades.

5. Depois de adicionar todas as substituições que você deseja aplicar, salve o arquivo de modelo.

6. Vá para **Dados** > **Fontes de dados** e ingira os arquivos de modelo como novas entidades. Depois de ingerido, você pode usá-los para especificar a configuração de Correspondência.

7. Após o upload dos arquivos e entidades estarem disponíveis, selecione a opção **Correspondência personalizada** novamente. Você verá opções para especificar as entidades que deseja incluir. Selecione as entidades obrigatórias no menu suspenso.

   > [!div class="mx-imgBorder"]
   > ![Substituições de correspondência personalizada](media/custom-match-overrides.png "Substituições de correspondência personalizada")

8. Selecione as entidades para as quais você deseja usar **Sempre corresponder** e **Nunca corresponder**, selecione **Concluído**.

9. Selecione **Salvar** na página **Correspondência** da configuração de correspondência personalizada que você acabou de configurar.

10. Selecione **Executar** na página **Correspondência** para iniciar o processo de correspondência e a configuração de correspondência personalizada será aplicada. Quaisquer regras correspondidas pelo sistema são substituídas pelo conjunto de configurações.

11. Após a conclusão da correspondência, você pode verificar a entidade **ConflationMatchPair** para confirmar que as substituições são aplicadas nas correspondências de conflação.

## <a name="next-step"></a>Próxima etapa

Depois de concluir o processo de correspondência de pelo menos um par de correspondência, você pode resolver possíveis contradições em seus dados, percorrendo o tópico [**Mesclar**](merge-entities.md).
