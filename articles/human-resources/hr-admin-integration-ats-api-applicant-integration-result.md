---
title: Résultat de l’intégration du candidat
description: Cette rubrique décrit l’option Résultat de l’intégration du candidat définie pour Dynamics 365 Human Resources.
author: jaredha
ms.date: 02/05/2021
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
ms.openlocfilehash: 8bef974abff18d7c07ecd679b7e01b31ea1459c4
ms.sourcegitcommit: 879ee8a10e6158885795dce4b3db5077540eec41
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/18/2021
ms.locfileid: "6053897"
---
# <a name="applicant-integration-result"></a>Résultat de l’intégration du candidat

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’option Résultat de l’intégration du candidat définie pour Dynamics 365 Human Resources.

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