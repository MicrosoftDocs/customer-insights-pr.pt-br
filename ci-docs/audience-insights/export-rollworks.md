---
title: Exportar dados do Customer Insights para o RollWorks
description: Saiba como configurar a conexão e exportar para o RollWorks.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: dce5d51ca4587b4d7a0644cc701c1826854882b5
ms.sourcegitcommit: 831765a55775d358447cb7ffa56f2c3b85459084
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2021
ms.locfileid: "6124075"
---
# <a name="export-segments-to-rollworks-preview"></a>Exportar segmentos para o RollWorks (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o RollWorks e use-os para publicidade. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

-   Você deve ter uma [conta do RollWorks](https://www.rollworks.com/) e as credenciais de administrador correspondentes.
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Você pode exportar até 250.000 perfis por vez para o RollWorks.
- Você não pode exportar segmentos com menos de 100 perfis para o RollWorks. 
- A exportação para o RollWorks é limitada a segmentos.
- Exportar até 250.000 perfis para o RollWorks pode levar até 10 minutos para a conclusão. 
- O número de perfis que você pode exportar para o RollWorks depende e está limitado ao seu contrato com o RollWorks.

## <a name="set-up-connection-to-rollworks"></a>Configurar conexão com o RollWorks

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **RollWorks** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o RollWorks.

1. Selecione **Autenticar com o RollWorks** e forneça suas credenciais de administrador do RollWorks.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do RollWorks. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Insira sua **ID de Anunciante do RollWorks** [RollWorks Anunciável](https://help.adroll.com/hc/articles/212011838-Advertiser-Profiles).

3. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo no seu perfil de cliente unificado que representa o endereço de email de um cliente. A exportação de segmentos para o RollWorks é necessária.

1. Selecione os segmentos que você deseja exportar. Selecione um segmento com pelo menos 100 membros. Você não poderá exportar segmentos menores. Além disso, o tamanho máximo de um segmento para exportação é de 250.000 membros por exportação. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para o RollWorks, você permite a transferência de dados fora do limite de conformidade do Dynamics 365 Customer Insights, incluindo dados potencialmente confidenciais, como Dados Pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você é responsável por garantir que o RollWorks atenda a todas as obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
