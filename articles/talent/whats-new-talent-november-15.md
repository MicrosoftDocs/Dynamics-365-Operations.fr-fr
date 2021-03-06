---
title: Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (15 novembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent - Core HR.
author: Darinkramer
manager: AnnBe
ms.date: 11/15/2018
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2018-11-15
ms.dyn365.ops.version: Talent
ms.openlocfilehash: 1a7598db1dc4c11864cf5f5a73d00672ceb66e8c
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4461156"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent---core-hr-november-15-2018"></a>Nouveautés ou modifications dans Dynamics 365 Talent - Core HR (15 novembre 2018)

**Version 8.1.2045**

Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Core HR.

## <a name="other-changesfixes"></a>Autres modifications/corrections

### <a name="unable-to-change-employees-current-position-to-a-future-open-position"></a>Impossible de modifier le poste actuel de l'employé avec un futur poste vacant

Une modification a été apportée pour activer les transferts de poste lorsque le poste est uniquement disponible dans le futur. 

### <a name="position-does-not-display-when-creating-a-new-employee"></a>Le poste ne s'affiche pas lors de la création d'un employé

Une modification a été apportée pour afficher tous les postes à pourvoir disponibles pour une affectation lors de l'embauche de nouveaux employés dans Talent. Cela inclut les postes historiques ou si les postes ont été datés dans le futur. Les postes s'affichent maintenant correctement selon la date de début de l'emploi. 

### <a name="termination-date-is-displaying-based-on-user-settings"></a>La date de fin de contrat s'affiche selon les paramètres utilisateur

Une modification été apportée à la liste des employés passés pour tenir compte des décalages de fuseau horaire pour les fuseaux horaires choisis par les employés lors de l'affichage de la date de fin de contrat.

### <a name="work-items-assigned-to-me-links-not-displaying-the-correct-information"></a>Les liens des éléments de travail qui me sont affectés n'affichent pas les informations correctes

Avec cette modification, la navigation dans les détails des différents éléments de travail de la liste affichera les informations correcte de l'élément sélectionné. Ce problème se produisait uniquement avec des options de sécurité avancées.


## <a name="known-issue"></a>Problème connu

- **Problème** : Lors de l'ajout d'une pièce jointe à un collaborateur, les boutons **Nouveau** et **Modifier** sont grisés. 
- **Solution :** Avant d'ouvrir la page de la pièce jointe, assurez-vous que les récapitulatifs sur la page **Collaborateur** sont clôturés. Si les récapitulatifs sont fermés lorsque la page **Collaborateur** est chargée, les boutons de pièces jointes sont activés. (Ce problème sera résolu dans la prochaine mise à jour de la plateforme.)


[!INCLUDE[footer-include](../includes/footer-banner.md)]