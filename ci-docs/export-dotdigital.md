---
title: Exportar segmentos para o DotDigital (versão preliminar)
description: Saiba como configurar a conexão e exportar para o DotDigital.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: af0cce4edb9d47247c79ae08491366349da98b1c
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080826"
---
# <a name="export-segments-to-dotdigital-preview"></a>Exportar segmentos para o DotDigital (versão preliminar)

Exporte segmentos de perfis de clientes unificados para catálogos de endereços do DotDigital e use-os para campanhas, marketing por email e para criar segmentos de clientes com o DotDigital. 

## <a name="prerequisites-for-a-connection"></a>Pré-requisitos para uma conexão

-   Você tem uma [conta DotDigital](https://dotdigital.com/) e criou um [usuário API](https://support.dotdigital.com/hc/articles/115001718730-How-do-I-create-an-API-user). Você precisará usar as credenciais de usuário da API para criar uma conexão
-   Há catálogos de endereços existentes no DotDigital e as IDs correspondentes. A ID pode ser encontrada na URL ao selecionar e abrir um catálogo de endereços. Para obter mais informações, consulte [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).
-   Você tem [segmentos configurados](segments.md) no Customer Insights.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de clientes por exportação para DotDigital.
- A exportação para o DotDigital é limitada a segmentos.
- Exportar segmentos com um total de 1 milhão de perfis de clientes pode levar até 3 horas devido às limitações do fornecedor. 
- O número de perfis de clientes que você pode exportar para DotDigital depende e está limitado ao seu contrato com DotDigital.

## <a name="set-up-connection-to-dotdigital"></a>Configurar conexão com o DotDigital

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **DotDigital** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Insira seu **nome de usuário e senha da API DotDigital**. 

1. Insira sua **[ID do catálogo de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book)**.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Conectar** para inicializar a conexão com o DotDigital.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão. 

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do DotDigital. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.


1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. Repita as mesmas etapas para outros campos opcionais, como **Nome**, **Sobrenome**, **Nome completo**, **Gênero** e **Código postal**.

1. Selecione os segmentos que você deseja exportar. Você pode exportar até 1 milhão de perfis de clientes no total para o DotDigital.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 
 
No DotDigital, agora você pode encontrar seus segmentos nos [catálogos de endereços do DotDigital](https://support.dotdigital.com/hc/articles/212211968-Creating-an-address-book).


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao DotDigital, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o DotDigital cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]
