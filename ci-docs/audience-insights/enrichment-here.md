---
title: Enriquecimento com o enriquecimento de terceiros da HERE Technologies
description: Informações gerais sobre o enriquecimento de terceiros da HERE Technologies.
ms.date: 04/09/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahlMSFT
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 5d1f037377010153045c9255d2d01f98ebf1fdfd
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5896037"
---
# <a name="enrichment-of-customer-profiles-with-here-technologies-preview"></a>Enriquecimento de perfis de clientes com a HERE Technologies (versão preliminar)

A HERE Technologies é uma empresa de plataforma de localização que fornece dados e serviços centrados na localização. Com os serviços de enriquecimento de dados da HERE Technologies, você pode criar uma compreensão mais precisa da localização de seus clientes com normalização de endereço, extração de latitude e longitude e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar os enriquecimentos da HERE Technologies, os seguintes pré-requisitos devem ser atendidos:

- Você tem uma assinatura ativa da HERE Technologies. Para obter uma assinatura, você pode [se inscrever aqui](https://developer.here.com/sign-up?utm_medium=referral&utm_source=Microsoft-Dynamics-CI&create=Freemium-Basic) ou [entre contato com a HERE Technologies](https://developer.here.com/help?utm_medium=referral&utm_source=Microsoft-Dynamics-CI#how-can-we-help-you) diretamente. [Saiba mais sobre o enriquecimento de localização da HERE Technologies.](https://developer.here.com/location-enrichment?cid=Dev-MicrosoftDynamics-DB-0-Dev-&utm_source=MicrosoftDynamics&utm_medium=referral&utm_campaign=Online_Dev_ReferralMicrosoft)

- Há uma [conexão](connections.md) da HERE disponível *ou* você tem permissões de [administrador](permissions.md#administrator) e a chave de API da HERE Technologies.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento**. 

1. Selecione **Enriquecer meus dados** no bloco da HERE Technologies e selecione **Começar agora**.

   > [!div class="mx-imgBorder"]
   > ![Bloco da HERE Technologies](media/HERE-tile.png "Bloco da HERE Technologies")

1. Selecione uma [conexão](connections.md) na lista suspensa. Contate um administrador se nenhuma conexão estiver disponível. Se for administrador, você poderá criar uma conexão selecionando **Adicionar conexão**. Escolha **HERE Technologies** no menu suspenso. 

1. Selecione **Conectar-se à HERE Technologies** para confirmar a seleção da conexão.

1.  Selecione **Avançar** e escolha o **Conjunto de dados do cliente** que você deseja enriquecer com os dados de localização da HERE Technologies. Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.

    :::image type="content" source="media/enrichment-HERE-configuration-customer-data-set.png" alt-text="Captura de tela ao escolher o conjunto de dados do cliente.":::

1. Escolha se deseja mapear os campos para o endereço principal e/ou secundário. Você pode especificar um mapeamento de campos para ambos os endereços e enriquecer os perfis para ambos os endereços separadamente. Por exemplo, se houver um endereço residencial e comercial. Selecione **Avançar**.

1. Defina quais campos de seus perfis unificados devem ser usados para procurar dados de localização correspondentes da HERE Technologies. Os campos **Rua 1** e **CEP** são obrigatórios para o endereço principal e/ou secundário selecionado. Para uma maior precisão de correspondência, mais campos podem ser adicionados.

   > [!div class="mx-imgBorder"]
   > ![Página de configuração de enriquecimento da HERE Technologies](media/enrichment-HERE-configuration.png "Página de configuração de enriquecimento da HERE Technologies")

1. Selecione **Avançar** para concluir o mapeamento de campos.

1. Forneça um nome para o enriquecimento. 

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

## <a name="configure-the-connection-for-here-technologies"></a>Configurar a conexão para a HERE technologies 

Você deve ser um administrador para configurar as conexões. Selecione **Adicionar conexão** ao configurar um enriquecimento *ou* acesse **Administração** > **Conexões** e selecione **Configurar** no bloco da HERE technologies.

1. Insira um nome para a conexão na caixa **Nome de exibição**.

1. Forneça uma chave de API da HERE Technologies válida.

1. Revise e forneça seu consentimento para a **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**

1. Selecione **Verificar** para validar a configuração.

1. Depois de concluir a verificação, selecione **Salvar**.

> [!div class="mx-imgBorder"]
   > ![Página de configuração de conexão da HERE technologies](media/enrichment-HERE-connection.png "Página de configuração de conexão da HERE technologies")

## <a name="enrichment-results"></a>Resultados de enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados do cliente e dos tempos de resposta da API da HERE Technologies.

Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à HERE Technologies, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a HERE Technologies cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
