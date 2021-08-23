---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources 22 mars 2021
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 22 mars 2021.
author: marcelbf
ms.date: 03/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-03-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 0f08dc966353cc612c8145f29e2cd8c303da5b359292a8f928d97f0e0de99585
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6777086"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-22-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources 22 mars 2021

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4049.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Option pour forcer l’annulation et la réinitialisation des traitements par lots bloqués (560976) | NA | [Réinitialiser les traitements par lots bloqués](./hr-admin-troubleshooting-batch-execution.md) |
| Mises à jour mineures de l’expérience utilisateur pour la création d’un nouveau régime de prestations (419941) | NA | [Création d’un plan d’avantages](hr-benefits-plans-setup.md) |

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Sortie |  Description |
| --- | --- | --- |
| 554239 | Amélioration des performances des entités liées à la table **BusinessProcessTaskAssignment** | Amélioration des performances des entités liées à la table **BusinessProcessTaskAssignment** en ajoutant des index suggérés à la table. |
| 566061 | Suppression du code de secours d’entité V2 de la synchronisation nocturne | Suppression du code de secours V2 pour la synchronisation Dataverse nocturne. Le code de secours n’est plus nécessaire et empêche la synchronisation filtrée de fonctionner comme prévu. Le changement améliore la cohérence de la synchronisation des données Dataverse. |
| 538024 | Régimes d’avantages sociaux pour les collaborateurs > Suppression du paiement qui génère une erreur | Correction d’une erreur lors de la suppression de l’option de paiement pour le régime d’avantages dans le formulaire Avantages sociaux des collaborateurs. |
| 557965 | Espace de travail **Avantages** : le lien **Événements de la vie active** doit toujours être visible dans la section **Liens** | Correction du problème où le lien **Événements de la vie active** était visible dans la section **Liens**, mais générait une erreur lors de la tentative de navigation si la fonctionnalité **(Version préliminaire) Espace de travail de gestion des avantages** n’était pas activée. Pour plus d’informations sur l’activation de l’espace de travail, voir [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md). |
| 556672 | Impossible de traiter les régularisations pour un employé dont le contrat est terminé lorsque **Entrée d’employé simplifiée** est activé dans la Gestion des fonctionnalités | L’option d’accumuler les plans de congé et d’absence a été ajoutée à **Autres options** sous **Historique du travail** pour les employés quand **Entrée d’employé simplifiée** est activé dans la Gestion des fonctionnalités. |
| 562656 | L’élément de menu **SysRecordChangeLogValidTimeState** doit être inclus dans un privilège de sécurité et une extension du droit de sécurité **SystemExternalBasicMaintain** | Les rôles d’administrateur non-système ne disposaient pas du bouton **Afficher les modifications** sur les formulaires de gestionnaire de dates. |
| 505989 | Traitement des événements de la vie : le changement de l’éligibilité n’était pas traité correctement en raison de la date utilisée | Correction d’un problème où le changement dans le traitement de l’éligibilité dépendait de la date de début du poste, et pas seulement du poste actuel. |
| 562286 | La fin de contrat d’un collaborateur envoie plusieurs mises à jour à Dataverse | Lorsqu’un collaborateur achève son contrat, plusieurs opérations de mise à jour sont envoyées à Dataverse ; il en résulte en deux notifications de mise à jour pour la même modification. Cela peut actionner plusieurs déclencheurs si un flux Power Automate configuré pour se déclencher à partir de l’action. |
| 527340 | L’erreur « DateHeure non représentable » s’affiche lors de l’ouverture des inscriptions des congés et absences | Lors de la sélection d’une inscription des congés et absences, l’erreur ne s’affiche plus. |
| 561663 | Augmentation de l’intervalle de temps d’attente pour le provisionnement du cluster | Amélioration de la stabilité de l’infrastructure et la cohérence du provisionnement grâce aux mises à jour du provisionnement des clusters. |
| 486129 | Impossible de modifier les champs personnalisés dans **Postes > Gérer les modifications** | Correction d’un problème où les champs personnalisés ne pouvaient pas être modifiés dans l’onglet **Gérer les modifications** pour les **Postes**. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Empêcher les employés de modifier leurs coordonnées professionnelles | [Empêcher les employés de modifier leurs coordonnées professionnelles](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/restrict-employees-editing-business-contact-details) | [Restreindre la modification des informations personnelles](hr-employee-self-service-restrict-editing.md)|

## <a name="coming-soon"></a>Prochainement

| Fonctionnalité | Détails |
| --- | --- |
| Les compétences saisies par un responsable pour ses employés peuvent être approuvées automatiquement par un workflow | Prochainement. |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]