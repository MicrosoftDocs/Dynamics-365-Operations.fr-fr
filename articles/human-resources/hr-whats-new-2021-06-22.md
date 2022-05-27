---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (22 juin 2021)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 22 juin 2021.
author: marcelbf
ms.date: 06/22/2021
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: marcelbf
ms.search.validFrom: 2021-06-22
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: b1d2ccf1083f34aefbe87354f03dbebd6cb5be7e
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8694422"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-june-22-2021"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (22 juin 2021)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

Cette rubrique décrit les fonctionnalités qui sont nouvelles, ont été modifiées ou seront bientôt disponibles dans Dynamics 365 Human Resources.

Pour plus d’informations sur notre processus et programme de mise à jour, voir [Processus de mise à jour](hr-admin-setup-update-process.md).

Pour plus d’informations sur les nouvelles fonctionnalités et leurs dates de disponibilité générale prévues, voir [Vue d’ensemble de la 1re vague de lancement Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="in-this-release"></a>Dans cette version

Cette version inclut les nouvelles fonctionnalités et correctifs de bogues suivants. Les modifications s’appliquent au numéro de version 8.1.4258.

### <a name="new-features"></a>Nouvelles fonctionnalités

Les fonctionnalités suivantes sont mises à la disposition générale avec cette version.

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Fonctionnalité Informer les utilisateurs des collaborateurs sans emploi : lorsque l’accès avancé est activé et que la fonction **Voir tous les collaborateurs sans emploi** est désactivée dans la gestion des fonctionnalités, une bannière s’affiche dans le formulaire Collaborateurs sans emploi. La bannière indique à l’utilisateur d’activer la fonctionnalité **Voir tous les collaborateurs sans emploi**. | Non applicable| [Collaborateurs sans emploi](/dynamics365/human-resources/hr-personnel-workers-without-employment)|
| Prise en charge des champs personnalisés pour les règles d’admissibilité de gestion des avantages | [Prise en charge des champs personnalisés pour le traitement de l’admissibilité](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/custom-field-support-eligibility-processing) |[Configuration des règles d’éligibilité](/dynamics365/human-resources/hr-benefits-setup-eligibility-rules) |
| Audit des transactions de régularisation de congés | Non applicable | [Audit des transactions de régularisation de congés](hr-leave-and-absence-accrue.md)|
| Améliorations de l’expérience du flux de travail sur les congés et les absences | [Améliorations de l’expérience du flux de travail sur les congés et les absences](https://go.microsoft.com/fwlink/?linkid=2147528) | [Demander un congé](hr-employee-self-service-request-time-off.md)|

### <a name="bug-fixes"></a>Correctifs de bogue

Les correctifs de bogues suivants sont compris dans cette version.

> [!NOTE]
> Notre objectif est de vous fournir ces informations le plus rapidement possible. Il se peut que nous mettions à jour de cette rubrique pour inclure des correctifs de bogues qui sont intégrés à la version après la publication initiale de cette rubrique.

| Numéro du problème | Problème |  Description |
| --- | --- | --- |
| 583052 | L’utilisateur recevant des commentaires peut modifier les commentaires reçus | Lorsqu’un employé recevant des commentaires sur un journal des performances sélectionne **Ajouter un lien externe**, le formulaire devient modifiable, ce qui permet à l’employé de modifier les commentaires sur les performances qu’il a reçus. |
| 522281 | La sélection du nombre d’employés sur les vignettes de la structure de la rémunération dans la Gestion de la rémunération conduit à des résultats incorrects| Lorsque vous explorez les régimes de rémunération à partir de l’espace de travail de rémunération, le nombre correct d’employés s’affiche désormais. |
| 580683 | Les utilisateurs affectés aux rôles Employé et Responsable ne peuvent pas joindre de notes ou mettre à jour un journal des performances | Les utilisateurs affectés aux rôles Employé et Responsable ne peuvent pas joindre de notes ou mettre à jour un journal des performances. L’utilisateur reçoit l’erreur « Impossible de créer un enregistrement dans l’entrée du Journal des performances (HcmPerfJournal). Autorisation de stratégie de sécurité refusée. » |
| 583077 | La date de naissance d’un employé dans le calendrier des congés et des absences de l’entreprise indique une date incorrecte | Les utilisateurs pourront afficher la date de naissance correcte des employés dans le calendrier des congés et des absences de l’entreprise. |
| 586996 | La fonction d’affichage des congés interentreprises fait que les soldes sont vides lorsque l’accès est limité à une seule société | Les utilisateurs peuvent afficher correctement les soldes de congés futurs des employés lorsque la vue des congés interentreprises est activée. |
| 581014 | L’activation de la vue des congés et absences interentreprises provoque une erreur lors de la visualisation des soldes futurs | Des erreurs ont été corrigées lorsque les utilisateurs affichaient les futurs soldes de congés avec la vue des congés interentreprises activée. |
| 509404 | L’analyse des effectifs des services ne prend pas en compte le transfert des employés d’un service à un autre. | lorsqu’un employé passe d’un service à un autre, les données d’effectif du service ne se répercutent pas sur l’ancien service doù est parti l’employé si le détail du poste a expiré dans l’année en cours. |
| 584851 | La règle de prorata des crédits d’avantage « Aucune » n’accorde jamais de crédit |La règle de prorata des crédits d’avantage flexibles « Aucune » a conduit à ce que les employés ne reçoivent aucun crédit pour la période de prestations, quelle que soit leur date d’embauche. Cela a été corrigé de sorte qu’un employé doit recevoir des crédits flexibles complets s’il a été embauché avant le début de la période de prestations, et aucun s’il a été embauché après le début de la période. |
| 584897 | La duplication de l’obligation « Utiliser la fonctionnalité externe de base » entraîne une erreur | Lors de la tentative de duplication de l’obligation « Utiliser la fonctionnalité externe de base », l’utilisateur recevait l’erreur : « Impossible de trouver l’objet ayant l’identifiant UserDefinedAppHostDialogView ». |
| 575692 | Le cumul des congés et des absences n’est pas disponible pour les collaborateurs en attente | Le cumul des congés et des absences peut être exécuté sur les futures embauches lorsque l’option **Entrée d’employé simplifiée** est activée. |
| 580110 | L’ajout d’une entreprise à l’intégration de la paie réinitialise l’intégration pour utiliser toutes les entités, même si l’option est définie pour ne pas actualiser le projet | Si un client a supprimé des entités ou a modifié le projet de données pour l’intégration de la paie, et a défini l’option de manière à empêcher l’actualisation automatique du projet, l’ajout d’une nouvelle entreprise à l’intégration ignore le paramètre et actualise le projet.  |
| 584518 |Problème de performances du traitement des inscriptions aux avantages | Ce bogue concernait des problèmes de performances dans l’ancien processus d’inscription aux avantages. |

## <a name="in-preview"></a>En mode aperçu

Les nouvelles fonctions suivantes sont en version préliminaire. Pour plus d’informations sur l’activation ou la désactivation des fonctionnalités, voir [Gestion des fonctionnalités](hr-admin-manage-features.md).

| Fonctionnalité | Programme de lancement | Documentation |
| --- | --- | --- |
| Espace de travail de gestion des avantages | [Espace de travail de gestion des avantages (version préliminaire)](/dynamics365-release-plan/2020wave2/human-resources/dynamics365-human-resources/benefits-management-workspace) | [Espace de travail de gestion des avantages](hr-benefits-management-workspace.md) |
| Activer l’intégration simplifiée de la paie (API d’intégration de la paie) | [Activer l’intégration simplifiée avec des prestataires de paie](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-simplified-integration-payroll-providers) | [API d’intégration de la paie](hr-admin-integration-payroll-api-introduction.md)|


## <a name="coming-soon"></a>Bientôt disponible

| Fonctionnalité | Détails |
| --- | --- |
| Platform update 10.0.19 (43) | La mise à jour de la plateforme 10.0.19 devrait commencer à être déployée avec la version du service du 28 juin 2021. Pour en savoir plus, consultez [Mises à jour de plateforme pour les applications de finances et d’opérations, version 10.0.19 (juin 2021)](/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-updates-10-0-19). |
|  Basculement de l’affichage des années de service | Cette fonction offre la possibilité d’utiliser différentes dates pour calculer les années de service affichées dans le formulaire **Entrée d’employé simplifiée** et dans le formulaire **Personnes**.  Elle sera disponible dans les paramètres de Human Resources. |
|  Activer un gestionnaire des absences pour gérer les congés | [Activer un gestionnaire des absences pour gérer les congés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-absence-manager-manage-leave) |
|  Rendre obligatoires les pièces jointes pour des types de congés spécifiques | Cette fonctionnalité permet aux administrateurs d’exiger l’ajout de pièces jointes lors de l’envoi de demandes de congé pour des types de congé spécifiques. |
|  Configurer les unités de congé par type de congé | Cette fonctionnalité permet aux administrateurs de configurer des unités de congé (heures ou jours) pour chaque type de congé.  |
| Permettre aux employés d’être marqués comme prêts à être payés | [Permettre aux employés d’être marqués comme prêts à être payés](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/enable-employees-be-marked-as-ready-pay) |

Pour obtenir la liste complète des fonctionnalités prévues et de leur lancement, voir [Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Vue d’ensemble de la 1re vague de lancement de Dynamics 365 Human Resources 2021](/dynamics365-release-plan/2021wave1/human-resources/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]
