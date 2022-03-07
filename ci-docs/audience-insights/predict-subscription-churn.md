---
title: Previsão da rotatividade de assinaturas (contém vídeo)
description: Preveja se um cliente está em risco de não usar mais os produtos ou serviços de assinatura da sua empresa.
ms.date: 08/19/2020
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: b61e87ad833dd7a8e51c6619945a9e216d85f221
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354679"
---
# <a name="subscription-churn-prediction"></a>Previsão de rotatividade de assinaturas

A previsão de rotatividade de assinaturas ajuda a prever se um cliente está em risco de não usar mais os produtos ou serviços de assinatura da sua empresa. Você pode criar uma previsão de rotatividade de assinaturas na página **Inteligência** > **Previsões**. Selecione **Minhas previsões** para ver outras previsões que você criou.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWOKNQ]

> [!TIP]
> Experimente o tutorial para uma previsão de rotatividade de assinatura usando dados de exemplo: [Guia de exemplo para previsão de rotatividade de assinatura](sample-guide-predict-subscription-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

- Pelo menos [Permissões de colaborador](permissions.md).
- Conhecimento de negócios para entender o que rotatividade significa para o seu negócio. Oferecemos suporte a definições de rotatividade com base no tempo, o que significa que o cliente é considerado rotativo por um período após o término da assinatura.
- Dados sobre as assinaturas e o histórico:
    - Identificadores de assinatura para distinguir as assinaturas.
    - Identificadores de clientes para associar as assinaturas aos clientes.
    - Datas de eventos de assinatura, que definem datas de início, datas de término e as datas em que os eventos de assinatura ocorreram.
    - Informações de assinatura para definir se é uma assinatura recorrente e com que frequência ela é renovada.
    - O esquema de dados semânticos para assinaturas requer as seguintes informações:
        - **ID da Assinatura:** Um identificador exclusivo de uma assinatura.
        - **Data de Término da Assinatura:** A data em que a assinatura do cliente expira.
        - **Data de Início da Assinatura:** A data de início da assinatura do cliente.
        - **Data da Transação:** A data em que ocorreu uma alteração na assinatura. Por exemplo, um cliente comprou ou cancelou a assinatura.
        - **É uma assinatura recorrente:** Um campo booliano verdadeiro/falso que determina se a assinatura será renovada com a mesma ID de assinatura sem intervenção do cliente
        - **Frequência de Recorrência (em meses):** Para assinaturas recorrentes, é o período referente ao qual a assinatura será renovada. É representado em meses. Por exemplo, uma assinatura anual renovada automaticamente para um cliente todos os anos e é renovada por mais um ano tem o valor igual a 12.
        - (Opcional) **Valor da Assinatura:** O valor da moeda que o cliente pela renovação da assinatura. Isso pode ajudar a identificar padrões de diferentes níveis de assinatura.
- Dados sobre atividades do cliente:
    - Identificadores de atividades para diferenciar atividades do mesmo tipo.
    - Identificadores de clientes para mapear atividades para os clientes.
    - Informações de atividades que contêm o nome e a data da atividade.
    - O esquema de dados semânticos para atividades do cliente inclui:
        - **Chave primária:** Um identificador exclusivo para uma atividade. Por exemplo, o acesso a um site ou um registro de uso que mostra que o cliente assistiu ao episódio de um programa de TV.
        - **Carimbo de data/hora:** A data e a hora do evento identificado pela chave primária.
        - **Evento:** O nome do evento que você deseja usar. Por exemplo, um campo chamado "UserAction" em um serviço de streaming de vídeo pode ter o valor "Visualizado".
        - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo chamado "ShowTitle" em um serviço de streaming de vídeo pode ter o valor de um vídeo que o cliente assistiu.
- Características de dados sugeridas:
    - Dados históricos suficientes: dados de assinatura de pelo menos o dobro da janela de tempo selecionada. De preferência, de dois a três anos de dados de assinatura.
    - Status da assinatura: os dados incluem assinaturas ativas e inativas de cada cliente, portanto, há várias entradas por ID de cliente.
    - Número de clientes: pelo menos 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos. O modelo falhará com menos de 10 clientes e dados históricos insuficientes.
    - Integridade dos dados: menos de 20% de valores ausentes no campo de dados da entidade fornecida.
   
   > [!NOTE]
   > Você precisará de pelo menos dois registros de atividades para 50% dos clientes para os quais deseja calcular a rotatividade.

## <a name="create-a-subscription-churn-prediction"></a>Crie uma previsão de rotatividade de assinaturas

1. Nos insights de público-alvo, vá para **Inteligência** > **Previsões**.
1. Selecione o bloco **Modelo de rotatividade da assinatura** e selecione **Usar este modelo**.
   > [!div class="mx-imgBorder"]
   > ![Bloco do modelo de Rotatividade de Assinaturas com o botão Usar este modelo.](media/subscription-churn-usethismodel.PNG "Bloco do modelo de Rotatividade de Assinaturas com o botão Usar este modelo")

### <a name="name-model"></a>Nomear modelo

1. Forneça um nome para o modelo para diferenciá-lo dos outros modelos.
1. Forneça um nome para a entidade de saída usando somente letras e números, sem espaços. Esse é o nome que a entidade de modelo usará. Em seguida, selecione **Próximo**.

### <a name="define-customer-churn"></a>Definir rotatividade de clientes

1. Insira o número de **Dias desde o término da assinatura** que a sua empresa considera um cliente em um estado rotativo. Esse período geralmente é associado a atividades comerciais como ofertas ou outros esforços de marketing para tentar fidelizar o cliente.
1. Insira o número de **Dias para consultar no futuro para prever a rotatividade** para definir uma janela para prever a rotatividade. Por exemplo, para prever o risco de rotatividade de seus clientes nos próximos 90 dias para alinhar seus esforços de retenção de marketing. Prever o risco de rotatividade para períodos mais longos ou mais curtos pode dificultar ainda mais a abordagem dos fatores no seu perfil de risco de rotatividade, dependendo dos requisitos comerciais específicos. Selecione **Avançar** para continuar
   >[!TIP]
   > Você pode selecionar **Salvar rascunho** a qualquer momento para salvar o previsão como rascunho. Você encontrará o rascunho da previsão na guia **Minhas previsões** para continuar.

### <a name="add-required-data"></a>Adicionar dados necessários

1. Selecione **Adicionar dados** em **Histórico de assinaturas** e escolha a entidade que fornece as informações do histórico de assinaturas conforme descrito nos [pré-requisitos](#prerequisites).
1. Se os campos abaixo não estiverem preenchidos, configure a relação da entidade do histórico de assinaturas para a entidade do Cliente.
    1. Selecione a **Entidade do histórico de assinaturas**.
    1. Selecione o **Campo** que identifica o cliente na entidade do histórico de assinaturas. Ele precisa estar relacionado à ID do cliente primário da sua entidade Cliente.
    1. Selecione a **Entidade Cliente** que corresponde à entidade do cliente primário.
    1. Insira um nome que descreva a relação.
       > [!div class="mx-imgBorder"]
       > ![Página do histórico de assinaturas que mostra a criação de um relacionamento com o cliente.](media/subscription-churn-subscriptionhistoryrelationship.PNG "Página do histórico de assinaturas que mostra a criação de uma relação com o cliente")
1. Selecione **Avançar**
1. Mapeie os campos semânticos para atributos dentro da entidade do histórico de assinaturas e selecione **Salvar**. Para obter descrições dos campos, observe os [pré-requisitos](#prerequisites).
   > [!div class="mx-imgBorder"]
   > ![Página do histórico de assinaturas que mostra atributos semânticos que são mapeados para campos na entidade do histórico de assinaturas selecionado.](media/subscription-churn-subscriptionhistorymapping.PNG "Página do histórico de assinaturas que mostra atributos semânticos que são mapeados para campos na entidade do histórico de assinaturas selecionado")
1. Selecione **Adicionar dados** em **Atividades do cliente** e escolha a entidade que fornece as informações da atividade do cliente conforme descrito nos pré-requisitos.
1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está configurando.  Selecione **Criar** e forneça um nome caso não encontre uma opção que corresponda ao tipo de atividade do qual precisa.
1. Você precisará configurar a relação da entidade de atividade do cliente com a entidade do Cliente.
    1. Selecione o campo que identifica o cliente na tabela de atividades do cliente, que pode estar relacionada diretamente à ID do cliente primário da entidade do Cliente.
    1. Selecione a entidade do Cliente que corresponda à entidade do Cliente primário
    1. Insira um nome que descreva a relação.
1. Selecione **Avançar**.
1. Mapeie os campos semânticos para atributos dentro da entidade da atividade do cliente e selecione **Salvar**. Para obter descrições dos campos, observe os [pré-requisitos](#prerequisites).
1. (Opcional) Se você tiver outras atividades do cliente que gostaria de incluir, repita as etapas acima.
   > [!div class="mx-imgBorder"]
   > ![Defina o relacionamento da entidade.](media/subscription-churn-customeractivitiesmapping.PNG "Página de atividades do cliente que mostra atributos semânticos que são mapeados para campos na entidade de atividade do cliente")
1. Selecione **Avançar**

### <a name="set-schedule-and-review-configuration"></a>Defina o agendamento e revise a configuração

1. Defina uma frequência para treinar o modelo novamente. Essa configuração é importante para atualizar a precisão das previsões à medida que novos dados são ingeridos nos insights de público-alvo. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.
1. Selecione **Avançar**.
1. Revise a configuração. Você pode voltar para qualquer parte da configuração da previsão selecionando **Editar** abaixo do valor exibido. Ou você pode selecionar uma etapa da configuração no indicador de progresso.
1. Se todos os valores estiverem configurados corretamente, selecione **Salvar e executar** para iniciar o processo de previsão. Na guia **Minhas previsões**, você pode ver o status das previsões. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Revisar o status e os resultados de uma previsão

1. Vá para a guia **Minhas previsões** em **Inteligência** > **Previsões**.
   > [!div class="mx-imgBorder"]
   > ![Exibição da página Minhas Previsões.](media/subscription-churn-mypredictions.PNG "Exibição da página Minhas Previsões")
1. Selecione a previsão que você deseja revisar.
   - **Nome da previsão:** O nome da previsão que foi fornecido ao criá-la.
   - **Tipo de previsão:** O tipo do modelo usado na previsão
   - **Entidade de saída:** Nome da entidade que armazenará a saída da previsão. Você pode encontrar uma entidade com esse nome em **Dados** > **Entidades**.    
     Na entidade de saída, *ChurnScore* é a probabilidade prevista de rotatividade e *IsChurn* é um rótulo binário baseado em *ChurnScore* com limite de 0,5. O limite padrão pode não funcionar para o seu cenário. [Criar um novo segmento](segments.md#create-a-new-segment) com o limite de sua preferência.
   - **Campo previsto:** Este campo é preenchido somente para alguns tipos de previsões e não é usado na previsão de rotatividade de assinaturas.
   - **Status:** O status atual da execução da previsão.
        - **Na fila:** A previsão está aguardando a execução de outros processos.
        - **Atualizando:** A previsão está atualmente executando o estágio de "pontuação" do processamento para gerar resultados que fluirão para a entidade de saída.
        - **Falha:** a previsão falhou. Selecione **Logs** para obter mais detalhes.
        - **Êxito:** a previsão foi bem sucedida. Selecione **Exibir** nos três pontos verticais para revisar a previsão
   - **Editado:** A data em que a configuração da previsão foi alterada.
   - **Última atualização:** A data em que a previsão atualizou resultados na entidade de saída.
1. Selecione os três pontos verticais ao lado da previsão cujos resultados deseja revisar e selecione **Exibir**.
   > [!div class="mx-imgBorder"]
   > ![Exibição das opções no menu de três pontos verticais de uma previsão, que inclui editar, atualizar, exibir, logs e excluir.](media/subscription-churn-verticalellipses.PNG "Exibição das opções no menu de três pontos verticais para uma previsão, incluindo editar, atualizar, exibir, logs e excluir")
1. Há três seções principais de dados na página de resultados:
    1. **Desempenho do modelo de treinamento:** A, B ou C são pontuações possíveis. Essa pontuação indica o desempenho da previsão e pode ajudar você a decidir usar os resultados armazenados na entidade de saída.
        - As pontuações são determinadas com base nas seguintes regras:
            - **A** quando o modelo previu com precisão pelo menos 50% do total de previsões e quando a porcentagem de previsões precisas para clientes com rotatividade for maior que a taxa média histórica de churn, em pelo menos 10% da taxa média histórica de churn.
            - **B** quando o modelo previu com precisão, pelo menos 50% do total de previsões e quando a porcentagem de previsões precisas para clientes com rotatividade for até 10% maior do que a taxa média histórica de churn, da taxa média histórica de churn.
            - **C** quando o modelo previu com precisão menos 50% das previsões totais ou quando a porcentagem de previsões precisas para clientes com rotatividade for menor que a taxa média histórica de churn.
               > [!div class="mx-imgBorder"]
               > ![Exibição do resultado do desempenho do modelo.](media/subscription-churn-modelperformance.PNG "Exibição do resultado de desempenho do modelo")
    1. **Probabilidade de rotatividade (número de clientes):** Grupos de clientes com base no risco previsto de rotatividade. Esses dados podem ajudar você mais tarde, se quiser criar um segmento de clientes com alto risco de rotatividade. Esses segmentos ajudam a entender qual deve ser o limite para a assinatura do segmento.
       > [!div class="mx-imgBorder"]
       > ![Gráfico que mostra a distribuição dos resultados de rotatividade, divididos em intervalos de 0-100%.](media/subscription-churn-resultdistribution.PNG "Gráfico que mostra a distribuição dos resultados de rotatividade, divididos em intervalos de 0-100%")
    1. **Fatores mais influentes:** Muitos fatores são levados em consideração ao criar a previsão. Cada um deles tem a sua importância calculada para as previsões agregadas criadas por um modelo. Você pode usar esses fatores para ajudar a validar os resultados de previsão. Ou você pode usar essas informações posteriormente para [criar segmentos](segments.md) que podem ajudar a influenciar o risco de rotatividade dos clientes.
       > [!div class="mx-imgBorder"]
       > ![Lista que mostra os fatores influentes e a importância deles na previsão de resultados de rotatividade.](media/subscription-churn-influentialfactors.PNG "Lista que mostra os fatores influentes e a respectiva importância deles na previsão de resultados de rotatividade")

## <a name="manage-predictions"></a>Gerenciar previsões

É possível otimizar, solucionar problemas, atualizar ou excluir previsões. Revise um relatório de usabilidade de dados de entrada para descobrir como fazer uma previsão mais rápida e confiável. Para obter mais informações, consulte [Gerenciar previsões](manage-predictions.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]
