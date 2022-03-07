---
title: Gerenciar permissões de usuário
description: Saiba mais sobre permissões e funções de usuário.
ms.date: 10/27/2020
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: NimrodMagen
ms.author: nimagen
manager: shellyha
ms.openlocfilehash: e58bb1a3bd4c0920ff984daffabbf16162185f3d
ms.sourcegitcommit: bae40184312ab27b95c140a044875c2daea37951
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "5595688"
---
# <a name="user-permissions"></a>Permissões de usuário

Na página **Permissões**, você configurará funções e permissões para usar insights de público-alvo.

Você precisa ter permissões de administrador para ver a página. Para acessar a página de permissões nos insights de público-alvo, vá para **Administrador** > **Permissões**.

Há três tipos de funções:

## <a name="viewer"></a>Espectador

- Explore insights e segmentos nas páginas **Página Inicial** e **Segmentos**.
- Pesquise e filtre perfis do cliente usando a página **Clientes**. Os campos devem ser pesquisáveis.
- Exiba e explore a página **Enriquecimento**.
- Explorar e exportar entidades usando a página **Entidades**.
- Exiba o status dos processos do sistema usando a página **Sistema**.
- Exporte segmentos da página **Segmentos**.
- Instale e use o painel **Power BI Customer Insights**.

## <a name="contributor"></a>Colaborador

- Todas as permissões disponíveis para o Visualizador.
- Carregue e transforme dados usando a página **Fontes de dados**.
- Preencha as seções de *Unificação de Dados* (**Mapear**, **Corresponder** e **Mesclar**) que resultam na entidade de perfil de cliente unificado.
- Defina **Relacionamentos** e **Atividades**.
- Crie segmentos usando a página **Segmentos**.
- Crie medidas usando a página **Medidas**.
- Gerencie a configuração e enriqueça os perfis de cliente na página **Enriquecimento** (somente para os primeiros enriquecimentos da parte).

## <a name="administrator"></a>Administrador

- Todas as permissões disponíveis para o Colaborador.
- Altere as configurações na página **Sistema**, incluindo o idioma de trabalho, e atualize os cronogramas de seus processos do sistema.
- Exiba e adicione permissões usando a página **Permissões**.
- Configure as definições de filtro e pesquisa para a página Clientes usando a página **Índice de filtro e pesquisa** (accessível pela página **Clientes**).
- Defina os destinos do segmento do Dynamics 365 Sales usando a página **Exportar destinos**.
- Gerencie a configuração e enriqueça os perfis de cliente na página **Enriquecimento** (para todos os enriquecimentos).
- Instale e use o **Complemento do Cartão do Cliente**.
- Adicione e use o **conector do Power Apps**.
- Habilite o uso de [APIs do Customer Insights](apis.md).

## <a name="assign-roles-and-permissions"></a>Atribuir funções e permissões

1. Nos insights de público-alvo, vá para **Administrador** > **Permissões**.

1. Selecione **Adicionar usuários** para abrir o painel **Adicionar/Editar permissões**.

1. Use o campo **Pesquisar** para localizar o usuário ou grupo do Azure Active Directory para o qual você deseja ajustar as permissões. Selecione uma **Função** para atribuir a esse usuário ou grupo.

1. Selecione **Salvar**. O ambiente atual será compartilhado automaticamente com o usuário ou os membros do grupo cujas permissões você alterou. Os usuários podem acessar o aplicativo Customer Insights e trabalhar de acordo com sua função especificada.

## <a name="view-current-permissions"></a>Ver as permissões atuais

Nos insights de público-alvo, vá para **Administrador** > **Permissões** para ver quais atribuições de função estão ativas no momento.

- A coluna **Tipo** especifica um usuário único, grupo ou aplicativo. O sistema suporta usuários e grupos individuais.
- As funções são especificadas na coluna **Função**.
- Selecione qualquer título de coluna para classificar os resultados pelo valor dessa coluna.
- Use o campo **Pesquisar** na parte superior da página para localizar usuários específicos.


[!INCLUDE[footer-include](../includes/footer-banner.md)]