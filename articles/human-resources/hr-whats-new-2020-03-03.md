---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (3 mars 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 3 mars 2020.
author: andreabichsel
manager: tfehr
ms.date: 03/03/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-03-03
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 695ae11278a270a44c1ade51964aa396d2fafc60
ms.sourcegitcommit: 6affb3316be757c99e1fe9c7c7b312b93c483408
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/17/2021
ms.locfileid: "5463740"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-march-3-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (3 mars 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.2955. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="dataverse-solution-is-now-available-with-the-following-changes"></a>La solution Dataverse est désormais disponible avec les modifications suivantes :

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

3.  Recherchez l’environnement que vous souhaitez mettre à niveau. L’environnement doit correspondre à **Nom de l’environnement** dans la section **Informations relatives à Common Data Service** dans le formulaire **À propos de** dans Human Resources.

4.  Sélectionnez l’environnement pour afficher les détails de l’environnement.

5.  Dans la barre d’action située en haut, sélectionnez **Gérer les solutions**. Une nouvelle fenêtre de navigateur s’ouvrira et accédera au **Centre d’administration Dynamics 365** dans le contexte de votre environnement.

6.  Dans la liste **Solution**, sélectionnez **Ancre Dynamics 365 Human Resources**.

7.  Sélectionnez **Mettre à niveau** pour appliquer la dernière solution.

## <a name="import-issues-with-the-leave-enrollment-data-entity-406082"></a>Problèmes d’importation avec l’entité de données Inscription aux congés (406082)

Vous pouvez désormais inscrire un employé à un nouveau plan de congé du même type, dans la mesure où la nouvelle date d’inscription est ultérieure à la date d’inscription du plan précédent qui a expiré.

## <a name="issue-with-exporting-contribution-rates-in-the-401k-payrollworkerenrolledbenefitdetail-entity-in-dmf-420700"></a>Problème avec l’exportation des taux de cotisation dans l’entité 401k payrollWorkerEnrolledBenefitDetail dans DMF (420700)

Cette modification corrige la fonctionnalité d’exportation pour l’entité **payrollWorkerEnrolledBenefitDetail** pour refléter les valeurs actuelles de la cotisation patronale.

## <a name="searching-in-the-streamlined-worker-form-causes-message-saying-person-field-must-be-filled-in-402525"></a>La recherche dans le formulaire de collaborateur simplifié génère un message indiquant que le champ Personne doit être rempli (402525)

Lorsque vous recherchez un employé, vous ne recevrez plus de message indiquant que vous devez remplir le champ **Personne**.

## <a name="note-field-value-doesnt-render-on-the-add-more-skills-form-380134"></a>Sachez que la valeur du champ ne s’affiche pas sur le formulaire Ajouter plus de compétences (380134)

Cette modification corrige un problème lorsque vous personnalisez le formulaire **Ajouter plus de compétences** dans le libre-service des employés.

## <a name="multiple-fixed-compensation-plans-dont-expire-when-transferring-employees-389466"></a>Plusieurs régimes de rémunération fixe n’expirent pas lors du transfert d’employés (389466)

Avec cette modification, tous les enregistrements de rémunération fixe actifs pour l’ancien poste expireront à la date de transition.

## <a name="in-preview"></a>En mode aperçu

Les fonctionnalités d’aperçu suivantes sont disponibles depuis le 3 février 2020 :

- **Fonctionnalités d’aperçu de congé et d’absence** - Pour plus d’informations, voir [Fonctionnalités d’aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Fonction d’aperçu de la gestion des avantages** - Pour plus d’informations, y compris les problèmes connus, voir [Aperçu de la gestion des avantages](hr-benefits-management-overview.md).

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]