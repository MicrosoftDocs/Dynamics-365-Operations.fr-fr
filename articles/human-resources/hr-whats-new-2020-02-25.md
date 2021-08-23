---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (25 février 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 25 février 2020.
author: andreabichsel
ms.date: 02/25/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-25
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 8ae5a834c89ac648f7b74080a2cba51e5a7fb1a68fa81a0269c581daee56b5f7
ms.sourcegitcommit: 42fe9790ddf0bdad911544deaa82123a396712fb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "6770382"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-25-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (25 février 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.2927. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="enable-case-management-navigation-and-data-management-framework-dmf-entity-414754"></a>Activer l’entité Infrastructure de gestion des données (DMF) et navigation de la gestion des dossiers (414754)

Cette fonction d’aperçu permet une navigation supplémentaire vers les cas de gestion des dossiers. Vous pouvez activer cette fonctionnalité en version préliminaire dans l’espace de travail **Gestion des fonctionnalités**. Ces éléments de menu apparaissent dans l’espace de travail **Conformité** de Dynamics 365 Human Resources. Avec cette modification, les ressources humaines peuvent accéder à :

- Tous les dossiers
- Mes dossiers
- Mes dossiers ouverts
- Mes dossiers en retard
- Dossiers affectés à moi-même via le flux de travail

Parallèlement à ces nouvelles vues des dossiers, l’entité DMF **Détail du dossier** est également disponible.

## <a name="enable-relationship-definitions-in-global-address-bbook-414762"></a>Activer les définitions de relations dans l’adresse bBook globale (414762)

Les relations sont désormais activées dans le carnet d’adresses global. Avant la sortie de cette semaine, le récapitulatif **Relation** affichait toutes les relations définies par le système. Vous pouvez maintenant définir ces relations dans la page du carnet d’adresses global.

## <a name="a-position-can-be-removed-when-active-compensation-records-exist-for-the-position-414568"></a>Un poste peut être supprimé lorsqu’il existe des enregistrements de rémunération actifs pour le poste (414568)

Avec cette modification, un avertissement s’affiche lorsque vous tentez de supprimer un poste et un collaborateur a un enregistrement de rémunération actif pour ce même poste. Dans ce cas, vous devez mettre à jour l’enregistrement de rémunération fixe des employés avant de supprimer le poste.

## <a name="performance-review-workflow-occasionally-adds-sign-offs-from-people-who-are-not-part-of-the-process-414171"></a>Le flux de travail d’examen des performances ajoute occasionnellement des approbations de personnes qui ne font pas partie du processus (414171)

Cette modification corrige un problème dans lequel des participants d’approbation supplémentaires sont ajoutés à l’évaluation des performances.

## <a name="worker-position-assignment-not-created-in-dataverse-when-selected-on-the-new-worker-dialog-413479"></a>Affectation de poste de travail non créée dans Dataverse lorsque sélectionné dans la boîte de dialogue Nouveau collaborateur (413479)

Cette modification corrige un problème lors du recrutement d’un nouveau collaborateur et de l’affectation de la nouvelle recrue à un poste via la boîte de dialogue **Nouveau collaborateur**. Maintenant, l’affectation de poste se reflète dans Dataverse.

## <a name="coming-soon"></a>Prochainement

### <a name="updated-dataverse-solution"></a>Solution Dataverse mise à jour

Une nouvelle solution Dataverse sera bientôt disponible avec les modifications suivantes :

| Description | Monnaie |
| ----------------------------------------- | --- |
| Modifications de l’entité **Poste** | **Région de rémunération** ajoutée</br>**Dimensions financières** ajoutées |
| Modifications de l’entité **Collaborateur** | **Séquence de noms** ajoutée</br>**Télétravaille** ajouté</br>**Langue** ajoutée</br>**Date d’ancienneté** ajoutée</br>**Date anniversaire** ajoutée</br>**Date d’embauche d’origine** ajoutée |
| Modifications de l’entité **Emploi** | **Dimensions financières** ajoutées</br>**Motif de la fin du contrat** ajouté</br>**Date de résiliation** renommée à partir de **Date de transition**</br>**Période d’essai** ajoutée |
| Modifications de l’entité **Adresse du collaborateur** | **Nom de la rue** ajouté</br>**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression |
| Nouvelles entités de configuration de la rémunération variable | **Type de régime variable de rémunération**</br>**Régime variable de rémunération**</br>**Règles d’acquisition**</br>**Niveau de régime variable de rémunération** |
| Nouvelle entité **Emploi du calendrier du collaborateur** | **Entité de calendrier de travail** ajoutée |
| Nouvelle entité **Détails du poste de paie** | **Détails du poste de paie** ajoutés |
| Nouvelle entité **Titre** | **Titre** ajouté. La nouvelle entité **Titre** sera incluse dans le processus de synchronisation entre Human Resources et Dataverse. Elle ne sera pas référencée initialement à partir des entités **Poste** ou **Tâche**. |

Au cours des prochaines semaines, ces modifications d’entités seront disponibles dans tous les environnements. Pour installer manuellement la dernière solution Dataverse pour les ressources humaines :

1.  Accédez au [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).

2.  Sélectionner **Environnements**.

3.  Recherchez l’environnement que vous souhaitez mettre à niveau. Celui-ci doit correspondre à **Nom de l’environnement** dans la section **Informations relatives à Common Data Service** dans le formulaire **À propos de** dans Human Resources.

4.  Sélectionnez l’environnement pour afficher les détails de l’environnement.

5.  Dans la barre d’action située en haut, sélectionnez **Gérer les solutions**. Une nouvelle fenêtre de navigateur s’ouvrira et accédera au **Centre d’administration Dynamics 365** dans le contexte de votre environnement.

6.  Dans la liste **Solution**, sélectionnez **Ancre Dynamics 365 Human Resources**.

7.  Sélectionnez **Mettre à niveau** pour appliquer la dernière solution.

## <a name="in-preview"></a>En mode aperçu

Les fonctionnalités d’aperçu suivantes sont disponibles depuis le 3 février 2020 :

- **Fonctionnalités d’aperçu de congé et d’absence** – Pour plus d’informations, voir [Fonctionnalités d’aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Fonction d’aperçu de la gestion des avantages** – Pour plus d’informations, y compris les problèmes connus, voir [Aperçu de la gestion des avantages](hr-benefits-management-overview.md).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]