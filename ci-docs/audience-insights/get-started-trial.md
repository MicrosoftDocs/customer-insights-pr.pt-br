---
title: Criar e configurar uma avaliação do Customer Insights
description: Etapas para obter uma assinatura de avaliação do Dynamics 365 Customer Insights e configurá-lo.
ms.date: 07/22/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: MichelleDevaney
ms.author: midevane
manager: shellyha
ms.custom: intro-internal
ms.openlocfilehash: f80654f03252142ce08241ff3ca3606be4595740
ms.sourcegitcommit: 5c9c54ffe045017c19f0042437ada2c101dcaa0f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/22/2021
ms.locfileid: "6650443"
---
# <a name="set-up-a-trial-environment"></a>Configurar um ambiente de avaliação 

Uma avaliação do Dynamics 365 Customer Insights permite que você analise as principais funcionalidades e saiba mais sobre os vários recursos. A assinatura de avaliação é excluída depois que expira. Os ambientes de avaliação são criados por usuários individuais que se tornam administradores do ambiente de avaliação. Eles podem convidar mais usuários para a avaliação e configurar os vários recursos.

## <a name="create-a-trial-environment"></a>Criar um ambiente de avaliação

Você pode se inscrever em uma avaliação na [página de inscrição de avaliação](https://dynamics.microsoft.com/get-started/free-trial/?appname=customerinsights). 

1. Escolha a opção **Inscrever-se em uma avaliação gratuita** e selecione **Inscrever-se agora**.

1. Forneça seu endereço de email corporativo ou de estudante, conte-nos mais sobre você e selecione **Introdução**.

   :::image type="content" source="media/trial-signup-dialog.png" alt-text="Caixa de diálogo para se inscrever em uma instância de avaliação":::

1. Examine os termos e condições e selecione **Concordo** para confirmar.

1. Forneça um **Nome** para o novo ambiente. 

1. Defina o **Tipo** de ambiente como **Avaliação**.

1. No campo **Selecione uma demonstração de setor**, você pode opcionalmente escolher um conjunto de dados específico do setor. Você também pode [alterar para uma demonstração do setor](#use-industry-specific-demo-data-sets-in-audience-insights) posteriormente e começar com o conjunto de dados padrão.

1. Escolha a **Região** para o ambiente.

1. Opcionalmente, se você for o administrador de uma organização do Dynamics 365: selecione **Configurações avançadas** e forneça a URL de sua organização para usar recursos de previsão, como a previsão de rotatividade de clientes. 

1. Selecione **Criar**. 

A conclusão da configuração do ambiente leva alguns instantes. Após a conclusão, você será redirecionado para o ambiente de demonstração ou para a demonstração do setor que você escolheu na etapa acima. Agora você pode explorar o aplicativo com dados de demonstração somente leitura. Para adicionar seus próprios dados ao ambiente, consulte [Criar dados de demonstração específicos do cenário em seu próprio ambiente](#create-scenario-specific-demo-data-in-your-own-environment).

:::image type="content" source="media/trial-environment.png" alt-text="Captura de tela de um ambiente de avaliação recém-criado.":::

## <a name="use-industry-specific-demo-data-sets-in-audience-insights"></a>Usar conjuntos de dados de demonstração específicos do setor em insights de público-alvo

Conectar fontes de dados reais é uma das etapas essenciais no uso do poder do Customer Insights. Para experimentar os recursos sem interferir em seus próprios dados, você pode usar, opcionalmente, dados de demonstração específicos do setor. Existem alguns conjuntos de dados de demonstração disponíveis para os seguintes setores: 

-   Automotivo
-   Bancos
-   Bens de consumo
-   Administração Pública
-   Serviços de Saúde
-   Hotéis e Restaurantes
-   Seguros
-   Fabricação
-   Serviços profissionais
-   Varejo

### <a name="see-industry-specific-demo-data-in-trials"></a>Veja os dados de demonstração específicos do setor em avaliações

Para obter uma versão somente leitura do Customer Insights, adaptada a um setor ou cenário específico, comece no ambiente de demonstração. 
 
1.  Nos insights de público-alvo, escolha o ambiente **Demonstração** no seletor de ambiente.

2.  Na **Página Inicial**, escolha uma opção no menu suspenso Selecionar uma demonstração do setor.

:::image type="content" source="media/trial-select-industry-demo.png" alt-text="Escolha um setor para o ambiente de avaliação.":::

### <a name="create-scenario-specific-demo-data-in-your-own-environment"></a>Criar dados de demonstração específicos do cenário em seu próprio ambiente

Como administrador, selecione o seletor de ambiente no cabeçalho do aplicativo para criar um ambiente. No novo ambiente, você pode configurar suas próprias fontes de dados e configurar o aplicativo de acordo com seus requisitos. 

1.  Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.

2.  Para importar suas próprias fontes de dados, acesse o [guia sobre ingestão de dados](data-sources.md).     
   Se preferir trabalhar com dados de exemplo que permitem experimentar a ingestão de dados, você poderá ingerir os dados de demonstração do setor em seu ambiente. Escolha a opção **Importar do Datahub** e siga as etapas abaixo.

3.  Selecione o cartão do setor que se adapte ao seu cenário. 

4.  Examine e, opcionalmente, atualize o nome sugerido da fonte de dados. 

5.  Selecione **Avançar** para ingerir os dados de exemplo. 

Agora, você pode usar os dados ingeridos para adaptar o Customer Insights ao seu cenário. Para ver um ambiente específico para os dados de demonstração ingeridos, escolha a opção **Demonstração de <Industry>** no seletor de ambiente.

## <a name="limitations-in-trials"></a>Limitações nas avaliações

- As avaliações ficam ativas por 30 dias por padrão. No entanto, você poderá estendê-las após o 23º dia, quando entrar na avaliação.
- Não é possível usar sua própria conta de armazenamento do Azure Data Lake para armazenar dados de saída durante uma avaliação. No entanto, você pode ingerir dados de uma conta de armazenamento do Data Lake.
- É possível armazenar até 3 GB de dados no ambiente do Dataverse que é provisionado automaticamente quando você inicia uma avaliação do Customer Insights.

## <a name="copy-data-from-a-trial-to-a-paid-subscription"></a>Copiar os dados de uma avaliação em uma assinatura paga

Geralmente, recomendamos começar do zero com seus próprios dados ao atualizar para a versão paga do Customer Insights. 

Opcionalmente, você pode copiar os dados de um ambiente de avaliação se você comprar o Customer Insights. Você deve ser o administrador da avaliação do Customer Insights e o administrador global de seu locatário do Microsoft 365 ou o administrador do Dynamics 365 em sua organização para migrar as configurações de um ambiente de avaliação para um ambiente pago. 

Depois que entrar em sua instância paga do Customer Insights pela primeira vez, você será solicitado a criar um ambiente. Nesse processo, você poderá optar por copiar a configuração de um ambiente existente e migrar a maioria das configurações. Se você tiver as permissões mencionadas acima, o ambiente de avaliação aparecerá nesta lista. Para obter mais informações, consulte [Copiar a configuração do ambiente](manage-environments.md#copy-the-environment-configuration).

## <a name="next-steps"></a>Próximas etapas

Examine os artigos a seguir para ajudá-lo a começar a configurar o Customer Insights. 

- [Adicionar mais usuários e atribuir permissões](permissions.md).
- [Ingerir suas fontes de dados](data-sources.md) e executá-las por meio do [processo de unificação de dados](data-unification.md) para obter [perfis de clientes unificados](customer-profiles.md).
- [Enriquecer os perfis de clientes unificados](enrichment-hub.md) ou [executar modelos preditivos](predictions-overview.md).
- Criar [segmentos](segments.md) para agrupar clientes e KPIs de análise de [medidas](measures.md).
- Configurar [conexões](connections.md) e [exportações](export-destinations.md) para processar subconjuntos de seus dados em outros aplicativos.