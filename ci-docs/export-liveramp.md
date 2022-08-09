---
title: Exportar segmentos para o LiveRamp (versão preliminar)
description: Saiba como configurar a conexão e a exportação para o LiveRamp.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: kishorem-ms
ms.author: kishorem
manager: shellyha
ms.openlocfilehash: 55eacea3af83f46583a3a43797d625479f56586b
ms.sourcegitcommit: 594081c82ca385f7143b3416378533aaf2d6d0d3
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/27/2022
ms.locfileid: "9196702"
---
# <a name="export-segments-to-liverampreg-preview"></a>Exportar segmentos para o LiveRamp&reg; (versão preliminar)

Ative seus dados no LiveRamp para se conectar a mais de 500 plataformas em ecossistemas digitais, sociais e de TV. Trabalhe com seus dados no LiveRamp para segmentar, suprimir e personalizar campanhas publicitárias.

## <a name="prerequisites"></a>Pré-requisitos

- Uma assinatura do LiveRamp para usar o conector. Para obter uma assinatura, [entre em contato com a LiveRamp](https://liveramp.com/contact/) diretamente. [Saiba mais sobre o LiveRamp Onboarding](https://liveramp.com/our-platform/data-onboarding/).

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação para LiveRamp está usando uma exportação via SFTP. Destinos SFTP por trás de firewalls não têm suporte no momento.
- Se você usar uma chave SSH para autenticação, [crie uma chave privada](/azure/virtual-machines/linux/create-ssh-keys-detailed#basic-example) no formato PEM ou SSH.COM. Se você estiver usando Putty, converta a chave privada exportando como Open SSH. Há suporte para os seguintes formatos de chave privada:
  - RSA no formato OpenSSL PEM e ssh.com
  - DSA no formato OpenSSL PEM e ssh.com
  - ECDSA 256/384/521 no formato OpenSSL PEM
  - ED25519 e RSA no formato de chave OpenSSH
- O tempo de execução de uma exportação depende do desempenho do sistema. Recomendamos dois núcleos de CPU e 1Gb de memória como configuração mínima do servidor.
- Exportar entidades de até 100 milhões de perfis de cliente pode levar 90 minutos ao usar a configuração mínima recomendada de dois núcleos de CPU e 1 Gb de memória.
- O número real de perfis (ou dados) que você pode exportar para LiveRamp depende de sua assinatura do LiveRamp.

## <a name="set-up-connection-to-liveramp"></a>Configurar conexão com o LiveRamp

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **LiveRamp**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são somente os administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Escolha se deseja autenticar por SSH ou nome de usuário/senha para sua conexão e forneça os detalhes necessários.

1. Selecione **Verificar** para testar a conexão com o LiveRamp.

1. Depois de uma verificação bem-sucedida, examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do LiveRamp. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. No campo **Conectar dados**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar ao LiveRamp para resolução de identidade.

   :::image type="content" source="media/export-liveramp-segments.png" alt-text="Conector LiveRamp com mapeamento de atributos.":::

1. Mapeie os atributos correspondentes da sua entidade *Cliente* para o identificador de chave selecionado.

1. Selecione **Adicionar atributo** para mapear mais atributos para enviar para o LiveRamp.

   > [!TIP]
   > Enviar mais atributos de identificador de chave para o LiveRamp provavelmente resultará em uma taxa de correspondência mais alta.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
