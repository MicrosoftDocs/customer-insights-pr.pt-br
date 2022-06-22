---
title: Enriquecer perfis de clientes com dados do Microsoft Office 365
description: Use dados proprietários do Microsoft Office para enriquecer seus perfis de clientes com dados de engajamento.
ms.date: 06/10/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: jodahl
ms.author: jodahl
manager: shellyha
ms.openlocfilehash: 7192b7680e73a581dd603de174c57b20bec996dd
ms.sourcegitcommit: 27c5473eecd851263e60b2b6c96f6c0a99d68acb
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/13/2022
ms.locfileid: "8954119"
---
# <a name="enrich-customer-profiles-with-engagement-data-preview"></a>Enriquecer perfis de clientes com dados de engajamento (versão preliminar)

Use dados do Microsoft Office 365 para enriquecer os perfis das contas dos clientes com insights sobre engajamentos por meio de aplicativos do Office 365. Os dados de engajamento consistem em atividades de email e reunião, que são agregadas no nível da conta. Por exemplo, o número de emails de uma conta comercial ou o número de reuniões com a conta. Nenhum dado sobre usuários individuais é disponibilizado.

## <a name="supported-countries-or-regions"></a>Países ou regiões com suporte

No momento, oferecemos suporte às seguintes regiões: Reino Unido, Europa, América do Norte.

## <a name="prerequisites"></a>Pré-requisitos

- Uma licença de nuvem ativa do Office 365.
- [Perfis de clientes unificados](customer-profiles.md) com base em [contas comerciais](work-with-business-accounts.md).
- Uma [organização do Microsoft Dataverse anexada](create-environment.md#step-3-connect-to-microsoft-dataverse) em seu ambiente do Customer Insights.
- Permissões de [administrador](permissions.md#admin).
- Consentimento do seu administrador do locatário do Office 365 para usar dados do Office 365 para fornecer **Insights para a Organização** nos aplicativos do Dynamics 365.

## <a name="configure-the-enrichment"></a>Configurar o enriquecimento

1. Vá para **Dados** > **Enriquecimento** e selecione a guia **Descobrir**.

1. Selecione **Enriquecer meus dados** no bloco **Participação da Conta**.

   :::image type="content" source="media/enrichment-office-tile.png" alt-text="Bloco Engajamento da conta.":::

1. Revise a visão geral e selecione **Avançar**.

1. Insira os endereços de email da sua organização para os quais os dados do Office serão agregados. Apenas os dados dos endereços de email listados são processados para comunicação relevante. Uma prática recomendada é usar grupos de email, por exemplo, *Equipe de vendas dos EUA*, que você pode gerenciar no Office 365. O número de endereços de email nos grupos que são resolvidos e exibidos. O número total de endereços de email deve ser pelo menos 2 e não pode exceder 2.500.

   :::image type="content" source="media/enrichment-office-email-addresses.png" alt-text="Endereços de email de engajamento da conta.":::

1. Revise e dê seu consentimento para o [consentimento do administrador de locatários do Office 365](#office-365-tenant-administrator-consent) ao selecionar **Concordo**.

1. Selecione **Avançar**

1. Selecione **Conjunto de dados do contato** e escolha o perfil que deseja enriquecer. Selecione **Avançar**

1. Mapeie o campo do endereço de email de contato e selecione **Avançar**.

1. Forneça um **Nome** para o enriquecimento e a **Entidade de saída**.

1. Selecione **Salvar enriquecimento** depois de revisar suas escolhas.

1. Selecione **Fechar** para retornar à página **Enriquecimentos**.

### <a name="office-365-tenant-administrator-consent"></a>Consentimento do administrador do locatário do Office 365

Consentimento de um administrador de locatário do Office 365 é necessário para ativar o enriquecimento. Um email é enviado para os administradores de locatários do Office 365 quando o enriquecimento é salvo. Ele solicita a revisão e o consentimento deles para permitir que os aplicativos do Dynamics 365 usem os dados do Office 365 das suas empresas para fornecer **Insights para a Organização**. O administrador do locatário do Office 365 também pode consentir diretamente em seu console de administração do Office 365, selecionando **Insights para a Organização**.

## <a name="running-the-enrichment-for-the-first-time"></a>Executar o enriquecimento pela primeira vez

Quando o enriquecimento é iniciado pela primeira vez, após o consentimento do administrador do locatário do Office 365, o download de dados do Office 365 começa. Esse processo leva algum tempo. A primeira execução de enriquecimento será agendada para ocorrer com atraso de seis horas. Você pode ver o número de dias que os dados abrangem na página de visão geral do engajamento da conta após a conclusão do enriquecimento. Com um grande volume de dados, execute o enriquecimento novamente após alguns dias. Isso garante que os dados estejam completos durante toda a janela de tempo, que é de um ano.

Dependendo do tamanho dos seus dados do Office, pode levar várias horas para que uma execução de enriquecimento seja concluída.

Quando você executa um enriquecimento, a Microsoft processa os dados dentro do limite de conformidade do Office 365 para criar insights agregados, que são então adicionados ao seu ambiente do Customer Insights. Nenhum dado em um nível individual (por exemplo, o corpo de qualquer email ou convite de calendário) é disponibilizado para os usuários do Customer Insights.

Selecione **Executar** para iniciar o processo de enriquecimento.

[!INCLUDE [progress-details-pane](includes/progress-details-pane.md)]

## <a name="enrichment-results"></a>Resultados de enriquecimento

[!INCLUDE [enrichment-results](includes/enrichment-results.md)] Esta é a entidade *Escritório*. *Office_UserEntity* contém as IDs do Active Directory para os endereços de email que foram escolhidos durante a configuração de enriquecimento.

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

## <a name="see-enrichment-data-on-the-customer-card"></a>Veja dados de enriquecimento no cartão do cliente

O engajamento da conta também pode ser exibido em cartões de cliente individuais. Vá para **Clientes** e selecione um perfil do cliente. No cartão do cliente, você encontrará a pontuação de engajamento da conta, o número total de emails e o número total de reuniões agregadas no último ano. Você também encontra gráficos que mostram o histórico de emails e reuniões.

:::image type="content" source="media/enrichment-office-customer-card.png" alt-text="Cartão de cliente com dados enriquecidos.":::

## <a name="next-steps"></a>Próximas etapas

[!INCLUDE [next-steps-enrichment](includes/next-steps-enrichment.md)]
Por exemplo, um segmento que contenha todos os clientes com um valor acima de 60 para *dias desde o último email* e *dias desde a última reunião*. Esse segmento contém contas obsoletas que você pode tentar reativar.

[!INCLUDE [footer-include](includes/footer-banner.md)]
