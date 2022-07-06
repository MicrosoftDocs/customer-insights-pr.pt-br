---
title: Mapeamentos semânticos (versão preliminar)
description: Visão geral dos mapeamentos semânticos e como usá-los.
ms.date: 12/01/2021
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
searchScope:
- ci-semantic-mapping
- customerInsights
ms.openlocfilehash: b3a0643ab71c98ce212f4e4581a584d8382c67eb
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080836"
---
# <a name="semantic-mappings-preview"></a>Mapeamentos semânticos (versão preliminar)

Os mapeamentos semânticos permitem que você mapeie seus dados de não atividade para esquemas predefinidos. Esses esquemas ajudam o Customer Insights a entender melhor atributos de dados. O mapeamento semântico e os dados fornecidos permitem novos insights e recursos no Customer Insights. Para mapear seus dados de atividade para os esquemas, revise a documentação [Atividades](activities.md).

**Os mapeamentos semânticos estão atualmente ativados para ambientes baseados em contas comerciais**. *ContactProfile* é o único tipo de mapeamento semântico disponível atualmente no Customer Insights.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Defina um mapeamento de entidade semântica ContactProfile

1. Vá para **Dados** > **Mapeamentos semânticos (versão preliminar)**.

1. Selecione **Adicionar mapeamento semântico** para iniciar a experiência guiada.

1. Na etapa **Dados da entidade**, defina os valores para os seguintes campos:

   - **Nome do mapeamento da entidade semântica**: Forneça um nome para seu mapeamento de entidade semântica.
   - **Entidade fonte**: Selecione uma entidade que inclua dados de contato.
   - **Chave primária**:  Selecione o campo que identifica exclusivamente um registro de contato. Não deve conter valores duplicados, valores vazios ou valores ausentes.

   :::image type="content" source="media/Semantic_Mapping_Wizard1.png" alt-text="Configure o mapeamento de entidade semântica com nome, entidade de origem e chave primária.":::

1. Selecione **Avançar** para continuar.

1. Na etapa **Relacionamento**, configure os detalhes para conectar seus dados de contato aos dados da conta correspondente. Esta etapa visualiza a conexão entre as entidades.  

   Existem dois tipos de caminhos de relacionamento que podem ser implementados: **Relacionamentos diretos** e **Relacionamentos indiretos**. Para obter mais informações, vá para [caminhos de relacionamento direto e indireto](relationships.md#relationship-paths).

   1. Selecione **Adicionar relacionamento** configurar o relacionamento.
   1. Escolha o atributo de sua entidade de origem que conecta sua entidade de contato a outra entidade.
   1. Escolha a entidade à qual conectar sua entidade de contato. Você pode escolher uma entidade da seção **Entidades de conta** ou **Entidade intermediária**. Se você selecionar uma entidade intermediária, você precisa definir um segundo relacionamento para se conectar à sua entidade de conta alvo.

      :::image type="content" source="media/Semantic_Mapping_Wizard2.png" alt-text="Selecione uma entidade de conta ou uma entidade intermediária.":::

   1. Forneça um **Nome de relacionamento**. Se já existir um relacionamento entre suas entidades, o nome do relacionamento será somente leitura. Se não houver relacionamento, um novo relacionamento será criado com o nome que você forneceu.
   1. Selecione **Aplicar** para finalizar a configuração do relacionamento.

   > [!NOTE]
   > Você pode configurar mais relacionamentos entre a entidade de contato e outras entidades de conta com entidades intermediárias.
   >  :::image type="content" source="media/Semantic_Mapping_Wizard4.png" alt-text="A visualização de vários relacionamentos conecta entidades de contato a entidades de conta.":::

1. Selecione **Próximo** quando você terminar com a configuração de relacionamento.

1. Na etapa **Defina o tipo semântico**, escolha um **Tipo semântico**. Atualmente, existe um **Tipo Semântico** chamado *ContactProfile*.

1. Mapeie seus dados a *ContactProfile* **(tipo semântico)** para os campos exibidos.
   - Campo obrigatório: ID de Contato
   - Campos opcionais: Nome, Sobrenome, Data de nascimento, Sexo, Email primário e Telefone primário

   :::image type="content" source="media/Semantic_Mapping_Wizard5.png" alt-text="Mapeie seus atributos de dados de contato para os campos obrigatórios e opcionais fornecidos.":::

1. Selecione **Avançar** para continuar.

1. Na etapa **Análise**, dê uma olhada na configuração do mapeamento semântico. Selecione **Editar** para a seção correspondente para fazer alterações.

1. Selecione **Salvar** para salvar seu novo **Mapeamento semântico**.

1. Depois de salvar, você pode selecionar **Executar** processar o mapeamento semântico ou você pode selecionar **Fechar** para salvar seu mapeamento semântico sem processá-lo.

1. Para executar um mapeamento semântico posteriormente, selecione o mapeamento semântico e selecione **Atualizar**.

[!INCLUDE [progress-details-include](includes/progress-details-pane.md)]

## <a name="manage-existing-semantic-mappings"></a>Gerenciar mapeamentos semânticos existentes

Em **Dados** > **Mapeamentos semânticos (versão preliminar)**, você pode visualizar todos os seus mapeamentos semânticos salvos e gerenciá-los. Cada mapeamento semântico é representado por uma linha separada. Você encontrará detalhes sobre a entidade de origem, tipo semântico, tipo de mapeamento e seu status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opções para gerenciar mapeamentos semânticos.":::

- **Editar**: Abre a configuração do mapeamento semântico na etapa de revisão. Você pode alterar a configuração atual. Selecione **Salvar** e **Executar** para processar as alterações.

- **Atualizar**: Atualiza o mapeamento semântico selecionado com os dados mais atualizados das entidades que fazem parte de sua configuração. Atualizar qualquer mapeamento semântico fornecido irá atualizar todos os mapeamentos semânticos do mesmo tipo.

- **Renomear**: Abre uma caixa de diálogo onde você pode inserir um nome diferente para o mapeamento semântico selecionado. Selecione **Salvar** para aplicar suas alterações.

- **Excluir**: Abre uma caixa de diálogo para confirmar a exclusão do mapeamento semântico selecionado. Você também pode excluir mais de um mapeamento semântico de uma vez, selecionando os mapeamentos semânticos e o ícone de exclusão. Selecione **Excluir** para confirmar a exclusão.

## <a name="use-a-contactprofile-semantic-entity-mapping-to-create-contact-level-activities"></a>Usar um mapeamento de entidade semântica ContactProfile para criar atividades no nível do contato

Depois de criar um mapeamento de entidade semântica *ContactProfile*, você pode capturar atividades de contatos. Isso permite ver na linha do tempo de atividades de uma conta qual contato foi responsável por cada atividade. A maioria das etapas segue a configuração típica de mapeamento de atividades.

   > [!NOTE]
   > Para que as atividades no nível do contato funcionem, você deve ter os atributos **AccountID** e **ContactID** para cada registro nos seus dados de atividade.

1. [Defina um mapeamento de entidade semântica *ContactProfile*](#define-a-contactprofile-semantic-entity-mapping) e execute o mapeamento semântico.

1. Vá para **Dados** > **Atividades**.

1. Selecione **Adicionar Atividade** para criar uma nova atividade.

1. Nomeie a atividade, selecione a entidade de atividade de origem e selecione a chave primária da entidade de atividade.

1. Na etapa **Relacionamentos**, crie um relacionamento indireto entre seus dados de origem de atividade e contas, usando seus dados de contato como uma entidade intermediária. Para obter mais informações, consulte [caminhos de relacionamento direto e indireto](relationships.md#relationship-paths).
   - Relacionamento de exemplo para uma atividade chamada *Compras*:
      - **Dados da Atividade de Origem de Compras** > **Dados de Contato** no atributo **ContactID**
      - **Dados de Contato** > **Dados de Conta** no atributo **AccountID**

   :::image type="content" source="media/Contact_Activities1.png" alt-text="Configuração do relacionamento de exemplo.":::

1. Depois de configurar os relacionamentos, selecione **Avançar** e conclua a configuração do seu mapeamento de atividades. Para obter etapas detalhadas sobre a criação de atividades, consulte [definir uma atividade](activities.md).

1. Execute seus mapeamentos de atividades.

1. Suas atividades no nível do contato agora estarão visíveis na linha do tempo do cliente.

   :::image type="content" source="media/Contact_Activities2.png" alt-text="Resultado final após a configuração das atividades de contato":::

### <a name="contact-level-activity-timeline-filtering"></a>Filtragem da linha do tempo de atividades no nível do contato

Depois de configurar um mapeamento de atividades no nível do contato e executá-lo, a linha do tempo de atividades dos seus clientes será atualizada. Ela inclui as IDs ou nomes, dependendo da sua configuração *ContactProfile*, das atividades em que atuaram. Você pode filtrar atividades por contatos na linha do tempo para ver contatos específicos de seu interesse. Além disso, você pode ver todas as atividades que não estão atribuídas a um contato específico, selecionando **Atividades não mapeadas para um Contato**.

   :::image type="content" source="media/Contact_Activities3.png" alt-text="Opções de filtragem disponíveis para atividades no nível do contato.":::

[!INCLUDE [footer-include](includes/footer-banner.md)]
