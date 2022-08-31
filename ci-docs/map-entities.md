---
title: Selecionar campos de origem para unificação de dados
description: A primeira etapa no processo de unificação é selecionar entidades, atributos, chaves primárias e tipos semânticos para mapear dados para o perfil de cliente unificado.
recommendations: false
ms.date: 08/12/2022
ms.subservice: audience-insights
ms.topic: tutorial
author: v-wendysmith
ms.author: mukeshpo
ms.reviewer: v-wendysmith
manager: shellyha
searchScope:
- ci-map
- ci-match
- customerInsights
ms.openlocfilehash: bc120aa7a3713e1184ff278edf0942925faafa12
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304551"
---
# <a name="select-source-fields-for-data-unification"></a>Selecionar campos de origem para unificação de dados

A primeira etapa na unificação é selecionar as entidades e os campos nos conjuntos de dados que você deseja unificar. Selecione entidades que contenham detalhes relacionados ao cliente, como nome, endereço, número de telefone e email. Você pode selecionar uma ou mais entidades.

[!INCLUDE [m3-first-run-note](includes/m3-first-run-note.md)]

## <a name="select-entities-and-fields"></a>Selecionar entidades e campos

1. Acesse **Dados** > **Unificar**.

   Para clientes individuais (B-to-C), é exibida a página de aterrissagem **Unificar** mostrando **Começar agora** na primeira etapa, **Campos de origem**.

   :::image type="content" source="media/m3_unify_land.png" alt-text="Captura de tela da página de aterrissagem unificada para experiência de primeira execução para clientes individuais.":::

   Para contas corporativas (B-to-B), a página de aterrissagem **Unificar** exibe **Unificar contas** mostrando **Começar agora** na primeira etapa, **Campos de origem**. As etapas **Unificar contatos (versão preliminar)** são opcionais e estão pendentes de conclusão da unificação da conta.

   :::image type="content" source="media/b2b_unify_land.png" alt-text="Captura de tela da página de aterrissagem unificada para experiência de primeira execução para contas corporativas.":::

1. Selecione **Introdução**.

1. Na página **Campos de origem**, selecione **Selecionar entidades e campos**. O painel **Selecionar entidades e campos** é exibido.

1. Selecione pelo menos uma entidade.

1. Para cada entidade selecionada, identifique os campos que deseja usar para corresponder aos registros do cliente e aos campos a serem incluídos no perfil unificado. Esses campos são chamados *Atributos*. Você pode selecionar os atributos necessários individualmente de uma entidade ou incluir todos os atributos de uma entidade marcando a caixa de seleção no nível da entidade. Você pode pesquisar palavras-chave em todos os atributos e entidades para selecionar os atributos necessários que deseja mapear.

   :::image type="content" source="media/m3_select_entities.png" alt-text="Captura de tela de entidades e atributos selecionados.":::

   Neste exemplo, estamos adicionando as entidades **eCommerceContacts** e **loyCustomer**. Ao escolher essas entidades, você pode obter insights nos quais clientes de negócios online são membros do programa de fidelidade.

1. Selecione **Aplicar** para confirmar suas seleções. As entidades e atributos selecionados são exibidos.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selecione a chave primária e o tipo semântico dos atributos

   :::image type="content" source="media/m3_select_primary.png" alt-text="Captura de tela de entidades selecionadas com chave primária ainda não selecionada." lightbox="media/m3_select_primary.png":::

Para cada entidade, execute as etapas a seguir.

1. Escolha a **Chave primária**. A chave primária é um atributo exclusivo da entidade. Para um atributo ser uma chave primária válida, ele não deve ter valores duplicados, valores ausentes ou valores nulos. Os atributos de tipo de dados de cadeia de caracteres, inteiro e GUID são compatíveis como chaves primárias.

1. Para usar modelos de IA para previsão inteligente de semântica que economiza tempo e melhora a precisão, verifique se o **Mapeamento inteligente** está ativado. O mapeamento inteligente fornece recomendações semânticas baseadas em IA no campo **Tipo**.

1. Para cada atributo, escolha uma semântica **Tipo** que melhor descreve esse atributo, como nome, cidade ou endereço de email.

   > [!NOTE]
   > Em B-to-C, um campo deve mapear para o tipo semântico *Person.FullName* para preencher o nome do cliente no cartão do cliente. Em B-to-B, o nome da conta deve mapear para *Organization.Name*. Caso contrário, os cartões do cliente aparecerão sem nome.

   1. Para substituir um tipo de atributo identificado pelo sistema, selecione outra opção. Se o tipo não existir, crie um tipo semântico personalizado selecionando o campo **Tipo** para o atributo e inserindo o nome do tipo semântico personalizado.

   1. Para adicionar um atributo que contém uma URL a imagens ou logotipos de perfil disponíveis publicamente, selecione a entidade e o campo que contêm a URL. No campo **Tipo**, insira o seguinte:
      - Para uma pessoa: Person.ProfileImage
      - Para uma organização: Organization.LogoImage

1. Revise os atributos em que um tipo semântico é identificado automaticamente. Esses atributos estão listados em **Revisar campos mapeados**. Somente atributos com o mesmo tipo podem ser combinados na etapa **Unificar campos de cliente**. Os tipos semânticos são usados para sugerir insights automaticamente. Certifique-se de que os tipos escolhidos sejam consistentes em todas as entidades selecionadas.

1. Para atributos que não são mapeados automaticamente para um tipo semântico, selecione um campo de tipo semântico, insira o nome do tipo de atributo personalizado ou deixe-os sem mapeamento. Esses atributos estão listados em **Definir os dados nos campos não mapeados**.

1. Depois de concluir as etapas para cada entidade, selecione **Salvar campos de origem**.

1. Selecione **Avançar**

> [!div class="nextstepaction"]
> [Próxima etapa: remover duplicatas](remove-duplicates.md)

[!INCLUDE [footer-include](includes/footer-banner.md)]
