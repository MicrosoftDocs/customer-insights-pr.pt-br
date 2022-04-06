---
title: Exportar dados do Customer Insights para o Iterable
description: Saiba como configurar a conexão e exportar para o Iterable.
ms.date: 03/29/2022
ms.reviewer: mhart
ms.subservice: audience-insights
ms.topic: conceptual
author: pkieffer
ms.author: philk
manager: shellyha
---

# <a name="export-segment-lists-to-iterable-preview"></a>Exportar listas de segmentos para o Iterable (versão preliminar)

Exporte segmentos de perfis de clientes unificados para o Iterable e use-os para atividades de marketing.

## <a name="prerequisites"></a>Pré-requisitos

-   Você tem uma [conta Iterable](https://iterable.com/) e as respectivas credenciais de administrador.
-   Você deve ter [segmentos configurados](segments.md) em insights do público-alvo.
-   Os perfis de clientes unificados nos segmentos exportados contêm um campo que representa um endereço de email.

## <a name="known-limitations"></a>Limitações conhecidas

- A exportação para o Iterable é limitada a segmentos.
- Exportar até 1 milhão de perfis de clientes para o Iterable pode levar até 30 minutos para ser concluído. 
- O número de perfis de clientes que você pode exportar para o Iterable depende e está limitado ao seu contrato com o Iterable.

## <a name="set-up-connection-to-iterable"></a>Configurar a conexão com o Iterable

1. Vá para **Administração** > **Conexões**.

1. Selecione **Adicionar conexão** e escolha **Iterable** para configurar a conexão.

1. Dê um nome reconhecível à sua conexão no campo **Nome de exibição**. O nome e o tipo da conexão a descrevem. Recomendamos escolher um nome que explique a finalidade e o objetivo da conexão.

1. Escolha quem pode usar essa conexão. Se você não fizer nada, o padrão será Administradores. Para obter mais informações, consulte [Permitir que os colaboradores usem uma conexão para exportações](connections.md#allow-contributors-to-use-a-connection-for-exports).

1. Informe sua [Chave de API do Iterable](https://support.iterable.com/hc/en-us/articles/360043464871) para continuar com o login. 

1. Selecione **Concordo** para confirmar a **Conformidade e privacidade dos dados**.

1. Selecionar **Conectar** para inicializar a conexão com o Iterable.

1. Selecione **Adicionar a si mesmo como usuário de exportação** e forneça suas credenciais do Customer Insights.

1. Selecione **Salvar** para concluir a conexão.

## <a name="configure-an-export"></a>Configurar uma exportação

Você pode configurar esta exportação se tiver acesso a uma conexão deste tipo. Para obter mais informações, consulte [Permissões necessárias para configurar uma exportação](export-destinations.md#set-up-a-new-export).

1. Vá para **Dados** > **Exportações**.

1. Para criar uma nova exportação, selecione **Adicionar destino**.

1. No campo **Conexão para exportação**, escolha uma conexão na seção do Iterable. Se não vir este nome de seção, não há conexões deste tipo disponíveis para você.

3. Na seção **Correspondência de dados**, no campo **Email**, selecione o campo que representa o endereço de email de um cliente. É necessário exportar segmentos para o Iterable. A lista criada no Iterable receberá exatamente o mesmo nome que o seu segmento no Dynamics 365 Customer Insights.

1. Selecione **Salvar**.

Salvar uma exportação não a executa imediatamente.

A exportação é executada com cada [atualização agendada](system.md#schedule-tab). Você também pode [exportar dados sob demanda](export-destinations.md#run-exports-on-demand). 


## <a name="data-privacy-and-compliance"></a>Conformidade e privacidade dos dados

Ao habilitar o Dynamics 365 Customer Insights para transmitir dados ao Iterable, você permite a transferência de dados para fora dos limites de conformidade do Dynamics 365 Customer Insights, incluindo dados possivelmente confidenciais, como dados pessoais. A Microsoft vai transferir esses dados de acordo com suas instruções, mas você é responsável por garantir que o Iterable atenda às obrigações de privacidade ou segurança que você possa ter. Para obter mais informações, consulte [Política de Privacidade da Microsoft](https://go.microsoft.com/fwlink/?linkid=396732).

Seu Administrador do Dynamics 365 Customer Insights pode remover este destino de exportação a qualquer momento para interromper o uso dessa funcionalidade.
