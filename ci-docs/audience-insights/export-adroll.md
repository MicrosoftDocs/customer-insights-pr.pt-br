---
title: Exportar dados do Customer Insights para o AdRoll
description: Aprenda a configurar a conexão e exportar para o AdRoll.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e8f4d4ee6b2c6cdec513b700641db568fa16076d
ms.sourcegitcommit: aaa275c60c0c77c88196277b266a91d653f8f759
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/14/2021
ms.locfileid: "5895945"
---
# <a name="export-segment-lists-to-adroll-preview"></a>Exportar listas de segmentos para o AdRoll (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o AdRoll e use-os para publicidade. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

-   Você deve ter uma [conta do AdRoll](https://www.adroll.com/) e as credenciais de administrador correspondentes.
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- É possível exportar até 250.000 perfis por vez para o AdRoll.
- Não é possível exportar segmentos com menos de 100 perfis para o AdRoll. 
- A exportação para o AdRoll é limitada a segmentos.
- Exportar até 250.000 perfis para AdRoll pode levar até 10 minutos para a conclusão. 
- O número de perfis que você pode exportar para o AdRoll depende e está limitado ao seu contrato com o AdRoll.

## <a name="set-up-connection-to-adroll"></a>Configurar conexão com o AdRoll

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **AdRoll** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o AdRoll.

1. Selecione **Autenticar com o AdRoll** e forneça suas credenciais de administrador do AdRoll. 

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do AdRoll. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira a **ID de Anunciante do AdRoll**. Para obter mais informações, consulte os [Perfis de Anunciante do AdRoll](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. É necessário exportar os segmentos para o AdRoll.

1. Selecione os segmentos que você deseja exportar. Selecione um segmento com pelo menos 100 membros. Você não poderá exportar segmentos menores. Além disso, o tamanho máximo de um segmento para exportação é de 250.000 membros por exportação. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao AdRoll, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o AdRoll cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
