--- 
title: "Création de modèles de temps de travail"
description: "Les modèles de temps de travail définissent les heures de travail au cours d'une semaine et permettent de générer des temps de travail pour une période."
author: sorenva
manager: AnnBe
ms.date: 03/02/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: sorenand
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 9b947a02be981155053e33a4ef20e19bf2a194a5
ms.openlocfilehash: ff1978f127a014e75619a4bbbb9b6ff3a3ad7c7a
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="create-working-time-templates"></a>Création de modèles de temps de travail

[!include[task guide banner](../../includes/task-guide-banner.md)]

Les modèles de temps de travail définissent les heures de travail au cours d'une semaine et permettent de générer des temps de travail pour une période. Cette procédure vous indique comment définir un modèle de temps de travail à l'aide des propriétés de la planification du temps de travail pour classer les intervalles de temps de travail par catégorie. Vous pouvez parcourir cette procédure dans la société fictive USMF ou utiliser vos propres données.

1. Accédez à Tous les espaces de travail > Gestion des cycles de vie des ressources.
2. Cliquez sur Modèles de temps de travail.

## <a name="create-working-time-template"></a>Créer un modèle de temps de travail
1. Cliquez sur Nouveau.
2. Dans le champ Modèle de temps de travail, tapez une valeur.
3. Tapez une valeur dans le champ Nom.
4. Développez la section Lundi.
5. Cliquez sur Ajouter.
6. Dans le champ De, entrez une heure.
    * Spécifiez l'heure à laquelle le travail commence le matin.  
7. Dans le champ À, entrez une heure.
    * Spécifiez l'heure à laquelle les collaborateurs prennent leur pause déjeuner.  
8. Cliquez sur Ajouter.
9. Dans le champ De, entrez une heure.
    * Spécifiez l'heure à laquelle le travail reprend après le déjeuner.  
10. Dans le champ À, entrez une heure.
    * Spécifiez la fin de la journée de travail.  

## <a name="replicate-working-times-to-all-week-days"></a>Répliquer les temps de travail à tous les jours de la semaine
1. Cliquez sur Copier jour
    * Copiez les définitions de temps de travail de lundi à mardi.  
2. Cliquez sur OK.
3. Cliquez sur Copier jour
    * Copiez les définitions de temps de travail de lundi à mercredi.  
4. Dans le champ Au, sélectionnez une option.
5. Cliquez sur OK.
6. Cliquez sur Copier jour
    * Copiez les définitions de temps de travail de lundi à jeudi.  
7. Dans le champ Au, sélectionnez une option.
8. Cliquez sur OK.
9. Cliquez sur Copier jour
    * Copiez les définitions de temps de travail de lundi à vendredi.  
10. Dans le champ Au, sélectionnez une option.
11. Cliquez sur OK.

## <a name="define-time-slots-for-special-operations"></a>Définir des créneaux horaires pour les opérations spéciales
1. Développez la section Vendredi.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans le champ Propriété, saisissez ou sélectionnez une valeur.
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Dans le champ Propriété, saisissez ou sélectionnez une valeur.

## <a name="mark-weekend-days-as-closed-for-pickup"></a>Marquer les jours de week-end comme clôturés pour le prélèvement
1. Développez la section Samedi.
2. Sélectionnez Oui dans le champ Clôturé pour prélèvement.
3. Développez la section Dimanche.
4. Sélectionnez Oui dans le champ Clôturé pour prélèvement.

