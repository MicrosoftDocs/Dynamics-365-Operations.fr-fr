---
title: Tâche du poste de paie
description: Cette rubrique fournit des détails un exemple de requête pour l’entité Tâche du poste de paie dans Dynamics 365 Human Resources.
author: jcart
manager: tfehr
ms.date: 04/07/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jcart
ms.search.validFrom: 2021-04-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 72f3109f5bea36a390b04b7165fc3831d777b640
ms.sourcegitcommit: d18d9cdb175c9d42eafbed66352c24b2aa94258b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5881984"
---
# <a name="payroll-position-job"></a>Tâche du poste de paie

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique fournit des détails un exemple de requête pour l’entité de relation de Tâche du poste de paie dans Dynamics 365 Human Resources.

## <a name="properties"></a>Propriétés

| Propriété<br>**Nom physique**<br>**_Type_** | Cas d’emploi | Description |
| --- | --- | --- |
| **ID tâche**<br>mshr_jobid<br>*Chaîne* | Lecture seule<br>Requis |ID de la tâche. |
| **Valide à partir du**<br>mshr_validto<br>*Décalage de date et heure* | Lecture seule <br>Requis | Date à partir de laquelle la relation entre le poste et la tâche sont valides. |
| **Valide jusqu’au**<br>mshr_validto<br>*Décalage de date et heure* | Lecture seule <br>Requis | Date jusqu'à laquelle la relation entre le poste et la tâche sont valides.  |
| **ID poste**<br>mshr_positionid<br>*Chaîne* | Lecture seule<br>Requis | ID du poste. |
| **Champ principal**<br>mshr_primaryfield<br>*Chaîne* | Requis<br>Généré par le système |  |
| **Valeur d’ID du poste**<br>_mshr_fk_positionjob_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_PayrollPositionJobEntity de mshr_payrollpositionjobentity |ID du travail associé au poste.|
| **Valeur de l'ID du régime de rémunération fixe**<br>_mshr_fk_fixedcompplan_id_value<br>*GUID* | Lecture seule<br>Requis<br>Clé étrangère : mshr_FixedCompPlan_id de mshr_payrollfixedcompensationplanentity  | ID du régime de rémunération fixe associé au poste. |
| **ID de l'entité Tâche du poste de paie**<br>mshr_payrollpositionjobentityid<br>*Guid* | Requis<br>Généré par le système. | Valeur GUID générée par le système pour identifier la tâche de manière unique.  |

