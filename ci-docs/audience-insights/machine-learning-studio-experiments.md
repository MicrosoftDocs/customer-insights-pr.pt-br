---
title: Experimentos do Machine Learning Studio (clássico)
description: Use modelos do Machine Learning Studio (clássico) no Dynamics 365 Customer Insights.
ms.date: 12/03/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: m-hartmann
ms.author: mhart
ms.reviewer: ameetj
manager: shellyha
ms.openlocfilehash: 8a861d62bdfee6a3a82468fe1ab4a3fbbdad43d4
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5270190"
---
# <a name="use-models-based-on-azure-machine-learning-studio-classic"></a>Usar modelos baseados no Azure Machine Learning Studio (clássico)

Os dados unificados no Dynamics 365 Customer Insights são uma fonte para a criação de modelos de machine learning que podem gerar insights de negócios adicionais. O Customer Insights integra-se ao Machine Learning Studio (clássico) para usar seus próprios modelos personalizados. Para ver como os modelos desenvolvidos no Azure Machine Learning são integrados ao Customer Insights, consulte [Experimentos do Azure Machine Learning](azure-machine-learning-experiments.md).

## <a name="prerequisites"></a>Pré-requisitos

- Acesso ao Customer Insights
- Ativar assinatura do Azure Enterprise
- [Perfis de cliente unificados](data-unification.md)
- Configuração da [Exportação de entidade para armazenamento de Blob do Azure](export-azure-blob-storage.md)

## <a name="set-up-machine-learning-studio-classic"></a>Configurar o Machine Learning Studio Classic

Em uma primeira etapa, precisamos criar um espaço de trabalho e abrir o Machine Learning Studio (clássico).

1. Vá para [https://www.portal.azure.com](https://www.portal.azure.com/) e entre.

1. Selecione **Criar um recurso**.

1. Procure **Espaço de Trabalho do Machine Learning Studio** e selecione **Criar**.

1. Insira os detalhes necessários para [criar o espaço de trabalho](https://docs.microsoft.com/azure/machine-learning/studio/create-workspace). Escolha o **Tipo de preço do plano do serviço Web** com base na quantidade de dados que você planeja importar. Para um melhor desempenho, selecione o **Local** geograficamente mais próximo de você.

1. Depois de criar o recurso, o painel da área de trabalho Machine Learning Studio aparecerá. Selecione **Lançar Machine Learning Studio**.

   ![Interface do usuário do Azure Machine Learning Studio](media/azure-machine-learning-studio.png)

## <a name="work-with-azure-machine-learning-studio"></a>Trabalhar com o Azure Machine Learning Studio

Agora você pode criar um novo experimento ou importar um modelo de experimento existente da galeria de amostra. Há experimentos de exemplo para três cenários padrão:

- [Previsão de rotatividade](#churn-analysis)

- [Valor do tempo de vida do cliente](#customer-lifetime-value-prediction)

- [Recomendação de produto ou próxima melhor ação](#productrecommendation-or-next-best-action)

1. Se você criar um novo experimento ou usar um modelo de experimento da galeria, será necessário configurar as propriedades **Importar Dados**. Use a experiência guiada ou forneça detalhes diretamente para acessar o Armazenamento de Blobs do Azure que contém seus dados.  

   ![Experimento do Azure Machine Learning Studio](media/azure-machine-learning-studio-experiment.png)

1. Agora você pode construir um pipeline de processamento personalizado para limpar e pré-processar os dados, extrair recursos e adaptar um modelo adequado.

1. Testar e otimizar o desempenho do modelo.

1. Quando estiver satisfeito com a qualidade de um modelo, selecione **Configurar serviço Web** > **Serviço Web Preditivo**. Esta opção importa o modelo adaptado e o pipeline de caracterização do experimento de treinamento para um serviço preditivo. O serviço preditivo pode usar outro conjunto de dados de entrada com o esquema usado no experimento de treinamento para fazer previsões.

   ![Configure um serviço web preditivo](media/predictive-webservice-control.png)

1. Depois que o experimento de serviço web preditivo for bem-sucedido, você pode implantá-lo para agendamento automático. Para que o serviço Web funcione com o Customer Insights, selecione **Implantar Serviço Web** > **Versão Preliminar Implantar Serviço Web [Novo]**. [Saiba mais sobre como implantar um serviço Web](https://docs.microsoft.com/azure/machine-learning/studio/deploy-a-machine-learning-web-service).

   ![Implantar um serviço Web preditivo](media/predictive-webservice-deploy.png)

## <a name="sample-models-from-the-gallery"></a>Modelos de amostra da galeria

Usaremos um cenário fictício do Contoso Hotel para os modelos neste artigo. O Contoso Hotel coleta os seguintes dados:

- Dados de CRM que consistem na atividade de estadia do hotel. O conjunto de dados inclui informações sobre as datas de estadia de cada cliente cadastrado. Ele também contém informações sobre a reserva, tipos de quarto, detalhes de gastos e assim por diante. Os dados abrangem quatro anos, de janeiro de 2014 a janeiro de 2018.
- Perfis de clientes dos hóspedes do hotel. Esses perfis contêm informações sobre cada cliente, incluindo seu nome, data de nascimento, endereço postal, gênero e número de telefone.
- Utilização de serviços oferecidos pelo hotel, como spa, lavanderia, Wi-Fi ou correio. Esta informação é registrada para cada cliente cadastrado. Normalmente, o uso dos serviços está relacionado com a estadia. Em alguns casos, os serviços podem ser usados pelos clientes sem se hospedar no hotel.

## <a name="churn-analysis"></a>Análise de Rotatividade

A análise de rotatividade se aplica a diferentes áreas de negócios. Neste exemplo, vamos examinar a rotatividade de serviços, especificamente no contexto de serviços de hotel, conforme descrito acima. Ele fornece um exemplo prático de um pipeline de modelo de ponta a ponta que pode ser usado como ponto de partida para qualquer outro tipo de modelo de rotatividade.

### <a name="definition-of-churn"></a>Definição de Rotatividade

A definição de rotatividade pode variar de acordo com o cenário. Neste exemplo, um hóspede que não visitou o hotel no último ano deve ser rotulado como hóspede com rotatividade.  

O modelo de experimento pode ser importado da galeria. Primeiro, importe os dados referentes a **Atividade de Estadia no Hotel**, **Dados do cliente** e **Dados de Uso do Serviço** do Armazenamento de Blobs do Azure.

   ![Importar dados para modelo de rotatividade](media/import-data-azure-blob-storage.png)

### <a name="featurization"></a>Definição de recursos

Com base na definição de rotatividade, primeiro identificamos as características brutas que influenciarão o rótulo. Em seguida, processamos esses recursos brutos em recursos numéricos que podem ser usados com modelos de aprendizado de máquina. A integração de dados ocorre no Customer Insights para que possamos unir essas tabelas usando a *ID do Cliente*.

   ![Unir dados importados](media/join-imported-data.png)

A definição de recursos para construir o modelo para análise de rotatividade pode ser um pouco complicada. Os dados são uma função do tempo com novas atividades hoteleiras registradas diariamente. Durante a definição de recursos, queremos gerar recursos estáticos a partir dos dados dinâmicos. Nesse caso, geramos vários recursos da atividade hoteleira com uma janela deslizante de um ano. Também expandimos os recursos categóricos como tipo de quarto ou tipo de reserva em recursos separados usando a codificação one-hot.  

Lista final de recursos:

| **Número:**  | **Original_Column**          | **Recursos Derivados**                                                                                                                      |
|-------------|------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------|
| 1           | Tipo de Sala                    | RoomTypeLargeCount, RoomTypeSmallCount                                                                                                    |
| 2           | Tipo de Reserva                 | BookingTypeOnlineCount, BookingTypePhoneCallCount                                                                                         |
| 3           | Categoria de Viagem              | TravelCategoryBusinessCount, TravelCategoryLeisureCount                                                                                   |
| 4           | Dólares Gastos                | TotalDollarSpent                                                                                                                          |
| 5           | Datas de Check-in e Check-out  | StayDayCount, StayDayCount2016, StayDayCount2015, StayDayCount2014, StayCount, StayCount2016. StayCount2015, StayCount2014                |
| 6           | Uso de Serviço                | UsageTenure, ConciergeUsage, CourierUsage, DryCleaningUsage, GymUsage, PhoneUsage, RestaurantUsage, SpaUsage, TelevisionUsage, WifiUsage  |

### <a name="model-selection"></a>Seleção do modelo

Agora precisamos escolher o algoritmo ideal a ser usado. Nesse caso, a maioria dos recursos é baseada em recursos categóricos. Normalmente, os modelos baseados em árvore de decisão funcionam bem. Se houver apenas recursos numéricos, as redes neurais podem ser uma escolha melhor. A máquina de vetores de suporte (SVM) também é uma boa opção em tais situações; no entanto, é necessário um pouco de ajuste para extrair o melhor desempenho. Escolhemos **Árvore de Decisão Aumentada de Duas Classes** como o primeiro modelo seguido por **SVM de Duas Classes** como o segundo modelo. O Azure Machine Learning Studio permite fazer testes A/B, portanto, é benéfico começar com dois modelos, em vez de um.

A imagem a seguir mostra o pipeline de treinamento e avaliação do modelo do Azure Machine Learning Studio:

![Modelo de rotatividade do Azure Machine Learning Studio](media/azure-machine-learning-model.png)

Também aplicamos uma técnica chamada **Importância do Recurso de Permutação**, um aspecto importante da otimização do modelo. Os modelos integrados têm pouco ou nenhum insight sobre o impacto de qualquer recurso específico na previsão final. A calculadora de importância de recurso usa um algoritmo personalizado para calcular a influência de recursos individuais no resultado de um modelo específico. A importância do recurso é normalizada entre +1 e -1. Uma influência negativa significa que o recurso correspondente tem uma influência contra intuitiva no resultado e deve ser removido do modelo. Uma influência positiva indica que o recurso está contribuindo fortemente para a previsão. Esses valores não são coeficientes de correlação, pois são métricas diferentes. Para obter mais informações, consulte [Importância do Recurso de Permutação](https://docs.microsoft.com/azure/machine-learning/studio-module-reference/permutation-feature-importance).

Todo o [experimento de rotatividade está disponível na Galeria de IA do Azure](https://gallery.azure.ai/Experiment/Hotel-Churn-Predictive-Exp).

## <a name="customer-lifetime-value-prediction"></a>Previsão do valor do tempo de vida do cliente

O cálculo do valor da vida útil do cliente (CLTV) é uma das principais métricas que uma empresa pode usar para avaliar e segmentar seus clientes. Para a hotelaria, é fundamental conhecer os clientes. Por exemplo, compreender os fatores que constituem bons clientes é crucial. Isso ajuda a gerência do hotel a avaliar em quais recursos precisa se concentrar e melhorar para satisfazer seus clientes com altos salários. Essas decisões podem ter um impacto direto nas vendas e nos ganhos.  

### <a name="definition-of-cltv"></a>Definição de CLTV

Para este exemplo, definimos o CLTV de um cliente como o valor total em dólares que ele deve gastar nos próximos 365 dias. Usaremos os dados dos últimos três anos de todos os clientes para prever esse valor.

### <a name="featurization"></a>Definição de recursos

Nesse caso, a definição de recursos vai ser bem parecida com o cenário de rotatividade. No entanto, os rótulos e valores previstos são diferentes dos definidos acima.

### <a name="model-selection"></a>Seleção do modelo

A previsão do CLTV é um problema de regressão, pois o valor previsto é uma variável contínua de valor positivo. Com base nas propriedades do recurso, selecionamos **Regressão de Árvore de Decisão Aumentada** como um algoritmo e **Regressão de Rede Neural** como outro algoritmo para treinar o modelo.

## <a name="product-recommendation-or-next-best-action"></a>Recomendação de produto ou Próxima Melhor Ação

A recomendação de produto em um cenário de hotel é interpretada como recomendação de serviços oferecidos pelo hotel aos clientes. O objetivo é escolher os serviços adequados para os clientes de forma que sua utilização seja maximizada. É semelhante às recomendações de filmes para usuários de serviços de streaming de vídeo.

### <a name="definition-of-product-recommendation-or-next-best-action"></a>Definição de Recomendação de Produto ou Próxima Melhor Ação

Definimos o objetivo como maximizar a quantidade de dólares do uso do serviço, oferecendo os melhores serviços correspondentes aos clientes do hotel de acordo com seus interesses.

### <a name="featurization"></a>Definição de recursos

Como no modelo de rotatividade, estamos unindo o ServiceCustomerID do hotel e o CustomerID para criar recomendações consistentemente por CustomerID.

![Definição de recursos do modelo de recomendação](media/azure-machine-learning-model-featurization.png)

Os dados são originados de três entidades diferentes e os recursos são derivados delas. A definição de recursos para o problema de recomendação é diferente em comparação com cenários de rotatividade ou CLTV. O modelo de recomendação precisa de dados de entrada na forma de três conjuntos de recursos.

### <a name="model-selection"></a>Seleção do modelo

Prevemos produtos ou serviços usando o algoritmo chamado **Treinar Recomendação do Matchbox** para treinar o modelo de recomendação.

![Algoritmo de recomendação do produto](media/azure-machine-learning-model-recommendation-algorithm.png)

As três portas de entrada para o modelo **Treinar Recomendação do Matchbox** incluem os dados de uso do serviço de treinamento, a descrição do cliente (opcional) e a descrição do serviço. Há três maneiras diferentes de pontuar o modelo. Uma é para avaliação do modelo em que uma pontuação de Ganho Cumulativo com Desconto Normalizado (NDCG) é calculada para classificar os itens avaliados. Neste experimento, temos a pontuação NDCG de 0,97. As outras duas opções são pontuar o modelo em todo o catálogo de serviços recomendáveis ou pontuar apenas em itens que os usuários não usaram antes.

Olhando mais adiante nas distribuições das recomendações em todo o catálogo de serviços, notamos que telefone, WiFi e correio são os principais serviços a serem recomendados. Isso é consistente com o que descobrimos nas distribuições dos dados de consumo de serviço:

![Saída do modelo de recomendação](media/azure-machine-learning-model-output.png)

Todo o [experimento de recomendação de produto pode ser acessado na Galeria de IA do Azure.](https://gallery.azure.ai/Experiment/Recommendation-4)

## <a name="integrate-custom-models"></a>Integrar modelos personalizados

Para usar essas previsões no Customer Insights, você precisa **exportar** as previsões junto com as IDs dos clientes. [Exporte-as para o mesmo local de Armazenamento de Blobs do Azure](https://docs.microsoft.com/azure/storage/common/storage-import-export-data-from-blobs) para o qual você exporta os dados de origem. O serviço web preditivo pode ser planejado para ser executado regularmente e atualizar as pontuações.

Os dados gerados pelo modelo personalizado podem ser usados para enriquecer ainda mais os dados dos clientes. Para obter mais informações, consulte [Modelos personalizados de aprendizado de máquina](custom-models.md).


[!INCLUDE[footer-include](../includes/footer-banner.md)]