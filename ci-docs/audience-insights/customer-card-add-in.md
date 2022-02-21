---
title: Suplemento Cartão do Cliente para aplicativos do Dynamics 365 (contém vídeo)
description: Mostre dados de insights do público-alvo em aplicativos Dynamics 365 com este suplemento.
ms.date: 02/02/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: Nils-2m
ms.author: nikeller
manager: shellyha
ms.openlocfilehash: ce6c8fab84fd4c5dfc9f78b91dde3483a1d358c1
ms.sourcegitcommit: 11308ed275b4b25a35576eccfcae9dda9e2c2784
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/02/2022
ms.locfileid: "8085193"
---
# <a name="customer-card-add-in-preview"></a>Suplemento do Cartão do Cliente (versão prévia)



Obtenha uma exibição de 360 graus de seus clientes diretamente nos aplicativos do Dynamics 365. Com o suplemento do Cartão do Cliente instalado em um aplicativo Dynamics 365 suportado, você pode optar por exibir os campos de perfil do cliente, insights e cronograma de atividades. O suplemento recuperará dados do Customer Insights sem afetar os dados no aplicativo conectado Dynamics 365.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWN1qv]

## <a name="prerequisites"></a>Pré-requisitos

- O suplemento só funciona com aplicativos baseados em modelo do Dynamics 365, como Vendas ou Customer Service, versão 9.0 e superior.
- Para que seus dados do Dynamics 365 possam mapear para os perfis dos clientes de insights de público-alvo, recomendamos que eles sejam [ingeridos a partir do aplicativo Dynamics 365 utilizando o conector do Microsoft Dataverse](connect-power-query.md). Se você usar um método diferente para ingerir contatos (ou contas) do Dynamics 365, verifique se `contactid` (ou `accountid`) está definida como a [chave primária para essa fonte de dados na etapa de mapa do processo de unificação de dados](map-entities.md#select-primary-key-and-semantic-type-for-attributes). 
- Todos os usuários do Dynamics 365 do Suplemento de Cartão do Cliente devem ser [adicionados como usuários](permissions.md) nos insights do público-alvo para ver os dados.
- [É preciso que haja recursos de filtro e pesquisa configurados](search-filter-index.md) em insights de público-alvo para que a pesquisa de dados funcione.
- Cada controle de suplemento depende de dados específicos nos insights do público-alvo. Alguns dados e controles estão disponíveis apenas em ambientes de tipos específicos. A configuração do suplemento irá informá-lo se um controle não estiver disponível devido ao tipo de ambiente selecionado. Saiba mais sobre [casos de uso de ambiente](work-with-business-accounts.md).
  - **Controle de medida**: Requer [ medidas configuradas](measures.md) do tipo de atributos do cliente.
  - **Controle de inteligência**: requer dados gerados usando [previsões ou modelos personalizados](predictions-overview.md).
  - **Controle de detalhes do cliente**: Todos os campos do perfil estão disponíveis no perfil de cliente unificado.
  - **Controle de enriquecimento**: Requer [enriquecimentos](enrichment-hub.md) ativos aplicados aos perfis de clientes. O suplemento de cartão oferece suporte a estes enriquecimentos: [Marcas](enrichment-microsoft.md) fornecido pela Microsoft, [Interesses](enrichment-microsoft.md) fornecido pela Microsoft e [Dados de engajamento do Office](enrichment-office.md) fornecido pela Microsoft.
  - **Controle de contatos**: Requer definição de entidade semântica de tipo de contato.
  - **Controle de linha do tempo**: Requer [atividades configuradas](activities.md).

## <a name="install-the-customer-card-add-in"></a>Instalar o Complemento do Cartão do Cliente

O Suplemento do Cartão do Cliente é uma solução para aplicativos customer engagement no Dynamics 365. Para instalar a solução, vá para AppSource e procure **Cartão do Cliente do Dynamics**. Selecione o [Suplemento do Cartão do Cliente no AppSource](https://appsource.microsoft.com/product/dynamics-365/mscrm.dynamics_365_customer_insights_customer_card_addin?tab=Overview) e selecione **Obter Agora**.

Pode ser necessário entrar com suas credenciais de administrador no aplicativo Dynamics 365 para instalar a solução. Pode levar algum tempo para a solução ser instalada no seu ambiente.

## <a name="configure-the-customer-card-add-in"></a>Configurar o Suplemento do Cartão do Cliente

1. Como administrador, vá para a seção **Configurações** no Dynamics 365 e selecione **Soluções**.

1. Selecione o link **Nome para Exibição** da solução **Suplemento do Cartão do Cliente do Dynamics 365 Customer Insights (versão prévia)**.

   > [!div class="mx-imgBorder"]
   > ![Selecione o nome de exibição.](media/select-display-name.png "Selecione o nome para exibição.")

1. Selecione **Entrar** e insira as credenciais da conta de administrador que você usa para configurar o Customer Insights.

   > [!NOTE]
   > Verifique se o bloqueador de pop-up do navegador não bloqueia a janela de autenticação quando você seleciona o botão **Entrar**.

1. Selecione o ambiente do Customer Insights do qual você deseja extrair os dados.

1. Defina o mapeamento de campo para registros no aplicativo Dynamics 365. Dependendo de seus dados no Customer Insights, você pode escolher mapear estas opções:
   - Para mapear com um contato, selecione o campo na entidade Cliente que corresponde à ID de sua entidade de contato.
   - Para mapear com uma conta, selecione o campo na entidade Cliente que corresponde à ID da entidade de sua conta.

   > [!div class="mx-imgBorder"]
   > ![Campo ID do Contato.](media/contact-id-field.png "Campo ID de Contato.")

1. Selecione **Salvar configuração** para salvar as configurações.

1. Em seguida, você precisa atribuir funções de segurança no Dynamics 365 para que os usuários possam personalizar e exibir o cartão do cliente. No Dynamics 365, vá para **Configurações** > **Segurança** > **Usuários**. Selecione os usuários para editar as funções do usuário e selecione **Gerenciar funções**.

1. Atribua a função **Personalizador de Cartão do Customer Insights** a usuários que personalizarão o conteúdo mostrado no cartão para toda a organização.

## <a name="add-customer-card-controls-to-forms"></a>Adicionar controles de cartão de cliente a formulários

Dependendo do seu cenário, você pode optar por adicionar controles a qualquer formulário de **Contato** ou de **Conta**. Se o seu ambiente de insights de público-alvo for para contas corporativas, recomendamos adicionar os controles ao formulário de Conta. Nesse caso, substitua "contato" nas etapas abaixo por "conta".

1. Para adicionar os controles do Cartão do Cliente ao seu formulário de contato, vá para **Configurações** > **Personalizações** no Dynamics 365.

1. Selecione **Personalizar o sistema**.

1. Navegue até a entidade **Contato**, expanda-a e selecione **Formulários**.

1. Selecione o formulário de contato ao qual você deseja adicionar os controles do Cartão do Cliente.

    > [!div class="mx-imgBorder"]
    > ![Selecione o formulário de Contato.](media/contact-active-forms.png "Selecione o formulário de Contato.")

1. Para adicionar um controle, no editor de formulários, arraste qualquer campo do **Gerenciador de Campos** para o local em que deseja que o controle apareça.

1. Selecione o campo no formulário que você acabou de adicionar e selecione **Alterar Propriedades**.

1. Vá para a guia **Controles** e selecione **Adicionar Controle**. Escolha um dos controles personalizados disponíveis e selecione **Adicionar**.

1. Na caixa de diálogo **Propriedades do Campo**, limpe a caixa de seleção **Exibir rótulo no formulário**.

1. Selecione a opção **Web** para o controle. Para o controle Enriquecimento, selecione qual tipo de enriquecimento você quer exibir, configurando o campo **enriqumentType**. Adicione um controle de enriquecimento separado para cada tipo de enriquecimento.

1. Selecione **Salvar** e **Publicar** para publicar o formulário de contato atualizado.

1. Vá para o formulário de contato publicado. Você verá o controle recém-adicionado. Pode ser necessário fazer login na primeira vez em que o utilizar.

1. Para personalizar o que você deseja mostrar no controle personalizado, selecione o botão de edição no canto superior direito.

## <a name="upgrade-customer-card-add-in"></a>Atualizar Suplemento do Cartão do Cliente

O Suplemento do Cartão do Cliente não é atualizado automaticamente. Para atualizar para a versão mais recente, siga estas etapas no aplicativo Dynamics 365 que possui o suplemento instalado.

1. No aplicativo Dynamics 365, acesse **Configurações** > **Personalização** e selecione **Soluções**.

1. Na tabela de suplementos, procure **CustomerInsightsCustomerCard** e selecione a linha.

1. Selecione **Aplicar Atualização de Solução** na barra de ações.

   :::image type="content" source="media/customer-card-add-in-upgrade.png" alt-text="Atualize a solução na Área de personalização dos aplicativos do Dynamics 365.":::

1. Depois de iniciar o processo de atualização, você verá um indicador de carregamento até que a atualização seja concluída. Se não houver uma versão mais recente, a atualização exibirá uma mensagem de erro.

## <a name="troubleshooting"></a>Solução de Problemas

### <a name="controls-from-customer-card-add-in-dont-find-data"></a>Os controles do Suplemento do Cartão do Cliente não encontram dados

**Problema:**

Mesmo com campos de ID configurados corretamente, os controles não conseguem encontrar dados dos clientes.  

**Resolução:**

1. Verifique se você configurou o Suplemento do Cartão seguindo as instruções: [Configurar o Suplemento do Cartão do Cliente](#configure-the-customer-card-add-in) 

1. Consulte a configuração de ingestão de dados. Edite a fonte de dados do sistema do Dynamics 365 que contém o GUID de ID de contato. Se o GUID de ID de contato for mostrado com caracteres maiúsculos no editor do Power Query, siga estas etapas: 
    1. Edite a fonte de dados para abri-la no editor do Power Query.
    1. Selecione a coluna de ID de contato.
    1. Selecione **Transformar** na barra de cabeçalho para ver as ações disponíveis.
    1. Selecione **minúsculas**. Verifique se os GUIDs na tabela agora estão em minúsculas.
    1. Salvar a fonte de dados.
    1. Execute processos de ingestão, unificação e downstream de dados para propagar as alterações no GUID. 

Depois de concluir a atualização completa, os controles do Suplemento do Cartão do Cliente devem mostrar os dados esperados. 

[!INCLUDE[footer-include](../includes/footer-banner.md)]
