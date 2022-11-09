---
title: Exportar segmentos para o Sendinblue (versão preliminar)
description: Saiba como configurar a conexão e exportar para o Sendinblue.
ms.date: 07/25/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: how-to
author: phkieffer
ms.author: philk
manager: shellyha
ms.openlocfilehash: fc4ac34c1de096e25ba6c374fe17b1da6b2f745f
ms.sourcegitcommit: c3ae7e7e0c9566f9479ba71a26afc5a17fb589c2
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/27/2022
ms.locfileid: "9724880"
---
# <a name="export-segments-to-sendinblue-preview"></a>Exportar segmentos para o Sendinblue (versão preliminar)

Exporte segmentos de perfis de cliente unificados para gerar campanhas, fornecer marketing por email e usar grupos de clientes específicos com o Sendinblue.

## <a name="prerequisites"></a>Pré-requisitos

- Uma [conta do Sendinblue](https://www.sendinblue.com/) e as credenciais de administrador correspondentes.
- Uma [chave de API do SendinBlue](https://developers.sendinblue.com/docs/getting-started#:~:text=Get%20your%20API%20key&text=You%20can%20create%20one%20from,your%20settings%20This%20API%20key).
- Listas existentes no Sendinblue e as IDs correspondentes.
- [Segmentos configurados](segments.md).
- Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- Não há suporte ao link privado associado a Traga seu próprio armazenamento (BYOS).
- Até 1 milhão de perfis de cliente por exportação para o Sendinblue, o que pode levar até 90 minutos. O número de perfis de cliente que você pode exportar para o Sendinblue depende de seu contrato com o Sendinblue.
- Apenas segmentos.

## <a name="set-up-connection-to-sendinblue"></a>Configurar conexão com a Sendinblue

[!INCLUDE [export-connection-include](includes/export-connection-admn.md)]

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Sendinblue**.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Por padrão, são apenas administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Digite sua **Chave de API do SendinBlue**.

1. Examine a [conformidade e privacidade dos dados](connections.md#data-privacy-and-compliance) e selecione **Concordo**.

1. Selecione **Conectar** para inicializar a conexão.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

[!INCLUDE [export-permission-include](includes/export-permission.md)]

1. Vá para **Dados** > **Exportações**.

1. Selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção Sendinblue. Contate um administrador se nenhuma conexão estiver disponível.

1. Insira um nome para a exportação.

1. Digite a **ID de lista do Sendinblue**.

1. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente.

1. Como opção, você pode exportar o **Nome**, o **Sobrenome** e o **Telefone** para criar emails mais personalizados. Selecione **Adicionar atributo** para mapear esses campos.

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

[!INCLUDE [export-saving-include](includes/export-saving.md)]

[!INCLUDE [footer-include](includes/footer-banner.md)]
