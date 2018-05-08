--- 
title: "Ajouter une contrainte d'expression à un modèle de configuration de produit"
description: "Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit."
author: YuyuScheller
manager: AnnBe
ms.date: 10/27/2016
ms.topic: business-process
ms.prod: 
ms.service: dynamics-ax-applications
ms.technology: 
audience: Application User
ms.reviewer: yuyus
ms.search.scope: Operations
ms.search.region: Global
ms.author: yuyus
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.translationtype: HT
ms.sourcegitcommit: 7e0a5d044133b917a3eb9386773205218e5c1b40
ms.openlocfilehash: 8db46c5b8361c96745b440c0d0684e18c06a6c6f
ms.contentlocale: fr-fr
ms.lasthandoff: 11/06/2017

---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Ajouter une contrainte d'expression à un modèle de configuration de produit

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit. Elle indique la manière dont vous pouvez demander que la protection des coins soit appliquée à un haut-parleur si l'utilisateur a sélectionné une grille avant métallique. Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.


## <a name="create-an-expression-constraint"></a>Création d'un contrainte d'expression
1. Cliquez sur Définition du modèle de variante de produit.
2. Cliquez sur Modèles de configuration de produit.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Cet exemple utilise le modèle de Haut-parleur haut de gamme.  
4. Dans la liste, cliquer sur le lien dans la ligne sélectionnée.
5. Développez la section Contraintes.
6. Cliquez sur Ajouter.
7. Cliquez sur Créer.
8. Tapez une valeur dans le champ Nom.

## <a name="enter-expression"></a>Entrer une expression
1. Cliquez sur Modifier l'expression.
    * Si vous déverrouillez l'interface utilisateur dans l'enregistreur de tâche à cette étape, vous pouvez utiliser IntelliSense et la liste des symboles pour établir l'expression de contrainte.  
2. Dans le champ ConstraintBody, entrez « Implies[FrontGrill=="Métal", CornerProtection] ».
    * Cette expression logique stipule : si la grille avant est en métal, il faut sélectionner l'option de protection des coins.  
3. Cliquez sur Valider.
    * La fonction de validation fonctionne via l'expression de contrainte et vérifie les erreurs de syntaxe.  
4. Cliquez sur Fermer.
5. Cliquez sur OK.


