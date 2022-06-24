---
title: Statut d’exemption de tâche
description: Cet article décrit l’option Statut d’exonération d’un travail définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: e59a71264d50cecce4d31dfa26ad7f05ef3f34e4
ms.sourcegitcommit: 52b7225350daa29b1263d8e29c54ac9e20bcca70
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/03/2022
ms.locfileid: "8894670"
---
# <a name="job-exempt-status"></a>Statut d’exemption de tâche


[!INCLUDE [PEAP](../includes/peap-1.md)]

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cet article décrit l’option Statut d’exonération d’un travail définie pour Dynamics 365 Human Resources.

Nom physique : cdm_jobexemptstatus

Cette énumération spécifie l’option définie pour les valeurs du statut d’exonération FLSA (Fair Labor Standards Act). Ceci est fourni dans le jeu d’options cdm_jobexemptstatus existant.

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 | Exempté | Le travail a un statut d’exonération basé sur les directives de la FLSA. |
| 200000001 | Non exonéré | Le travail a un statut Non exonéré basé sur les directives de la FLSA. |
| 200000002 | Ne s’applique pas | Les directives du statut FLSA ne s’appliquent pas à l’emploi. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
