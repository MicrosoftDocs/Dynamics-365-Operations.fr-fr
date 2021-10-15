---
title: Rechercher les variantes de produit obsolètes
description: Cette procédure décrit comment rechercher des produits ou des variantes de produits lancés obsolètes et comment associer un état du cycle de vie des produits aux produits obsolètes.
author: t-benebo
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 13db6620575b4c97b3f8079ac94f5231a2fd9c1b
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7577238"
---
# <a name="find-obsolete-product-variants"></a>Rechercher les variantes de produit obsolètes 

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment rechercher des produits ou des variantes de produits lancés obsolètes et comment associer un état du cycle de vie des produits aux produits obsolètes. Conditions préalables : vous devez définir au moins un état du cycle de vie des produits qui est inactif pour la planification avant de lire ce guide de tâche.


## <a name="run-a-simulation"></a>Exécuter une simulation
1. Accédez à Gestion des informations sur les produits > Tâches périodiques > Modifier l’état du cycle de vie des produits obsolètes.
2. Dans le champ Nouvel état du cycle de vie des produits, entrez ou sélectionnez une valeur.
3. Sélectionnez Oui dans le champ Exécuter la simulation sans mettre à jour les données du produit.
4. Dans le champ Exclure les produits créés dans ce nombre de jours, entrez un nombre.
5. Dans le champ Exclure les produits utilisés dans les transactions (en nombre de jours), entrez un nombre.
6. Développez les enregistrements pour inclure la section.
7. Cliquez sur Filtre.
8. Dans la liste, marquez la ligne sélectionnée.
9. Tapez une valeur dans le champ Critères.
10. Cliquez sur OK.
11. Cliquez sur OK.

> [!NOTE]
> Nous vous recommandons d’exécuter la simulation par lots si vous comptez rechercher un grand nombre de produits. En outre, vérifiez que la simulation n’est pas exécutée pendant le temps de travail le plus actif de la société.  

## <a name="review-the-simulation-results"></a>Examiner les résultats de la simulation
1. Accédez à Gestion des informations sur les produits > Recherches et états > Historique de maintenance de l’état du cycle de vie des produits.
   
> [!NOTE]
> Sur cette page, vous pouvez examiner les résultats de la simulation et effectuer une évaluation du nombre de produits et de variantes de produit à associer à un nouvel état du cycle de vie des produits lors de l’exécution de la mise à jour sans simulation.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>Exécuter la mise à jour de l’état du cycle de vie des produits pour les produits obsolètes
1. Fermez la page.
2. Accédez à Gestion des informations sur les produits > Tâches périodiques > Modifier l’état du cycle de vie des produits obsolètes.
3. Développez les enregistrements pour inclure la section.

> [!NOTE]
> Notez que la dernière sélection a été enregistrée.  

4. Sélectionnez Non dans le champ Exécuter la simulation sans mettre à jour les données du produit.
5. Développez la section Exécuter à l’arrière-plan.

> [!NOTE]
> Selon le nombre de produits et de variantes de produit affectés, envisagez d’exécuter cette tâche par lots. Vérifiez que vous n’exécutez pas une tâche de mise à jour volumineuse pendant les heures de travail les plus actives de la société.  

6. Cliquez sur OK.
7. Accédez à Gestion des informations sur les produits > Recherches et états > Historique de maintenance de l’état du cycle de vie des produits.

> [!NOTE]
> Examinez les modifications des produits et des variantes de produits lancés.  

8. Dans la liste, recherchez et sélectionnez l’enregistrement souhaité.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]