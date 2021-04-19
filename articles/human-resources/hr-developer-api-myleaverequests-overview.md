---
title: Vue d’ensemble de MyLeaveRequests
description: L’entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l’utilisateur actuel interrogeant l’entité.
author: andreabichsel
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: 7521
ms.assetid: ''
ms.search.region: Global
ms.author: anbichse
ms.search.validFrom: 2020-02-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 44e23a076733bac782a0366aeba3456911522abe
ms.sourcegitcommit: 3cdc42346bb653c13ab33a7142dbb7969f1f6dda
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2021
ms.locfileid: "5803631"
---
# <a name="myleaverequests-overview"></a>Vue d’ensemble de MyLeaveRequests

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

L’entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l’utilisateur actuel interrogeant l’entité.

## <a name="key"></a>Clé

  | Nom de la propriété | Type de données |
  |---------------|-----------|
  | ID de zone de données    | Chaîne    |
  | ID demande     | Chaîne    |
  | LeaveType     | Chaîne    |
  | Date de congé     | Date      |
  
## <a name="properties"></a>Propriétés

  | Nom de la propriété     | Type de données | Obligatoire |
  |-------------------|-----------|----------|
  | ID de zone de données        | Chaîne    | O        |
  | ID demande         | Chaîne    | O        |
  | LeaveType         | Chaîne    | O        |
  | Date de congé         | Date      | O        |
  | ID code motif      | Chaîne    |          |
  | Numéro personnel   | Chaîne    | O        |
  | Date de la demande       | Date      | O        |
  | Commentaire           | Chaîne    |          |
  | Statut            | Énumération      | O        |
  | Montant            | Réel      |          |
  | Définition mi-journée | Énumération      |          |

## <a name="actions"></a>Actions

 | Nom de l’action                               | Description                                     |
 |-------------------------------------------|-------------------------------------------------|
 | [soumettre](hr-developer-api-myleaverequests-submit.md)   | Soumettez la demande à traiter par workflow. |

## <a name="see-also"></a>Voir également :

- [Soumettre une demande d’absence au workflow](hr-developer-api-myleaverequests-submit.md)
- [Authentification](hr-developer-api-authentication.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]