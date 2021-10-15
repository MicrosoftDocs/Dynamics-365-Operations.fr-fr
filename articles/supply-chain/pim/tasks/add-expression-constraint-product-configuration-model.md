---
title: Ajouter une contrainte d’expression à un modèle de configuration de produit
description: Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit.
author: t-benebo
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCProductConfigurationModelDetails, SysClientPolymorphicCreateSelector, PCConstraintEditor, PCRuntimeConfiguratorValidate
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: AX 7.0.0
ms.openlocfilehash: 77e8b991a2615a8f5d238acc4655f231edb6ca98
ms.sourcegitcommit: 3b87f042a7e97f72b5aa73bef186c5426b937fec
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/29/2021
ms.locfileid: "7569647"
---
# <a name="add-an-expression-constraint-to-a-product-configuration-model"></a>Ajouter une contrainte d’expression à un modèle de configuration de produit

[!include [banner](../../includes/banner.md)]

Cette procédure montre comment ajouter une nouvelle expression de contrainte à un modèle de configuration de produit. Elle indique la manière dont vous pouvez demander que la protection des coins soit appliquée à un haut-parleur si l’utilisateur a sélectionné une grille avant métallique. Cette procédure utilise le composant Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF.

## <a name="create-an-expression-constraint"></a>Création d’un contrainte d’expression

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
3. Dans la liste, recherchez et sélectionnez l'enregistrement souhaité.
    * Cet exemple utilise le modèle de Haut-parleur haut de gamme.  
4. Dans la liste, sélectionnez le lien dans la ligne sélectionnée.
5. Développez la section **Contraintes**.
6. Sélectionnez **Ajouter**.
7. Sélectionnez **Créer**.
8. Tapez une valeur dans le champ **Nom**.

## <a name="enter-expression"></a>Entrer une expression

1. Sélectionnez **Modifier l’expression**.
    * Si vous déverrouillez l’interface utilisateur dans l’enregistreur de tâche à cette étape, vous pouvez utiliser IntelliSense et la liste des symboles pour établir l’expression de contrainte.  
2. Dans le champ **ConstraintBody**, entrez « Implies[FrontGrill=="Métal", CornerProtection] ».
    * Cette expression logique stipule : si la grille avant est en métal, il faut sélectionner l’option de protection des coins.  
3. Sélectionnez **Valider**.
    * La fonction de validation fonctionne via l’expression de contrainte et vérifie les erreurs de syntaxe.  
4. Sélectionnez **Fermer**.
5. Cliquez sur **OK**.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]