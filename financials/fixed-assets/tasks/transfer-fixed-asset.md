--- 
title: "Transférer une immobilisation"
description: "Ce Guide de tâche transfèrera les informations financières pour un registre d'immobilisation provenant d'un ensemble de dimensions financières vers le nouvel ensemble de dimensions financières."
author: saraschi2
manager: AnnBe
ms.date: 02/23/2017
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: twheeloc
ms.search.scope: Operations
ms.search.region: Global
ms.author: saraschi
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f01d88149074b37517d00f03d8f55e1199a5198f
ms.openlocfilehash: ebde1e8bd8a87b44dd77b9050d05d6c2f4774ef2
ms.contentlocale: fr-fr
ms.lasthandoff: 07/27/2017

---
# <a name="transfer-a-fixed-asset"></a>Transférer une immobilisation

[!include[task guide banner](../../includes/task-guide-banner.md)]

Ce Guide de tâche transfèrera les informations financières pour un registre d'immobilisation provenant d'un ensemble de dimensions financières vers le nouvel ensemble de dimensions financières.  Il utilise le rôle de comptable et les données de démonstration de l'entité juridique USMF.

1. Accédez à Immobilisations > Immobilisations > Immobilisations.
2. Dans la liste, recherchez et sélectionnez l'immobilisation à transférer.
3. Cliquez sur Immobilisation dans le volet Actions.
4. Cliquez sur Transférer des immobilisations.
5. Entrez une date dans le champ Date de transfert.
6. Entrez des commentaires pour décrire le transfert.
    * Cette liste répertorie tous les registres pour l'immobilisation.  
7. Marquez les registres à transférer vers le nouvel ensemble de dimensions financières.
    * Cette liste répertorie les valeurs de dimension financière existantes pour le registre sélectionné.  
    * Sélectionnez la dimension financière que vous souhaitez mettre à jour pour le registre d'immobilisation sélectionné.  
8. Dans le champ Dimension financière, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Définissez d'autres valeurs de dimension financière, le cas échéant.  
    * Toutes les valeurs de dimension financière sont modifiées lorsqu'un transfert a lieu, même si une valeur a été entrée ou est laissée vide. Par exemple, si vous avez entré une valeur pour BusinessUnit et laissé les dimensions financières pour CostCenter et Département vides. Si votre structure de compte avait autorisé les valeurs vides pour CostCenter et Département, suite au transfert, chaque modèle de valeur aurait eu la nouvelle valeur pour BusinessUnit et une valeur vide pour CostCenter et Département.  
9. Cliquez sur Mise à jour.
    * Vous pouvez prévisualiser les modifications avant de finaliser le transfert.  
    * Réexaminez les résultats avant de transférer les registres d'immobilisation.  
10. Cliquez sur Transférer.


