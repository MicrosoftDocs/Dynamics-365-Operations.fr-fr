---
title: Statut d’exemption de tâche
description: Cette rubrique décrit l’option Statut d’exonération d’un travail définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 1c3996d8f693b6df0bf6230b25c9339b2aad1ceaf49a790fda90bbfc1b68be41
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6720442"
---
# <a name="job-exempt-status"></a>Statut d’exonération d’un travail

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’option Statut d’exonération d’un travail définie pour Dynamics 365 Human Resources.

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