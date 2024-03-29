---
title: Fonds budgétaires disponibles
description: Cet article présente la fonctionnalité de disponibilité des fonds budgétaires et fournit des informations pour vous aider à configurer le contrôle budgétaire afin d’optimiser la gestion des ressources financières de votre organisation.
author: RyanCCarlson2
ms.date: 11/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: BudgetControlConfiguration
audience: Application User
ms.reviewer: kfend
ms.custom:
- "60493"
- intro-internal
ms.assetid: be964167-43bc-431d-9adb-48bff32d68d5
ms.search.region: Global
ms.author: rcarlson
ms.search.validFrom: 2021-11-28
ms.dyn365.ops.version: AX 10.0.24
ms.openlocfilehash: b6f94931ba3514c1c66d80b64846d882861d555c
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8898238"
---
# <a name="budget-funds-available"></a>Fonds budgétaires disponibles

[!include [banner](../includes/banner.md)]
[!include [preview banner](../includes/preview-banner.md)]

Cet article présente la fonctionnalité de disponibilité des fonds budgétaires et fournit des informations pour vous aider à configurer le contrôle budgétaire afin d’optimiser la gestion des ressources financières de votre organisation.

## <a name="enhanced-calculation-feature-for-budget-funds-available"></a>Fonctionnalité de calcul améliorée pour les fonds budgétaires disponibles

La fonctionnalité **Ne suivre que les montants dans le calcul des fonds budgétaires disponibles** vous permet de suivre les tableaux de contrôle budgétaire sous-jacents pour les types et les états de documents, en fonction des paramètres de la page **Définition des paramètres de contrôle budgétaire**.

Certaines options de configuration du contrôle budgétaire doivent avoir des paramètres spécifiques pour que la fonctionnalité fonctionne correctement. Ces options sont sélectionnées ou désactivées sur l’onglet **Fonds budgétaires disponibles** de la page **Définition des paramètres de contrôle budgétaire**. Le tableau suivant présente les paramètres requis pour la fonction de disponibilité des fonds budgétaires.

| Si cette option est sélectionnée | Cette option doit également être sélectionnée |
| ------------------------- | -------------------------------- |
| Réservations budgétaires pour les engagements préalables | Réservations budgétaires pour les engagements *et* les dépenses réelles |
| Réservations budgétaires pour les engagements | Dépenses réelles |
| Réservations budgétaires pour les engagements avec des documents de type Demande d’achat | Réservations budgétaires pour les engagements préalables |

Cette fonctionnalité n’affecte que les nouveaux documents. Les montants des documents existants continueront de faire l’objet d’un suivi et d’être affichés dans les études statistiques du contrôle budgétaire jusqu’à ce qu’un paramètre de disponibilité des fonds budgétaires soit modifié et que la nouvelle configuration de contrôle budgétaire soit activée. À ce stade, les données de suivi budgétaire seront supprimées pour les documents qui ont été supprimés du calcul des fonds budgétaires disponibles.

Nous vous recommandons de laisser l’option **Dépenses réelles non validées** désactivée. Si elle est sélectionnée, un calcul de contrôle budgétaire fastidieux sera effectué sur les documents non validés, tels que les factures fournisseurs en attente.
