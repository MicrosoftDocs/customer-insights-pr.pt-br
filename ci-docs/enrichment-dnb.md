---
title: Enriquecimento de perfis de empresas com a Dun & Bradstreet
description: Informações gerais sobre o enriquecimento de terceiros da Dun & Bradstreet.
ms.date: 04/26/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: ecbbf2c94020bf395f4eb70a99a63cea335af2dd
ms.sourcegitcommit: cf74b8c20d88eb96e1ac86e18cd44fe27aad5ab9
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/28/2022
ms.locfileid: "8653693"
---
# <a name="enrichment-of-company-profiles-with-dun--bradstreet-preview"></a>Enriquecimento de perfis de empresas com a Dun & Bradstreet (versão preliminar)

A Dun & Bradstreet fornece dados comerciais, análises e insights para empresas. Ela permite que os clientes com perfis de cliente unificados para as empresas possam enriquecer seus dados. Os enriquecimentos incluem atributos como número DUNS, porte da empresa, localização, setor e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o enriquecimento da Dun & Bradstreet, atenda aos seguintes pré-requisitos:

- Você deve ter uma licença ativa da [Dun & Bradstreet](https://www.dnb.com/marketing/media/give-your-data-a-boost.html?source=microsoft_audience_insights).
- Você ter [perfis unificados de clientes](customer-profiles.md) para empresas.
- A [conexão](connections.md) da Dun & Bradstreet é configurada por um administrador. Você poderá criá-la se tiver permissões de [administrador](permissions.md#admin) e as credenciais do Dun & Bradstreet Connect. 

## <a name="setting-up-your-dun--bradstreet-project"></a>Configurar seu projeto da Dun & Bradstreet

Como usuário licenciado da Dun & Bradstreet, você pode configurar um projeto em [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). 


1. Entre no [Dun & Bradstreet Connect](https://connect.dnb.com?lead_source=microsoft_audienceinsights). Para recuperar credenciais, [restaure sua senha](https://sso.dnb.com/signin/forgot-password?lead_source=microsoft_audienceinsights).

1. Faça download do [nosso arquivo de modelo csv](https://c360devenrichment.blob.core.windows.net/mapping/DnBCIdatamapping.csv) que será usado para mapear os campos de insights do público-alvo para os campos correspondentes da Dun & Bradstreet. 

1. Carregue o arquivo na etapa **Carregar dados** da experiência de criação do projeto Dun & Bradstreet. 

1. Selecione os pontos horizontais na **fonte** relevante no projeto recém-criado da Dun & Bradstreet para ver as opções disponíveis.

   :::image type="content" source="media/enrichment-dnb-dots.png" alt-text="Captura de tela de pontos em um projeto da Dun & Bradstreet.":::

1. Escolha **Obter detalhes do S3**. Armazene essas informações em um local seguro. Você precisará delas para [configurar a conexão para o enriquecimento](#configure-a-connection-for-dun--bradstreet) em insights do público-alvo. 

   :::image type="content" source="media/enrichment-dnb-s3info.png" alt-text="Captura de tela da seleção de informações s3 em um projeto da Dun & Bradstreet.":::



## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Nos insights de público-alvo, vá para **Dados** > **Enriquecimento**.

1. Selecione **Enriquecer meus dados** no bloco Dun & Bradstreet e selecione **Iniciar**.

   :::image type="content" source="media/enrichment-dnb-tile.png" alt-text="Captura de tela do bloco Dun & Bradstreet.":::

1. Selecione uma [conexão](connections.md) na lista suspensa. Contate um administrador se nenhuma conexão estiver disponível. Se você for um administrador, poderá criar uma conexão. Selecione **Adicionar conexão** e escolha **Dun & Bradstreet**. 

1. Selecione **Conectar-se a Dun & Bradstreet** para confirmar a conexão.

1. Selecione **Avançar** e escolha o **Conjunto de dados do cliente** a ser enriquecido com dados da empresa Dun & Bradstreet. Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes unificados contidos nesse segmento.

1. Selecione **Avançar** e defina quais campos de perfis unificados são usados para procurar dados da empresa correspondentes da Dun & Bradstreet. Os campos **Número DUNS** ou **Nome da empresa** e **País** são obrigatórios. O campo país dá suporte a [códigos de país com duas ou três letras](https://www.iso.org/iso-3166-country-codes.html), nome do país em inglês, nome do país no idioma nativo e prefixo do telefone. Algumas variantes de país comuns incluem:

   * EUA: Estados Unidos da América, Estados Unidos, EUA, América.
   * CA: Canadá.
   * GB: Reino Unido, UK, Grã-Bretanha, GB, Reino Unido da Grã-Bretanha e Irlanda do Norte, Reino Unido da Grã-Bretanha.
   * AU: Austrália, Comunidade da Austrália.
   * FR: França, República Francesa.
   * DE: Alemanha, Alemão, Deutschland, Allemagne, República Federal da Alemanha, República da Alemanha.

   :::image type="content" source="media/enrichment-dnb-mapping.png" alt-text="Painel de mapeamento de campo da Dun & Bradstreet.":::

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento e selecione **Salvar enriquecimento** depois de revisar suas escolhas.


## <a name="configure-a-connection-for-dun--bradstreet"></a>Configurar uma conexão para Dun & Bradstreet 

Você deve ser um administrador para configurar as conexões. Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administrador** > **Conexões** e selecione **Configurar** no bloco da Dun & Bradstreet.

1. Selecione **Introdução**. 

1. Insira um nome para a conexão na caixa **Nome de exibição**.

1. Forneça credenciais válidas da Dun & Bradstreet e detalhes do projeto da Dun & Bradstreet *Região, caminho da pasta de destino e nome da pasta de destino*. Você [obtém estas informações](#setting-up-your-dun--bradstreet-project) do projeto da Dun & Bradstreet.

1. Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** selecionando **Eu concordo**.

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Salvar**.
   
   :::image type="content" source="media/enrichment-dnb-connection.png" alt-text="Página de configuração de uma conexão da Dun & Bradstreet.":::

## <a name="enrichment-results"></a>Resultados de enriquecimento

Depois de atualizar o enriquecimento, você pode revisar os dados da empresa recém-enriquecidos em [Meus enriquecimentos](enrichment-hub.md). Você pode encontrar o horário da última atualização e o número de perfis aprimorados.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Dun & Bradstreet, você permite a transferência de dados fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que a Dun & Bradstreet atenda às obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu administrador do Dynamics 365 Customer Insights poderá remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](includes/footer-banner.md)]
