---
title: Exportar dados do Customer Insights para hosts SFTP
description: Aprenda a configurar a conexão com um host de SFTP.
ms.date: 01/27/2021
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: ddba55b3ca159c0095371e46385dcf1d3ed4a63d
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5267984"
---
# <a name="connector-for-sftp-preview"></a>Conector do SFTP (versão preliminar)

Use seus dados de cliente em aplicativos de terceiros, exportando-os para um host SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Pré-requisitos

- Disponibilidade de um host SFTP e credenciais correspondentes.

## <a name="connect-to-sftp"></a>Conectar ao SFTP

1. Vá para **Administrador** > **Exportar destinos**.

1. Em **SFTP**, selecione **Configurar**.

1. Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.

1. Forneça um **Nome de usuário**, uma **Senha**, um **Nome de host** e uma **Pasta de exportação** para sua conta SFTP.

1. Selecione **Verificar** para testar a conexão.

1. Após a verificação com sucesso, escolha se deseja exportar os dados de conteúdo **Gzip** ou **Descompactado** e selecione o **delimitador de campo** para os arquivos exportados.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Próximo** para começar a configurar a exportação.

## <a name="configure-the-export"></a>Configurar a exportação

1. Selecione as entidades, por exemplo, segmentos que deseja exportar.

   > [!NOTE]
   > Cada entidade selecionada terá até cinco arquivos de saída quando exportada. 

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitações conhecidas

- O tempo de execução de uma exportação depende do desempenho do sistema. Recomendamos dois núcleos de CPU e 1Gb de memória como configuração mínima do servidor. 
- Exportar entidades de até 100 milhões de perfis de cliente pode levar 90 minutos ao usar a configuração mínima recomendada de dois núcleos de CPU e 1 Gb de memória. 

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados via SFTP, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o destino de exportação cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]