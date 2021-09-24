---
title: Habilitar relatórios de perfis prontos para uso
description: Como criar relatórios de perfis prontos para uso agrupados por gênero, idade e município ou região de origem.
author: darrinw-docs
ms.reviewer: mhart
ms.author: darrinw
ms.date: 05/03/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: conceptual
ms.manager: shellyha
ms.openlocfilehash: bf2ec67c9fb99918b87841d3c0b131934e31b58b
ms.sourcegitcommit: 0ceb46c4f57ab49d3a2ebb1c8a816bbafe979e3d
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2021
ms.locfileid: "7486106"
---
# <a name="out-of-box-profile-reports"></a>Relatórios de perfis prontos para uso

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um relatório é uma coleção de visualização de dados para ajudá-lo a entender como os usuários se comportam. Quando se conectam aos insights de público-alvo do Customer Insights, os insights de interação podem mostrar um relatório com informações sobre perfis de clientes unificados. Esse relatório inclui o número de perfis que você possui, agrupados por gênero, idade e localização geográfica.

## <a name="prerequisites"></a>Pré-requisitos

O ambiente dos insights de público-alvo deve armazenar dados em uma conta do Azure Data Lake Storage gerenciada pelo cliente.

Se você estiver usando uma versão de avaliação do recurso de insights de público-alvo ou um ambiente em um data lake gerenciado do Customer Insights, [fale conosco](https://go.microsoft.com/fwlink/?linkid=2145734) para obter ajuda.  


## <a name="enable-the-customer-profile-report"></a>Habilitar o relatório de perfil do cliente

Um administrador de ambiente deve [vincular insights de participação e insights de público-alvo](integrate-audience-insights-engagement-insights.md).

Depois de especificar os detalhes da conexão, o administrador pode conceder acesso a outras pessoas na organização para ver o relatório. O administrador de ambiente que configura a conexão automaticamente tem acesso ao relatório. 

Depois de concluir a conexão, o recurso **Perfis** estará disponível no painel de navegação esquerdo. 

- Vá para **Descobrir** > **Perfis** para ver o relatório.

O relatório **Perfis** contém visualizações sobre gênero, idade e localização geográfica dos perfis de clientes conectados.

:::image type="content" source="media/customer-profiles.png" alt-text="Relatório de perfil do cliente.":::

[!INCLUDE[footer-include](../includes/footer-banner.md)]