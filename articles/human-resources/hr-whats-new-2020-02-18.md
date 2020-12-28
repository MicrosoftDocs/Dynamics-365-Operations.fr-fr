---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (18 février 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 18 février 2020.
author: Darinkramer
manager: AnnBe
ms.date: 02/18/2020
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
ms.search.validFrom: 2020-02-18
ms.dyn365.ops.version: Human Resources
ms.openlocfilehash: 002b1b8b86c4fb40f46c239669cd5dfead251bfe
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526976"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-18-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (18 février 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.2903. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support LCS pour référence.

## <a name="platform-update-32"></a>Platform update 32 

Platform update 32 est désormais disponible. Pour plus d’informations, voir [Nouveautés ou modifications dans Platform update 32 pour Finance and Operations (février 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

## <a name="search-values-are-remembered-when-changing-view-options-in-streamlined-employee-form-383833"></a>Les valeurs de recherche sont mémorisées lors de la modification des options d’affichage dans le formulaire simplifié des employés (383833)

Le nouveau formulaire **Collaborateur** mémorise désormais les valeurs de recherche lorsque vous modifiez les options d’affichage et appliquez les modifications.

## <a name="compensation-management-summary-tiles-in-preview-feature-redirect-to-wrong-form-401861"></a>Les vignettes récapitulatives de gestion de la rémunération dans la fonctionnalité en version préliminaire redirigent vers un formulaire incorrect (401861)

Les vignettes de gestion de la rémunération fixe et variable affichent désormais les enregistrements corrects dans le nouveau formlaire **Collaborateur**. S’applique uniquement à la fonctionnalité en version préliminaire du formulaire simplifié des employés. Vous pouvez activer cette fonctionnalité en version préliminaire dans **Gestion des fonctionnalités**. Pour plus d’informations, voir [Gérer les fonctionnalités](hr-admin-manage-features.md).

## <a name="empty-status-field-for-some-leave-request-records-in-common-data-service-414915"></a>Champ Statut vide pour certains enregistrements de demande de congé dans Common Data Service (414915)

Cette modification corrige un problème dans Common Data Service lorsque le champ **Statut** d’une demande de congé est défini sur **Révision**. Common Data Service reflète maintenant le statut.

## <a name="skill-gap-analysis-only-possible-for-assigned-job-411390"></a>L’analyse des écarts de compétences n’est possible que pour les tâches affectées (411390)

Vous pouvez désormais effectuer une analyse des écarts de compétences sur n’importe quelle tâche définie dans Human Resources.

## <a name="system-currency-doesnt-sync-from-common-data-service-to-human-resources-in-new-environments-418011"></a>La devise du système ne se synchronise pas entre Common Data Service et Human Resources dans les nouveaux environnements (418011)

La devise du système dans Common Data Service peut maintenant se synchroniser avec Human Resources.

## <a name="in-preview"></a>En mode aperçu

- [Fonctionnalités d’aperçu des congés et absences](hr-leave-and-absence-overview.md?leave-and-absence-preview-features)

- [Fonctionnalités en version préliminaire de gestion des avantages](hr-benefits-management-overview.md)

## <a name="coming-soon"></a>Prochainement

### <a name="updated-common-data-service-solution"></a>Solution Common Data Service mise à jour

Une nouvelle solution Common Data Service sera bientôt disponible avec les modifications suivantes :

| Description | Monnaie |
| ----------------------------------------- | --- |
| Modifications de l’entité **Poste** | **Région de rémunération** ajoutée</br>**Dimensions financières** ajoutées |
| Modifications de l’entité **Collaborateur** | **Séquence de noms** ajoutée</br>**Télétravaille** ajouté</br>**Langue** ajoutée</br>**Date d’ancienneté** ajoutée</br>**Date anniversaire** ajoutée</br>**Date d’embauche d’origine** ajoutée |
| Modifications de l’entité **Emploi** | **Dimensions financières** ajoutées</br>**Motif de la fin du contrat** ajouté</br>**Date de résiliation** renommée à partir de **Date de transition**</br>**Période d’essai** ajoutée |
| Modifications de l’entité **Adresse du collaborateur** | **Nom de la rue** ajouté</br>**Ligne d’adresse 1**, **Ligne d’adresse 2** et **Ligne d’adresse 3** marquées pour suppression |
| Nouvelles entités de configuration de la rémunération variable | **Type de régime variable de rémunération**</br>**Régime variable de rémunération**</br>**Règles d’acquisition**</br>**Niveau de régime variable de rémunération** |
| Nouvelle entité **Emploi du calendrier du collaborateur** | **Entité de calendrier de travail** ajoutée |
| Nouvelle entité **Détails du poste de paie** | **Détails du poste de paie** ajoutés |
| Nouvelle entité **Titre** | **Titre** ajouté. La nouvelle entité **Titre** sera incluse dans le processus de synchronisation entre Human Resources et Common Data Service. Elle ne sera pas référencée initialement à partir des entités **Poste** ou **Tâche**. |

## <a name="see-also"></a>Voir également :

[Nouveautés ou modifications dans Human Resources](hr-admin-whats-new.md)</br>
[Présentation de Dynamics 365 Human Resources 2019 vague de publication 2](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-human-resources/)</br>
[Processus de mise à jour](hr-admin-setup-update-process.md)</br>
[Gérer les fonctionnalités](hr-admin-manage-features.md)