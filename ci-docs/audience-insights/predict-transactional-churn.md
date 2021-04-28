---
title: Previsão de rotatividade transacional
description: Preveja se um cliente está em risco de não comprar mais seus produtos ou serviços.
ms.date: 11/12/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: zacookmsft
ms.author: zacook
manager: shellyha
ms.openlocfilehash: 43fcd37f8dd71e2890334a4cc53d49dae97d63c6
ms.sourcegitcommit: 6d5dd572f75ba4c0303ec77c3b74e4318d52705c
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/16/2021
ms.locfileid: "5906842"
---
# <a name="transactional-churn-prediction-preview"></a>Previsão de rotatividade transacional (versão preliminar)

A previsão de rotatividade transacional ajuda a prever se um cliente não comprará mais seus produtos ou serviços em uma determinada janela de tempo. Você pode criar novas previsões de rotatividade em **Inteligência** > **Previsões**. Selecione **Minhas previsões** para ver outras previsões que você criou.

> [!TIP]
> Experimente o tutorial para uma previsão de rotatividade transacional usando dados de exemplo: [Guia de exemplo para previsão de rotatividade transacional (versão preliminar)](sample-guide-predict-transactional-churn.md).

## <a name="prerequisites"></a>Pré-requisitos

- Por último, [Permissões de colaborador](permissions.md) em Customer Insights.
- Conhecimento de negócios para entender o que rotatividade significa para o seu negócio. Oferecemos suporte a definições de rotatividade baseadas em tempo, ou seja, um cliente é considerado um cliente com rotatividade após um período sem compras.
- Dados sobre as transações/compras e seu histórico:
    - Identificadores de transação para distinguir compras/transações.
    - Identificadores de cliente para corresponder transações aos seus clientes.
    - Datas dos eventos de transação, que definem as datas em que a transação ocorreu.
    - O esquema de dados semânticos para compras/transações requer as seguintes informações:
        - **ID da transação:** um identificador exclusivo de uma compra ou transação.
        - **Data da transação:** a data da compra ou transação.
        - **Valor da transação:** a quantia em moeda/valor numérico da transação/item.
        - (Opcional) **ID exclusiva do produto:** a ID do produto ou serviço adquirido se os seus dados estiverem em um nível de item de linha.
        - (Opcional) **Se esta transação foi uma devolução:** um campo verdadeiro/falso que identifica se a transação foi uma devolução ou não. Se o **Valor da transação** for negativo, também usaremos essa informação para inferir uma devolução.
- (Opcional) Dados sobre atividades do cliente:
    - Identificadores de atividades para diferenciar atividades do mesmo tipo.
    - Identificadores de clientes para mapear atividades para os clientes.
    - Informações de atividades que contêm o nome e a data da atividade.
    - O esquema de dados semânticos para atividades do cliente inclui:
        - **Chave primária:** Um identificador exclusivo para uma atividade. Por exemplo, uma visita a um site ou um registro de uso mostrando que o cliente experimentou uma amostra do seu produto.
        - **Carimbo de data/hora:** A data e a hora do evento identificado pela chave primária.
        - **Evento:** O nome do evento que você deseja usar. Por exemplo, um campo denominado "UserAction" em um supermercado pode ser um cupom usado pelo cliente.
        - **Detalhes:** Informações detalhadas sobre o evento. Por exemplo, um campo denominado "CouponValue" em um supermercado pode ser o valor da moeda do cupom.
- Características de dados sugeridas:
    - Dados históricos suficientes: dados de transação de pelo menos o dobro da janela de tempo selecionada. De preferência, de dois a três anos de dados de assinatura. 
    - Várias compras por cliente: idealmente, pelo menos duas transações por cliente.
    - Número de clientes: pelo menos 10 perfis de clientes, de preferência mais de 1.000 clientes exclusivos. O modelo falhará com menos de 10 clientes e dados históricos insuficientes.
    - Integridade dos dados: menos de 20% de valores ausentes no campo de dados da entidade fornecida.

> [!NOTE]
> Para uma empresa com alta frequência de compra pelos clientes (em intervalos de algumas semanas), é recomendável selecionar uma janela de previsão e uma definição de rotatividade mais curtas. Para baixa frequência de compra (em intervalos de alguns meses ou uma vez por ano), escolha uma janela de previsão e uma definição de rotatividade mais longas.

## <a name="create-a-transactional-churn-prediction"></a>Criar uma previsão de rotatividade transacional

1. No Customer Insights, acesse **Inteligência** > **Previsões**.

1. Selecione o bloco **Modelo de rotatividade de clientes (versão preliminar)** e, em seguida, selecione **Usar este modelo**.
   
1. No painel do **Modelo de rotatividade de clientes**, escolha **Transacional** e selecione **Começar**.

:::image type="content" source="media/select-transaction-churn.PNG" alt-text="Captura de tela com a opção transacional selecionada no painel do Modelo de rotatividade de clientes.":::

### <a name="name-model"></a>Nomear modelo

1. Forneça um nome para o modelo para diferenciá-lo dos outros modelos.

1. Forneça um nome para a entidade de saída usando somente letras e números, sem espaços. Esse é o nome que a entidade de modelo usará. 

1. Selecione **Avançar**.

### <a name="define-customer-churn"></a>Definir rotatividade de clientes

1. Defina uma janela de dias para prever a rotatividade no campo **Identificar os clientes que podem apresentar rotatividade no próximo**. Por exemplo, preveja o risco de rotatividade para seus clientes nos próximos 90 dias a fim de alinhá-lo aos seus esforços de retenção de marketing. A previsão do risco de rotatividade para um período mais longo ou mais curto pode dificultar a abordagem dos fatores no seu perfil de risco de rotatividade, mas depende dos requisitos comerciais específicos. 
   >[!TIP]
   > Você pode selecionar **Salvar e fechar** a qualquer momento para salvar a previsão como rascunho. Você encontrará o rascunho da previsão na guia **Minhas previsões** para continuar.

1. Insira o número de dias para definir a rotatividade no campo **Um cliente apresenta rotatividade quando não faz compras em:**. Por exemplo, se um cliente não fez compras nos últimos 30 dias, ele pode ser considerado como um cliente com rotatividade para sua empresa. 

1. Selecione **Avançar** para continuar

### <a name="add-required-data"></a>Adicionar dados obrigatórios

1. Selecione **Adicionar dados** para **Histórico de compras** e escolha a entidade que fornece as informações do histórico de transações/compras, conforme descrito nos [pré-requisitos](#prerequisites).

1. Mapeie os campos semânticos para atributos na sua entidade do histórico de compras e selecione **Avançar**. Para obter descrições dos campos, observe os [pré-requisitos](#prerequisites).

   :::image type="content" source="media/model-map-purchase-entity.PNG" alt-text="Mapear os campos semânticos da entidade de compra.":::

1. Se os campos abaixo não estiverem preenchidos, configure o relacionamento da sua entidade do histórico de compras com a entidade Cliente.
    1. Selecione a **Entidade do histórico de compras**.
    1. Selecione o **Campo** que identifica o cliente na entidade do histórico de compras. Ele precisa estar relacionado à ID do cliente primário da sua entidade Cliente.
    1. Selecione a **Entidade Cliente** que corresponde à entidade do cliente primário.
    1. Insira um nome que descreva a relação.

    :::image type="content" source="media/model-purchase-join.PNG" alt-text="Página do histórico de compras mostrando a criação de um relacionamento com o cliente.":::
   
1. Selecione **Avançar**.

1. Opcionalmente, selecione **Adicionar dados** para **Atividades do cliente**. Escolha a entidade que fornece as informações de atividades do cliente conforme descrito nos pré-requisitos.

1. Mapeie os campos semânticos para atributos na sua entidade de atividades do cliente e selecione **Avançar**. Para obter descrições dos campos, observe os [pré-requisitos](#prerequisites).

   :::image type="content" source="media/map-transaction-data-fields.png" alt-text="Mapeie os campos do cliente para dados transacionais.":::

1. Selecione um tipo de atividade que corresponda ao tipo de atividade do cliente que está configurando. Selecione **Criar novo** e escolha um tipo de atividade disponível ou crie um novo.

1. Você precisará configurar a relação da entidade de atividade do cliente com a entidade do Cliente.
    1. Selecione o campo que identifica o cliente na tabela de atividades do cliente. Ele pode estar diretamente relacionado à ID do cliente principal da sua entidade Cliente.
    1. Selecione a entidade do Cliente que corresponda à entidade do Cliente primário
    1. Insira um nome que descreva a relação.

1. Selecione **Salvar**.

1. Se você tiver outras atividades do cliente que gostaria de incluir, repita as etapas acima.

1. Selecione **Avançar**.

### <a name="set-schedule-and-review-configuration"></a>Defina o agendamento e revise a configuração

1. Defina uma frequência para treinar o modelo novamente. Essa configuração é importante para atualizar a precisão das previsões à medida que novos dados são ingeridos. A maioria das empresas pode realizar o treinamento novamente uma vez por mês e obter uma boa precisão para suas previsões.

1. Selecione **Avançar**.

1. Revise a configuração da previsão. Você pode voltar às etapas anteriores selecionando **Editar** sob o valor mostrado. Ou você pode selecionar uma etapa da configuração no indicador de progresso.

1. Se todos os valores estiverem configurados corretamente, selecione **Salvar e executar** para iniciar o processo de previsão. Na guia **Minhas previsões**, você pode ver o status das previsões. O processo pode demorar várias horas para ser concluído, dependendo da quantidade de dados usados na previsão.

## <a name="review-a-prediction-status-and-results"></a>Revisar o status e os resultados de uma previsão

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione a previsão que você deseja revisar.
   - **Nome da previsão:** nome da previsão fornecido ao criá-la.
   - **Tipo de previsão:** tipo de modelo usado para a previsão
   - **Entidade de saída:** Nome da entidade que armazenará a saída da previsão. Você pode encontrar uma entidade com esse nome em **Dados** > **Entidades**.    
     Na entidade de saída, *ChurnScore* é a probabilidade prevista de rotatividade e *IsChurn* é um rótulo binário baseado em *ChurnScore* com limite de 0,5. O limite padrão pode não funcionar para o seu cenário. [Criar um novo segmento](segments.md#create-a-new-segment) com o limite de sua preferência.
     Nem todos os clientes são necessariamente clientes ativos. Alguns deles podem não ter tido nenhuma atividade por um longo período e já são considerados com rotatividade, com base na sua definição de rotatividade. Prever o risco de rotatividade para clientes que já apresentaram rotatividade não é útil porque eles não são o público de interesse.
   - **Campo previsto:** este campo é preenchido apenas para alguns tipos de previsões e não é usado na previsão de rotatividade.
   - **Status:** status da execução da previsão.
        - **Enfileirada:** a previsão está aguardando a execução de outros processos.
        - **Atualizando:** a previsão está em execução no momento para produzir resultados que fluirão para a entidade de saída.
        - **Falha:** a execução da previsão falhou. [Analisar os logs](#troubleshoot-a-failed-prediction) para obter mais detalhes.
        - **Êxito:** a previsão teve êxito. Selecione **Exibir** nos três pontos verticais para revisar a previsão
   - **Editado:** A data em que a configuração da previsão foi alterada.
   - **Última atualização:** A data em que a previsão atualizou resultados na entidade de saída.

1. Selecione os três pontos verticais ao lado da previsão cujos resultados deseja revisar e selecione **Exibir**.

   :::image type="content" source="media/model-subs-view.PNG" alt-text="Exibir controle para ver os resultados de uma previsão.":::   

1. Há três seções principais de dados na página de resultados:
    1. **Desempenho do modelo de treinamento:** A, B ou C são pontuações possíveis. Essa pontuação indica o desempenho da previsão e pode ajudar você a decidir usar os resultados armazenados na entidade de saída. As pontuações são determinadas com base nas seguintes regras:
         
         - **A** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é maior do que a taxa de linha de base em pelo menos 10%.
            
         - **B** quando o modelo previu com precisão pelo menos 50% das previsões totais e quando a porcentagem de previsões precisas para clientes com rotatividade é até 10% maior do que a linha de base.
            
         - **C** quando o modelo previu com precisão menos de 50% das previsões totais ou quando a porcentagem de previsões precisas para clientes com rotatividade é menor do que a linha de base.
               
         - A **linha de base** usa a entrada de janela de tempo da previsão para o modelo (por exemplo, um ano) e o modelo cria diferentes frações de tempo dividindo-a por 2 até atingir um mês ou menos. Ele usa essas frações para criar uma regra de negócios para clientes que não compraram nesse período. Esses clientes são considerados clientes com rotatividade. A regra de negócios baseada em tempo com a maior capacidade de prever quem tem propensão à rotatividade é escolhida como modelo de linha de base.
            
    1. **Probabilidade de rotatividade (número de clientes):** Grupos de clientes com base no risco previsto de rotatividade. Esses dados podem ajudar você mais tarde, se quiser criar um segmento de clientes com alto risco de rotatividade. Esses segmentos ajudam a entender qual deve ser o limite para a assinatura do segmento.
       
    1. **Fatores mais influentes:** Muitos fatores são levados em consideração ao criar a previsão. Cada um dos fatores tem sua importância calculada para as previsões agregadas que um modelo cria. Você pode usar esses fatores para ajudar a validar os resultados de previsão. Ou você pode usar essas informações posteriormente para [criar segmentos](segments.md) que podem ajudar a influenciar o risco de rotatividade dos clientes.

## <a name="troubleshoot-a-failed-prediction"></a>Solucionar uma previsão com falha

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione as reticências verticais ao lado da previsão para a qual deseja exibir os logs de erros.

1. Selecione **Logs**.

1. Revise todos os erros. Há vários tipos de erros que podem ocorrer e eles descrevem qual condição causou o erro. Por exemplo, um erro causado por dados insuficientes para gerar uma previsão de forma precisa é geralmente resolvido ao carregar dados adicionais no Customer Insights.

## <a name="refresh-a-prediction"></a>Atualizar uma previsão

As previsões serão atualizadas automaticamente no mesmo [cronograma de atualização dos dados](system.md#schedule-tab) conforme definido nas configurações. Você também pode atualizá-las manualmente.

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione os três pontos verticais ao lado da previsão que deseja atualizar.

1. Selecione **Atualizar**.

## <a name="delete-a-prediction"></a>Excluir uma previsão

A exclusão de uma previsão também remove sua entidade de saída.

1. Vá para **Inteligência** > **Previsões** e selecione a guia **Minhas previsões**.

1. Selecione os três pontos verticais ao lado da previsão que deseja excluir.

1. Selecione **Excluir**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
