---
title: Exportar dados do Customer Insights para o Braze
description: Saiba como configurar a conexão e exportar para o Braze.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 8d7cf95c1f157c771b2d655346464e5af03d73b9
ms.sourcegitcommit: 5bd07f3a1288f003704acd576741cf6aedc1ac33
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2022
ms.locfileid: "8524136"
---
# <a name="export-segment-lists-to-braze-preview"></a>Exportar listas de segmentos para o Braze (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Braze e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Você tem uma [conta Braze](https://www.braze.com/) e as respectivas credenciais de administrador.
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de e-mail e um ID do cliente do Braze. 

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação para o Braze é limitada a segmentos.
- Exportar até 1 milhão de perfis de clientes para o Braze pode levar até 40 minutos para ser concluído. 
- O número de perfis de clientes que você pode exportar para o Braze depende e está limitado ao seu contrato com o Braze.

## <a name="set-up-connection-to-braze"></a>Configurar a conexão com o Braze

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Braze** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Informe sua [Chave de API do Braze](https://www.braze.com/docs/api/basics/) para continuar com o login. 

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecionar **Conectar** para inicializar a conexão com o Braze.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Braze. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.  

3. Na seção **Correspondência de dados**, no campo **E-mail**, selecione o campo que representa o endereço de e-mail de um cliente, no campo "ID do Cliente", selecione o campo que representa o ID Braze do cliente. É necessário exportar segmentos para o Braze. Os segmentos no Braze serão criados com o mesmo nome do segmento no Dynamics 365 Customer Insights. Você pode escolher campos opcionais adicionais para dados correspondentes. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Braze, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft vai transferir esses dados de acordo com suas instruções, mas você é responsável por garantir que o Braze atenda às obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
