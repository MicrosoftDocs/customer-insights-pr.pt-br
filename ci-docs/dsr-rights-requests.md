---
title: Solicitações de Direitos do Titular dos Dados (DSR) no RGPD | Microsoft Docs
description: Responda a Solicitações do Titular dos Dados para o recurso de insights de público-alvo do Dynamics 365 Customer Insights.
ms.date: 08/11/2021
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: wimohabb
manager: shellyha
ms.openlocfilehash: c116f7ce208c0288851a4b2230e27784ba3a5337
ms.sourcegitcommit: 834651b933b1e50e7557d44f926a3fb757c1f83a
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/02/2021
ms.locfileid: "7732666"
---
# <a name="data-subject-rights-dsr-requests-under-gdpr"></a>Solicitações de Direitos do Titular dos Dados (DSR) no GDPR

O Regulamento Geral sobre a Proteção de Dados (RGPD) da União Europeia está em vigor desde 25 de maio de 2018. Ele concede direitos significativos aos indivíduos em relação aos seus dados. O RGPD refere-se à proteção e à viabilização dos direitos de privacidade dos usuários. Você pode ler mais sobre o compromisso da Microsoft com a segurança e conformidade no [Microsoft Trust Center](https://www.microsoft.com/trust-center).

Temos o compromisso de ajudar nossos clientes a atender aos requisitos do RGPD. Inclui o direito de excluir e exportar dados que incluem informações pessoais, como IDs de usuário, números de telefone e endereços de email. Os administradores podem implementar solicitações do usuário para excluir ou exportar dados pessoais.

## <a name="audience-insights"></a>Insights do público-alvo

### <a name="responding-to-gdpr-data-subject-delete-requests-for-dynamics-365-customer-insights-audience-insights-capability"></a>Responder a solicitações de exclusão do titular dos dados de RGPD para o recurso de insights de público-alvo do Dynamics 365 Customer Insights

O "direito de apagar" através de remoção de dados pessoais dos dados do cliente de uma organização é uma proteção chave no Regulamento Geral sobre a Proteção de Dados (RGPD). A remoção de dados pessoais inclui a remoção de todos os dados pessoais e os logs gerados pelo sistema, exceto informações de log de auditoria.

#### <a name="manage-data-subject-delete-requests"></a>Gerenciar solicitações de exclusão do titular dos dados

Os insights de público-alvo oferecem as seguintes experiências no produto para excluir dados pessoais de um cliente ou usuário específico:

- **Gerenciar solicitações de exclusão de dados do cliente** : Os dados do cliente no Customer Insights são ingeridos de fontes de dados originais externas ao Customer Insights. Todas as solicitações de exclusão de RGPD devem ser executadas no fonte de dados original.
- **Gerenciar solicitações de exclusão de dados do usuário do Customer Insights**: dados para usuários são criados pelo Customer Insights. Todas as solicitações de exclusão de RGPD devem ser executadas no Customer Insights.

##### <a name="manage-requests-to-delete-customer-data"></a>Gerenciar solicitações para excluir dados do cliente

Um administrador do Customer Insights pode seguir estas etapas para remover dados do cliente que foram excluídos no fonte de dados:

1. Entre no Dynamics 365 Customer Insights.
2. Nos insights de público-alvo, vá para **Dados** > **Fontes de dados**.
3. Para cada fonte de dados na lista que contém dados excluídos do cliente:
   1. Selecione (...) e depois selecione **Atualizar**.
   2. Verifique o status da fonte de dados em **Status**. Uma marca de seleção significa que a atualização foi bem-sucedida. Um triângulo de aviso significa que algo deu errado. Se um triângulo de aviso for exibido, entre em contato com D365CI@microsoft.com.

> [!div class="mx-imgBorder"]
> ![Tratar solicitações de exclusão de RGPD de dados do cliente.](audience-insights/media/gdpr-data-sources.png "Tratar solicitações de exclusão de RGPD de dados do cliente")

##### <a name="manage-delete-requests-for-user-data"></a>Gerenciar solicitações de exclusão de dados do usuário

Um administrador do Customer Insights pode seguir estas etapas para excluir os dados do usuário do Customer Insights:

1. Entre no Dynamics 365 Customer Insights.
2. Nos insights de público-alvo, vá para **Administrador** > **Permissões**.
3. Marque a caixa de seleção do usuário que você deseja excluir.
4. Selecione **Remover**.

### <a name="responding-to-gdpr-data-subject-export-requests"></a>Responder a solicitações de exportação do titular dos dados de RGPD

Como parte de nosso compromisso de fazer parceria com você em sua jornada para o Regulamento Geral sobre a Proteção de Dados (GDPR), desenvolvemos uma documentação para ajudá-lo a se preparar. Essa documentação descreve as etapas que você pode seguir hoje para oferecer suporte à conformidade com o RGPD ao usar insights de público-alvo.

#### <a name="manage-export-and-view-requests"></a>Gerenciar solicitações de exportação e exibição

O direito de portabilidade de dados permite que um titular dos dados solicite uma cópia de seus dados pessoais em um formato eletrônico (definido como “formato estruturado, comumente usado, legível por máquina e interoperável”) que pode ser transmitido para outro controlador de dados.

##### <a name="export-customer-data-tenant-admin"></a>Exportar dados do cliente (administrador do locatário)

Um administrador do locatário pode seguir estas etapas para exportar dados:

1. Enviar um email para D365CI@microsoft.com especificando o endereço de email do cliente na solicitação. A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.
2. Reconheça a confirmação para exportar os dados para o cliente solicitado.
3. Receba os dados exportados através do endereço de e-mail do administrador do locatário.

##### <a name="export-user-data-tenant-admin"></a>Exportar dados do usuário (administrador do locatário)

1. Enviar um email para D365CI@microsoft.com especificando o endereço de email do usuário na solicitação. A equipe do Customer Insights enviará um email para o endereço de email do administrador do locatário registrado, pedindo confirmação para exportar dados.
2. Reconheça a confirmação para exportar os dados para o usuário solicitado.
3. Receba os dados exportados através do endereço de e-mail do administrador do locatário.

## <a name="consent-management-preview"></a>Gerenciamento de consentimento (versão preliminar)

O recurso de gerenciamento de consentimento não coleta dados do usuário diretamente. Ele apenas importa e processa os dados de consentimento fornecidos por usuários em outros aplicativos.

Para remover os dados de consentimento sobre usuários específicos, remova-os das fontes de dados ingeridas para o recurso de gerenciamento de consentimento. Depois de atualizar a fonte de dados, os dados removidos também serão excluídos do Centro de Consentimento. Os aplicativos que usam a entidade de consentimento também excluirão os dados que foram removidos da fonte após uma [atualização](audience-insights/system.md#refresh-processes). Recomendamos atualizar as fontes de dados rapidamente depois de responder a uma solicitação do titular dos dados para remover os dados do usuário de todos os outros processos e aplicativos.


## <a name="engagement-insights-preview"></a>Insights de participação (versão preliminar)

### <a name="deleting-and-exporting-event-data-containing-end-user-identifiable-information"></a>Exclusão e exportação de dados de eventos que contêm informações de identificação do usuário final

As seções a seguir descrevem como excluir e exportar dados de eventos que podem conter dados pessoais.

Para excluir ou exportar dados:

1. Marque propriedades de eventos que contêm dados com informações pessoais.
2. Exclua ou exporte dados associados a valores específicos (por exemplo: um ID de usuário especificado).

#### <a name="tag-and-update-event-properties"></a>Marque e atualize as propriedades do evento

Os dados pessoais são marcados em um nível de propriedade do evento. Primeiro, marque as propriedades que estão sendo consideradas para exclusão ou exportação.

Para marcar uma propriedade de evento como contendo informações pessoais, siga estas etapas:

1. Abra o espaço de trabalho que contém o evento.

1. Vá para **Dados** > **Eventos** para ver a lista de eventos no espaço de trabalho selecionado.
  
1. Selecione o evento que deseja marcar.

1. Selecione **Editar propriedades** para abrir o painel que lista todas as propriedades do evento selecionado.
     
1. Selecione **...** e então escolha **Editar** para ir para o diálogo **Atualizar propriedade**.

   ![Edite o evento.](engagement-insights/media/edit-event.png "Editar evento")

1. Na janela **Atualizar Propriedade**, escolha **...** no canto superior direito e, em seguida, escolha a caixa **Contém EUII**. Escolha **Atualizar** para salvar suas alterações.

   ![Salve suas alterações.](engagement-insights/media/update-property.png "Salve suas alterações")

   > [!NOTE]
   > Cada vez que o esquema do evento muda ou você cria um novo evento, é recomendado que avalie as propriedades do evento associado e marque ou desmarque-as como contendo dados pessoais, se necessário.

#### <a name="delete-or-export-tagged-event-data"></a>Excluir ou exportar dados de eventos marcados

Se todas as propriedades do evento foram marcadas apropriadamente, conforme descrito na etapa anterior, um administrador de ambiente pode emitir uma solicitação de exclusão nos dados do evento marcados.

Para gerenciar a exclusão de EUII ou solicitações de exportação

1. Vá para **Admin** > **Ambiente** > **Configurações**.

1. Na seção **Gerenciar informações de identificação do usuário final (EUII)**, selecione **Gerenciar EUII**.

##### <a name="deletion"></a>Exclusão

Para exclusão, você pode inserir uma lista de IDs de usuário separados por vírgulas na seção **Excluir informações de identificação do usuário final (EUII)**. Essas IDs serão então comparadas com todas as propriedades de eventos marcadas de todos os projetos no ambiente atual por meio de correspondência exata de string. 

Se um valor de propriedade corresponder a um dos IDs fornecidos, o evento associado será excluído permanentemente. Devido à irreversibilidade desta ação, você deve confirmar a exclusão após selecionar **Excluir**.

##### <a name="export"></a>Export

O processo de exportação é idêntico ao processo de exclusão quando se trata de definir os valores das propriedades do evento na seção **Exportar informações de identificação do usuário final (EUII)**. Além disso, você precisará fornecer um **URL de armazenamento de blobs do Azure** para especificar o destino da exportação. O URL do Blob do Azure deve incluir uma [Assinatura de Acesso Compartilhado (SAS)](/azure/storage/common/storage-sas-overview).

Depois de selecionar **Exportar**, todos os eventos da equipe atual que contêm propriedades marcadas correspondentes serão exportados no formato CSV para o destino de exportação.

### <a name="good-practices"></a>Práticas recomendadas

* Tente evitar o envio de eventos que contenham dados pessoais.
* Se você precisar enviar eventos que contém dados EUII, limite o número de eventos e propriedades do evento que contêm dados EUII. De preferência, limite-se a um desses eventos.
* Certifique-se de que o menor número possível de pessoas tenha acesso aos dados pessoais enviados.
* Para eventos que contêm dados pessoais, certifique-se de definir uma propriedade para emitir um identificador exclusivo que pode ser facilmente vinculado a um usuário específico (por exemplo, um ID de usuário). Isso torna mais fácil separar os dados e exportar ou excluir os dados corretos.
* Marque apenas uma propriedade por evento como contendo dados pessoais. De preferência, um que contenha apenas um identificador exclusivo.
* Não marque propriedades que contenham valores detalhados (por exemplo, um corpo de solicitação inteiro). O recurso de insights de interação usa correspondência exata de string ao decidir quais eventos excluir ou exportar.

[!INCLUDE[footer-include](includes/footer-banner.md)]