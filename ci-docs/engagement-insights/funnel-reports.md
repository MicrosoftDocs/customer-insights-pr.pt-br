---
title: Relatórios de funil
description: Como usar relatórios de funil para entender como o público toma decisões.
ms.reviewer: mhart
ms.author: kamacdon
author: kamacdon
ms.date: 06/23/2021
ms.service: customer-insights
ms.subservice: engagement-insights
ms.topic: how-to
ms.manager: shellyha
ms.openlocfilehash: 7c6b7b7285556f8a531ce9e29f0d1de162562be6fb43dd826a65fd9e00d87b30
ms.sourcegitcommit: aa0cfbf6240a9f560e3131bdec63e051a8786dd4
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2021
ms.locfileid: "7032241"
---
# <a name="create-and-manage-funnel-reports"></a>Criar e gerenciar relatórios de funil

[!INCLUDE [cc-beta-prerelease-disclaimer](includes/cc-beta-prerelease-disclaimer.md)]

Um relatório em forma de funil coleta informações sobre as etapas que ocorrem durante uma jornada do cliente por meio de seu site ou aplicativo móvel. Isso ajuda a compreender como o público progride em um processo e identifica os pontos de desistência. Por exemplo, você pode usar um relatório de funil para identificar caminhos que seus clientes percorrem antes de fazer uma compra. Um relatório de funil fornece dados para informar decisões e identificar áreas para otimização e melhorias de processo.

## <a name="create-a-funnel-report"></a>Criar um relatório de funil

Para criar o relatório de funil, especifique as etapas que deseja incluir e a atividade de cada etapa. Uma atividade é um [evento](glossary.md) que representa o comportamento do usuário. O relatório de funil exibe o número de usuários que concluíram cada etapa definida. 

1. Vá para **Funis** e selecione **+Novo funil** para iniciar um relatório de funil.

1. No **Editor de funil**, em **Etapas** selecione **+ Adicionar etapa.** 

1. Digite um nome em  **Título da etapa**.

   :::image type="content" source="media/new-funnel-report.png" alt-text="Novo relatório de funil.":::

1. Selecione uma **Atividade**. Uma atividade é registrada quando um usuário exibe uma página (atividade **Exibir**) ou interage com o conteúdo (atividade **Ação**).

1. Use **Critérios da etapa** para especificar a dimensão da atividade. [Dimensões](dimensions.md) são atributos que podem descrever, filtrar ou agrupar dados.

1. Opcionalmente, você pode configurar etapas de funil com várias condições. Selecione **Adicionar condição** para especificar mais dimensões em uma etapa. Critérios adicionais devem usar o mesmo tipo de atividade. Você pode escolher se várias condições estarão conectadas a um operador AND ou OR.

   :::image type="content" source="media/funnel-add-condition.png" alt-text="Editor de funil mostrando a configuração da etapa com etapas de várias condições.":::

1. Selecione **Adicionar etapa** até que você conclua todas as etapas que deseja no relatório.

1. Selecione **Salvar**, nomeie o relatório e **Salve** novamente. 

### <a name="example-fourth-coffee-company-funnel-report"></a>Exemplo: relatório de funil da empresa Fourth Coffee

O cenário a seguir demonstra uma maneira de usar um relatório de funil. Um analista da empresa Fourth Coffee quer entender a influência de uma promoção recente nas taxas de assinatura. O analista cria um relatório de funil para identificar a atividade do cliente. Ele começa quando os clientes chegam à página inicial da empresa até usarem o código de promoção da assinatura. O analista cria um relatório de funil com as seguintes etapas:

Etapa 1: clientes que acessam a página inicial   
Etapa 2: clientes que fazem uma compra   
Etapa 3: clientes que usam o código promocional para obter um desconto em uma assinatura   
Etapa 4: Inscrição de inscrição   

:::image type="content" source="media/funnel-report-example.png" alt-text="exemplo de relatório de funil.":::
  
Este funil permite que você veja o número de usuários que usaram o código promocional após uma compra única para se inscrever no programa de assinatura.

### <a name="configure-advanced-settings"></a>Definir configurações avançadas 

Os relatórios de funil permitem que você defina um limite para o tempo necessário para concluir um funil. Por exemplo, você pode definir o tempo para concluir o funil como quatro dias. Essa configuração contará somente as inscrições de assinatura com êxito que ocorreram em até quatro dias depois de um usuário visitar a página inicial.

1. Vá para **Funis** para abrir a **Biblioteca de funis**.

1. Selecione um nome para abrir o relatório. 

1. No painel **Editor de Funil**, selecione **Configurações avançadas**. 

1. Defina Limitar o tempo de conclusão do funil como **Ativado**.

   :::image type="content" source="media/funnel-limit-time.png" alt-text="Editor de funil mostrando as configurações avançadas e as opções para limitar o tempo para concluir um funil.":::

1. Escolha o tempo que o funil deve ter sido concluído na lista suspensa **Definir limite como**.

1. Selecione **Salvar** para aplicar suas alterações.


## <a name="cross-channel-funnel-reports"></a>Relatórios de funil entre canais 

Os insights sobre engajamento também podem coletar dados de comportamento do cliente no seu aplicativo móvel. Após instrumentar seu aplicativo móvel com o [SDK para Android](get-started-android.md) ou [SDK para iOS](get-started-ios.md) dos insights sobre engajamento, você pode criar relatórios de funil entre canais. 

### <a name="create-a-cross-channel-funnel-report"></a>Criar um relatório funil entre canais 

1. Siga as etapas para [criar um relatório funil](#create-a-funnel-report).    

1. Para acompanhar como seus clientes estão interagindo com a sua marca no seu site e aplicativo móvel, ou diversos sites, use o alternador de espaço de trabalho para criar etapas de funil com dados de outros espaços de trabalho. No **Editor funil**, em **Etapas**, selecione de qual espaço de trabalho os dados da sua etapa funil devem vir.

## <a name="manage-funnel-reports"></a>Gerenciar relatórios de funil

Você pode revisar relatórios de funil para analisar dados, controlar o desempenho e coletar insights.

> [!NOTE]
> - Os relatórios de funil de insights de interação atualmente oferecem suporte a cenários em que todos os usuários no funil são anônimos ou todos os usuários são autenticados. 
> - Os dados históricos em relatórios de funil estão disponíveis para os últimos 30 dias.

### <a name="view-funnel-reports"></a>Exibir relatórios de funil

1. Vá para **Funis** para abrir a **Biblioteca de funis**.
1. Selecione um nome para abrir o relatório.    

### <a name="see-the-data-collected-for-a-report"></a>Veja os dados coletados de um relatório   

Para ver informações sobre uma fase

- Aponte para uma etapa do relatório.

:::image type="content" source="media/funnel-step-data.png" alt-text="dados do funil.":::

### <a name="change-the-date-range-for-the-funnel-report"></a>Altere o intervalo de dados do relatório de funil

1. Vá para **Funis** para abrir a **Biblioteca de funis**.

1. Selecione um nome para abrir o relatório.

1. Abra o **intervalo de tempo** e selecione um novo período da lista ou **Período fixo** para especificar um intervalo de datas.

## <a name="edit-or-delete-funnel-reports"></a>Editar ou excluir relatórios de funil

Você pode alterar o nome de um relatório de funil, excluí-lo ou modificar as etapas do relatório.

### <a name="rename-or-delete-a-funnel-report"></a>Renomear ou excluir um relatório de funil

1. Vá para **Funis** para abrir a **Biblioteca de funis**. 

1. Selecione **Mais** ao lado do relatório que você deseja alterar e escolha **Editar nome** ou **Excluir**.

### <a name="edit-a-funnel-step"></a>Editar uma etapa de funil  

1. Vá para **Funis** para abrir a **Biblioteca de funis**. 

1. Selecione um nome para abrir o relatório.

1. Selecione a etapa que deseja editar.

1. Selecione **Editar**.

1. No **Editor de Funil**, atualize as informações que deseja alterar.  

1. Selecione **Salvar**.

### <a name="reorder-a-funnel-step"></a>Reordenar uma etapa de funil

1. Vá para **Funis** para abrir a **Biblioteca de funis**. 

1. Selecione um nome para abrir o relatório.

1. Selecione a etapa que deseja reordenar.

1. Selecione **Mover**, e depois **Para cima**, **Para baixo**, **Para o início** ou **Para o final**, para mover a etapa.

### <a name="delete-a-funnel-step"></a>Excluir uma etapa de funil

1. Vá para **Funis** para abrir a **Biblioteca de funis**. 

1. Selecione um nome para abrir o relatório.

1. Selecione a etapa que deseja remover e escolha **Excluir**.

