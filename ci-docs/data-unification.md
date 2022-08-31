---
title: Crie uma visão unificada de seus clientes
description: Passe pelo processo de unificação de dados com seus dados para criar um único conjunto de dados mestre de perfis de clientes ou contas.
ms.date: 08/12/2022
ms.reviewer: v-wendysmith
ms.subservice: audience-insights
ms.topic: overview
author: Scott-Stabbert
ms.author: sstabbert
manager: shellyha
searchScope:
- ci-map
- customerInsights
ms.openlocfilehash: c2a81776eab147c4b5209a6fbf89c0f4c9853d1d
ms.sourcegitcommit: 267c317e10166146c9ac2c30560c479c9a005845
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/16/2022
ms.locfileid: "9304413"
---
# <a name="data-unification-overview"></a>Visão geral da unificação de dados

Após a [configuração das fontes de dados](data-sources.md), você pode unificar os dados. A unificação de dados permite unificar fontes de dados díspares em um único conjunto de dados mestre que fornece uma visão unificada desses dados.

Para consumidores individuais (B2C), em que os dados são centrados em indivíduos, a unificação fornece uma visão unificada de seus clientes. Para contas comerciais (B2B) em que os dados são centrados em contas, a unificação fornece uma visão unificada de suas contas. [Unificação de contatos (versão preliminar)](data-unification-contacts.md) permite que os contatos dessas contas sejam unificados separadamente e associados às contas.

Os dados podem ser unificados em uma única entidade ou em várias entidades.

# <a name="individual-consumers-b-to-c"></a>[Consumidor individual (B2C)](#tab/b2c)

O processo de unificação mapeia os dados do cliente de suas fontes de dados, remove duplicatas, compara os dados entre entidades e cria um perfil unificado. A unificação é realizada na seguinte ordem:

1. [Campos de origem](map-entities.md) (anteriormente chamados de Mapa): na etapa de campos de origem, selecione entidades e campos a serem incluídas no processo de unificação. Mapeie campos para um tipo semântico comum que descreva a finalidade do campo.

1. [Registros duplicados](remove-duplicates.md) (anteriormente parte da Correspondência): na etapa de registros duplicados, opcionalmente, defina regras para remover registros duplicados de clientes de cada entidade.

1. [Condições correspondentes](match-entities.md) (anteriormente chamadas de Correspondência): na etapa de condições de correspondência, defina regras que correspondam a registros de clientes entre entidades. Quando um cliente é encontrado em duas ou mais entidades, é criado um único registro consolidado com todas as colunas e dados de cada entidade.

1. [Campos de cliente unificados](merge-entities.md) (anteriormente chamados de Mesclagem): na etapa de campos de cliente unificados, determine quais campos de origem devem ser incluídos, excluídos ou mesclados em um perfil de cliente unificado.  

1. [Revise](review-unification.md) e crie o perfil unificado.

# <a name="business-accounts-b-to-b"></a>[Contas comerciais (B2B)](#tab/b2b)

O processo de unificação mapeia os dados da conta de suas fontes de dados, remove duplicatas, compara os dados entre entidades e cria um perfil unificado. A unificação é realizada na seguinte ordem:

1. [Campos de origem](map-entities.md) (anteriormente chamados de Mapa): na etapa de campos de origem, selecione entidades e campos a serem incluídas no processo de unificação de contas. Mapeie campos para um tipo semântico comum que descreva a finalidade do campo.

1. [Registros duplicados](remove-duplicates.md) (anteriormente parte da Correspondência): na etapa de registros duplicados, opcionalmente, defina regras para remover registros duplicados de contas de cada entidade.

1. [Condições correspondentes](match-entities.md) (anteriormente chamadas de Correspondência): na etapa de condições de correspondência, defina regras que correspondam a registros de contas entre entidades. Quando uma conta é encontrada em duas ou mais entidades, é criado um único registro consolidado com todas as colunas e dados de cada entidade.

1. [Campos de cliente unificados](merge-entities.md) (anteriormente chamados de Mesclagem): na etapa de campos de cliente unificados, determine quais campos de origem devem ser incluídos, excluídos ou mesclados em um perfil de cliente unificado.  

1. [Revise](review-unification.md) e crie o perfil unificado.

Depois de unificar as contas corporativas, é possível [unificar os contatos (versão preliminar)](data-unification-contacts.md) dessas contas e vincular os contatos unificados às contas unificadas.

---

Depois de concluir a unificação de dados, você pode opcionalmente:

- [Configure relacionamentos entre entidades](relationships.md) para criar segmentos sofisticados.
- [Enriqueça seus dados](enrichment-hub.md) para obter um intervalo maior de insights sobre seus clientes.
- [Defina atividades](activities.md) a partir de alguns dos atributos ingeridos.
- [Crie medidas](measures.md) para entender melhor os comportamentos dos clientes e o desempenho dos negócios.

[!INCLUDE [footer-include](includes/footer-banner.md)]
