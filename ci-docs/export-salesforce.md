---
title: Exportar dados para o Salesforce Marketing Cloud (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Salesforce Marketing Cloud.
ms.date: 07/23/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: c3a6a40d9b9f08c8ebca8cb4a9196a1a79f03afa
ms.sourcegitcommit: dca46afb9e23ba87a0ff59a1776c1d139e209a32
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9080811"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportar dados para o Salesforce Marketing Cloud (versão preliminar)

Use seus dados do cliente no Salesforce Marketing Cloud ao exportá-los por meio de um local SFTP (Secure File Transfer Protocol, protocolo de transferência segura de arquivo).

## <a name="prerequisites-for-connection"></a>Pré-requisitos para conexão

- Disponibilidade de um host SFTP e as credenciais de administrador correspondentes. [Como configurar locais SFTP para o Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) 

## <a name="set-up-the-connection-to-salesforce-marketing-cloud"></a>Configurar a conexão para o Salesforce Marketing Cloud

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Salesforce Marketing Cloud** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça um **Nome de usuário**, uma **Senha**, um **Nome de host** e uma **Pasta de exportação** para sua conta SFTP.

1. Selecione **Verificar** para testar a conexão.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do SFTP. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Escolha se você deseja exportar seus dados **Compactados com o Gzip** ou **Descompactados** e o **delimitador de campo** para os arquivos exportados.

1. Selecione as entidades, por exemplo, segmentos que deseja exportar.

   > [!NOTE]
   > Cada entidade selecionada será dividida em até cinco arquivos de saída quando exportada. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar dados do Customer Insights do local SFTP para o Salesforce Marketing Cloud

1. Crie [extensões de dados no Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o arquivo de dados do Customer Insights do local SFTP.

2. [Importe os dados do local SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) na extensão de dados do Salesforce Marketing Cloud. 

3. Configure a automação para importar os dados nas extensões de dados. Saiba mais sobre [automações de transferência de arquivo e automações agendadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Defina uma [automação de transferência de dados](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou uma [automação agendada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5). 

Veja a seguir um exemplo de uma [automação com o SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados via SFTP, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o destino de exportação cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.

[!INCLUDE [footer-include](includes/footer-banner.md)]
