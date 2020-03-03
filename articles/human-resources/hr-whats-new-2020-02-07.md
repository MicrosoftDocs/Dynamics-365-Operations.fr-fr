---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (7 février 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2020
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-human-resources
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Human Resources
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2020-02-07
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 78043273fb98a12a8d33f7bb94ba8ad2e9fb49fb
ms.sourcegitcommit: 13c4a6f98ccce243d6befde90992aefcf562bdab
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "3029955"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-7-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (7 février 2020)

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s'appliquent au numéro de version 8.1.2835. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

## <a name="learning-analytics-doesnt-show-the-course-if-the-classroom-is-blank-388289"></a>Les analyses d'apprentissage n'affichent pas le cours si la salle de classe est vide (388289)

La page des analyses d'apprentissage affiche désormais le cours si la salle de classe est vide.

## <a name="position-lookup-doesnt-take-the-time-zone-into-account-405344"></a>La recherche de poste ne prend pas en compte le fuseau horaire (405344)

La recherche de postes ouverts prend désormais en compte le fuseau horaire lors de la validation de l'ouverture d'un poste.

## <a name="current-balance-analysis-view-doesnt-update-with-the-correct-current-leave-balance-after-submitting-time-off-requests-409756"></a>La vue d'analyse du solde actuel ne se met pas à jour avec le solde de congés actuel correct après la soumission des demandes de congé (409756)

Le solde actuel comprend désormais les demandes de congé soumises.

## <a name="in-preview"></a>En mode aperçu

Les fonctionnalités d'aperçu suivantes sont disponibles le 3 février 2020 :

- **Fonctionnalités d'aperçu de congé et d'absence** - Pour plus d'informations, voir [Fonctionnalités d'aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Fonction d'aperçu de la gestion des avantages** - Pour plus d'informations, y compris les problèmes connus, voir [Aperçu de la gestion des avantages](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Prochainement

### <a name="platform-update-32"></a>Update 32 de la plateforme 

La mise à jour de la plate-forme 32 sera bientôt disponible. [Pour en savoir plus sur la mise à jour de la plate-forme 32, cliquez ici ](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

### <a name="updated-common-data-service-solution"></a>Solution Common Data Service mise à jour

Une nouvelle solution Common Data Service sera bientôt disponible avec les modifications suivantes :

| Description | Monnaie |
| ----------------------------------------- | --- |
| Modifications de l'entité **Poste** | **Région de rémunération** ajoutée</br>**Dimensions financières** ajoutées |
| Modifications de l'entité **Collaborateur** | **Séquence de noms** ajoutée</br>**Télétravaille** ajouté</br>**Langue** ajoutée</br>**Date d'ancienneté** ajoutée</br>**Date anniversaire** ajoutée</br>**Date d'embauche d'origine** ajoutée |
| Modifications de l'entité **Emploi** | **Dimensions financières** ajoutées</br>**Motif de la fin du contrat** ajouté</br>**Date de résiliation** renommée à partir de **Date de transition**</br>**Période d'essai** ajoutée |
| Modifications de l'entité **Adresse du collaborateur** | **Nom de la rue** ajouté</br>**Ligne d'adresse 1**, **Ligne d'adresse 2** et **Ligne d'adresse 3** marquées pour suppression |
| Nouvelles entités de configuration de la rémunération variable | **Type de régime variable de rémunération**</br>**Régime variable de rémunération**</br>**Règles d'acquisition**</br>**Niveau de régime variable de rémunération** |
| Nouvelle entité **Emploi du calendrier du collaborateur** | **Entité de calendrier de travail** ajoutée |
| Nouvelle entité **Détails du poste de paie** | **Détails du poste de paie** ajoutés |
| Nouvelle entité **Titre** | **Titre** ajouté. La nouvelle entité **Titre** sera incluse dans le processus de synchronisation entre Human Resources et Common Data Service, mais ne sera pas référencée initialement à partir des entités **Poste** ou **Emploi**. |
