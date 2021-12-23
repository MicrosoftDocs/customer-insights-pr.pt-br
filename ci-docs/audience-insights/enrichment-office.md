---
title: Enriquecer perfis de clientes com dados do Microsoft Office 365
description: Use dados proprietários do Microsoft Office para enriquecer seus perfis de clientes com dados de engajamento.
ms.date: 12/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: a30e09b5ed491c8d36019b5f0d35e0a2f7a0199c
ms.sourcegitcommit: 48d799535fad84e8b63c80aef48b5c5e87628f58
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/03/2021
ms.locfileid: "7889744"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Enriquecer perfis de clientes com dados de engajamento (versão preliminar)

Use dados do Microsoft Office 365 para enriquecer os perfis das contas dos clientes com insights sobre engajamentos por meio de aplicativos do Office 365. Os dados de engajamento consistem em atividades de email e reunião, que são agregadas no nível da conta. Por exemplo, o número de emails de uma conta comercial ou o número de reuniões com a conta. Nenhum dado sobre usuários individuais é disponibilizado. 

Este enriquecimento está disponível nas seguintes regiões: Reino Unido, Europa, América do Norte.

## <a name="prerequisites"></a>Pré-requisitos

Para configurar o enriquecimento, os seguintes pré-requisitos devem ser atendidos:

- Você deve ter uma licença de nuvem do Office 365 ativa.
- Você deve ter [perfis de clientes unificados](customer-profiles.md) baseados em [contas comerciais](work-with-business-accounts.md).
- Seu ambiente do Customer Insights deve ter uma [organização do Microsoft Dataverse anexada](create-environment.md#step-3-connect-to-microsoft-dataverse).
- Você deve ter permissões de [administrador](permissions.md#administrator).
- Você deve ter, ou poder obter, consentimento do seu administrador do locatário do Office 365 para usar dados do Office 365 para fornecer **Insights para a Organização** nos aplicativos do Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Nos insights de público-alvo, vá para **Dados** > **Enriquecimento**.

1. Acesse a guia **Descobrir** e selecione **Enriquecer meus dados** no bloco **Engajamento da Conta**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Bloco Engajamento da conta.":::
   
1. Selecione **Avançar** na etapa **Visão geral** e insira os endereços de email da sua organização para os quais os dados do Office serão agregados. Apenas os dados dos endereços de email listados são processados para comunicação relevante. Uma prática recomendada é usar grupos de email, por exemplo, *Equipe de vendas dos EUA*, que são facilmente gerenciados no Office 365. O número de endereços de email nos grupos que são resolvidos e exibidos. O número total de endereços de email deve ser pelo menos 2 e não pode exceder 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Endereços de email de engajamento da conta.":::

1. Revise a declaração de consentimento, marque a caixa de seleção **Concordo** e selecione **Avançar**.

1. Selecione o conjunto de dados do cliente e, em seguida, selecione **Avançar**.

1. Mapeie o campo do endereço de email de contato e selecione **Avançar**.

1. Revise a configuração de enriquecimento, dê um nome a ele e selecione **Salvar enriquecimento** para salvá-lo.

## <a name="office-365-tenant-administrator-consent"></a>Consentimento do administrador do locatário do Office 365

Consentimento de um administrador de locatário do Office 365 é necessário para ativar o enriquecimento. Um email é enviado para os administradores de locatários do Office 365 quando o enriquecimento é salvo. Ele solicita a revisão e o consentimento deles para permitir que os aplicativos do Dynamics 365 usem os dados do Office 365 das suas empresas para fornecer **Insights para a Organização**. O administrador do locatário do Office 365 também pode consentir diretamente em seu console de administração do Office 365, selecionando **Insights para a Organização**.

## <a name="running-the-enrichment-for-the-first-time"></a>Executar o enriquecimento pela primeira vez

Quando o enriquecimento é iniciado pela primeira vez, após o consentimento do administrador do locatário do Office 365, o download de dados do Office 365 começa. Esse processo leva algum tempo. A primeira execução de enriquecimento será agendada para ocorrer com atraso de seis horas. Você pode ver o número de dias que os dados abrangem na página de visão geral do engajamento da conta após a conclusão do enriquecimento. Com um grande volume de dados, execute o enriquecimento novamente após alguns dias. Isso garante que os dados estejam completos durante toda a janela de tempo, que é de um ano.

Para iniciar o processo, selecione **Executar** na página de configuração Engajamento da conta. Além disso, você pode permitir que o sistema execute o enriquecimento automaticamente como parte de uma [atualização agendada](system.md#schedule-tab). Por padrão, o enriquecimento é executado uma vez por semana.

Dependendo do tamanho dos seus dados do Office, pode levar várias horas para que uma execução de enriquecimento seja concluída.

Quando você executa um enriquecimento, a Microsoft processa os dados dentro do limite de conformidade do Office 365 para criar insights agregados, que são então adicionados ao seu ambiente do Customer Insights. Nenhum dado em um nível individual (por exemplo, o corpo de qualquer email ou convite de calendário) é disponibilizado para os usuários do Customer Insights. 

[!INCLUDE [progress-details-pane](../includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultados de enriquecimento

Depois de executar o processo de enriquecimento, vá para **Meus enriquecimentos** para analisar os resultados do enriquecimento. Você encontrará o número total de clientes enriquecidos e uma visão geral dos resultados do enriquecimento. Isso inclui o número de emails e reuniões processados, o número de dias para os quais os dados foram agregados e muito mais.

Você também encontrará um gráfico com o número de clientes enriquecidos ao longo do tempo e uma visualização dos dados de enriquecimento.  

:::image type="content" source="media/enrichment-office-results-overview.png" alt-text="Visualização dos resultados após a execução do processo de enriquecimento.":::

Todos os dados são agregados até o nível da conta. O sistema calcula uma pontuação de engajamento, que varia de 0 a 100, para cada conta. A pontuação de engajamento fornece uma medida composta da engajamento da conta em emails e reuniões em relação às suas outras contas. A lista a seguir contém os dados agregados que o enriquecimento do engajamento da conta fornece:



| Dados                                                                              | Nome da coluna                              |
| :-------------------------------------------------------------------------------- |:---------------------------------------- |
| Pontuação de participação                                                                  |  EngagementScore                         |
| Número de emails para a conta                                                       |  NoOfEmails_ToAccount                    |
| Número de emails da conta                                                     |  NoOfEmails_FromAccount                  | 
| Número de reuniões iniciadas pela conta                                           |  NoOfMeetings_FromAccount                | 
| Número de reuniões iniciadas pela sua organização                                 |  NoOfMeetings_ToAccount                  | 
| Número de pessoas da sua organização em reuniões com a conta                  |  NoOfContactsInvolved_Meetings           | 
| Número de pessoas da sua organização em conversas de email com a conta       |  NoOfContactsInvolved_Emails             | 
| Número de pessoas da conta em reuniões com a sua organização                  |  NoOfAccountContactsInvolved_Meetings    | 
| Número de pessoas da conta em conversas de email com a sua organização       |  NoOfAccountContactsInvolved_Emails      | 
| Data de início do engajamento (primeiro email ou reunião nos dados)                        |  EngagementStartDate                     | 
| Dias desde o último email                                                             |  DaysSinceLastEmail                      | 
| Dias desde a última reunião                                                           |  DaysSinceLastMeeting                    | 
| Duração média das reuniões                                                      |  AverageDuration_Of_Meetings             | 
| Duração média das respostas de email da conta                                    |  AverageDuration_Of_AccountEmailReplies  | 
| Data de início da agregação                                                            |  AggregationStartDate                    | 
| Nível da agregação (ano, mês ou semana)                                          |  AggregationLevel                        | 


Revise os dados enriquecidos selecionando **Ver mais** na seção de visualização. A entidade *Office* será aberta. Você também pode encontrar a entidade listada no grupo **Enriquecimento** em **Dados** > **Entidades**. Você também encontrará a *Office_UserEntity*, que contém as IDs do Active Directory para os endereços de email que foram escolhidos durante a configuração de enriquecimento 

## <a name="see-enrichment-data-on-the-customer-card"></a>Veja dados de enriquecimento no cartão do cliente

O engajamento da conta também pode ser exibido em cartões de cliente individuais. Vá para **Clientes** e selecione um perfil do cliente. No cartão do cliente, você encontrará a pontuação de engajamento da conta, o número total de emails e o número total de reuniões agregadas no último ano. Você também encontra gráficos que mostram o histórico de emails e reuniões.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos.":::

## <a name="create-segments-and-measures-based-on-the-enriched-data"></a>Criar segmentos e medidas com base nos dados enriquecidos

Os dados enriquecidos podem ser usados para criar segmentos e medidas conforme detalhado abaixo. Por exemplo, um segmento que contenha todos os clientes com um valor acima de 60 para *dias desde o último email* e *dias desde a última reunião*. Esse segmento contém contas obsoletas que você pode tentar reativar. 

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](../includes/next-steps-enrichment.md)]


[!INCLUDE[footer-include](../includes/footer-banner.md)]
