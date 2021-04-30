---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (10 mars 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 10 mars 2020.
author: andreabichsel
ms.date: 03/10/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-03-10
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 7a82ff2b1faf99b7776fabb5fae3798b16f32b75
ms.sourcegitcommit: 951393b05bf409333cb3c7ad977bcaa804aa801b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/13/2021
ms.locfileid: "5892103"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-10-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (10 mars 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.2985. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="cant-access-skill-gap-analysis-report-394460"></a>Impossible d’accéder au rapport d’analyse des écarts de compétences (394460)

Cet état n’est pas pris en charge dans Dynamics 365 Human Resources. L’élément de menu pour imprimer l’état SSRS est supprimé.

## <a name="incorrect-message-accessing-the-getting-started-page-417950"></a>Message incorrect accédant à la page Mise en route (417950)

Avec cette modification, la sécurité masque cet élément de menu si vous n’avez pas accès au formulaire.

## <a name="streamlined-task-maintenance-for-employees-380538"></a>Maintenance simplifiée des tâches pour les employés (380538)

Le formulaire de maintenance des tâches du collaborateur répertorie toutes les tâches d’un employé dans les processus d’intégration, de départ, de transition et d’entreprise. Vous pouvez désormais supprimer, réattribuer ou mettre à jour le statut des tâches.

Exemple : Benjamin Martin est administrateur des avantages sociaux. Lors de l’intégration des employés, des tâches sont créées pour que Benjamin examine la sélection des avantages du nouvel employé. Benjamin a des tâches passées qu’il a accomplies et des tâches futures qu’il doit accomplir. Benjamin décide de quitter l’entreprise, ses tâches doivent donc être réaffectées ou supprimées. Le formulaire de maintenance des tâches (dans le volet Actions du formulaire **Collaborateur**) permet à toutes les tâches de Benjamin d’être réaffectées à un autre collaborateur ou supprimées.  

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>La solution Dataverse est désormais disponible avec les modifications suivantes :

| Description | Monnaie |
| --- | --- |
| Modifications de l’entité **Poste** | <ul><li>**Région de rémunération** ajoutée</li>|
| Entité **Dimension du poste** ajoutée | <ul><li>**Dimensions financières** ajoutées</li>
| Modifications de l’entité **Collaborateur** | <ul><li>**Séquence de noms** ajoutée</li><li>**Télétravaille** ajouté</li><li>**Langue** ajoutée</li><li>**Date d’ancienneté** ajoutée</li><li>**Date anniversaire** ajoutée</li><li>**Date d’embauche d’origine** ajoutée</li></ul> |
| Modifications de l’entité **Emploi** | <ul><li>**Dimensions financières** ajoutées</li><li>**Motif de la fin du contrat** ajouté</li><li>**Date de résiliation** renommée à partir de **Date de transition**</li><li>**Période d’essai** ajoutée</li></ul> |
| Modifications de l’entité **Adresse du collaborateur** | <ul><li>**Nom de la rue** ajouté</li><li>**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression</li></ul> |
| Nouvelles entités de configuration de la rémunération variable | <ul><li>**Type de régime variable de rémunération**</li><li>**Régime variable de rémunération**</li><li>**Règles d’acquisition**</li><li>**Niveau de régime variable de rémunération**</li></ul> |
| Nouvelle entité **Emploi du calendrier du collaborateur** | <ul><li>**Entité de calendrier de travail** ajoutée</li></ul> |
| Nouvelle entité **Détails du poste de paie** | <ul><li>**Détails du poste de paie** ajoutés</li></ul> |
| Nouvelle entité **Titre** | <ul><li>**Titre** ajouté</li></ul> La nouvelle entité **Titre** est incluse dans Dataverse, mais n’est pas référencée depuis les entités **Poste** ou **Tâche** à ce moment même. |

> [!NOTE]
> Les dimensions financières des postes et de l’emploi offrent une intégration à sens unique pour les mises à jour des ressources humaines vers Dataverse. Les mises à jour des dimensions financières ne sont actuellement pas synchronisées à partir de Dataverse vers les ressources humaines.

Au cours des prochaines semaines, ces modifications d’entités seront disponibles dans tous les environnements. Pour installer manuellement la dernière solution Dataverse pour les ressources humaines :

1.  Accédez au [Centre d’administration Power Platform](https://admin.powerplatform.microsoft.com).

2.  Sélectionner **Environnements**.

3.  Recherchez l’environnement que vous souhaitez mettre à niveau. L’environnement doit correspondre à **Nom de l’environnement** dans la section **Informations relatives à Dataverse** dans le formulaire **À propos de** dans Human Resources.

4.  Sélectionnez l’environnement pour afficher les détails de l’environnement.

5.  Dans la barre d’action située en haut, sélectionnez **Gérer les solutions**. Une nouvelle fenêtre de navigateur s’ouvrira et accédera au **Centre d’administration Dynamics 365** dans le contexte de votre environnement.

6.  Dans la liste **Solution**, sélectionnez **Ancre Dynamics 365 Human Resources**.

7.  Sélectionnez **Mettre à niveau** pour appliquer la dernière solution.

## <a name="in-preview"></a>En mode aperçu

Les fonctionnalités d’aperçu suivantes sont disponibles le 3 février 2020 :

- **Fonctionnalités d’aperçu de congé et d’absence** – Pour plus d’informations, voir [Fonctionnalités d’aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Fonction d’aperçu de la gestion des avantages** – Pour plus d’informations, y compris les problèmes connus, voir [Aperçu de la gestion des avantages](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Prochainement

### <a name="platform-update-33"></a>Update 33 de la plateforme

- Applications pleine page (Aperçu) - Cette fonctionnalité d’aperçu, qui vous oblige à activer la fonction Vues enregistrées, permet à Power Apps et aux applications tierces d’être ajoutées en tant qu’expériences pleine page via le tableau de bord.

- Vues enregistrées (Aperçu) - Cette fonction d’aperçu active les vues enregistrées, ce qui constitue une amélioration significative du sous-système de personnalisation. Cette fonctionnalité permet aux utilisateurs d’avoir plusieurs ensembles de personnalisations nommés par page. Vous pouvez également publier des vues sur les rôles de sécurité.

- Expérience de filtrage optimisée « fait partie de » - Cette fonctionnalité permet une expérience de filtrage optimisée « fait partie de » qui facilite la saisie de plusieurs valeurs de filtre, a un mécanisme plus simple pour supprimer une valeur de filtre individuelle ou toutes les visualisations des valeurs de filtre.

- Champs recommandés - Les utilisateurs doivent souvent ajouter des champs à une grille ou à une page. Cela peut être difficile avec autant de champs disponibles. Au lieu d’avoir à parcourir une grande liste, cette fonction permet au système de faire apparaître un ensemble de champs recommandés en fonction de ce que les autres utilisateurs ajoutent le plus souvent dans des scénarios similaires.

- Actions par défaut rémanentes dans les grilles - Cette fonctionnalité garantit que l’action par défaut dans une grille est liée à une colonne spécifique dans une grille, que cette colonne soit déplacée ou masquée.

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]