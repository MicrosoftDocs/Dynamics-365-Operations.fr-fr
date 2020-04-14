---
title: Paramétrer la tarification par attribut pour les produits configurables
description: Cette rubrique explique comment paramétrer la tarification basée sur des attributs.
author: ShylaThompson
manager: AnnBe
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.service: dynamics-ax-applications
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: josaw
ms.search.scope: Core, Operations
ms.search.region: Global
ms.author: shylaw
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: d23030b79670e31cc237b9ca53b0b3881678786f
ms.sourcegitcommit: fcb27d6a46cd544feef34f6ec7607bdd46b0c12b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/18/2020
ms.locfileid: "3149824"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Paramétrer la tarification par attribut pour les produits configurables

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer la tarification basée sur des attributs. Comme condition préalable, vous devez avoir un modèle de configuration de produit contenant un ou plusieurs composants et attributs. Cet exemple utilise le modèle de produit Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF. Généralement, un responsable de produit utilise cette procédure.


## <a name="create-a-new-price-model"></a>Créer un modèle de prix
1. Sélectionnez **Définition du modèle de variante de produit** sur la page d'accueil.
2. Sélectionnez **Modèles de configuration du produit** dans la section **liens**.
3. Dans la liste, sélectionnez la ligne **Haut-parleur haut de gamme**, mais ne cliquez pas sur le lien du nom.
4. Dans le volet Actions, sélectionnez **Modèle**.
5. Sélectionnez **Modèles de prix**.
6. Sélectionnez **Nouveau**.
7. Dans le champ **Nom du modèle de prix**, saisissez une valeur. Utilisez un nom qui permet d'identifier facilement le modèle.  
8. Tapez une valeur dans le champ **Description**.
9. Sélectionnez **Enregistrer**.

## <a name="add-price-elements"></a>Ajouter des éléments de prix
1. Sélectionnez **Modifier**. Chaque composant d'un modèle de produit peut avoir un élément de prix de base et plusieurs règles d'expression de prix. Vous pouvez également ajouter des prix dans différentes devises.  
2. Dans le champ **Expression de prix de base**, tapez une valeur. Entrez 100, par exemple. Une expression de prix de base peut être une valeur numérique, ou elle peut consister en un calcul arithmétique qui implique un ou plusieurs attributs.  
3. Sélectionnez **Ajouter**.
4. Dans le champ **Nom**, saisissez `Rosewood`. Le nom de l'expression de prix permet d'identifier ce que représente l'élément de prix. Dans cet exemple, nous créons un élément de prix pour l'option Finitions du meuble pour haut-parleur en bois de rose.  
5. Sélectionnez **Modifier la condition**. Une condition de prix permet de garantir qu'un élément d'expression de prix est inclus dans le prix de vente uniquement si une combinaison spécifique d'attributs est présente.  
6. Dans le champ **ConstraintBody**, saisissez `CabinetFinish=="Rosewood"`.
7. Cliquez sur **OK**.
8. Dans le champ **Expression**, saisissez une valeur. Par exemple, saisissez `50`. 
9. Fermez la page.

