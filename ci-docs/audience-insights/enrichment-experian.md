---
title: Enriquecimento com o enriquecimento de terceiros da Experian
description: Informações gerais sobre o enriquecimento de terceiros da Experian.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ad1023135516ca9c49818d19aa84df68d16b2e3c
ms.sourcegitcommit: e7cdf36a78a2b1dd2850183224d39c8dde46b26f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/16/2022
ms.locfileid: "8229950"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriqueça os perfis dos clientes com dados demográficos da Experian (versão preliminar)

Experian é uma líder global em serviços de marketing e relatórios de crédito para consumidores e empresas. Com os serviços de enriquecimento de dados da Experian, você pode obter uma compreensão mais profunda de seus clientes, enriquecendo seus perfis de clientes com dados demográficos, como o tamanho da família, renda e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a Experian, os seguintes pré-requisitos devem ser atendidos:

- Você deve ter uma assinatura ativa da Experian. Para obter uma assinatura, [contate a Experian](https://www.experian.com/marketing-services/contact) diretamente. [Saiba mais sobre o enriquecimento de dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).

- Uma conexão da Experian já foi configurada por um administrador *ou* você tem permissões de [administrador](permissions.md#administrator). Você também precisa da ID do Usuário, da ID do Participante e do número do modelo para sua conta de Transporte Seguro (ST) habilitada para SSH que a Experian criou para você.

## <a name="supported-countriesregions"></a>Países/regiões com suporte

No momento, oferecemos suporte ao enriquecimento de perfis de clientes somente nos Estados Unidos.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** no bloco da Experian.

   > [!div class="mx-imgBorder"]
   > ![Bloco da Experian.](media/experian-tile.png "Experian tile")
   > 

1. Selecione uma [conexão](connections.md) na lista suspensa. Contate um administrador se nenhuma conexão estiver disponível. Se for um administrador, você poderá criar uma conexão selecionando **Adicionar conexão** e escolhendo Experian na lista suspensa. 

1. Selecione **Conectar à Experian** para confirmar a seleção da conexão.

1.  Selecione **Avançar** e escolha o **Conjunto de dados do cliente** que deseja enriquecer com dados demográficos da Experian. Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.

    :::image type="content" source="media/enrichment-Experian-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. Selecione **Avançar** e defina quais tipos de campos de seus perfis unificados devem ser usados para procurar dados demográficos correspondentes na Experian. Pelo menos um dos campos **Nome e endereço**, **Telefone**, ou **E-mail** é necessário. Para uma maior precisão de correspondência, até dois outros campos podem ser adicionados. Esta seleção afetará os campos de mapeamento aos quais você tem acesso na próxima etapa.

    > [!TIP]
    > É provável que mais atributos de identificador de chave enviados para a Experian rendam uma taxa de correspondência mais alta.

1. Selecione **Avançar** para iniciar o mapeamento de campos.

1. Defina quais tipos de campos de seus perfis unificados devem ser usados para procurar dados demográficos correspondentes na Experian. Os campos obrigatórios são marcados.

1. Forneça um nome para o enriquecimento e um nome para a entidade de saída.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

## <a name="configure-the-connection-for-experian"></a>Configurar a conexão para a Experian 

Você deve ser um administrador para configurar as conexões. Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da Experian.

1. Selecione **Começar**.

1. Insira um nome para a conexão na caixa **Nome de exibição**.

1. Insira uma ID de Usuário, uma ID de Participante e um número de modelo válidos para sua conta de Transporte Seguro da Experian.

1. Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** selecionando **Eu concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Salvar**.
   
   :::image type="content" source="media/enrichment-Experian-connection.png" alt-text="Painel de configuração de conexão da Experian":::

## <a name="enrichment-results"></a>Resultados de enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados do cliente e dos processos de enriquecimento configurados para sua conta pela Experian.

Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para a Experian, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que a Experian cumpra quaisquer obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
