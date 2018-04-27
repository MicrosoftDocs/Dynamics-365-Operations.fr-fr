--- 
title: "Créer des activités de processus pour la lean manufacturing"
description: "Créez une activité de processus pour la lean manufacturing."
author: cvocph
manager: AnnBe
ms.date: 11/11/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.search.industry: Manufacturing
ms.author: conradv
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: f827b4787506cfdec8b9a91c4a68f3293190158a
ms.openlocfilehash: dd77c20b622fd8a14e1cdf77883043699f9a6317
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="create-process-activities-for-lean-manufacturing"></a>Créer des activités de processus pour la lean manufacturing

[!INCLUDE [task guide banner](../../includes/task-guide-banner.md)]

Créez une activité de processus pour la lean manufacturing. 

Conditions préalables : 

1. Un flux de production et une version non actifs doivent être créés.

2. Une cellule de travail doit être créée.


## <a name="find-the-production-flow-version"></a>Cherchez la version du flux de production.
1. Accédez à Contrôle de la production > Paramétrage > Flux de production lean > Flux de production.
2. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
3. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="create-a-new-activity"></a>Créer une nouvelle activité
1. Cliquez sur Activités.
    * Vérifiez que le flux de production sélectionné a une version à l'état de brouillon, et sélectionnez celle-ci.  
2. Cliquez sur Créer une nouvelle activité de plan.
3. Cliquez sur Suivant.
4. Tapez une valeur dans le champ Nom.
5. Tapez une valeur dans le champ Nom.
    * Notez que le nom doit être unique pour un flux de production donné pour toutes les versions.  
6. Dans le champ Quantité à traiter, entrez un nombre.
    * Notez que, indépendamment de la quantité qui sera traitée, c'est la quantité minimale par tâche qui sert à calculer le coût de travail. Si les quantités de tâche dévient de cette quantité, l'écart de coût du travail est créé.  
7. Cliquez sur Suivant.

## <a name="select-the-work-cell"></a>Sélectionner la cellule de travail
1. Dans le champ Cellule de travail, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
2. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.

## <a name="define-the-inventory-updates"></a>Définir les mises à jour de stock
1. Activez ou désactivez la case à cocher Mettre à jour la réception disponible.
    * Si Mise à jour disponible = Non, vous pouvez définir l'activité de manière à recevoir un produit semi-fini (l'activité n'atteint pas le niveau de nomenclature suivant).    Vous pouvez également choisir de consommer des produits semi-finis.  

## <a name="define-the-picking-activities"></a>Définir les activités de prélèvement
1. Cliquez sur Suivant.
2. Dans la liste, marquez la ligne sélectionnée.
    * Une activité de prélèvement par défaut est créée pour l'emplacement d'entrée de la cellule de travail sélectionnée.  
3. Cliquez sur Ajouter.
    * Vous pouvez créer des activités de prélèvement supplémentaires pour des produits spécifiques, qui ne sont pas intermédiaires dans l'activité d'entrée de la cellule de travail.  
4. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
5. Tapez une valeur dans le champ Numéro d'article.
6. Dans le champ Entrepôt, cliquez sur le bouton de liste déroulante pour ouvrir la recherche.
    * Avec cette définition, toutes les matières consommées dans l'activité sont prélevées dans l'entrepôt et l'emplacement d'entrée par défaut, à l'exception de l'article qui est défini dans la deuxième activité de prélèvement. Cet article sera prélevé à partir d'un entrepôt et d'un emplacement différents.  
7. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
8. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
9. Activez ou désactivez la case à cocher Enregistrer le rebut.
10. Cliquez sur Suivant.

## <a name="define-the-activity-times"></a>Définir les durées d'activité
1. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * La définition d'un Délai d'exécution est requise. Le délai d'exécution est utilisé pour calculer les coûts et les délais de débit des tâches de kanban. Les délais d'exécution ne sont pas utilisés pour calculer la charge de la capacité et la consommation ; celles-ci sont calculées par durée de cycle, dérivée de la tâche de version du flux de production.  
2. Entrez un nombre dans le champ Durée.
3. Dans le champ Unité, tapez une valeur.
4. Sélectionnez l'Unité de temps.
5. Dans le champ Par quantité, entrez un nombre.
6. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Les temps d'attente sont facultatifs.  
7. Entrez un nombre dans le champ Durée.
8. Dans le champ Unité, tapez une valeur.
9. Sélectionnez l'Unité de temps.
10. Dans le champ Par quantité, entrez un nombre.
11. Cliquez sur Suivant.
12. Cliquez sur Terminer.
13. Fermez la page.


