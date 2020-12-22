---
title: Exportar dados do Customer Insights para hosts SFTP
description: Aprenda a configurar a conexão com um host de SFTP.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c2529744d7a26a06324b79cad6a8001d75903545
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4643489"
---
# <a name="connector-for-sftp-preview"></a>Conector do SFTP (versão preliminar)

Use seus dados de cliente em aplicativos de terceiros, exportando-os para um host SFTP (Secure File Transfer Protocol).

## <a name="prerequisites"></a>Pré-requisitos

- Disponibilidade de um host de SFTP e credenciais correspondentes.

## <a name="connect-to-sftp"></a>Conecte-se ao SFTP

1. Vá para **Administrador** > **Exportar destinos**.

1. Em **SFTP**, selecione **Configurar**.

1. Dê ao seu destino um nome reconhecível no campo **Nome de exibição**.

1. Forneça um **Nome de usuário**, uma **Senha** e um **Nome de host** para sua conta SFTP. Exemplo: se a pasta raiz do seu servidor SFTP for /root/folder e você quiser que os dados sejam exportados para /root/folder/ci_export_destination_folder, o host deverá ser sftp://<server_address>/ci_export_destination_folder".

1. Selecione **Verificar** para testar a conexão.

1. Após a verificação bem-sucedida, escolha se deseja exportar seus dados **Fechados** ou **Descompactados** e selecione o **delimitador de campo** para os arquivos exportados.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Próximo** para começar a configurar a exportação.

## <a name="configure-the-connection"></a>Configurar a conexão

1. Selecione os **atributos do cliente** que você deseja exportar. Você pode exportar um ou vários atributos.

1. Selecione **Avançar**.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados via SFTP, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o destino de exportação cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
