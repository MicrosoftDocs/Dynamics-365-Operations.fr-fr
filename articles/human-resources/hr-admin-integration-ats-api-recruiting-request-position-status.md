---
title: Statut du poste pour la demande de recrutement
description: Cette rubrique décrit l'option Statut du poste pour la demande de recrutement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: 3f7bae64f58f0bdc1603b3c1b5493f1ebcfa8de9
ms.sourcegitcommit: 33b5c8bc4f9461e290513aa22de1ec1fba3b0742
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2021
ms.locfileid: "5126048"
---
# <a name="recruiting-request-position-status"></a>Statut du poste pour la demande de recrutement

Cette rubrique décrit l'option Statut du poste pour la demande de recrutement définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmrecruitingrequestpositionstatus

Cette énumération fournit l'option définie pour les valeurs de statut de chaque poste ayant une demande de recrutement dans l'entité RecruitingRequestPosition.

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 | Ouverte(s) | Le poste dans la demande de recrutement est ouvert au recrutement. Cela n'indique pas qu'il n'y a pas d'affectation de poste actuellement active pour le poste. Il est possible qu'un employé occupe le poste au moment du recrutement. Cela indique uniquement que le poste est disponible pour le recrutement dans le cadre de la demande. |
| 200000001 | Pourvu | Un collaborateur a été sélectionné pour être affecté au poste. |
| 200000002 | Annulée | La demande de recrutement pour ce poste a été annulée. |

## <a name="see-also"></a>Voir également :

[Introduction à l'API d'intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)
