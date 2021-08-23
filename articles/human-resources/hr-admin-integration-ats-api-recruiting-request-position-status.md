---
title: Statut du poste pour la demande de recrutement
description: Cette rubrique décrit l’option Statut du poste pour la demande de recrutement définie pour Dynamics 365 Human Resources.
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
ms.openlocfilehash: dee34366289f2e7ade1a1ae24bea15c0d19683d79720a44a6327879e8060a810
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6725888"
---
# <a name="recruiting-request-position-status"></a>Statut du poste pour la demande de recrutement

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit l’option Statut du poste pour la demande de recrutement définie pour Dynamics 365 Human Resources.

Nom physique : mshr_hcmrecruitingrequestpositionstatus

Cette énumération fournit l’option définie pour les valeurs de statut de chaque poste ayant une demande de recrutement dans l’entité RecruitingRequestPosition.

| Valeur | Étiquette | Description |
| --- | --- | --- |
| 200000000 | Ouverte(s) | Le poste dans la demande de recrutement est ouvert au recrutement. Cela n’indique pas qu’il n’y a pas d’affectation de poste actuellement active pour le poste. Il est possible qu’un employé occupe le poste au moment du recrutement. Cela indique uniquement que le poste est disponible pour le recrutement dans le cadre de la demande. |
| 200000001 | Pourvu | Un collaborateur a été sélectionné pour être affecté au poste. |
| 200000002 | Annulée | La demande de recrutement pour ce poste a été annulée. |

## <a name="see-also"></a>Voir également :

[Introduction à l’API d’intégration du système de suivi des candidats](hr-admin-integration-ats-api-introduction.md)<br>
[Exemple de requête pour une demande de recrutement](hr-admin-integration-ats-api-recruiting-request-example-query.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]