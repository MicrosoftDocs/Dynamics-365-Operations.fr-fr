---
title: Statut d'exemption de tâche
description: Cette rubrique décrit l'option Statut d'exonération d'un travail définie pour Dynamics 365 Human Resources.
author: jaredha
manager: tfehr
ms.date: 02/05/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
audience: Application User
ms.reviewer: anbichse
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2021-02-05
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0cd6ffc01793c8ff12e36175c7c9feaf8a4b3cdf
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5125567"
---
# <a name="job-exempt-status"></a>Statut d'exonération d'un travail

Cette rubrique décrit l'option Statut d'exonération d'un travail définie pour Dynamics 365 Human Resources.

Nom physique : cdm_jobexemptstatus

Cette énumération spécifie l'option définie pour les valeurs du statut d'exonération FLSA (Fair Labor Standards Act). Ceci est fourni dans le jeu d'options cdm_jobexemptstatus existant.

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 | Exempté | Le travail a un statut d'exonération basé sur les directives de la FLSA. |
| 200000001 | Non exonéré | Le travail a un statut Non exonéré basé sur les directives de la FLSA. |
| 200000002 | Ne s'applique pas | Les directives du statut FLSA ne s'appliquent pas à l'emploi. |

## <a name="see-also"></a>Voir également :

[Introduction à l'API d'intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)
