---
title: Perguntas frequentes sobre a avaliação do Dynamics 365 Customer Insights
description: Soluções para dúvidas comuns relacionadas à configuração e gerenciamento da avaliação do Customer Insights. Saiba como resolver problemas específicos de plataforma e de aplicativos.
author: m-hartmann
ms.author: mhart
ms.date: 02/10/2022
ms.topic: get-started
ms.custom: template-trial-faq
ms.reviewer: jeffhar
manager: shellyha
ms.openlocfilehash: 41f112466d54c9923d0daf7c55d343f9b5c81d98
ms.sourcegitcommit: a97d31a647a5d259140a1baaeef8c6ea10b8cbde
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2022
ms.locfileid: "9051485"
---
# <a name="dynamics-365-customer-insights-trial-faq"></a>Perguntas frequentes sobre a avaliação do Dynamics 365 Customer Insights

## <a name="sign-up"></a>Inscrever-se

### <a name="what-are-the-system-requirements-for-the-trial"></a>Quais são os requisitos de sistema para a avaliação?

Este aplicativo é um serviço baseado em nuvem que não requer outro software especial além de um navegador web atualizado, embora algumas restrições se apliquem. Para obter a melhor experiência de avaliação, evite acessar o site de avaliação em modo incógnito e escolha o local de avaliação mais próximo de você. [Saiba mais sobre os requisitos do aplicativo web.](/power-platform/admin/web-application-requirements)

### <a name="how-do-i-sign-up-for-the-trial-without-a-microsoft-365-tenant"></a>Como posso me inscrever para a avaliação sem um locatário do Microsoft 365?

Você pode inserir um endereço de email não comercial e criaremos uma conta e um locatário para você.

### <a name="can-i-sign-up-for-multiple-dynamics-365-apps-such-as-sales-marketing-and-customer-service"></a>Posso me inscrever em vários aplicativos do Dynamics 365, como Sales, Marketing e Customer Service?

Sim, pode. Para ver todos as avaliações disponíveis, [acesse a página do hub de avaliações](https://dynamics.microsoft.com/dynamics-365-free-trial). Você pode usar a mesma conta de email para inscrever-se em avaliações diferentes. No entanto, não é possível ter vários aplicativos no mesmo site de avaliação. Cada avaliação estará em uma organização e URL diferentes. Os dados da avaliação não serão compartilhados entre os aplicativos.

## <a name="trial-app"></a>Aplicativo de avaliação

### <a name="i-didnt-receive-the-trial-details-email-after-signing-up-what-should-i-do"></a>Não recebi o email com os detalhes do teste após a inscrição, o que devo fazer?

Ao se inscrever para a avaliação, você receberá um email com os detalhes da avaliação. Se você não vir o email em sua caixa de entrada, verifique sua pasta de spam. Como alternativa, use as seguintes etapas para acessar o aplicativo:

1. Acesse o site de avaliação e selecione **Avaliação gratuita**.
1. Digite o email de identificação que você usou para se inscrever para a avaliação. Você será redirecionado para o aplicativo de avaliação.

### <a name="how-do-i-add-more-users-to-a-trial"></a>Como faço para adicionar mais usuários à avaliação?

Para adicionar usuários, acesse o [centro de administração do Microsoft 365](https://admin.microsoft.com) usando a conta do administrador da avaliação. Siga as [orientações do centro de administração](/microsoft-365/admin/add-users/add-users) para adicionar usuários até o limite da licença de avaliação. Se o usuário que você estiver adicionando já tiver uma conta do Microsoft 365, atribua a ele um direito de acesso apropriado na organização de avaliação. Para obter mais informações, consulte [Atribuir um direito de acesso a um usuário](/power-platform/admin/create-users-assign-online-security-roles#assign-a-security-role-to-a-user).

### <a name="how-many-users-can-i-add-to-my-trial-environment"></a>Quantos usuários posso adicionar ao meu ambiente de avaliação?

Você pode adicionar um número ilimitado de usuários ao ambiente de avaliação.

### <a name="how-do-i-reset-the-trial-environment"></a>Como faço para reiniciar o ambiente de avaliação?

Não é possível reiniciar o ambiente de avaliação. No entanto, você pode esperar o fim do período de avaliação e se inscrever novamente para uma nova.

## <a name="trial-expiration-and-extension"></a>Expiração e extensão da avaliação

### <a name="how-do-i-extend-the-trial"></a>Como faço para estender a avaliação?

Você pode estender a avaliação diretamente no aplicativo. Você pode estender sua avaliação uma vez.

### <a name="can-i-convert-the-trial-to-a-paid-license"></a>Posso converter a avaliação em uma licença paga?

Geralmente, recomendamos começar do zero com seus próprios dados ao atualizar para a versão paga do Customer Insights. 

Opcionalmente, se você só usar o Customer Insights, poderá copiar dados de um ambiente de avaliação se adquirir o Customer Insights. Você deve ser o administrador da avaliação do Customer Insights e o administrador global do locatário do Microsoft 365 ou o administrador do Dynamics 365 em sua organização para migrar as configurações de um ambiente de avaliação para um ambiente pago.

Depois que entrar em sua instância paga do Customer Insights pela primeira vez, você será solicitado a criar um ambiente. Nesse processo, você poderá optar por copiar a configuração de um ambiente existente e migrar a maioria das configurações. Se você tiver as permissões mencionadas acima, o ambiente de avaliação aparecerá nesta lista. Para obter mais informações, consulte [Copiar a configuração do ambiente](create-environment.md#copy-the-environment-configuration).

### <a name="what-are-the-trial-limits-and-quotas"></a>Quais são os limites e as cotas da avaliação?

- Você não pode usar sua própria conta do Azure Data Lake Storage para armazenar dados de saída durante uma avaliação do Customer Insights. No entanto, você pode ingerir dados de uma conta do Data Lake Storage.
- Você pode armazenar um máximo de 3 GB de dados no Dataverse ambiente que é provisionado automaticamente quando você inicia uma avaliação do Customer Insights.

## <a name="customer-insights-specific-questions"></a>Perguntas específicas sobre o Customer Insights

### <a name="how-do-i-start-using-the-trial"></a>Como faço para começar a usar a avaliação?

Depois que se inscrever para a avaliação, você chegará à tela principal do aplicativo. A tela principal fornece links para guias do usuário e tutoriais. Para saber mais, acesse os links em [Recursos adicionais](trial-signup.md#additional-resources) na página de configuração da avaliação.

### <a name="what-features-are-available-in-the-trial"></a>Quais recursos estão disponíveis na avaliação?

A maioria dos recursos do Customer Insights estão disponíveis na avaliação.

Os seguintes recursos **não estão disponíveis**:

- Você não pode criar novos ambientes que usem sua própria conta de armazenamento do Azure Data Lake Storage.
- Não é possível excluir o ambiente de avaliação.

### <a name="how-long-does-the-trial-last"></a>Quanto tempo leva a avaliação?

A avaliação do Customer Insights dura 30 dias. Você pode estender a avaliação uma vez após 23 dias ao fazer login no ambiente de avaliação.

### <a name="how-do-i-remove-sample-data-from-the-trial"></a>Como faço para remover dados de exemplo da avaliação?

Você não pode remover os dados da amostra da avaliação.
