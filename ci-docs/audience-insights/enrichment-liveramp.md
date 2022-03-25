---
title: Enriquecimento de dados de identidade do LiveRamp
description: Enriqueça perfis de clientes com dados do LiveRamp.
ms.date: 03/02/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: ee65cb49447df61dd5c298a84ad21bc119ead558
ms.sourcegitcommit: bb1f9e96023490ab340c114f54200ab4dd48da78
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "8373005"
---
# <a name="enrich-customer-profiles-with-identity-data-from-liveramp-preview"></a>Enriquecer perfis dos clientes com dados de identidade do LiveRamp (versão preliminar) 

O LiveRamp fornece resolução de identidade offline determinada e consolidação de dados do cliente. Você pode mapear identificadores pessoais em seus dados de cliente para o gráfico de identidade da AbiliTec e receber IDs da AbiliTec. Você pode usar essas IDs para uma unificação melhor dos dados de seus clientes. 

## <a name="prerequisites"></a>Pré-requisitos 

Para configurar o enriquecimento, os seguintes pré-requisitos devem ser atendidos: 

- Você tem uma assinatura ativa do LiveRamp. Para obter uma assinatura, entre em contato com a equipe da sua conta LiveRamp ou pelo email [dynamics@liveramp.com](mailto:dynamics@liveramp.com) para saber mais.   

- Uma assinatura ativa da AbiliTec com uma ID do cliente e segredo para acessar a API. Para obter mais informações, consulte [Hub dos desenvolvedores da API da AbiliTec](https://developers.liveramp.com/abilitec-api/). 

## <a name="supported-countriesregions"></a>Países/regiões com suporte 

Atualmente, oferecemos suporte ao enriquecimento de perfis de clientes com dados do LiveRamp apenas nos Estados Unidos. 

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento 

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**. 

1. Selecione **Enriquecer meus dados** no bloco **Identidade**. 

   :::image type="content" source="media/liveramp-tile.png" alt-text="Bloco de identidade na página de visão geral do enriquecimento. ":::

1. Selecione uma [conexão](connections.md) na lista suspensa. Contate um administrador se nenhuma conexão estiver disponível. Se você for um administrador, poderá criar uma conexão selecionando **Adicionar conexão**. Selecione **LiveRamp** na lista suspensa. 

1. Selecione **Avançar** e escolha o **Conjunto de dados do cliente** que deseja enriquecer com os dados de identidade do LiveRamp. Você pode selecionar a entidade *Cliente* para enriquecer todos os perfis de cliente ou selecionar uma entidade de *segmento* para enriquecer apenas perfis de clientes contidos nesse segmento. 

1. Selecione **Avançar** e defina quais tipos de campos de perfis unificados devem ser usados para procurar dados de identidade correspondentes do LiveRamp. Pelo menos um dos campos **Nome e endereço**, **Telefone** ou **Email** é obrigatório. 

   > [!TIP]
   > Quanto mais identificadores e campos principais você mapear, maior será a probabilidade de uma taxa de correspondência mais alta 

1. Mapeie os campos da sua entidade unificada de *Cliente* que serão usados para correspondência com o gráfico de ID da AbiliTec da LiveRamp. 

   :::image type="content" source="media/liveramp-data-mapping.png" alt-text="Opções de mapeamento de dados para o enriquecimento do LiveRamp.":::

1. Selecione **Avançar** para concluir o mapeamento de campos. 

1. Forneça um **Nome** para o enriquecimento e a **Entidade de saída**. 

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas. 

## <a name="configure-the-connection-for-liveramp"></a>Configurar a conexão para LiveRamp 

Você deve ser um administrador para [configurar as conexões](connections.md). Selecione **Adicionar conexão** ao configurar o enriquecimento ou acesse **Administrador** > **Conexões** e selecione **Configurar** no bloco **LiveRamp**. 

:::image type="content" source="media/liveramp-connection.png" alt-text="Painel de configuração para configurar a conexão com o serviço do LiveRamp da AbiliTec. ":::

1. Em **Nome de exibição**, insira o nome da conexão. 

1. Forneça uma ID de cliente do LiveRamp válida e um segredo. 

1. Revise e forneça seu consentimento para **Conformidade e privacidade dos dados** marcando a caixa de seleção **Concordo**. 

1. Selecione **Verificar** para validar a configuração. 

1. Para concluir a conexão, selecione **Salvar**. 

## <a name="enrichment-results"></a>Resultados de enriquecimento 

Para iniciar o processo de enriquecimento, selecione Executar na barra de comandos. Você também pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). A duração do processamento depende do tamanho dos dados do cliente. 

Após a conclusão do processo de enriquecimento, você pode revisar os dados de perfis de clientes recém-enriquecidos em  **Meus enriquecimentos**. Além disso, você encontrará a hora da última atualização e o número de perfis enriquecidos. 

Você pode acessar uma visão detalhada de cada perfil aprimorado selecionando **Exibir dados enriquecidos**. 

## <a name="next-steps"></a>Próximas etapas

Compile com base nos dados de cliente enriquecidos. Use as IDs da AbiliTec para consolidar os perfis dos clientes em uma visão baseada em pessoa. 
[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados 

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao LiveRamp, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o LiveRamp atenda às obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, revise a [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732). Seu Administrador do Dynamics 365 Customer Insights pode remover esse enriquecimento a qualquer momento para interromper o uso dessa funcionalidade. 


[!INCLUDE[footer-include](../includes/footer-banner.md)]
