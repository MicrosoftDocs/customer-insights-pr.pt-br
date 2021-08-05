---
title: Mapear entidades para unificação de dados
description: Mapeie dados para criar perfis de clientes unificados.
ms.date: 09/25/2020
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: tutorial
author: adkuppa
ms.author: adkuppa
ms.reviewer: mhart
manager: shellyha
ms.openlocfilehash: 7fc05aca61d1136f620019ee82dc6937ea39d8e5
ms.sourcegitcommit: dab2cbf818fafc9436e685376df94c5e44e4b144
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/13/2021
ms.locfileid: "6555109"
---
# <a name="map-entities-and-attributes"></a>Mapear entidades e atributos

**Mapear** é o primeiro estágio do processo de unificação de dados de insights de público-alvo. O mapeamento consiste em três fases:

- *Seleção de entidade* : Identifique as entidades combináveis que levam a um conjunto de dados com informações mais completas sobre seus clientes.
- *Seleção de atributo*: Para cada entidade, identifique as colunas que você deseja combinar e reconcilie nas fases *corresponder* e *mesclar*. Essas colunas são chamadas *Atributos*.
- *Seleção de chave primária e tipo semântico*: Para cada entidade, identifique um atributo que deseja definir como a chave primária dessa entidade e, para cada atributo, identifique um tipo semântico que melhor descreve esse atributo.

Para obter mais informações sobre o fluxo geral de unificação de dados, consulte [Unificar](data-unification.md).

## <a name="select-the-first-entities"></a>Selecione as primeiras entidades

1. Nos insights de público-alvo, vá para **Dados** > **Unificar** > **Mapear**.

2. Inicie a fase de mapeamento escolhendo **Selecionar entidades**.

3. Selecione as entidades e atributos que deseja usar nas fases de *correspondência* e *mesclagem*. Você pode selecionar os atributos necessários individualmente de uma entidade ou incluir todos os atributos de uma entidade marcando a caixa de seleção **Incluir todos os campos** no nível da entidade. Recomendamos selecionar pelo menos duas entidades para se beneficiar do processo de unificação de dados.

   > [!div class="mx-imgBorder"]
   > ![Adicionar exemplos de entidades.](media/data-manager-configure-map-add-entities-example.png "Adicionar exemplo de entidades")

   Neste exemplo, estamos adicionando as entidades **eCommerceContacts** e **loyCustomers**. Ao escolher essas entidades, você pode obter insights nos quais clientes de negócios online são membros do programa de fidelidade.
   
   Você pode pesquisar palavras-chave em todos os atributos e entidades para selecionar os atributos necessários que deseja mapear.
   
     > [!div class="mx-imgBorder"]
   > ![Exemplo de campos de pesquisa.](media/data-manager-configure-map-search-fields-example.png "Exemplo de campos de pesquisa")

4. Selecione **Aplicar** para confirmar suas seleções.

## <a name="select-primary-key-and-semantic-type-for-attributes"></a>Selecione a chave primária e o tipo semântico dos atributos

Depois de selecionar suas entidades, a página **Mapa** lista as entidades selecionadas para sua revisão. Defina a chave primária para uma entidade e identifique o tipo semântico de um atributo na entidade.

- **Chave primária**: Selecione um atributo como chave primária para cada uma de suas entidades. Para um atributo ser uma chave primária válida, ele não deve ter valores duplicados, valores ausentes ou valores nulos. Os atributos de tipo de dados cadeia de caracteres, inteiro e GUID têm suporte como chaves primárias e serão exibidos em um campo para você selecionar.

- **Tipo de semântico de atributo**: Categorias de seus atributos, como endereço de email ou nome. Para usar modelos de IA para previsão inteligente de semântica, economizar tempo e melhorar a precisão, defina **Mapeamento inteligente** como **ATIVADO**. O mapeamento inteligente destaca a recomendação de semântica baseada em IA no campo **Tipo**. Se defini-lo como **DESATIVADO**, você verá nossas recomendações de mapeamento regulares. Você pode selecionar qualquer tipo semântico da lista de opções disponível e substituir a seleção sugerida.

> [!div class="mx-imgBorder"]
> ![Tipo de atributo e previsão semântica.](media/data-manager-configure-map-add-attributes-semantic-prediction.png "Tipo de atributo e previsão semântica")

Também é possível adicionar um tipo semântico personalizado. Selecione o campo de tipo para um atributo e digite seu nome de tipo semântico personalizado. Dessa forma, você também pode alterar os tipos de atributos que foram identificados pelo sistema.

Todos os atributos para os quais um tipo semântico é automaticamente identificado são agrupados na seção **Rever campos mapeados**. Revise esses atributos e seus tipos semânticos, pois eles serão usados para combinar suas entidades na etapa de mesclagem da unificação de dados.

Atributos que não são mapeados automaticamente para um tipo semântico são agrupados na seção **Definir os dados nos campos não mapeados**. Selecione o campo de tipo semântico para os atributos não mapeados ou insira seu nome de tipo de atributo personalizado.

> [!div class="mx-imgBorder"]
> ![Chave primária e tipo de atributo.](media/data-manager-configure-map-add-attributes.png "Chave primária e tipo de atributo")

> [!NOTE]
> Um campo deve ser mapeado para o tipo semântico Person.FullName para preencher o nome do cliente no cartão do cliente. Caso contrário, os cartões do cliente aparecerão sem nome. 

## <a name="add-and-remove-attributes-and-entities"></a>Adicionar e remover atributos e entidades

1. Em **Unificar** > **Mapa**, selecione **Editar campos**.

2. No painel **Editar campos**, adicione ou remova atributos e entidades. Use a pesquisa ou role para localizar e selecionar seus atributos e entidades de interesse. Você não pode remover um atributo ou uma entidade se eles já foram correspondidos.

   > [!div class="mx-imgBorder"]
   > ![Adicionar ou remover atributos.](media/configure-data-map-edit.png "Adicionar ou remover atributos")

3. Selecione **Aplicar**.

## <a name="add-images-to-profiles"></a>Adicionar imagens aos perfis

Se uma entidade contiver URLs para imagens ou logotipos de perfil disponíveis publicamente, você poderá adicioná-los ao perfil de cliente unificado.

Selecione a entidade e encontre o campo que contém a URL para a imagem do perfil. No campo de entrada **Tipo**, insira manualmente o seguinte valor: 
- Para uma pessoa: Person.ProfileImage
- Para uma organização: Organization.LogoImage

Continue com as etapas de unificação e certifique-se de que o atributo que contém a URL da imagem também seja adicionada à etapa [Mesclar](merge-entities.md).

## <a name="set-attributes-for-organizations"></a>Definir atributos para organizações

Para organizações (Visualização), o tipo de atributo deve ser mapeado para "Organization.Name"
> [!div class="mx-imgBorder"]
> ![Chave primária e tipo de atributo B2B](media/configure-data-map-edit-b2b.png "Chave primária e tipo de atributo B2B")

## <a name="next-step"></a>Próxima etapa

Como parte do processo de unificação de dados, vá para a página **Corresponder**. Visite [**Corresponder**](match-entities.md) para aprender sobre esta fase.

> [!TIP]
> Confira o seguinte vídeo: [Introdução: Criando um Perfil de Cliente Unificado](https://youtu.be/oBfGEhucAxs).


[!INCLUDE[footer-include](../includes/footer-banner.md)]