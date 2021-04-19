---
title: Violations et incidents de stratégie d’audit
description: Cet article décrit la manière dont les incident d’audit sont générés à la suite de violations des règles de stratégie d’audit. Il inclut également des informations sur les différentes manières dont les stratégies d’audit utilisent la plage de dates de sélection de document.
author: panolte
ms.date: 06/20/2017
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: AuditPolicyAdditionalOption, AuditPolicyRule
audience: Application User
ms.reviewer: roschlom
ms.custom: 13091
ms.assetid: e0e66c6d-c396-4a9d-b3b6-3641d130fdc0
ms.search.region: Global
ms.author: panolte
ms.search.validFrom: 2016-02-28
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: b4c7b9426cc98f62cd7a62b841c0f90c7c57889d
ms.sourcegitcommit: 0e8db169c3f90bd750826af76709ef5d621fd377
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2021
ms.locfileid: "5821959"
---
# <a name="audit-policy-violations-and-cases"></a>Violations et incidents de stratégie d’audit

[!include [banner](../includes/banner.md)]

Cet article décrit la manière dont les incident d’audit sont générés à la suite de violations des règles de stratégie d’audit. Il inclut également des informations sur les différentes manières dont les stratégies d’audit utilisent la plage de dates de sélection de document.

<a name="how-audit-cases-are-generated"></a>Génération des incidents d’audit
-----------------------------

Les stratégies d’audit permettent d’identifier les états de dépenses, commandes fournisseur et factures fournisseur non conformes aux règles métier définies et configurées en tant que règles de stratégie d’audit. 

Les stratégies d’audit sont exécutées en mode de traitement par lots. Lorsque vous exécutez une stratégie d’audit, toutes les règles de stratégie qui lui appartiennent sont exécutées simultanément.

Chaque règle de stratégie évalue un ensemble de documents. La règle de stratégie sélectionne des documents compris dans la plage de dates de sélection des documents et qui correspondent aux critères spécifiés. Par exemple, une règle de stratégie peut sélectionner les états de dépenses dont le prix des repas est supérieur à 50,00. Une autre règle de stratégie peut sélectionner les factures fournisseur payables à un fournisseur spécifique. Pour chaque document sélectionné dans l’ensemble, une violation est générée. Cette violation correspond à un enregistrement qui indique qu’un document particulier, tel que la facture 12345, n’est pas conforme à la règle de stratégie. 

Plusieurs enregistrements de violation d’audit sont regroupés et associés aux demandes de devis d’audit. Par défaut, les incidents de chaque stratégie d’audit sont regroupés par règle de stratégie d’audit. Si vous le souhaitez, vous pouvez sélectionner d’autres critères de regroupement à l’aide de la page **Critères de regroupement des incidents**. Par exemple, vous pouvez regrouper les en-têtes de dépenses par ID projet et les factures fournisseur par compte fournisseur. Dans ce cas, toutes les violations d’en-tête de dépenses avec le même ID projet sont regroupées dans le même incident, et toutes les factures fournisseur avec le même compte fournisseur sont regroupées dans le même incident. 

> [!NOTE]
> Pour les règles de stratégie d’audit basées sur le type de requête **Doublon**, les violations ne sont pas regroupées par règle de stratégie ou en fonction des critères spécifiés dans la page **Critères de regroupement des incidents**. Au lieu de cela, elles sont regroupées par les critères indiqués dans la règle de stratégie d’audit. Par exemple, si une règle de stratégie recherche dans les états de dépenses les dépenses en double possédant les mêmes montants, ID marchand et dates, toutes les dépenses dont les champs spécifient des valeurs identiques constituent un incident. Toutes les dépenses qui ont des valeurs différentes font partie d’un incident distinct.

Une fois les incidents d’audit générés, ils sont gérés à l’aide des processus habituels de gestion des incidents.

## <a name="document-selection-date-ranges"></a>Plages de dates de sélection des documents
Lorsqu’une stratégie d’audit est exécutée, chaque règle de stratégie sélectionne les documents du type indiqué dont la date est comprise dans la plage de dates de sélection des documents. La plage de dates de sélection des documents est spécifiée dans la page **Options supplémentaires**. De nombreux documents sont associés à plusieurs dates. Le champ Date utilisé par la règle de stratégie d’audit est spécifié dans la page **Type de règle de stratégie**.

Voici quelques autres manières dont une stratégie d’audit utilise la plage de dates de sélection des documents :

-   La stratégie utilise la version de chaque règle de stratégie effective le dernier jour de la plage de dates de sélection des documents. Vous pouvez voir les dates d’effet de chaque règle de stratégie dans la page de liste **Stratégies d’audit**.
-   La stratégie utilise les nœuds d’organisation qui sont associés à la stratégie le dernier jour de la plage de dates de sélection des documents. Seuls les nœuds d’organisation actuellement associés à la stratégie s’affichent dans la page de liste **Stratégies d’audit**.
-   Pour les règles de stratégie basées sur un type de requête **Recherche de liste**, la stratégie évalue les documents pour des entités contrôlées qui sont effectives le dernier jour de la plage de dates de sélection des documents.


Pour plus d’informations, voir [Règles de stratégie d’audit](audit-policy-rules.md)





[!INCLUDE[footer-include](../../includes/footer-banner.md)]