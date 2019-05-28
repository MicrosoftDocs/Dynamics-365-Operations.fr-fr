---
title: Paramétrer la tarification par attribut pour les produits configurables
description: Cette procédure décrit comment paramétrer la tarification basée sur des attributs.
author: ShylaThompson
manager: AnnBe
ms.date: 08/29/2018
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: shylaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 8568b5f4933ae58bc2d55a169c798668e03bed2a
ms.sourcegitcommit: 9d4c7edd0ae2053c37c7d81cdd180b16bf3a9d3b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/15/2019
ms.locfileid: "1573278"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Paramétrer la tarification par attribut pour les produits configurables

[!include [task guide banner](../../includes/task-guide-banner.md)]

Cette procédure décrit comment paramétrer la tarification basée sur des attributs. Comme condition préalable, vous devez avoir un modèle de configuration de produit contenant un ou plusieurs composants et attributs. Cet exemple utilise le modèle de produit Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF. Généralement, un responsable de produit utilise cette procédure.


## <a name="create-a-new-price-model"></a>Créer un modèle de prix
1. Cliquez sur Définition du modèle de variante de produit.
2. Cliquez sur Modèles de configuration de produit.
3. Dans la liste, sélectionnez la ligne Haut-parleur haut de gamme, mais ne cliquez pas sur le lien du nom.
4. Dans le volet Actions, cliquez sur Modèle.
5. Cliquez sur Modèles de prix.
6. Cliquez sur Nouveau.
7. Dans le champ Modèle de prix, tapez une valeur.
    * Utilisez un nom qui permet d'identifier facilement le modèle.  
8. Dans le champ Description, entrez une valeur.
9. Cliquez sur Enregistrer.

## <a name="add-price-elements"></a>Ajouter des éléments de prix
1. Cliquez sur Modifier.
    * Chaque composant d'un modèle de produit peut avoir un élément de prix de base et plusieurs règles d'expression de prix. Vous pouvez également ajouter des prix dans différentes devises.  
2. Dans le champ Expression de prix de base, tapez une valeur.
    * Entrez 100, par exemple.   Une expression de prix de base peut être une valeur numérique, ou elle peut consister en un calcul arithmétique qui implique un ou plusieurs attributs.  
3. Cliquez sur Ajouter.
4. Dans le champ Nom, tapez « Bois de rose ».
    * Le nom de l'expression de prix permet d'identifier ce que représente l'élément de prix. Dans cet exemple, nous créons un élément de prix pour l'option Finitions du meuble pour haut-parleur en bois de rose.  
5. Cliquez sur Modifier la condition.
    * Une condition de prix permet de garantir qu'un élément d'expression de prix est inclus dans le prix de vente uniquement si une combinaison spécifique d'attributs est présente.  
6. Dans le champ ConstraintBody, entrez « CabinetFinish=="Rosewood" ».
7. Cliquez sur OK.
8. Dans le champ Expression, tapez une valeur.
    * Entrez 50, par exemple.  
9. Fermez la page.
10. Fermez la page.

