---
title: Nouveautés ou modifications dans Dynamics 365 for Talent (7 février 2019)
description: Cette rubrique décrit les fonctionnalités qui sont nouvelles ou ont été modifiées dans Microsoft Dynamics 365 for Talent.
author: Darinkramer
manager: AnnBe
ms.date: 02/07/2019
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
ms.search.validFrom: 2019-02-07
ms.dyn365.ops.version: Talent
ms.openlocfilehash: b89fc15130755a80b56f26cf7c61674a26f43e36
ms.sourcegitcommit: 608e68b603afef9eb98d8fb25e90109c2473ef87
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2019
ms.locfileid: "858926"
---
# <a name="whats-new-or-changed-in-dynamics-365-for-talent-february-7-2019"></a>Nouveautés ou modifications dans Dynamics 365 for Talent (7 février 2019)

[!include [banner](includes/banner.md)]

Cette rubrique décrit les fonctionnalités inédites ou ayant fait l'objet de modifications dans Talent.

## <a name="changes-in-attract"></a>Modifications apportées à Attract

### <a name="interview-scheduling-enhancements"></a>Améliorations de la planification des entretiens
Des améliorations ont été apportées à l'expérience de planification des entretiens de bout en bout. Vous pouvez désormais voir la disponibilité du calendrier d'un candidat interne et utiliser le calendrier du candidat interne pour les recommandations du programme. Pour en savoir plus, consultez la rubrique [Planification et commentaires sur les entretiens](interview-scheduling-feedback.md).

### <a name="job-posting-to-linkedin--company-mismatch-issue-fixed"></a>Offre d'emploi sur LinkedIn : problème de société inappropriée corrigé
Un problème a été corrigé suite à la publication d'offres d'emploi sur LinkedIn depuis Attract sous un mauvais nom de société. Pour plus d'informations, voir [Créer, approuver et publier des annonces dans Attract](creating-jobs-attract.md).

### <a name="career-site-url-displayed-in-admin-settings"></a>URL du site de carrière affichée dans les paramètres d'administration
L'URL de la page d'accueil du site de carrière s'affiche désormais dans **Paramètres d'administration** sous **Gestion du site de carrière**.

## <a name="changes-in-core-hr"></a>Modifications apportées à Core HR

**Version 8.1.2134**

### <a name="multiple-compensation-levels-supported-on-jobs"></a>Plusieurs niveaux de rémunération pris en charge par les tâches
Cette modification permet de définir plusieurs niveaux de rémunération pour une tâche, générant ainsi des plages de rémunération fixe des employés, qui peuvent différer d'un plan à l'autre pour une même tâche. 

Par exemple :    
*Tâche* - Gestionnaire de compte *Niveaux de rémunération associés :* B1 et B2 - Chaque niveau a une plage de valeurs définie. B1 = 50 000 min, 60 000 moyen, 75 000 max et B2 = 65 000 min, 74 000 moyen, 85 000 max. En créant une rémunération fixe pour les employés, selon les règles d'éligibilité définies, chaque plan fixe peut désormais désigner la même tâche et différents niveaux de la tâche. Cela permet de définir des plans dans différentes régions/sociétés et de désigner la même tâche, mais différentes plages sans dupliquer les tâches pour tenir compte de ces différences.

### <a name="compensation-level-field-has-been-added-to-the-employee-fixed-compensation-entity"></a>Le champ du niveau de rémunération a été ajouté à l'entité de rémunération fixe des employés. 
Avec cette mise à jour, l'entité de rémunération fixe des employés a été mise à jour pour inclure le champ **Niveau de rémunération**. Cet ajout facilite la mise à jour des plans de rémunération fixe des employés. 

### <a name="update-job-family-when-updating-and-creating-new-positions"></a>Mettre à jour la famille de tâches lors de la mise à jour et de la création de postes
Lorsque vous modifiez la tâche sur un poste, l'option **Famille de tâches** est désormais définie par défaut sur la tâche sélectionnée.

### <a name="performance-improvements-when-rendering-workspaces"></a>Améliorations des performances lors du rendu des espaces de travail
Les onglets d'analyse des espaces de travail se chargent uniquement lors de l'accès à ces pages. Un indicateur s'affiche pendant le rendu initial de la page dans l'angle supérieur gauche de la page.
