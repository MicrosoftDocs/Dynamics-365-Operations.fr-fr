---
title: Paramétrer la tarification par attribut pour les produits configurables
description: Cette rubrique explique comment paramétrer la tarification basée sur des attributs.
author: ShylaThompson
ms.date: 08/20/2019
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: DefaultDashboard, EcoResProductVariantMaintainWorkspace, PCProductConfigurationModelListPage, PCPriceModelList, PCPriceModel, PCConstraintEditor
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: kamaybac
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: Version 7.0.0
ms.openlocfilehash: 0c30c520e7265c2676937f5191844f6789c364e6
ms.sourcegitcommit: fa99a36c3d30d0c0577fd3f63ed6bf2f71599e40
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/20/2021
ms.locfileid: "5921239"
---
# <a name="set-up-attribute-based-pricing-for-configurable-products"></a>Paramétrer la tarification par attribut pour les produits configurables

[!include [banner](../../includes/banner.md)]

Cette rubrique explique comment paramétrer la tarification basée sur des attributs. Comme condition préalable, vous devez avoir un modèle de configuration de produit contenant un ou plusieurs composants et attributs. Cet exemple utilise le modèle de produit Haut-parleur haut de gamme dans les données de démonstration de la société fictive USMF. Généralement, un responsable de produit utilise cette procédure.


## <a name="create-a-new-price-model"></a>Créer un modèle de prix

1. Accédez à **Gestion des informations sur les produits \> Produits \> Modèles de configuration de produit**.
1. Dans la liste, sélectionnez la ligne **Haut-parleur haut de gamme**, mais ne cliquez pas sur le lien du nom.
1. Dans le volet Actions, sélectionnez **Modèle**.
1. Sélectionnez **Modèles de prix**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Nom du modèle de prix**, saisissez une valeur. Utilisez un nom qui permet d’identifier facilement le modèle.  
1. Tapez une valeur dans le champ **Description**.
1. Sélectionnez **Enregistrer**.

## <a name="add-price-elements"></a>Ajouter des éléments de prix

1. Sélectionnez **Modifier**. Chaque composant d’un modèle de produit peut avoir un élément de prix de base et plusieurs règles d’expression de prix. Vous pouvez également ajouter des prix dans différentes devises.  
2. Dans le champ **Expression de prix de base**, tapez une valeur. Entrez 100, par exemple. Une expression de prix de base peut être une valeur numérique, ou elle peut consister en un calcul arithmétique qui implique un ou plusieurs attributs.  
3. Sélectionnez **Ajouter**.
4. Dans le champ **Nom**, saisissez `Rosewood`. Le nom de l’expression de prix permet d’identifier ce que représente l’élément de prix. Dans cet exemple, nous créons un élément de prix pour l’option Finitions du meuble pour haut-parleur en bois de rose.  
5. Sélectionnez **Modifier la condition**. Une condition de prix permet de garantir qu’un élément d’expression de prix est inclus dans le prix de vente uniquement si une combinaison spécifique d’attributs est présente.  
6. Dans le champ **ConstraintBody**, saisissez `CabinetFinish=="Rosewood"`.
7. Cliquez sur **OK**.
8. Dans le champ **Expression**, saisissez une valeur. Par exemple, saisissez `50`. 
9. Fermez la page.



[!INCLUDE[footer-include](../../../includes/footer-banner.md)]