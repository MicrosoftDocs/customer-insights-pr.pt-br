---
title: Exportar dados do Customer Insights para o Adobe Campaign Standard
description: Saiba como usar segmentos do Customer Insights no Adobe Campaign Standard.
ms.date: 03/29/2021
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: stefanie-msft
ms.author: antando
manager: shellyha
ms.openlocfilehash: 2a62d2f889f199222eeb8cc969fce62fa89fa6f0
ms.sourcegitcommit: b7dbcd5627c2ebfbcfe65589991c159ba290d377
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2022
ms.locfileid: "8645656"
---
# <a name="use-customer-insights-segments-in-adobe-campaign-standard-preview"></a>Use segmentos do Customer Insights no Adobe Campaign Standard (versão preliminar)

Como usuário do Dynamics 365 Customer Insights, você pode ter criado segmentos para tornar campanhas de marketing mais eficientes ao segmentar públicos-alvo relevantes. Para usar um segmento do Customer Insights no Adobe Experience Platform e aplicativos como o Adobe Campaign Standard, você precisa seguir algumas etapas descritas neste artigo.

:::image type="content" source="media/ACS-flow.png" alt-text="Diagrama do processo das etapas descritas neste artigo.":::

## <a name="prerequisites"></a>Pré-requisitos

-   Licença do Dynamics 365 Customer Insights
-   Licença do Adobe Campaign Standard
-   Conta de Armazenamento de Blobs do Azure

## <a name="campaign-overview"></a>Visão geral da campanha

Para entender melhor como usar segmentos do Customer Insights no Adobe Experience Platform, vejamos uma campanha de amostra fictícia.

Vamos supor que sua empresa ofereça um serviço mensal baseado em assinatura para seus clientes nos Estados Unidos. Você deseja identificar os clientes com assinaturas que devem ser renovadas nos próximos oito dias, mas que ainda não renovaram a assinatura. Para manter esses clientes, você deseja enviar a eles uma oferta promocional por email, usando o Adobe Campaign Standard.

Neste exemplo, queremos executar a campanha promocional por email uma vez. Este artigo não aborda o caso de uso de execução da campanha mais de uma vez. No entanto, também é possível configurar o Customer Insights e o Adobe Campaign Standard para funcionar em um cenário de campanha recorrente.

## <a name="identify-your-target-audience"></a>Identificar o público-alvo

Em nosso cenário, supomos que os endereços de email dos clientes estão disponíveis e as preferências promocionais foram analisadas para identificar membros do segmento.

O [segmento que você definiu no Customer Insights](segments.md) é chamado de **ChurnProneCustomers** e você pretende enviar a esses clientes a promoção por email.

:::image type="content" source="media/churn-prone-customers-segment.png" alt-text="Captura de tela da página de segmentos com o segmento ChurnProneCustomers criado.":::

O email de oferta que você deseja enviar conterá o nome, o sobrenome e a data de término da assinatura do cliente. Ele informa os clientes sobre o desconto que terão se renovarem a assinatura antes que ela expire.

## <a name="export-your-target-audience"></a>Exportar o público-alvo

### <a name="configure-a-connection"></a>Configurar uma conexão

Com nosso público-alvo identificado, podemos configurar a exportação para uma conta de Armazenamento de Blobs do Azure.

1. No Customer Insights, vá para **Administrador** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Adobe Campaign** para configurar a conexão ou selecione **Configurar** no bloco **Adobe Campaign**.

   :::image type="content" source="media/adobe-campaign-standard-tile.png" alt-text="Bloco de configuração para o Adobe Campaign Standard.":::

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Insira o **Nome da conta**, a **Chave de conta** e o **Contêiner** da conta de Armazenamento de Blobs do Azure para a qual deseja exportar o segmento.  
      
   :::image type="content" source="media/azure-blob-configuration.png" alt-text="Captura de tela da configuração da conta de armazenamento. "::: 

   - Para saber mais sobre como encontrar o nome e a chave da conta do Azure Blob Storage, consulte [Gerenciar configurações de conta de armazenamento no portal do Azure](/azure/storage/common/storage-account-manage).

   - Para saber como criar um contêiner, consulte [Criar um container](/azure/storage/blobs/storage-quickstart-blobs-portal#create-a-container).

1. Selecione **Salvar** para concluir a conexão.

### <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma exportação, selecione **Adicionar exportação**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção Adobe Campaign. Se você não vir este nome de seção, significa que não há conexões desse tipo disponíveis para você.

1. Escolha o segmento que você deseja exportar. Neste exemplo, é **ChurnProneCustomers**.

   :::image type="content" source="media/select-segment-churnpronecustomers.png" alt-text="Captura de tela da interface do usuário de seleção de segmentos com o segmento ChurnProneCustomers selecionado.":::

1. Selecione **Avançar**

1. Agora mapeamos o campo **Fonte** do segmento Customer Insights para nomes do campo **Alvo** no esquema de perfil do Adobe Campaign Standard.

   :::image type="content" source="media/ACS-field-mapping.png" alt-text="Mapeamento de campo para conector do Adobe Campaign Standard.":::

   Se quiser adicionar mais atributos, selecione **Adicionar atributo**. O nome de destino pode ser diferente do nome do campo de origem; portanto, você ainda poderá mapear a saída do segmento do Customer Insights para o Adobe Campaign Standard se os campos não tiverem o mesmo nome nos dois sistemas.

   > [!NOTE]
   > O endereço de email é usado como um campo de identidade, mas você pode usar qualquer outro identificador do perfil do cliente para mapear dados para o Adobe Campaign Standard.

1. Selecione **Salvar**.

Depois de salvar o destino da exportação, você a encontrará em **Dados** > **Exportações**.

Agora você pode [exportar o segmento sob demanda](export-destinations.md#run-exports-on-demand). A exportação também será executada a cada [atualização agendada](system.md).

> [!NOTE]
> Certifique-se de que o número de registros no segmento exportado esteja dentro do limite permitido da sua licença do Adobe Campaign Standard.

Os dados exportados são armazenados no contêiner do Azure Blob Storage que você configurou acima. O seguinte caminho de pasta é criado automaticamente em seu contêiner:

*%ContainerName%/CustomerInsights_%instanceID%/% exportdestination-name%_%segmentname%_%timestamp%.csv*

Exemplo: Dynamics365CustomerInsights/CustomerInsights_abcd1234-4312-11f4-93dc-24f72f43e7d5/ChurnSegmentDemo_ChurnProneCustomers_1613059542.csv

## <a name="configure-adobe-campaign-standard"></a>Configurar o Adobe Campaign Standard

Os segmentos exportados contêm as colunas que você selecionou ao definir o destino de exportação na etapa anterior. Esses dados podem ser usados para [criar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/about-profiles.html#managing-profiles).

Para usar o segmento no Adobe Campaign Standard, precisamos estender o esquema de perfis no Adobe Campaign Standard para incluir dois campos adicionais. Saiba como [estender o recurso de perfil](https://experienceleague.adobe.com/docs/campaign-standard/using/developing/use-cases--extending-resources/extending-the-profile-resource-with-a-new-field.html#developing) com novos campos no Adobe Campaign Standard.

Em nosso exemplo, esses campos são *Nome do Segmento e Data do segmento (opcional)*.

Usaremos esses campos para identificar os perfis no Adobe Campaign Standard que desejamos segmentar para esta campanha.

Se não houver outros registros no Adobe Campaign Standard, além do que será importado, você poderá ignorar esta etapa.

## <a name="import-data-into-adobe-campaign-standard"></a>Importar dados para o Adobe Campaign Standard

Agora que tudo está pronto, precisamos importar os dados de público-alvo preparados do Customer Insights para o Adobe Campaign Standard para criar perfis. Saiba [como importar perfis no Adobe Campaign Standard](https://experienceleague.adobe.com/docs/campaign-standard/using/profiles-and-audiences/managing-profiles/creating-profiles.html#profiles-and-audiences) usando um fluxo de trabalho.

O fluxo de trabalho de importação na imagem abaixo foi configurado para ser executado a cada oito horas e procurar segmentos exportados do Customer Insights (arquivo .csv no Armazenamento de Blobs do Azure). O fluxo de trabalho extrai o conteúdo do arquivo .csv em uma ordem de coluna especificada. Este fluxo de trabalho foi criado para realizar o tratamento de erros básicos e garantir que cada registro tenha um endereço de email antes de hidratar os dados no Adobe Campaign Standard. O fluxo de trabalho também extrai o nome do segmento do nome do arquivo antes de fazer upsert para dados de perfis do Adobe Campaign Standard.

:::image type="content" source="media/ACS-import-workflow.png" alt-text="Captura de tela de um fluxo de trabalho de importação na interface de usuário do Adobe Campaign Standard.":::

## <a name="retrieve-the-audience-in-adobe-campaign-standard"></a>Recupere o público-alvo no Adobe Campaign Standard

Após a importação dos dados para o Adobe Campaign Standard, você [poderá criar um fluxo de trabalho](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/workflow-general-operation/building-a-workflow.html#managing-processes-and-data) e [consultar](https://experienceleague.adobe.com/docs/campaign-standard/using/managing-processes-and-data/targeting-activities/query.html#managing-processes-and-data) os clientes com base no *Nome do Segmento* e na *Data do Segmento* para selecionar perfis que foram identificados para nossa campanha de exemplo.

## <a name="create-and-send-the-email-using-adobe-campaign-standard"></a>Criar e enviar o email usando o Adobe Campaign Standard

Crie o conteúdo do email e, em seguida, [teste e envie](https://experienceleague.adobe.com/docs/campaign-standard/using/testing-and-sending/get-started-sending-messages.html#preparing-and-testing-messages) o email.

:::image type="content" source="media/contoso-sample-email.jpg" alt-text="Exemplo de email com oferta de renovação do Adobe Campaign Standard.":::
