---
title: Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (15 novembre 2018)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent Core HR.
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
ms.openlocfilehash: b90d4230fe1e666aba4075670f6df206e8df7ce9
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "857313"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-core-hr-november-15-2018"></a>Nouveautés ou modifications dans Dynamics 365 for Talent Core HR (15 novembre 2018)

[!include [banner](includes/banner.md)]

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
