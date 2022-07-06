---
title: Exportar segmentos para o Criteo (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Criteo.
ms.date: 05/27/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: ace9056d200a3179e442132004324a01f0d247b6
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080819"
---
# <a name="export-segments-to-criteo-preview"></a>Exportar segmentos para o Criteo (versão preliminar)

Exporte segmentos de Unified customer profiles para gerar campanhas, fornecer marketing de emails e usar grupos específicos de clientes com o Criteo.

## <a name="prerequisites-for-connection"></a>Pré-requisitos para conexão

-   Você tem uma [conta de redirecionamento do Criteo Dynamics](https://www.criteo.com/login/) e as respectivas credenciais de administrador.
-   Você deve ter [segmentos configurados](segments.md).
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de clientes por exportação para o Criteo.
- A exportação para o Criteo é limitada a segmentos.
- Exportar segmentos com um total de 1 milhão de perfis de clientes pode levar até 30 minutos. 
- O número de perfis de clientes que você pode exportar para o Criteo depende e está limitado ao seu contrato com o Criteo.

## <a name="set-up-connection-to-criteo"></a>Configurar a conexão com o Criteo

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Criteo** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Selecione **Concordo** para confirmar a **Privacidade e conformidade dos dados** e selecione **Conectar** para inicializar a conexão com o Criteo.

1. Selecione **Autenticar com o Criteo** e forneça seu nome de usuário e credenciais de administrador do Criteo. 

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Criteo. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você. 

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. 

1. Opcionalmente, você pode exportar o **ID** e o **Nome do anunciante**

1. Selecione os segmentos que você deseja exportar. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Criteo, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft vai transferir esses dados de acordo com suas instruções, mas você é responsável por garantir que o Criteo atenda às obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](includes/footer-banner.md)]
