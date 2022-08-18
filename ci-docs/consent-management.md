---
title: Usar o consentimento do cliente
description: Honre as preferências de consentimento de seus clientes no Customer Insights importando dados de consentimento.
ms.date: 06/07/2022
ms.reviewer: mhart
ms.service: customer-insights
ms.subservice: audience-insights
ms.topic: conceptual
author: m-hartmann
ms.author: mhart
manager: shellyha
ms.openlocfilehash: 6c951219410b55adc34691f677158b574cea1e01
ms.sourcegitcommit: 49394c7216db1ec7b754db6014b651177e82ae5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/10/2022
ms.locfileid: "9245681"
---
# <a name="use-customer-consent"></a>Usar o consentimento do cliente

Os regulamentos de privacidade e proteção de dados fornecem aos indivíduos o direito de controlar como uma organização usa seus dados pessoais. Exemplos de tais regulamentos são o Regulamento Geral sobre a Proteção de Dados na União Europeia ou a Lei de Privacidade do Consumidor da Califórnia nos Estados Unidos. Esses regulamentos permitem que as pessoas optem por não ter seus dados pessoais coletados, processados ou compartilhados com terceiros.  

Os clientes podem optar por retirar ou reter seu consentimento para formas de contato específicas. Eles também podem solicitar que você os exclua da coleta, armazenamento, uso ou venda de seus dados pessoais. É importante que sua organização respeite o consentimento e as preferências de privacidade de todos os clientes.  

O Dynamics 365 Customer Insights ajuda você a atender às solicitações de seus clientes importando e armazenando suas preferências como parte dos perfis unificados de clientes.

Se os dados de consentimento forem armazenados separadamente de seus perfis de cliente, [adicione seus dados de consentimento como uma nova fonte de dados](#import-and-unify-consent-data). A fonte de dados que contém os dados de consentimento é adicionada ao processo de unificação de dados. A unificação bem-sucedida de dados de consentimento e perfis de clientes leva a perfis de clientes unificados que contêm as informações de consentimento. Para perfis de clientes que já contenham informações de consentimento, acesse diretamente a seção [usar dados de consentimento](#use-consent-data).

## <a name="prerequisites"></a>Pré-requisitos

As informações a seguir devem estar disponíveis em seus dados de origem para unificar os dados de consentimento com outros perfis de clientes:

- Chave alternativa para mapear as informações de consentimento para perfis de usuário no Customer Insights. Por exemplo, um endereço de email ou um número de telefone.
- Valor de consentimento para determinar o status do consentimento do cliente.

Considere a adição das seguintes informações *opcionais*:

- Chave primária para atualizar o status de consentimento se um cliente solicitar uma alteração.
- Tipo de consentimento, se houver mais de uma maneira de processar as informações do cliente.
- Data de consentimento ou qualquer outro tipo de dado relevante para seus cenários de consentimento.

Tabela de exemplo de um banco de dados de consentimento simples com várias opções de consentimento:

|ID do Consentimento (chave primária)   |Email (chave alternativa)  |Opção de consentimento  |Valor de consentimento  |
|---------|---------|---------|---------|
|0    |  holly@contoso.com       |  Boletim Informativo       |  False       |
|2    |  holly@contoso.com       |  Atualizações do produto       |  Verdadeiro       |
|3    |  frank@contoso.com       |  Boletim Informativo       | Verdadeiro        |
|4    |  frank@contoso.com       |  Atualizações do produto       |  False       |

## <a name="import-and-unify-consent-data"></a>Importar e unificar dados de consentimento

Importe dados de consentimento da mesma forma que ingere outras fontes de dados para o Customer Insights. Para obter mais informações sobre fontes de dados compatíveis e como importá-las, consulte [Visão geral das fontes de dados](data-sources.md).

Para obter mais informações sobre como unificar suas fontes de dados, consulte [Visão geral da unificação de dados](data-unification.md).

## <a name="use-consent-data"></a>Usar dados de consentimento

Depois que seus dados de consentimento fizerem parte de seus perfis de clientes unificados, você poderá usá-los no Customer Insights. Por exemplo, crie um segmento com uma regra para garantir que você respeite as preferências de privacidade e proteção de dados de seus clientes. As regras que dão suporte às preferências de consentimento são usadas para excluir usuários de um segmento com base nos atributos do perfil. Adicione uma regra a um segmento que exclua perfis de cliente que não deram consentimento para contato.

Referindo-se à tabela de exemplo acima, um segmento pode conter esta regra: `Consent option=Newsletter & Consent value=True`. Essa configuração resulta em um segmento que respeita as preferências de contato para enviar um boletim informativo.

Para obter mais informações sobre segmentos de construção, consulte [Criar segmentos](segment-builder.md).

Quanto o segmento for criado, você poderá usar uma das muitas [opções de exportação](export-destinations.md) para usar o segmento em outros aplicativos.

## <a name="ensure-updated-consent-status"></a>Garanta o status de consentimento atualizado

É importante manter atualizado o status de consentimento de seus clientes. A atualização agendada no Customer Insights sempre importa o estado mais recente de suas fontes de dados. Essas informações são então processadas por meio da unificação de dados e resultam em perfis de clientes atualizados. Esses perfis atualizados são usados para atualizar segmentos para garantir que você trabalhe com as informações mais atualizadas.

Em outras palavras, certifique-se de que os dados de origem importados para o Customer Insights sempre tenham as informações mais recentes.

Para mais informações, consulte [Atualizar segmentos manualmente](segments.md#refresh-segments) ou [configure uma atualização agendada](schedule-refresh.md).

[!INCLUDE [footer-include](includes/footer-banner.md)]
