---
title: Atividades do cliente
description: Defina as atividades do cliente e exiba-as na linha do tempo do cliente.
ms.date: 10/13/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.reviewer: adkuppa
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 1c95cba333266a73959de0a3afe1c8677130a3ec
ms.sourcegitcommit: 334633cbd58f5659d20b4f87252c1a10cc7130db
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2020
ms.locfileid: "4667215"
---
# <a name="customer-activities"></a>Atividades do cliente

Combine as atividades do cliente de [várias fontes de dados](data-sources.md) no Dynamics 365 Customer Insights para criar uma linha do tempo do cliente que lista as atividades em ordem cronológica. Você pode incluir a linha do tempo nos aplicativos de interação com os clientes no Dynamics 365 por meio do [Suplemento do Cartão do Cliente](customer-card-add-in.md), ou em um painel de controle do Power BI.

## <a name="define-an-activity"></a>Definir uma atividade

Suas fontes de dados incluem entidades com dados transacionais e de atividades de várias fontes de dados. Identifique essas entidades e selecione as atividades que deseja visualizar na linha do tempo do cliente. Escolha a entidade que inclui sua atividade ou atividades de destino.

1. Nos insights de público-alvo, vá para **Dados** > **Atividades**.

1. Selecione **Adicionar atividade**.

   > [!NOTE]
   > Uma entidade deve ter pelo menos um atributo do tipo **Data** para ser incluído na linha do tempo do cliente e você não pode adicionar entidades sem os campos de **Data**. O controle **Adicionar atividade** é desativado, se nenhuma entidade for encontrada.

1. No painel **Adicionar atividade**, defina os valores para os seguintes campos:

   - **Entidade**: Selecione uma entidade que inclua dados transacionais ou de atividade.
   - **Chave primária**: Seleciona o campo que identifica exclusivamente um registro. Não deve conter valores duplicados, valores vazios ou valores ausentes.
   - **Registro de data e hora**: Selecione o campo que representa a hora de início da sua atividade.
   - **Evento**: Selecione o campo que é o evento para a atividade.
   - **Endereço da Web**: Selecione o campo que representa uma URL que fornece informações adicionais sobre esta atividade. Por exemplo, o sistema transacional que origina essa atividade. Esse URL pode ser qualquer campo da fonte de dados ou pode ser construído como um novo campo usando uma transformação do Power Query. Esses dados de URL serão armazenados na entidade da Atividade Unificada, que pode ser consumida posteriormente com as APIs.
   - **Detalhes**: Como opção, selecione o campo que é adicionado para obter detalhes adicionais.
   - **Ícone**: Como opção, selecione o ícone que representa esta atividade.
   - **Tipo de Atividade**: Defina a referência do tipo de atividade para o Common Data Model que melhor descreve a definição semântica da atividade.

1. Na seção **Definir relacionamento**, configure os detalhes para conectar seus dados de atividade ao cliente correspondente.

   > [!div class="mx-imgBorder"]
   > ![Defina o relacionamento da entidade](media/activities-entities-define.png "Defina o relacionamento da entidade")

    - **Campo da entidade de atividade**: selecione o campo na sua entidade de atividade que será usado para estabelecer um relacionamento com outra entidade.
    - **Entidade do cliente**: selecione a entidade do cliente de origem correspondente com a qual sua entidade de atividade estará em relacionamento. É possível se relacionar apenas às entidades do cliente de origem que são usadas no processo de unificação de dados.
    - **Campo da entidade do cliente**: este campo mostra a chave primária da entidade do cliente de origem, conforme selecionada no processo de mapeamento. Esse campo de chave primária na entidade do cliente de origem é usado para estabelecer um relacionamento com a entidade da atividade.
    - **Nome**: se já existir um relacionamento entre esta entidade de atividade e a entidade cliente de origem selecionada, o nome do relacionamento estará no modo somente leitura. Se não existir esse relacionamento, um novo relacionamento será criado com o nome fornecido aqui.

1. Selecione **Salvar** para aplicar suas alterações.

1. Na página **Atividades**, selecione **Executar**.

> [!TIP]
> Existem [seis tipos de status](system.md#status-types) para tarefas/processos. Além disso, a maioria dos processos [depende de outros processos de downstream](system.md#refresh-policies). Você pode selecionar o status de um processo para ver detalhes sobre o progresso de todo o trabalho. Depois de selecionar **Ver detalhes** para uma das tarefas do trabalho, você encontra informações adicionais: tempo de processamento, a última data de processamento e todos os erros e avisos associados à tarefa.

## <a name="edit-an-activity"></a>Editar uma atividade

1. Nos insights de público-alvo, vá para **Dados** > **Atividades**.

2. Selecione a entidade da atividade que você deseja editar e selecione **Editar**. Ou você pode passar o mouse sobre a linha da entidade e selecionar o ícone **Editar**.

3. Clique no ícone **Editar**.

4. No painel **Editar atividade**, atualize os valores e selecione **Salvar**.

5. Na página **Atividades**, selecione **Executar**.

## <a name="delete-an-activity"></a>Excluir uma atividade

1. Nos insights de público-alvo, vá para **Dados** > **Atividades**.

2. Selecione a entidade da atividade que você deseja remover e selecione **Excluir**. Ou você pode passar o mouse sobre a linha da entidade e selecionar o ícone **Excluir**. Além disso, você pode selecionar várias entidades de atividade a serem excluídas de uma só vez.
   > [!div class="mx-imgBorder"]
   > ![Editar ou excluir o relacionamento da entidade](media/activities-entities-edit-delete.png "Editar ou excluir o relacionamento da entidade")

3. Selecione no ícone **Excluir**.

4. Confirme a exclusão.
