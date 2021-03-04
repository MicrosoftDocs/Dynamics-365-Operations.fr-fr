---
title: Rechercher les variantes de produit obsolètes
description: Cette procédure décrit comment rechercher des produits ou des variantes de produits lancés obsolètes et comment associer un état du cycle de vie des produits aux produits obsolètes.
author: cvocph
manager: tfehr
ms.date: 12/05/2017
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
audience: Application User
ms.reviewer: kamaybac
ms.search.scope: Operations
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: b5efd1d471559d320102cd81e4be1ba8c1858f45
ms.sourcegitcommit: 199848e78df5cb7c439b001bdbe1ece963593cdb
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/13/2020
ms.locfileid: "4427742"
---
# <a name="find-obsolete-product-variants"></a>Rechercher les variantes de produit obsolètes 

[!include [banner](../../includes/banner.md)]

Cette procédure décrit comment rechercher des produits ou des variantes de produits lancés obsolètes et comment associer un état du cycle de vie des produits aux produits obsolètes. Conditions préalables : vous devez définir au moins un état du cycle de vie des produits qui est inactif pour la planification avant de lire ce guide de tâche.


## <a name="run-a-simulation"></a>Exécuter une simulation
1. Accédez à Gestion des informations sur les produits > Tâches périodiques > Modifier l'état du cycle de vie des produits obsolètes.
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
> Nous vous recommandons d'exécuter la simulation par lots si vous comptez rechercher un grand nombre de produits. En outre, vérifiez que la simulation n'est pas exécutée pendant le temps de travail le plus actif de la société.  

## <a name="review-the-simulation-results"></a>Examiner les résultats de la simulation
1. Accédez à Gestion des informations sur les produits > Recherches et états > Historique de maintenance de l'état du cycle de vie des produits.
   
> [!NOTE]
> Sur cette page, vous pouvez examiner les résultats de la simulation et effectuer une évaluation du nombre de produits et de variantes de produit à associer à un nouvel état du cycle de vie des produits lors de l'exécution de la mise à jour sans simulation.  

## <a name="run-the-update-of-the-product-lifecycle-state-for-obsolete-products"></a>Exécuter la mise à jour de l'état du cycle de vie des produits pour les produits obsolètes
1. Fermez la page.
2. Accédez à Gestion des informations sur les produits > Tâches périodiques > Modifier l'état du cycle de vie des produits obsolètes.
3. Développez les enregistrements pour inclure la section.

> [!NOTE]
> Notez que la dernière sélection a été enregistrée.  

4. Sélectionnez Non dans le champ Exécuter la simulation sans mettre à jour les données du produit.
5. Développez la section Exécuter à l'arrière-plan.

> [!NOTE]
> Selon le nombre de produits et de variantes de produit affectés, envisagez d'exécuter cette tâche par lots. Vérifiez que vous n'exécutez pas une tâche de mise à jour volumineuse pendant les heures de travail les plus actives de la société.  

6. Cliquez sur OK.
7. Accédez à Gestion des informations sur les produits > Recherches et états > Historique de maintenance de l'état du cycle de vie des produits.

> [!NOTE]
> Examinez les modifications des produits et des variantes de produits lancés.  

8. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]