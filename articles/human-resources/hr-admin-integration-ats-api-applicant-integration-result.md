---
title: Résultat de l’intégration du candidat
description: Cet article décrit l’option Résultat de l’intégration du candidat définie pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 09/12/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 86f3f75e538268644cea4f927f04c07aae115f00
ms.sourcegitcommit: 27ce4fc706100b626b81c3a1023238acd872e76c
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/20/2022
ms.locfileid: "9702226"
---
# <a name="applicant-integration-result"></a>Résultat de l’intégration du candidat


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’option Résultat de l’intégration du candidat définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmapplicantintegrationresult

Cette énumération fournit le statut d’un dossier de candidature.

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 | Non traité | La candidature est toujours à l’étude. |
| 200000001 | Embauché | Le candidat a été embauché. |
| 200000002 | Non embauché | Il a été décidé de ne pas embaucher le candidat. |
| 200000003 | Ignoré | La candidature n’a pas été retenue. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour l’entité Candidat à l’embauche](hr-admin-integration-ats-api-candidate-to-hire-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
