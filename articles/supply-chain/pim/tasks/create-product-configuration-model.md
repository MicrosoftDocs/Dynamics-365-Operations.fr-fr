--- 
title: "Créer un modèle de configuration de produits"
description: "Cette procédure montre comment créer un modèle de configuration de produit et entrer des informations de base telles que des attributs et les sous-composants."
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCCreateProductConfigurationModel, PCProductConfigurationModelDetails, PCBOMLineDetails
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 674d2e1f2c5cdbccf43618a9083ca01abed0735a
ms.openlocfilehash: d494a20ba6f1f9c33a3935779b4bd3a8eefce26a
ms.contentlocale: fr-fr
ms.lasthandoff: 11/14/2017

---
# <a name="create-a-product-configuration-model"></a>Créer un modèle de configuration de produits

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment créer un modèle de configuration de produit et entrer des informations de base telles que des attributs et les sous-composants. Les données fictives utilisées pour créer cette procédure correspondent à la société USMF.


## <a name="create-a-product-model"></a>Créer un modèle de produit
1. Cliquez sur Définition du modèle de variante de produit.
2. Cliquez sur Modèles de configuration de produit.
3. Cliquez sur Nouveau.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Description, entrez une valeur.
6. Dans le champ Stratégie du solveur, sélectionnez une option.
    * La stratégie du solveur détermine la manière dont les contraintes sont traitées dans un modèle de configuration de produit basé sur les contraintes. Cette sélection peut avoir un impact sur les performances du modèle de configuration de produit.  
7. Tapez une valeur dans le champ Nom.
    * Le composant racine représente le modèle de configuration de produit, mais il peut également être utilisé dans d'autres modèles de produit.  
8. Cliquez sur OK.
9. Dans le champ Réutiliser les configurations, sélectionnez une option.
    * Si le paramètre de réutilisation de configurations est défini sur oui, le système cherchera des configurations identiques après chaque session de configuration et les réutilisera s'il trouve une correspondance exacte.  

## <a name="add-attributes"></a>Ajouter des attributs
1. Développer la section Attributs.
2. Cliquez sur Ajouter.
3. Dans la liste, marquez la ligne sélectionnée.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Nom du solveur, tapez une valeur.
    * Le nom de solveur est utilisé par le solveur de contrainte du configurateur de produit. Il ne doit pas inclure d'espaces ou de caractères spéciaux, sauf _ (trait de soulignement.)  
6. Dans le champ Description, entrez une valeur.
    * Le texte de description est affiché pour l'utilisateur de la configuration et il donc peut servir d'aide pour sélectionner la bonne valeur d'attribut.  
7. Saisissez ou sélectionnez une valeur dans le champ Type d'attribut.
    * Le type d'attribut détermine les valeurs disponibles pour l'attribut.  
8. Activez la case à cocher Inclure dans la réutilisation.
    * Cette option est disponible uniquement si l'option Réutiliser les configurations est sélectionnée. Inclure un attribut dans la case à cocher de réutilisation signifie que cet attribut sera pris en compte lorsque le système recherchera une correspondance exacte.  

## <a name="add-subcomponents"></a>Ajouter des sous-composants
1. Développez la section Sous-composants.
2. Cliquez sur Ajouter.
3. Dans la liste, marquez la ligne sélectionnée.
4. Tapez une valeur dans le champ Nom.
5. Dans le champ Nom du solveur, tapez une valeur.
6. Dans le champ Description, entrez une valeur.
7. Dans le champ Composant, saisissez ou sélectionnez une valeur.
    * Chaque sous-composant doit faire référence à une définition de composant. Cette conception prend en charge les composants réutilisables et garantit qu'une fois qu'un composant a été défini, il peut être utilisé dans de nombreux modèles de produit.  
8. Cliquez sur Enregistrer.
9. Cliquez sur Détails de ligne de nomenclature.
    * L'écran détails de ligne de nomenclature permet à l'utilisateur de sélectionner les propriétés requises pour le sous-composant. Chaque propriété peut se voir affecter une valeur fixe ou être mise en correspondance avec un attribut. La mise en correspondance avec un attribut a pour résultat que la propriété de ligne de nomenclature prend des valeurs différentes selon la configuration sélectionnée.  
10. Entrez ou sélectionnez une valeur dans le champ Numéro d'article.
    * Chaque sous-composant représente un produit générique configurable avec la technologie de configuration basée sur les contraintes. La référence est effectuée par le numéro d'article.  
11. Activez la case à cocher Définir.
12. Sélectionnez Oui dans le champ Calcul.
    * Définir l'option de calcul garantit que le produit sera inclus lors de l'exécution d'un calcul du coût du produit.  
13. Cliquez sur l'onglet Paramétrage.
14. Activez la case à cocher Définir.
15. Dans le champ Quantité, entrer un numéro.
    * Le champ de quantité détermine la quantité de ce produit qui sera consommée dans le produit configuré.  
16. Activez la case à cocher Définir.
17. Dans le champ Quantité de base, entrez un nombre.
18. Cliquez sur OK.


