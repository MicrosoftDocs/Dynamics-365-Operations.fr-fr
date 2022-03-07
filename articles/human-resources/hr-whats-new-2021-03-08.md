---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 8 mars 2021
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 8 mars 2021.
author: marcelbf
manager: tfehr
ms.date: 03/08/2021
ms.topic: article
ms.prod: ''
ms.service: dynamics-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-08
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: c3cd69c86e8590951dd96da75d99bfee2855ac93
ms.sourcegitcommit: 75b432ce9019c81253eb6bd865db905701e28a26
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/11/2021
ms.locfileid: "5579401"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-08-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 8 mars 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4017.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Vue transversale des congés pour les managers | [Vue transversale des congés pour les employés](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/cross-company-view-employee-leave-managers) | [Configurer les paramètres de congé et d’absence](https://docs.microsoft.com/dynamics365/human-resources/hr-leave-and-absence-parameters) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Sortie |  Description |
| --- | --- | --- |
| 486611 | Le congé est indiqué sur le calendrier des congés lorsque **Désactiver les congés sur tous les calendriers** est autorisé | Si **Désactiver les congés sur tous les calendriers** est activée, les informations de congé ne s’affichent plus lorsque la fonction d’améliorations du calendrier des congés et absences est activée.|
| 508972 | Entité de transaction bancaire de congés et d’absences dont la validation de l’inscription n’est pas valide | Lorsque vous utilisez l’entité Transaction bancaire de congés et d’absences, les employés non inscrits à un plan ne peuvent plus être importés. |
| 554854 | Mise à jour du calendrier dans les erreurs d’entité d’emploi si l’entité juridique par défaut dans les options de l’utilisateur est différente | L’utilisation de l’entité Emploi pour mettre à jour le calendrier d’un employé ne génère plus d’erreur si l’entité juridique par défaut dans les options utilisateur est différente. |
| 558347 | « Impossible de créer un enregistrement dans les configurations de formulaire (FormRunConfiguration) » apparaît lors du chargement de la page de démarrage. | Les personnalisations entraînent l’erreur « Impossible de créer un enregistrement dans les configurations de formulaire (FormRunConfiguration) » pour apparaître lors du chargement de la page de démarrage. |
| 557327 | Espace de travail de gestion des avantages : l’espace apparaît au-dessus de la grille. | Correction d’un problème d’expérience utilisateur avec un espace non intentionnel apparaissant sur les bordures de la grille du tableau dans l’espace de travail Avantages. |
| 557334 | Espace de travail de gestion des avantages : la liste déroulante de sélection **Période** ne doit apparaître que dans la vignette **Résumé** | La liste déroulante de sélection **Période** des avantages n’apparaît désormais que lorsque l’onglet **Résumé** est actif dans l’espace de travail Avantages, et non dans les sections **Résultats du processus** et **Liens**. |
| 557336 | Espace de travail de gestion des avantages : le texte **Inscription ouverte avec les plans extraits** est tronqué dans la vue en mosaïque | Le texte de la vue en mosaïque a été remplacé par **Plans vérifiés... inscription ouverte** pour éviter la troncature du contexte nécessaire. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Empêcher les employés de modifier leurs coordonnées professionnelles | [Empêcher les employés de modifier leurs coordonnées professionnelles](https://docs.microsoft.com/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restreindre la modification des informations personnelles](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Prochainement

| Fonctionnalité | Détails |
| --- | --- |
| Les compétences saisies par un responsable pour ses employés peuvent être approuvées automatiquement par un workflow | Prochainement. |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](https://docs.microsoft.com/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
