---
title: Nouveautés ou modifications dans Dynamics 365 Talent (19 novembre 2019)
description: Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 Talent.
author: Darinkramer
manager: AnnBe
ms.date: 11/19/2019
ms.topic: article
ms.prod: ''
ms.service: dynamics-365-talent
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: anbichse
ms.search.scope: Talent
ms.custom: ''
ms.assetid: ''
ms.search.region: Global
ms.author: dkrame
ms.search.validFrom: 2019-11-19
ms.dyn365.ops.version: Talent
ms.openlocfilehash: aa984a01e9da30e6da07516fa2986833366a882b
ms.sourcegitcommit: e89bb3e5420a6ece84f4e80c11e360b4a042f59d
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/17/2020
ms.locfileid: "4527142"
---
# <a name="whats-new-or-changed-in-dynamics-365-talent-november-19-2019"></a>Nouveautés ou modifications dans Dynamics 365 Talent (19 novembre 2019)

[!include [rename-banner](~/includes/cc-data-platform-banner.md)]

Cet article décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Dynamics 365 Talent.

## <a name="changes-in-attract"></a>Modifications apportées dans Attract

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Attract.

## <a name="changes-in-onboard"></a>Modifications apportées à Onboard

Cette version inclut des correctifs de bogues mineurs pour Dynamics 365 Talent: Onboard.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

Les modifications décrites dans cette section s'appliquent au numéro de version 8.1.2621. Les numéros entre parenthèses dans certains en-têtes se rapportent aux numéros de support dans Microsoft Dynamics Lifecycle Services (LCS).

### <a name="platform-update-31-for-finance-and-operations-apps"></a>Mise à jour de la plateforme 31 pour les applications Finance and Operations

Pour plus d'informations, voir [Afficher un aperçu des fonctionnalités dans Platform Update 31 pour les applications Finance and Operations (janvier 2020)](https://docs.microsoft.com/dynamics365/fin-ops-core/dev-itpro/get-started/whats-new-platform-update-31).

### <a name="feature-management-workspace-383856"></a>Espace de travail Gestion des fonctions (383856)

L'espace de travail **Gestion des fonctions** fournit une liste des fonctions fournies dans chaque lancement. Par défaut, les nouvelles fonctionnalités sont désactivées. Vous pouvez utiliser l'espace de travail pour les activer et consulter la documentation les concernant. Pour plus d'informations sur la gestion des fonctions, voir [Présentation de la gestion des fonctions](https://docs.microsoft.com/dynamics365/fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview).

Toutes les nouvelles fonctionnalités restent dans la version préliminaire pendant au moins 30 jours, et généralement entre 30 et 60 jours. Les fonctionnalités principales sont généralement disponibles en octobre et en avril chaque année suivant la période de version préliminaire. Dès que vous voyez de nouvelles fonctionnalités dans l'espace de travail **Gestion des fonctions**, vous pouvez les activer. Certaines fonctionnalités peuvent être activées par défaut.
 
Parfois, une fonctionnalité intégrale sera activée par défaut et ne pourra pas être désactivée (par exemple, l'espace de travail **Gestion des fonctions**).
 
Une fois qu’une fonction est généralement disponible, elle peut être activée ou désactivée dans les environnements de production. L'espace de travail **Gestion des fonctions** indique quand une fonction d'aperçu devient obligatoire. Cette date est généralement le 1er octobre ou le 1er avril pour s’aligner avec les plans de lancement semi-annuels. Vous ne pouvez pas désactiver les fonctions obligatoires. Tant qu'elle n'est pas obligatoire, vous pouvez activer et désactiver une fonction dans tous les environnements.

### <a name="message-appears-when-canceled-action-exists-for-a-position-382887"></a>Le message s'affiche lorsque l'action annulée existe pour un poste (382887)

Le message suivant n'apparaît plus lorsque vous sélectionnez un poste spécifique et une action annulée est disponible pour le poste : **Une action incomplète est en cours pour le poste xxxxxx**.

### <a name="in-learning-analytics-the-course-type-and-status-display-incorrect-data-381151"></a>Dans les analyses d'apprentissage, le type de cours et le statut affichent des données incorrectes (381151)

La version de cette semaine a mis à jour les analyses d'apprentissage pour afficher correctement les champs **Type de cours** et **Statut**.

### <a name="personnel-number-should-display-in-the-new-worker-form-banner-383832"></a>Le numéro personnel doit s'afficher dans la bannière de l'écran Nouvel employé (383832)

Dans l'écran **Nouvel employeur**, **Numéro personnel** s'affiche dans la bannière pour une référence rapide.

### <a name="position-start-date-determines-the-job-record-to-use-when-retrieving-a-compensation-level-during-hire-350361"></a>La date de début du poste détermine l'enregistrement de la tâche à utiliser lors de la récupération d'un niveau de rémunération pendant le recrutement (350361)

Dans cette version, **Date de début de rémunération** détermine le niveau affecté à la nouvelle tâche.

### <a name="custom-pick-list-fields-in-the-position-table-arent-synchronized-to-common-data-service-387503"></a>Les champs de liste de prélèvement personnalisés dans la table Poste ne sont pas synchronisés vers Common Data Service (387503)

Avec cette version, les articles de la liste de prélèvement sont désormais synchronisés avec Common Data Service.

### <a name="worker-address-entity-doesnt-synchronize-with-common-data-service-while-importing-new-data-349673"></a>L'entité d'adresse de l'employeur n'est pas synchronisée avec Common Data Service lors de l'importation de nouvelles données (349673)

Dans la version de cette semaine, les données d'adresse se synchronisent maintenant avec Common Data Service tout en important de nouvelles données.

## <a name="in-preview"></a>En mode aperçu

### <a name="print-performance-reviews"></a>Imprimer les évaluations des performances

Voir [Imprimer les examens des performances](https://docs.microsoft.com/dynamics365-release-plan/2019wave2/dynamics365-talent/print-performance-reviews) dans Dynamics 365 : 2e partie du lancement 2019.
