---
title: Vue d’ensemble de MyLeaveRequests
description: L’entité MyLeaveRequests dans Microsoft Dynamics 365 Human Resources fournit la liste des demandes de congé dans le système, étendue (limitée) aux demandes accessibles à l’utilisateur actuel interrogeant l’entité.
author: andreabichsel
manager: tfehr
ms.date: 02/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
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
ms.openlocfilehash: c2c14a0cc935ad166a2c6600f1e96c3e09ab16ca
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5465508"
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
  | État             | Énumération      | O        |
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