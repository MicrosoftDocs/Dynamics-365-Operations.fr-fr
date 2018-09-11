--- 
title: "Définir des modèles de flux de production"
description: "Les modèles de flux de production décrivent comment la capacité des cellules de travail Lean Manufacturing est calculée et mise à jour."
author: cvocph
manager: AnnBe
ms.date: 8/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: LeanProductionFlowModel
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 7850a121ca06f25f6c532e49e18c0b6811bd7455
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="define-production-flow-models"></a>Définir des modèles de flux de production

[!include [task guide banner](../../includes/task-guide-banner.md)]

Les modèles de flux de production décrivent comment la capacité des cellules de travail Lean Manufacturing est calculée et mise à jour. Par conséquent, la définition d'un modèle de flux de production est une connaissance préalable de la définition des cellules de travail. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="define-a-production-flow-model"></a>Définissez un modèle de flux de production 
1. Accédez à Contrôle de la production > Configuration > Flux de production au plus juste > Modèles de flux de production.
2. Cliquez sur Nouveau.
3. Dans le champ Modèle de flux de production, entrez un ID pour le modèle de flux de production.
4. Dans le champ Type de modèle, sélectionnez une option.
    * Il existe deux types modèles : Type de débit et Type d'heures. Pour le type de débit, la capacité des cellules de travail qui utilisent ce modèle de flux de production est exprimée et calculée en quantités de produits. Pour le type d'heures, la capacité des cellules de travail qui utilisent ce modèle de flux de production est exprimée et calculée en heures. Notez que cette propriété ne peut pas être modifiée pour un modèle de flux de production existant. Une fois que la cellule de travail a des réservations de capacité, le type de modèle de flux de production ne peut pas être modifié.  
5. Indiquez le nombre de jours du Cycle EPE.
    * L'intervalle décrit la période pendant laquelle chaque partie produite par un flux de production ou une cellule de travail est produite au moins une fois. Plus le cycle EPE est abrégé, plus le processus de production est flexible. Si le cycle EPE = 0 %, toute la demande peut être produit dans le même jour. Le cycle EPE permet de planifier des tâches de traitement au plus juste. Lorsque la planification d'une tâche dans une cellule de travail associée au cycle EPE = 5, le processus de planification recherche la capacité de la cellule de travail à la date d'échéance : le cycle EPE (5 jours avant de date d'échéance) pour garantir que le produit peut être fabriqué dans le cadre de ce cycle. Le délai de stock d'un produit est généralement égal ou supérieur au cycle EPE du processus de production connexe.  
6. Dans le champ Période de planification, sélectionnez une option.
    * Une fois que la cellule de travail a des réservations de capacité, le type de période de planification ne peut pas être modifié. Vous pouvez uniquement sélectionner les modèles de flux de production dotés du même type de période que cette cellule de travail donnée.  
7. Dans le champ Plage de gestion de planification, entrez un nombre.
    * La plage de gestion de planification décrit le nombre de jours où les réservations de capacité peuvent être effectuées pour les cellules de travail connexes. Dans la plage de gestion de planification, entrez le nombre de jours.   Les tâches de traitement Kanban qui tombent en dehors de cette période ne sont pas prévues avec la planification automatique. La plage de gestion de planification est généralement deux fois supérieure au délai de stock moyen des produits produits dans un flux de production ou une cellule de travail. Le cycle EPE ne doit pas être supérieur à la moitié de la plage de gestion de planification.     
8. Dans le champ Réaction de pénurie de capacité, sélectionnez une option.
    * Les options sont les suivantes : Ajourner - Ajourner la demande complète de l'événement de planification au prochain jour de production disponible, avec le débit disponible. Annuler - Terminer la planification automatique pour l'événement de planification et laisser les tâches connexes non planifiées.   Ajouter au jour demandé - Planifier les tâches demandées pour la période requise. Cela surcharge la cellule pour le jour en question et exige que le planificateur effectue un examen et une interaction manuelle.   Répartir sur les périodes disponibles - Distribuer les différentes tâches de l'événement de planification à tous les jours de production disponibles, à partir du premier jour disponible. La quantité de distribution minimum correspond à la quantité de tâches de kanban. La distribution affecte la quantité de planification minimale (quantité de kanban) à chaque jour doté de suffisamment de débit disponible.  


