---
title: Exportar dados do Customer Insights para o Adobe Campaign Standard
description: Saiba como usar os segmentos de insights de público-alvo no Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: b6c010d84119c2fa8b3ef99017c65f9939bf28c4
ms.sourcegitcommit: 1b671c6100991fea1cace04b5d4fcedcd88aa94f
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5760267"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Usar segmentos do Customer Insights no Adobe Campaign Standard (versão preliminar)

Como um usuário de insights de público-alvo para o Dynamics 365 Customer Insights, você pode ter criado segmentos para tornar suas campanhas de marketing mais eficientes, visando públicos-alvo relevantes. Para usar um segmento de insights de público-alvo na Adobe Experience Platform e em aplicativos, como o Adobe Campaign Standard, você deve seguir algumas etapas descritas neste artigo.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama do processo das etapas descritas neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

-   Licença do Dynamics 365 Customer Insights
-   Licença do Adobe Campaign Standard
-   Conta de Armazenamento de Blobs do Azure

## <a name="campaign-overview"></a>Visão Geral da Campanha

Para entender melhor como você pode usar segmentos de insights de público-alvo na Adobe Experience Platform, vamos examinar um exemplo de campanha fictício.

Vamos supor que sua empresa ofereça um serviço mensal baseado em assinatura para seus clientes nos Estados Unidos. Você deseja identificar os clientes com assinaturas que devem ser renovadas nos próximos oito dias, mas que ainda não renovaram a assinatura. Para manter esses clientes, você deseja enviar a eles uma oferta promocional por email, usando o Adobe Campaign Standard.

Neste exemplo, queremos executar a campanha promocional por email uma vez. Este artigo não aborda o caso de uso de execução da campanha mais de uma vez. No entanto, os insights de público-alvo e o Adobe Campaign Standard também podem ser configurados para funcionar em um cenário de campanha recorrente.

## <a name="identify-your-target-audience"></a>Identificar o público-alvo

Em nosso cenário, presumimos que os endereços de email dos clientes estão disponíveis nos insights de público-alvo e suas preferências promocionais foram analisadas para identificar os membros do segmento.

O [segmento que você definiu nos insights de público-alvo](segments.md) é chamado **ChurnProneCustomers** e você planeja enviar a promoção por email a esses clientes.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de tela da página de segmentos com o segmento ChurnProneCustomers criado.":::

O email de oferta que você deseja enviar conterá o nome, o sobrenome e a data de término da assinatura do cliente. Ele informa os clientes sobre o desconto que terão se renovarem a assinatura antes que ela expire.

## <a name="export-your-target-audience"></a>Exportar o público-alvo

### <a name="configure-a-connection"></a>Configurar uma conexão

Com nosso público-alvo identificado, podemos configurar a exportação dos insights de público-alvo para uma conta de Armazenamento de Blobs do Azure.

1. Em insights do público-alvo, acesse **Administrador** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Campanha da Adobe** para configurar a conexão ou selecione **Configurar** no bloco **Campanha da Adobe**

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Bloco de configuração para o Adobe Campaign Standard.":::

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Insira o **Nome da conta**, a **Chave de conta** e o **Contêiner** da conta de Armazenamento de Blobs do Azure para a qual deseja exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de tela da configuração da conta de armazenamento. "::: 

   - Para saber mais sobre como encontrar o nome e a chave da conta do Azure Blob Storage, consulte [Gerenciar as configurações da conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

   - Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Salvar** para concluir a conexão.

### <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma exportação, selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão da seção da Campanha do Adobe. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

1. Escolha o segmento que você deseja exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de tela da interface do usuário de seleção de segmentos com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Avançar**.

1. Agora mapeamos os campos **Origem** do segmento de insights de público-alvo para os nomes de campo **Destino** no esquema de perfil do Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapeamento de campo para o conector do Adobe Campaign Standard.":::

   Se quiser adicionar mais atributos, selecione **Adicionar atributo**. O nome do destino pode ser diferente do nome do campo de origem para que você ainda possa mapear a saída do segmento de insights de público-alvo para o Adobe Campaign Standard se os campos não tiverem o mesmo nome nos dois sistemas.

   > [!NOTE]
   > O endereço de email é usado como um campo de identidade, mas você pode usar qualquer outro identificador do perfil do cliente de seus insights de público-alvo para mapear os dados para o Adobe Campaign Standard.

1. Selecione **Salvar**.

Depois de salvar o destino da exportação, você a encontrará em **Dados** > **Exportações**.

Agora você pode [exportar o segmento sob demanda](export-destinations.md#run-exports-on-demand). A exportação também será executada a cada [atualização agendada](system.md).

> [!NOTE]
> Certifique-se de que o número de registros no segmento exportado esteja dentro do limite permitido de sua licença do Adobe Campaign Standard.

Os dados exportados são armazenados no contêiner de Armazenamento de Blobs do Azure que você configurou acima. O seguinte caminho de pasta é criado automaticamente em seu contêiner:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar o Adobe Campaign Standard

Quando um segmento de insights de público-alvo é exportado, ele contém as colunas que você selecionou ao definir o destino da exportação na etapa anterior. Esses dados podem ser usados para [criar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para usar o segmento no Adobe Campaign Standard, precisamos estender o esquema do perfil no Adobe Campaign Standard para incluir dois campos adicionais. Saiba como [estender o recurso de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) com novos campos no Adobe Campaign Standard.

Em nosso exemplo, esses campos são *Nome do segmento e Data do segmento (opcional).*

Usaremos esses campos para identificar os perfis no Adobe Campaign Standard para os quais queremos direcionar para esta campanha.

Se não houver outros registros no Adobe Campaign Standard, além dos que vai importar, você poderá ignorar esta etapa.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar dados para o Adobe Campaign Standard

Agora que tudo está pronto, precisamos importar os dados do público-alvo preparados a partir dos percepções de público-alvo para o Adobe Campaign Standard para criar perfis. Saiba [como importar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando um fluxo de trabalho.

O fluxo de trabalho de importação na imagem abaixo foi configurado para ser executado a cada 8 horas e procura segmentos de insights de público-alvo exportados (arquivo .csv no Armazenamento de Blobs do Azure). O fluxo de trabalho extrai o conteúdo do arquivo .csv em uma ordem de coluna especificada. Este fluxo de trabalho foi criado para executar o tratamento básico de erros e garantir que cada registro tenha um endereço de email antes de hidratar os dados no Adobe Campaign Standard. O fluxo de trabalho também extrai o nome do segmento do nome do arquivo antes de executar upsert nos dados do Perfil do ACS.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de tela de um fluxo de trabalho de importação na interface de usuário do Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recuperar o público-alvo no Adobe Campaign Standard

Depois que os dados forem importados para o Adobe Campaign Standard, você [poderá criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes com base no *Nome do Segmento* e na *Data do Segmento* para selecionar os perfis que foram identificados para nossa campanha de exemplo.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o email usando o Adobe Campaign Standard

Crie o conteúdo do email e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o email.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplo de email com oferta de renovação do Adobe Campaign Standard.":::
