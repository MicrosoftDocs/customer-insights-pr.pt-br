---
title: Exportar dados do Customer Insights para o Sendinblue
description: Saiba como configurar a conexão e exportar para o Sendinblue.
ms.date: 10/08/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: e6d63e0017caa50379426cd5f9b663571b568de7
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645623"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportar segmentos para o Sendinblue (versão preliminar)

Exporte segmentos de perfis de cliente unificados para gerar campanhas, fornecer marketing por email e usar grupos de clientes específicos com o Sendinblue.

## <a name="prerequisites-for-connection"></a>Pré-requisitos para conexão

-   Você tem uma [conta do Sendinblue](https://www.sendinblue.com/) e as credenciais de administrador correspondentes.
-   Há listas existentes no Sendinblue e os IDs correspondentes.
-   Você deve ter [segmentos configurados](segments.md).
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Até 1 milhão de perfis de clientes por exportação para o Sendinblue.
- A exportação para o Sendinblue é limitada a segmentos.
- Exportar segmentos com um total de 1 milhão de perfis de clientes pode levar até 90 minutos. 
- O número de perfis de clientes que você pode exportar para o Sendinblue depende e está limitado ao seu contrato com o Sendinblue.

## <a name="set-up-connection-to-sendinblue"></a>Configurar conexão com a Sendinblue

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Sendinblue** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são apenas administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Digite sua **[Chave de API da Sendinblue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key)**.

1. Selecione **Aceito** para confirmar a **Privacidade dos dados e conformidade** e selecione **Conectar** para inicializar a conexão com a Sendinblue.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção Sendinblue. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Digite seu **ID de lista da Sendinblue** 

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. 

1. Como outra opção, você pode exportar o **Nome**, **Sobrenome** e **Telefone** para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados para a Sendinblue, você permite a transferência de dados fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, tais como Dados Pessoais. A Microsoft transferirá esses dados mediante as suas instruções, mas você é responsável por garantir que a Sendinblue cumpra qualquer obrigação de privacidade ou segurança que você venha a ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE [footer-include](includes/footer-banner.md)]
