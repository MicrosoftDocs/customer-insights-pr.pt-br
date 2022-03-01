---
title: Mapeamentos semânticos (versão preliminar)
description: Visão geral dos mapeamentos semânticos e como usá-los.
ms.date: 09/28/2021
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: mhart
ms.topic: conceptual
author: CadeSanthaMSFT
ms.author: cadesantha
manager: shellyha
ms.openlocfilehash: b0884b8b6a2c5abe4b3967d1b57d11a3a6d65c5b
ms.sourcegitcommit: 5d82e5b808517e0e99fdfdd7e4a4422a5b8ebd5c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/11/2021
ms.locfileid: "7622921"
---
# <a name="semantic-mappings"></a>Mapeamentos semânticos

Os mapeamentos semânticos permitem que você mapeie seus dados de não atividade para esquemas predefinidos. Esses esquemas ajudam os insights do público-alvo a entender melhor seus atributos de dados. O mapeamento semântico e os dados fornecidos permitem novos insights e recursos nos insights do público-alvo. Para mapear seus dados de atividade para os esquemas, revise a documentação [Atividades](activities.md).

**Os mapeamentos semânticos estão atualmente ativados para ambientes baseados em contas comerciais**. *ContactProfile* é o único tipo de mapeamento semântico disponível atualmente em insights de público-alvo.

## <a name="define-a-contactprofile-semantic-entity-mapping"></a>Defina um mapeamento de entidade semântica ContactProfile

1. Em insights do público-alvo, vá para **Dados** > **Mapeamentos semânticos (versão preliminar)**.

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

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="manage-existing-semantic-mappings"></a>Gerenciar mapeamentos semânticos existentes

Em **Dados** > **Mapeamentos semânticos (versão preliminar)**, você pode visualizar todos os seus mapeamentos semânticos salvos e gerenciá-los. Cada mapeamento semântico é representado por uma linha separada. Você encontrará detalhes sobre a entidade de origem, tipo semântico, tipo de mapeamento e seu status.

:::image type="content" source="media/semantic-mapping-options.png" alt-text="Opções para gerenciar mapeamentos semânticos.":::

- **Editar**: Abre a configuração do mapeamento semântico na etapa de revisão. Você pode alterar a configuração atual. Selecione **Salvar** e **Executar** para processar as alterações.

- **Atualizar**: Atualiza o mapeamento semântico selecionado com os dados mais atualizados das entidades que fazem parte de sua configuração. Atualizar qualquer mapeamento semântico fornecido irá atualizar todos os mapeamentos semânticos do mesmo tipo.

- **Renomear**: Abre uma caixa de diálogo onde você pode inserir um nome diferente para o mapeamento semântico selecionado. Selecione **Salvar** para aplicar suas alterações.

- **Excluir**: Abre uma caixa de diálogo para confirmar a exclusão do mapeamento semântico selecionado. Você também pode excluir mais de um mapeamento semântico de uma vez, selecionando os mapeamentos semânticos e o ícone de exclusão. Selecione **Excluir** para confirmar a exclusão.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
