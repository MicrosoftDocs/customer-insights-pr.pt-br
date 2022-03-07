---
title: Criar e gerenciar ambientes
description: Saiba como se inscrever no serviço e gerenciar ambientes.
ms.date: 12/06/2021
ms.subservice: audience-insights
ms.topic: how-to
ms.reviewer: mhart
author: NimrodMagen
ms.author: nimagen
manager: shellyha
searchScope:
- ci-system-about
- customerInsights
ms.openlocfilehash: d9e0ee726dbbfcf330022c4d95747551d3114e7e
ms.sourcegitcommit: 73cb021760516729e696c9a90731304d92e0e1ef
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/25/2022
ms.locfileid: "8354265"
---
# <a name="manage-environments"></a>Gerenciar ambientes



## <a name="switch-environments"></a>Alternar ambientes

Selecione o controle de **Ambiente** no canto superior direito da página para alterar os ambientes.

:::image type="content" source="media/home-page-environment-switcher.png" alt-text="Captura de tela do controle para alternar ambientes.":::

Os administradores podem [criar](create-environment.md) e gerenciar ambientes.

## <a name="edit-an-existing-environment"></a>Editar um ambiente existente

Você pode editar alguns dos detalhes dos ambientes existentes.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

2.  Selecione o ícone **Editar**.

3. Na caixa **Editar ambiente**, você pode atualizar as configurações de ambiente.

Para obter mais informações sobre configurações de ambiente, consulte [Crie um novo ambiente](create-environment.md).

## <a name="connect-to-microsoft-dataverse"></a>Conectar-se ao Microsoft Dataverse
   
A etapa **Microsoft Dataverse** permite conectar o Customer Insights com o seu ambiente Dataverse.

Para usar [modelos de previsão prontos para uso](predictions-overview.md#out-of-box-models), configure o compartilhamento de dados com o Dataverse. Ou você pode ativar a ingestão de dados de fontes de dados na infraestrutura local, fornecendo o URL do ambiente Microsoft Dataverse que sua organização administra.

> [!IMPORTANT]
> O Customer Insights e o Dataverse devem estar na mesma região para habilitar o compartilhamento de dados.

:::image type="content" source="media/dataverse-provisioning.png" alt-text="Opções de configuração para habilitar o compartilhamento de dados com o Microsoft Dataverse.":::

> [!NOTE]
> O Customer Insights não suporta os seguintes cenários de compartilhamento de dados:
> - Se salvar todos os dados no seu próprio Azure Data Lake Storage, você não poderá habilitar o compartilhamento de dados com um data lake gerenciado do Dataverse.
> - Se você ativar o compartilhamento de dados com o Dataverse, você não será capaz de [criar valores previstos ou ausentes em uma entidade](predictions.md).

## <a name="copy-the-environment-configuration"></a>Copiar a configuração do ambiente

Ao criar um ambiente, você pode optar por copiar a configuração de um ambiente existente. 

:::image type="content" source="media/environment-settings-dialog.png" alt-text="Captura de tela das opções de configuração nas configurações do ambiente.":::

Você verá uma lista de todos os ambientes disponíveis da sua organização, dos quais é possível copiar dados.

As seguintes configurações são copiadas:

- Fontes de dados ingeridas/importadas
- Configuração de unificação de dados (Mapear, Corresponder, Mesclar)
- Segmentos
- Medidas
- Relações
- Atividades
- Índice de filtro e pesquisa
- Exportar destinos
- Atualização agendada
- Enriquecimentos
- Gerenciamento de modelos
- Atribuições de função

Os seguintes dados *não* são copiados:

- Perfis do cliente.
- Credenciais da fonte de dados. Você precisará fornecer as credenciais para cada fonte de dados e atualizar as fontes de dados manualmente.

- Fontes de dados da pasta do Common Data Model e do data lake gerenciado do Dataverse. Você precisará criar essas fontes de dados manualmente com o mesmo nome do ambiente de origem.

Ao copiar um ambiente, você verá uma mensagem de confirmação de que o novo ambiente foi criado. Selecione **Ir para fontes de dados** para ver a lista de fontes de dados.

Todas as fontes de dados mostrarão um status **Credenciais Necessárias**. Edite as fontes de dados e insira as credenciais para atualizá-las.

:::image type="content" source="media/data-sources-copied.png" alt-text="Lista de fontes de dados que foram copiadas e precisam de autenticação.":::

Após atualizar as fontes de dados, vá para **Dados** > **Unificar**. Aqui você encontrará configurações do ambiente de origem. Edite-os conforme necessário ou selecione **Executar** para iniciar o processo de unificação de dados e criar a entidade unificada do cliente.

Quando a unificação de dados estiver concluída, vá para **Medidas** e **Segmentos** para atualizá-los também.

## <a name="reset-an-existing-environment"></a>Redefinir um ambiente existente

Como administrador, você pode redefinir um ambiente para um estado vazio se quiser excluir todas as configurações e remover os dados ingeridos.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo. 

2.  Selecione o ambiente que deseja redefinir selecione as reticências (**...**). 

3. Escolha a opção **Redefinir**. 

4.  Para confirmar a exclusão, insira o nome do ambiente e selecione **Redefinir**.

## <a name="delete-an-existing-environment"></a>Excluir um ambiente existente

Como administrador, é possível excluir um ambiente administrado por você.

1.  Selecione o seletor de **Ambiente** no cabeçalho do aplicativo.

2.  Selecione o ambiente que deseja redefinir selecione as reticências (**...**). 

3. Escolha a opção **Excluir**. 

4.  Para confirmar a exclusão, insira o nome do ambiente e selecione **Excluir**.


[!INCLUDE[footer-include](../includes/footer-banner.md)]
