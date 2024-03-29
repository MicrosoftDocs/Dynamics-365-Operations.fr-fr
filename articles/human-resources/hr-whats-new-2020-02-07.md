---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (7 février 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 7 février 2020.
author: andreabichsel
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: jaredha
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: e58ab3ffc215a340dca694aee7cf04c65303b65b
ms.sourcegitcommit: a58dfb892e43921157014f0784bd411f5c40e454
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2022
ms.locfileid: "8687950"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-7-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (7 février 2020)

[!include [Applies to Human Resources](../includes/applies-to-hr.md)]



Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.2835. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

## <a name="learning-analytics-doesnt-show-the-course-if-the-classroom-is-blank-388289"></a>Les analyses d’apprentissage n’affichent pas le cours si la salle de classe est vide (388289)

La page des analyses d’apprentissage affiche désormais le cours si la salle de classe est vide.

## <a name="position-lookup-doesnt-take-the-time-zone-into-account-405344"></a>La recherche de poste ne prend pas en compte le fuseau horaire (405344)

La recherche de postes ouverts prend désormais en compte le fuseau horaire lors de la validation de l’ouverture d’un poste.

## <a name="current-balance-analysis-view-doesnt-update-with-the-correct-current-leave-balance-after-submitting-time-off-requests-409756"></a>La vue d’analyse du solde actuel ne se met pas à jour avec le solde de congés actuel correct après la soumission des demandes de congé (409756)

Le solde actuel comprend désormais les demandes de congé soumises.

## <a name="in-preview"></a>En mode aperçu

Les fonctionnalités d’aperçu suivantes sont disponibles le 3 février 2020 :

- **Fonctionnalités d’aperçu de congé et d’absence** – Pour plus d’informations, voir [Fonctionnalités d’aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Fonctionnalités en version préliminaire de gestion des avantages** – Pour plus d’informations, y compris les problèmes connus, voir [Vue d’ensemble de la gestion des avantages](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Prochainement

### <a name="platform-update-32"></a>Update 32 de la plateforme 

La mise à jour de la plate-forme 32 sera bientôt disponible. [Pour en savoir plus sur la mise à jour de la plate-forme 32, cliquez ici ](../fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32.md).

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

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)

[!INCLUDE[footer-include](../includes/footer-banner.md)]