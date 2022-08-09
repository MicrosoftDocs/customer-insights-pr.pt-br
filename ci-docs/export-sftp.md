---
title: Exportar dados para hosts SFTP (versão preliminar) (contém vídeo)
description: Saiba como configurar a conexão e exportar para um local do SFTP.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: b12d25ecbd2e5fb31d7d5a6bb775dc3e7c1bf007
ms.sourcegitcommit: 5807b7d8c822925b727b099713a74ce2cb7897ba
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/28/2022
ms.locfileid: "9207215"
---
# <a name="export-data-to-sftp-hosts-preview"></a>Exportar para hosts SFTP (versão preliminar)

Use dados de clientes em aplicativos de terceiros, exportando-os para um local do SFTP (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites"></a>Pré-requisitos

- Disponibilidade de um host SFTP e credenciais correspondentes.

## <a name="known-limitations"></a>Limitações conhecidas

- Destinos SFTP por trás de firewalls não têm suporte no momento.
- O tempo de execução de uma exportação depende do desempenho do sistema. Recomendamos dois núcleos de CPU e 1Gb de memória como configuração mínima do servidor.
- Até 100 milhões de perfis de cliente, o que pode levar 90 minutos ao usar a configuração mínima recomendada de dois núcleos de CPU e 1 Gb de memória.
- Se você usar uma chave SSH para autenticação, [crie uma chave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) no formato PEM ou SSH.COM. Se você estiver usando Putty, converta a chave privada exportando como Open SSH. Há suporte para os seguintes formatos de chave privada:
  - RSA no formato OpenSSL PEM e ssh.com
  - DSA no formato OpenSSL PEM e ssh.com
  - ECDSA 256/384/521 no formato OpenSSL PEM
  - ED25519 e RSA no formato de chave OpenSSH

## <a name="set-up-connection-to-sftp"></a>Configurar conexão com o SFTP

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **SFTP**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escolha se deseja autenticar por SSH ou nome de usuário/senha para sua conexão e forneça os detalhes necessários. Se você usar uma chave SSH para autenticação, [crie uma chave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) no formato PEM ou SSH.COM. Se você estiver usando Putty, converta a chave privada exportando como Open SSH. Há suporte para os seguintes formatos de chave privada:
   - RSA no formato OpenSSL PEM e ssh.com
   - DSA no formato OpenSSL PEM e ssh.com
   - ECDSA 256/384/521 no formato OpenSSL PEM
   - ED25519 e RSA no formato de chave OpenSSH

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

> [!TIP]
> A exportação de entidades que contêm uma grande quantidade de dados pode levar a vários arquivos CSV na mesma pasta para cada exportação. A divisão de exportações ocorre por motivos de desempenho para minimizar o tempo necessário para a conclusão de uma exportação.

[!INCLUDE [footer-include](includes/footer-banner.md)]
