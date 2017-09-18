--- 
title: "Créer des variantes de produits prédéfinies"
description: "Cette procédure décrit la création des variantes de produit pour un produit générique à l'aide des combinaisons de dimensions de produit."
author: BibiSp
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: bis
ms.search.scope: Operations
ms.search.region: Global
ms.author: bis
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 55b22d246d6bfa9e8159fb844da95f61fcf07c62
ms.openlocfilehash: fd6e6844b5920ba1364fa0fd5865d89d83789973
ms.contentlocale: fr-fr
ms.lasthandoff: 07/28/2017

---
# <a name="create-predefined-product-variants"></a>Créer des variantes de produits prédéfinies

[!include[task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit la création des variantes de produit pour un produit générique à l'aide des combinaisons de dimensions de produit. La société fictive de démonstration utilisée pour créer cette procédure est USMF.


## <a name="create-a-product-master"></a>Créer un produit générique
1. Accédez à Gestion des informations sur les produits > Produits > Produits génériques.
2. Cliquez sur Nouveau.
3. Dans le champ Numéro du produit, saisissez une valeur.
    * La saisie manuelle d'un numéro de produit est obligatoire uniquement si aucune souche de numéros n'a été paramétrée pour le champ du numéro de produit. Autrement dit, ignorez l'étape si la souche de numéros a été définie pour le champ.  
4. Dans le champ Nom du produit, saisissez une valeur.
5. Saisissez ou sélectionnez une valeur dans le champ Groupe de dimensions de produit.
    * Sélectionnez le groupe de dimensions de produit SizeCol (taille et couleur).  
6. Cliquez sur OK.

## <a name="add-product-dimensions"></a>Ajouter des dimensions de produit
1. Cliquez sur Dimensions de produit.
    * Cet exemple décrit la manière d'entrer manuellement les dimensions de produit. Vous pouvez également choisir de sélectionner un groupe de tailles, de couleurs ou de styles incluant les valeurs de dimension de produit à utiliser.  
2. Cliquez sur Nouveau.
3. Dans la liste, marquez la ligne sélectionnée.
4. Saisissez ou sélectionnez une valeur dans le champ Taille.
5. Tapez une valeur dans le champ Nom.
6. Cliquez sur Nouveau.
7. Dans la liste, marquez la ligne sélectionnée.
8. Saisissez ou sélectionnez une valeur dans le champ Taille.
9. Tapez une valeur dans le champ Nom.
10. Cliquez sur l'onglet Couleurs.
11. Cliquez sur Nouveau.
12. Dans la liste, marquez la ligne sélectionnée.
13. Dans le champ Couleur, saisissez ou sélectionnez une valeur.
14. Tapez une valeur dans le champ Nom.
15. Cliquez sur Nouveau.
16. Dans la liste, marquez la ligne sélectionnée.
17. Dans le champ Couleur, saisissez ou sélectionnez une valeur.
18. Tapez une valeur dans le champ Nom.
19. Cliquez sur Enregistrer.
20. Fermez la page.

## <a name="generate-product-variants"></a>Générer des variantes de produits
1. Cliquez sur Variantes de produit.
2. Cliquez sur Suggestions de variante.
3. Cliquez sur Sélectionner tout.
    * Dans cet exemple, toutes les variantes possibles sont sélectionnées. Si un seul sous-ensemble des combinaisons possibles de dimension de produit sera utilisé pour créer des variantes, vous pouvez sélectionner les entrées individuelles.  
4. Cliquez sur Créer.
    * Vous pouvez générer des descriptions pour toutes les variantes selon la combinaison des valeurs de dimension de produit. La description est facultative.  
5. Cliquez sur Enregistrer.

