---
title: Créer des variantes de produits prédéfinies
description: Cette procédure décrit la création des variantes de produit pour un produit générique à l’aide des combinaisons de dimensions de produit.
author: t-benebo
ms.date: 04/22/2021
ms.topic: business-process
ms.prod: ''
ms.technology: ''
ms.search.form: EcoResProductListPage, EcoResProductCreate, EcoResProductDetails, EcoResProductMasterDimension, EcoResProductVariants, EcoResProductVariantSuggestions, EcoResProductVariantsPendingReleaseFormPart, EcoResProductVariantSuggestionsEnhanced
audience: Application User
ms.reviewer: kamaybac
ms.search.region: Global
ms.author: benebotg
ms.search.validFrom: 2016-06-30
ms.dyn365.ops.version: 10.0.19
ms.openlocfilehash: 6f78441445baecba279f96eb3935d9ebbb4ff03f
ms.sourcegitcommit: 08ce2a9ca1f02064beabfb9b228717d39882164b
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2021
ms.locfileid: "6021906"
---
# <a name="predefined-product-variants"></a>Variantes de produits prédéfinies

[!include [banner](../../includes/banner.md)]

## <a name="example-scenario-create-predefined-product-variants"></a>Exemple de scénario : Créer des variantes de produits prédéfinies

Cet exemple de scénario décrit la création des variantes de produit pour un produit générique à l’aide des combinaisons de dimensions de produit.

### <a name="make-demo-data-available"></a>Rendre les données de démonstration disponibles

Pour suivre ce scénario en utilisant les valeurs suggérées ici, vous devez avoir des données de démonstration installées, et vous devez sélectionner l’entité juridique *USMF*.

### <a name="step-1-create-a-product-master"></a>Étape 1 : Créer un produit générique

Pour créer un produit générique :

1. Accédez à **Gestion des informations sur les produits > Produits > Produits génériques**.
1. Sélectionnez **Nouveau**.
1. Si le champ **Numéro de produit** n'affiche pas déjà un nombre, entrez une valeur. Cette étape n’est requise que si aucune souche de numéros n’a été paramétrée pour ce champ.
1. Entrez un nom dans le champ **Nom du produit**.
1. Dans le champ **Groupe de dimensions de produit**, sélectionnez le groupe de dimensions de produit *SizeCol* (Taille et couleur).
1. Sélectionnez **OK** pour créer et ouvrir le nouveau produit générique.

### <a name="step-2-add-product-dimensions"></a>Étape 2 : Ajouter des dimensions de produit

Cet exemple décrit la manière d’entrer manuellement les dimensions de produit. Vous pouvez également choisir de sélectionner un groupe de tailles, de couleurs ou de styles incluant les valeurs de dimension de produit à utiliser.

Pour ajouter des dimensions de produit :

1. La nouvelle fiche produit étant toujours ouverte, sélectionnez **Dimensions de produit** dans le volet Actions.
1. Ouvrez l'onglet **Taille** et sélectionnez **Nouveau** dans la barre d'outils pour ajouter une ligne à la grille. Définissez les paramètres suivants pour la nouvelle ligne :
    - **Taille** - Permet de sélectionner une valeur de taille.
    - **Nom** - Entrez un nom pour la taille.
1. Sélectionnez **Nouveau** dans la barre d'outils et ajoutez une deuxième taille à la grille avec un nouvelle **Taille** et un nouveau **Nom**.
1. Ouvrez l'onglet **Couleurs** et sélectionnez **Nouveau** dans la barre d'outils pour ajouter une ligne à la grille. Définissez les paramètres suivants pour la nouvelle ligne :
    - **Couleur** - Sélectionnez une valeur de couleur.
    - **Nom** - Entrez un nom pour la couleur.
1. Sélectionnez **Nouveau** dans la barre d'outils et ajoutez une deuxième couleur à la grille avec un nouvelle **Couleur** et un nouveau **Nom**.
1. Sélectionnez **Enregistrer**.
1. Fermez la page pour revenir à votre nouveau produit générique.

### <a name="step-3-generate-product-variants"></a>Étape 3 : Générer des variantes de produits

> [!NOTE]
> Cette section décrit comment générer des variantes de produit lorsque la fonctionnalité *Améliorations de la page de suggestions de variantes* n'est pas activée. Consultez la section suivante pour plus de détails sur la façon de générer des variantes de produit lorsque cette fonctionnalité est disponible.

Pour générer des variantes de produits :

1. La nouvelle fiche produit étant toujours ouverte, sélectionnez **Variantes de produit** dans le volet Actions.
1. Dans le volet Actions, sélectionnez **Suggestions de variantes**.
1. Le système génère une liste avec toutes les combinaisons possibles des tailles et des couleurs que vous avez définies pour le produit. Sélectionnez **Sélectionner tout** dans la barre d'outils.
    - Dans cet exemple, sélectionnez toutes les variantes possibles. Si vous souhaitez utiliser uniquement un sous-ensemble des combinaisons de dimensions de produit possibles, cochez uniquement les cases requises selon vos besoins.  
1. Sélectionnez **Créer**.
1. Sélectionnez **Enregistrer**.

## <a name="improved-variant-suggestions"></a>Suggestions de variantes améliorées

[!INCLUDE [preview-banner-section](../../../includes/preview-banner-section.md)]

La page *Améliorations de la page de suggestions de variantes* la fonctionnalité améliore les **Suggestions de variantes** pour résoudre les problèmes de performances et d'utilisabilité pour les entreprises qui ont un grand nombre de combinaisons de dimensions de produits. Le processus amélioré de sélection des valeurs de dimension de produit pour lesquelles générer des suggestions de variantes permet d'identifier et de libérer plus rapidement et plus facilement l'ensemble de variantes de produit approprié.

Les améliorations suivantes sont ajoutées par cette fonctionnalité :

- **Génération différée de suggestions de variantes :** la page **Suggestions de variantes** n'affiche plus de suggestions lorsque vous l'ouvrez pour la première fois. Au lieu de cela, vous devez choisir explicitement les valeurs dont vous aurez besoin, puis sélectionner le bouton **Suggérer** pour générer les combinaisons. Cela rend le processus plus visible et interactif.
- **Sélection des valeurs de dimensions :** lorsque vous avez de nombreuses valeurs de dimension, vous souhaitez généralement générer des suggestions de variantes qui n'en incluent que quelques-unes (par exemple lors de l'introduction d'un nouvel ensemble de couleurs ou de styles). Grâce à la conception améliorée, vous pouvez sélectionner les valeurs de dimension pour lesquelles vous souhaitez générer des suggestions de variantes de produit. Cela augmente considérablement la pertinence des variantes suggérées et améliore à la fois les performances du système et la productivité des utilisateurs.

### <a name="turn-on-the-variant-suggestions-page-improvements-feature"></a>Activer la fonctionnalité d'amélioration de la page de suggestions de variantes

Avant de pouvoir utiliser la fonctionnalité *Amélioration de la page de suggestions de variantes*, elle doit être activée sur votre système. Les administrateurs peuvent utiliser les paramètres de [gestion des fonctionnalités](../../../fin-ops-core/fin-ops/get-started/feature-management/feature-management-overview.md) pour vérifier le statut de la fonctionnalité et l’activer si nécessaire. Dans l’espace de travail **Gestion des fonctionnalités**, la fonctionnalité est répertoriée comme suit :

- **Module :** *Gestion des informations sur les produits*
- **Nom de la fonctionnalité :** *Amélioration de la page de suggestions de variantes*

### <a name="work-with-the-improved-variant-suggestions"></a>Travailler avec les suggestions de variantes améliorées

Pour générer des suggestions de variantes de produit lorsque la fonctionnalité *Améliorations de la page de suggestions de variantes* est activée :

1. Ouvrez ou créez un produit générique et ajoutez-y les dimensions de produit requises, comme décrit dans la section précédente.
1. Le nouveau produit générique étant toujours ouvert, sélectionnez **Variantes de produit** dans le volet Actions.
1. Dans le volet Actions, sélectionnez **Suggestions de variantes**.
1. Sélectionnez les valeurs que vous souhaitez utiliser pour chaque dimension.
1. Dans la barre d'outils supérieure, sélectionnez **Suggérer**.
1. Le système génère une liste avec toutes les combinaisons possibles des tailles et des couleurs que vous avez sélectionnées. Sur le raccourci **Variantes suggérées**, cochez la case de chaque combinaison de dimensions de produit que vous souhaitez utiliser ou sélectionnez **Sélectionner tout** dans la barre d'outils pour les sélectionner toutes.  
1. Sélectionnez **Créer** pour ajouter les variantes au produit générique actuel.

[!INCLUDE[footer-include](../../../includes/footer-banner.md)]
