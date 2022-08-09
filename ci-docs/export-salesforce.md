---
title: Exportar dados para o Salesforce Marketing Cloud (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Salesforce Marketing Cloud.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 58e76e51c18c25177f9b4551b70b25b41248b142
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9197024"
---
# <a name="export-data-to-salesforce-marketing-cloud-preview"></a>Exportar dados para o Salesforce Marketing Cloud (versão preliminar)

Use seus dados do cliente no Salesforce Marketing Cloud ao exportá-los por meio de um local SFTP (Secure File Transfer Protocol, protocolo de transferência segura de arquivo).

## <a name="prerequisites"></a>Pré-requisitos

- Um [host SFTP para Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_configure_enhanced_ftp.htm&type=5) e as credenciais de administrador correspondentes.

## <a name="set-up-connection-to-salesforce-marketing-cloud"></a>Configurar conexão com o Salesforce Marketing Cloud

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Salesforce Marketing Cloud**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça um **Nome de usuário**, uma **Senha**, um **Nome de host** e uma **Pasta de exportação** para sua conta SFTP.

1. Selecione **Verificar** para testar a conexão.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do SFTP. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Escolha se você deseja exportar seus dados **Compactados com o Gzip** ou **Descompactados** e o **delimitador de campo** para os arquivos exportados.

1. Selecione as entidades, por exemplo, os segmentos que você deseja exportar.

   > [!NOTE]
   > Cada entidade selecionada será dividida em, no máximo, cinco arquivos de saída quando exportada.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

## <a name="import-customer-insights-data-from-sftp-location-to-salesforce-marketing-cloud"></a>Importar dados do Customer Insights do local SFTP para o Salesforce Marketing Cloud

1. Crie [extensões de dados no Salesforce Marketing Cloud](https://help.salesforce.com/articleView?id=sf.mc_es_create_data_extension.htm&type=5) para importar o arquivo de dados do Customer Insights do local SFTP.

2. [Importe os dados do local SFTP](https://help.salesforce.com/articleView?id=sf.mc_es_import_data_extension_classic.htm&type=5) na extensão de dados do Salesforce Marketing Cloud.

3. Configure a automação para importar os dados nas extensões de dados. Saiba mais sobre [automações de transferência de arquivo e automações agendadas](https://help.salesforce.com/articleView?id=sf.mc_as_triggered_automations.htm&type=5).

   Defina uma [automação de transferência de dados](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_triggered_automation.htm&type=5) ou uma [automação agendada](https://help.salesforce.com/articleView?id=sf.mc_as_define_a_scheduled_automation.htm&type=5).

Veja a seguir um exemplo de uma [automação com o SFTP](https://help.salesforce.com/articleView?id=sf.mc_as_ftp_and_triggered_automation_scenario.htm&type=5).

[!INCLUDE [footer-include](includes/footer-banner.md)]
