---
title: Enriquecimento de perfis de empresas com a Dun & Bradstreet
description: Informações gerais sobre o enriquecimento de terceiros da Dun & Bradstreet.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: b1038970b6aee3bbdd7f79cc457f79aaf1c38222
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8953877"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enriquecimento de perfis de empresas com a Dun & Bradstreet (versão preliminar)

A Dun & Bradstreet fornece dados comerciais, análises e insights para empresas. Ela permite que os clientes com perfis de cliente unificados para as empresas possam enriquecer seus dados. Os enriquecimentos incluem atributos como número DUNS, porte da empresa, localização, setor e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

- Uma licença ativa da [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- [Perfis de clientes unificados](customer-profiles.md) para empresas.
- Um [projeto](#set-up-your-dun--bradstreet-project) da Dun & Bradstreet foi configurado.
- Uma [conexão](connections.md) da Dun & Bradstreet foi [configurada](#configure-a-connection-for-dun--bradstreet) por um administrador.

## <a name="set-up-your-dun--bradstreet-project"></a>Configurar seu projeto da Dun & Bradstreet

Como usuário licenciado da Dun & Bradstreet, você pode configurar um projeto em [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights).

1. Entre no [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Para recuperar credenciais, [restaure sua senha](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Faça download do [nosso arquivo de modelo csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) que será usado para mapear os campos de Customer Insights para os campos correspondentes da Dun & Bradstreet.

1. Carregue o arquivo na etapa **Carregar dados** da experiência de criação do projeto Dun & Bradstreet.

1. Selecione os pontos horizontais na **fonte** relevante no projeto recém-criado da Dun & Bradstreet para ver as opções disponíveis.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de tela de pontos em um projeto da Dun & Bradstreet.":::

1. Escolha **Obter detalhes do S3**. Armazene essas informações em um local seguro. Você precisará delas para [configurar a conexão para o enriquecimento](#configure-a-connection-for-dun--bradstreet) no Customer Insights.

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de tela da seleção de informações s3 em um projeto da Dun & Bradstreet.":::

## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurar uma conexão para Dun & Bradstreet

Você deve ser [administrador](permissions.md#admin) no Customer Insights e ter as credenciais do Dun & Bradstreet Connect.

1. Selecione **Adicionar conexão** ao configurar um enriquecimento ou acesse **Administrador** > **Conexões** e selecione **Configurar** no bloco da Dun & Bradstreet.

1. Insira um nome para a conexão.

1. Forneça credenciais válidas da Dun & Bradstreet e detalhes do projeto da Dun & Bradstreet *Região, caminho da pasta de destino e nome da pasta de destino*. Você [obtém estas informações](#set-up-your-dun--bradstreet-project) do projeto da Dun & Bradstreet.

1. Revise e forneça seu consentimento para a [Conformidade e privacidade dos dados](#data-privacy-and-compliance) selecionando **Eu concordo**.

1. Selecione **Verificar** para validar a configuração e, em seguida, selecione **Salvar**.

   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Página de configuração de uma conexão da Dun & Bradstreet.":::

### <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Dun & Bradstreet, você permite a transferência de dados fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que a Dun & Bradstreet atenda às obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.

## <a name="supported-countries-or-regions"></a>Países ou regiões com suporte

No momento, oferecemos suporte às seguintes opções de país/região: Canadá (inglês) ou Estados Unidos (inglês).

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** em **Dados da empresa** do bloco da Dun & Bradstreet.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de tela do bloco Dun & Bradstreet.":::

1. Revise a visão geral e selecione **Avançar**.

1. Selecione a conexão e confirme. Entre em contato com um administrador se não houver um disponível.

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do cliente** e escolha o perfil ou segmento que deseja enriquecer com dados da empresa da Dun & Bradstreet. A entidade *Cliente* enriquece todos os perfis de cliente enquanto um segmento enriquecer apenas perfis de clientes contidos nesse segmento.

1. Defina que tipo de campos de seus perfis unificados devem usar para fazer a correspondência de dados da empresa da Dun & Bradstreet. Pelo menos um dos campos **Nome e endereço**, **Telefone**, ou **E-mail** é necessário.

1. Selecione **Avançar**.

1. Mapeie os campos para os dados da empresa da Dun & Bradstreet. Os campos **Número DUNS** ou **Nome da empresa** e **País** são obrigatórios.

      :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Painel de mapeamento de campo da Dun & Bradstreet.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um **Nome** para o enriquecimento e o **Nome da entidade de saída**.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Executar** para iniciar o processo de enriquecimento ou feche para voltar para a página **Enriquecimentos**.

## <a name="enrichment-results"></a>Resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)]

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

[!INCLUDE[footer-include](includes/footer-banner.md)]
