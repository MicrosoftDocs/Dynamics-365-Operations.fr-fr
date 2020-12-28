---
title: Nouveautés ou modifications dans Dynamics 365 Human Resources (12 février 2020)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Human Resources pour le 12 février 2020.
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
ms.openlocfilehash: b89e022441f69825d9c9c56ecdbca2e09e461b9e
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4526886"
---
# <a name="whats-new-or-changed-in-dynamics-365-human-resources-february-12-2020"></a>Nouveautés ou modifications dans Dynamics 365 Human Resources (12 février 2020)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Human Resources. Les modifications s’appliquent au numéro de version 8.1.2867. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

## <a name="existing-entities-compfixedempls-and-hcmpersonimage-should-be-accessible-from-odata-414178"></a>Les entités existantes CompFixedEmpls et HcmPersonImage doivent être accessibles depuis OData (414178)

Avec la version de cette semaine, les entités **CompFixedEmpls** et **HcmPersonImage** sont désormais publiques et disponibles via ODAta.

## <a name="delete-employment-from-common-data-service-doesnt-work-when-employment-details-arent-active-403193"></a>La suppression d’un emploi de Common Data Service ne fonctionne pas lorsque les détails de l’emploi ne sont pas actifs (403193)

Cette modification permet désormais de supprimer un emploi via Common Data Service lorsqu’il n’existe aucun détail sur l’emploi actif.

## <a name="course-registration-workflow-changes-status-to-complete-and-errors-after-second-approval-409749"></a>Le statut du workflow d’inscription au cours passe à Terminé et des erreurs se produisent après la deuxième approbation (409749)

Le workflow d’inscription au cours a été mis à jour pour autoriser plusieurs approbateurs.

## <a name="in-preview"></a>En mode aperçu

Les fonctionnalités d’aperçu suivantes sont disponibles le 3 février 2020 :

- **Fonctionnalités d’aperçu de congé et d’absence** - Pour plus d’informations, voir [Fonctionnalités d’aperçu de congé et absence](hr-leave-and-absence-overview.md?leave-and-absence-preview-features).

- **Fonction d’aperçu de la gestion des avantages** - Pour plus d’informations, y compris les problèmes connus, voir [Aperçu de la gestion des avantages](hr-benefits-management-overview.md).

## <a name="coming-soon"></a>Prochainement

### <a name="platform-update-32"></a>Update 32 de la plateforme 

La mise à jour de la plate-forme 32 sera bientôt disponible. [Pour en savoir plus sur la mise à jour de la plate-forme 32, cliquez ici ](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-32).

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