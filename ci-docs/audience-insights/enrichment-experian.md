---
title: Enriquecimento com o enriquecimento de terceiros da Experian
description: Informações gerais sobre o enriquecimento de terceiros da Experian.
ms.date: 12/10/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 4d4723e8f793ee857c4f5204a42be8338c71d4c3
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5597773"
---
# <a name="enrich-customer-profiles-with-demographics-from-experian-preview"></a>Enriquecer os perfis dos clientes com dados demográficos da Experian (versão preliminar)

A Experian é líder global em serviços de marketing e relatórios de crédito para consumidores e empresas. Com os serviços de enriquecimento de dados da Experian, você pode compreender melhor seus clientes enriquecendo os perfis desses clientes com dados demográficos, como número de pessoas na família, renda e muito mais.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar a Experian, os seguintes pré-requisitos devem ser atendidos:

- Você ter uma assinatura ativa da Experian. Para obter uma assinatura, [entre em contato com a Experian](https://www.experian.com/marketing-services/contact) diretamente. [Saiba mais sobre o Enriquecimento de Dados da Experian](https://www.experian.com/marketing-services/microsoft?cmpid=ems_web_mci_cdppage).
- Você ter a ID de Usuário, a ID do Participante e o Número do Modelo da conta de Transporte Seguro (ST) habilitada para SSH que a Experian criou para você.
- Você tem permissões de [Administrador](permissions.md#administrator) em insights de público-alvo.

## <a name="configuration"></a>Configuração

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** no bloco da Experian.

   > [!div class="mx-imgBorder"]
   > ![Bloco da Experian](media/experian-tile.png "Bloco da Experian")

1. Selecione **Começar** e insira a ID de Usuário, a ID do Participante e o Número do Modelo da sua conta de Transporte Seguro da Experian. Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**. Confirme todas as entradas selecionando **Aplicar**.

## <a name="map-your-fields"></a>Mapear seus campos

1.  Selecione **Adicionar dados** e escolha o **Conjunto de dados do cliente** que deseja enriquecer com dados demográficos da Experian. Você pode selecionar a entidade **Cliente** para enriquecer todos os perfis de cliente ou selecionar uma entidade de segmento para enriquecer apenas perfis de clientes contidos nesse segmento.

1. Selecione os identificadores de chave de **Nome e Endereço**, **Email** ou **Telefone** para enviar à Experian para resolução de identidade.

   > [!TIP]
   > Mais atributos de identificadores de chave enviados à Experian provavelmente geram uma taxa de correspondência mais alta.

1. Selecione **Avançar** e mapeie os atributos correspondentes da sua entidade de cliente unificada para os campos de identificadores de chave selecionados.

1. Selecione **Adicionar atributo** para mapear quaisquer atributos adicionais que você gostaria de enviar à Experian.

1.  Selecione **Salvar** para concluir o mapeamento de campo.

    > [!div class="mx-imgBorder"]
    > ![Mapeamento de campos da Experian](media/experian-field-mapping.png "Mapeamento de campos da Experian")

## <a name="enrichment-results"></a>Resultados de enriquecimento

Para iniciar o processo de enriquecimento, selecione **Executar** na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). O tempo de processamento dependerá do tamanho dos dados dos clientes e dos processos de enriquecimento configurados para sua conta pela Experian.

Após a conclusão do processo de enriquecimento, você poderá analisar os dados dos perfis de clientes recém-enriquecidos em **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos.

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**.

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Crie [segmentos](segments.md), [medidas](measures.md), e até mesmo [exporte os dados](export-destinations.md) para oferecer experiências personalizadas aos seus clientes.

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados à Experian, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que a Experian cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]