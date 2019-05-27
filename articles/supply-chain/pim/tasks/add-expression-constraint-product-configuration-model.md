---
title: Ajouter une contrainte d'expression à un modèle de configuration de produit
description: Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 56f94b82f8b2642b12a993bde7d6bb323da79f98
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1547146"
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

