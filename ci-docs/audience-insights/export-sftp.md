---
title: Exportar dados do Customer Insights para hosts SFTP (contém vídeo)
description: Saiba como configurar a conexão e exportar para um local do SFTP.
ms.date: 03/03/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: pkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: 542bd908010cf0a8ccc12f15d54e0a3d5b72f189
ms.sourcegitcommit: 9132fdf54070cc551ab878378078e6285852818f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/18/2021
ms.locfileid: "7934873"
---
# <a name="export-segments-and-other-data-to-sftp-preview"></a>Exportar segmentos e outros dados para o SFTP (versão preliminar)

Use dados de clientes em aplicativos de terceiros, exportando-os para um local do SFTP (Secure File Transfer Protocol).

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWO94X]

## <a name="prerequisites-for-connection"></a>Pré-requisitos para conexão

- Disponibilidade de um host SFTP e credenciais correspondentes.

## <a name="known-limitations"></a>Limitações conhecidas

- Destinos SFTP por trás de firewalls não têm suporte no momento. 
- O tempo de execução de uma exportação depende do desempenho do sistema. Recomendamos dois núcleos de CPU e 1Gb de memória como configuração mínima do servidor. 
- Exportar entidades de até 100 milhões de perfis de cliente pode levar 90 minutos ao usar a configuração mínima recomendada de dois núcleos de CPU e 1 Gb de memória. 

## <a name="set-up-connection-to-sftp"></a>Configurar conexão com o SFTP

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **SFTP** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Forneça um **Nome de usuário**, uma **Senha**, um **Nome de host** e uma **Pasta de exportação** para sua conta SFTP.

1. Selecione **Verificar** para testar a conexão.

1. Escolha se você deseja exportar seus dados **Compactados com o Gzip** ou **Descompactados** e o **delimitador de campo** para os arquivos exportados.

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção do SFTP. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Selecione as entidades, por exemplo, segmentos que deseja exportar.

   > [!NOTE]
   > Cada entidade selecionada será dividida em até cinco arquivos de saída quando exportada. 

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados via SFTP, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o destino de exportação cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.

[!INCLUDE[footer-include](../includes/footer-banner.md)]
