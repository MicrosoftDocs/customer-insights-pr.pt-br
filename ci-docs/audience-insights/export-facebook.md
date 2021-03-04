---
title: Exportar dados do Customer Insights para o Gerenciador de Anúncios do Facebook
description: Aprenda a configurar a conexão com o Gerenciador de Anúncios do Facebook.
ms.date: 06/05/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: how-to
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: c839f9dc7e403412c0e3d936392d45a43bc63545
ms.sourcegitcommit: 139548f8a2d0f24d54c4a6c404a743eeeb8ef8e0
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2021
ms.locfileid: "5269960"
---
# <a name="connector-for-facebook-ads-manager-preview"></a>Conector para Gerenciador de Anúncios do Facebook (versão preliminar)

Exporte segmentos de perfis unificados de clientes para o Gerenciador de Anúncios do Facebook para criar campanhas no Facebook e no Instagram.

## <a name="prerequisites"></a>Pré-requisitos

- Você deve ter uma [**Conta de Anúncios do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account) que inclui uma [**Conta de Negócios do Facebook**](https://business.facebook.com/).
- Você deve ser um administrador na [**Conta de Anúncios do Facebook**](https://www.facebook.com/business/learn/lessons/step-by-step-ads-manager-account).

## <a name="connect-to-facebook-ads-manager"></a>Conecte-se ao Gerenciador de Anúncios do Facebook

1. Vá para **Administrador** > **Exportar destinos**.

1. Em Gerenciador de Anúncios do **Facebook**, selecione **Configuração**.

1. Dê ao seu destino de exportação um nome reconhecível no campo **Nome de exibição**.

1. Selecione **Continue com Facebook** para fazer login na sua Conta de Anúncios do Facebook.

1. Conceda permissão a **ads_management** depois de autenticar com o Facebook.

1. Selecione a Conta de Anúncios do **Facebook** na qual você deseja trabalhar.

1. Selecione um **Público-alvo personalizado existente** na lista suspensa ou crie um **Novo público-alvo personalizado**. Para obter mais informações, consulte [**Público no Gerenciador de Anúncios do Facebook**](https://www.facebook.com/business/help/744354708981227?id=2469097953376494).

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecione **Próximo** para configurar a exportação.

## <a name="configure-the-connector"></a>Configurar o conector

1. No campo **Escolher identificador de chave**, selecione **Email**, **Nome e endereço** ou **Telefone** para enviar para o Gerenciador de Anúncios do Facebook.

1. Mapeie os atributos correspondentes da sua entidade unificada do cliente para o identificador de chave selecionado.
   > [DICA] As melhores chances de correspondência ocorrem se você selecionar **E-mail** como o identificador. Adicionar identificadores adicionais pode melhorar a correspondência.

1. Selecione **Adicionar atributo** para mapear os atributos adicionais para enviar ao Gerenciador de Anúncios do Facebook. Os atributos do Gerenciador de Anúncios do Facebook estão sendo mapeados para os seguintes nomes de usuários amigáveis: **FN** = **Nome**, **LN** = **Sobrenome**, **FI** = **Primeira Inicial**, **PHONE** = **Telefone**, **GEN** = **Gênero**, **DOB** = **Data de Nascimento**, **ST** = **Estado**, **CT** = **Cidade**, **ZIP** = **Código postal/CEP**, **COUNTRY** = **País/Região**

1. Selecione os segmentos que você deseja exportar.

1. Selecione **Salvar**.

## <a name="export-the-data"></a>Exportar os dados

Você pode [exportar dados sob demanda](export-destinations.md). A exportação também será executada a cada [atualização agendada](system.md#schedule-tab).

## <a name="known-limitations"></a>Limitações conhecidas

- Até 10 milhões de perfis de cliente por exportação para o Gerenciador de Anúncios do Facebook 
- A exportação para o Gerenciador de Anúncios do Facebook é limitada a segmentos
- A exportação de segmentos com um total de 10 milhão de perfis pode levar até 90 minutos para ser concluída

## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Gerenciador de Anúncios do Facebook, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft transferirá esses dados de acordo com suas instruções, mas você será responsável por garantir que o Gerenciador de Anúncios do Facebook cumpra as obrigações de privacidade e segurança que possam existir. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).
Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.


[!INCLUDE[footer-include](../includes/footer-banner.md)]