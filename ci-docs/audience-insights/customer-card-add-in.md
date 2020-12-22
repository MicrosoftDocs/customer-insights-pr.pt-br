---
title: Instalar e configurar o Complemento do Cartão do Cliente
description: Instalar e configura o suplemento de Cartão de Cliente para o Dynamics 365 Customer Insights.
ms.date: 08/04/2020
ms.reviewer: philk
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: aab5deaf89b4b019f6688a1bca950ec2277ad5fb
ms.sourcegitcommit: 6a6df62fa12dcb9bd5f5a39cc3ee0e2b3988184b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "4644029"
---
# <a name="customer-card-add-in-preview"></a>Suplemento do Cartão do Cliente (versão prévia)

[!INCLUDE [cc-data-platform-banner](../includes/cc-data-platform-banner.md)]

Obtenha uma exibição de 360 graus de seus clientes diretamente nos aplicativos do Dynamics 365. Exiba dados demográficos, insights e linhas de tempo de atividades com o Suplemento do Cartão do Cliente.

## <a name="prerequisites"></a>Pré-requisitos

- Aplicativo Dynamics 365 (como Hub de Vendas ou Hub do SAC), versão 9.0 e posterior com Interface Unificada ativada.
- Perfis de clientes [ingeridos a partir do aplicativo do Dynamics 365 usando o Common Data Service](connect-power-query.md).
- Os usuários do complemento do cartão do cliente precisam ser [adicionados como usuários](permissions.md) nos insights de público-alvo.
- [Recursos de pesquisa e filtro configurados](search-filter-index.md).
- Controle demográfico: campos demográficos, como idade ou sexo, estão disponíveis no perfil de cliente unificado.
- Controle de enriquecimento: Requer [enriquecimentos](enrichment-hub.md) ativos aplicados aos perfis de clientes.
- Controle de inteligência: requer dados gerados usando o Azure Machine Learning ([Previsões](predictions.md) ou [Modelos Personalizados](custom-models.md))
- Controle de medida: requer [medidas configuradas](measures.md).
- Controle de linha do tempo: requer [atividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar o Complemento do Cartão do Cliente

O Suplemento do Cartão do Cliente é uma solução para aplicativos customer engagement no Dynamics 365. Para instalar a solução, vá para AppSource e procure **Cartão do Cliente do Dynamics**. Selecione o [Suplemento do Cartão do Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.

Pode ser necessário entrar com suas credenciais de administrador no aplicativo Dynamics 365 para instalar a solução.

Pode levar algum tempo para a solução ser instalada no seu ambiente.

## <a name="configure-the-customer-card-add-in"></a>Configurar o Suplemento do Cartão do Cliente

1. Como administrador, vá para a seção **Configurações** no Dynamics 365 e selecione **Soluções**.

1. Selecione o link **Nome para Exibição** da solução **Suplemento do Cartão do Cliente do Dynamics 365 Customer Insights (versão prévia)**.

   > [!div class="mx-imgBorder"]
   > ![Selecione nome para exibição](media/select-display-name.png "Selecione nome para exibição")

1. Selecione **Entrar** e insira as credenciais da conta de administrador que você usa para configurar o Customer Insights.

   > [!NOTE]
   > Verifique se o bloqueador de pop-up do navegador não bloqueia a janela de autenticação quando você seleciona o botão **Entrar**.

1. Selecione o ambiente por meio do qual você deseja buscar dados.

1. Defina o mapeamento de campo para registros no aplicativo do Dynamics 365.
   - Para mapear com um contato, selecione o campo na entidade Cliente que corresponde à ID de sua entidade de contato.
   - Para mapear com uma conta, selecione o campo na entidade Cliente que corresponde à ID da entidade de sua conta.

   > [!div class="mx-imgBorder"]
   > ![Campo ID de Contato](media/contact-id-field.png "Campo ID de Contato")

1. Selecione **Salvar configuração** para salvar as configurações.

1. Em seguida, você precisa atribuir funções de segurança no Dynamics 365 para que os usuários possam personalizar e exibir o cartão do cliente. No Dynamics 365, vá para **Configurações** > **Segurança** > **Usuários**. Selecione os usuários para editar as funções do usuário e selecione **Gerenciar funções**.

1. Atribua a função **Personalizador de Cartão do Customer Insights** a usuários que personalizarão o conteúdo mostrado no cartão para toda a organização.

## <a name="add-customer-card-controls-to-forms"></a>Adicionar controles de cartão de cliente a formulários
  
1. Para adicionar os controles do Cartão do Cliente ao seu formulário de contato, vá para **Configurações** > **Personalizações** no Dynamics 365.

1. Selecione **Personalizar o sistema**.

1. Navegue até a entidade **Contato**, expanda-a e selecione **Formulários**.

1. Selecione o formulário de contato ao qual você deseja adicionar os controles do Cartão do Cliente.

    > [!div class="mx-imgBorder"]
    > ![Selecione o formulário de Contato](media/contact-active-forms.png "Selecione o formulário de Contato")

1. Para adicionar um controle, no editor de formulários, arraste qualquer campo do **Gerenciador de Campos** para o local em que deseja que o controle apareça.

1. Selecione o campo no formulário que você acabou de adicionar e selecione **Alterar Propriedades**.

1. Vá para a guia **Controles** e selecione **Adicionar Controle**. Escolha um dos controles personalizados disponíveis e selecione **Adicionar**.

1. Na caixa de diálogo **Propriedades do Campo**, limpe a caixa de seleção **Exibir rótulo no formulário**.

1. Selecione a opção **Web** para o controle. Para o controle Enriquecimento, selecione qual tipo de enriquecimento você quer exibir, configurando o campo **enriqumentType**. Você precisa adicionar um controle de enriquecimento separado para cada tipo de enriquecimento.

1. Selecione **Salvar** e **Publicar** para publicar o formulário de contato atualizado.

1. Vá para o formulário de contato publicado. Você verá o controle recém-adicionado. Pode ser necessário fazer login na primeira vez em que o utilizar.

1. Para personalizar o que você deseja mostrar no controle personalizado, selecione o botão de edição no canto superior direito.
