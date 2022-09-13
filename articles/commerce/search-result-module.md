---
title: Module de résultats de recherche
description: Cet article couvre les modules des résultats de recherche et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 08/31/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application User
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.search.industry: ''
ms.search.form: ''
ms.openlocfilehash: eeb7cd0769fcb866a3d7dcc03e8e87daf24b2c5d
ms.sourcegitcommit: 1d5cebea3e05b6d758cd01225ae7f566e05698d2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/02/2022
ms.locfileid: "9405291"
---
# <a name="search-results-module"></a>Module de résultats de recherche

[!include [banner](includes/banner.md)]

Cet article couvre les modules des résultats de recherche et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.

Le module de résultats de recherche renvoie les résultats de la recherche de produits et une liste d’affineurs applicables pour les produits. Les modules de résultats de recherche sur les sites Dynamics 365 Commerce peuvent être utilisés pour afficher des pages dans les scénarios suivants :

- Résultats de recherche lancés par une recherche d’utilisateurs
- Résultats de recherche qui montrent un ensemble spécifique de produits, tels que « Acheter des aspects similaires »
- Listes des produits appartenant à une catégorie donnée

Pour plus d’informations sur les pages de catégorie et de résultats de recherche, voir [Vue d’ensemble de la page d’arrivée de la catégorie par défaut et de la page des résultats de la recherche](category-search-page-overview.md).

L’illustration suivante montre un exemple de page des résultats de la recherche pour une catégorie sur le site Fabrikam.

![Exemple de page des résultats de la recherche sur le site Fabrikam.](./media/SimpleCategoryLandingDressCategory.png)

## <a name="search-results-module-properties"></a>Propriétés du module des résultats de recherche

Le tableau suivant répertorie les propriétés des modules de résultats de recherche, ainsi que leurs valeurs et leurs descriptions.

| Propriété | Valeurs | Description |
|----------|--------|-------------|
| Articles par page | Entier | Le nombre d’éléments à afficher sur chaque page. |
| Autoriser le retour sur PDP | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, quand un utilisateur sélectionne un produit sur la page de résultats de recherche, le fil d’Ariane sur la page de détails du produit (PDP) qui est ouverte affichera un lien « Retour aux résultats ». |
| Développer les affinements | **Tout**, **1**, **2**, **3** ou **4** | Nombre de raffineurs supérieurs qui doivent être développés quand une page est chargée. Par exemple, si cette propriété est définie sur **3**, les trois premiers raffineurs de la page seront développés. |
| Masquer l’affichage de la hiérarchie de catégories | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, l’affichage de la hiérarchie des catégories sur la page sera masqué. Cette propriété doit être définie sur **True** si vous utilisez le [module de fil d’Ariane](add-breadcrumb.md) pour afficher la hiérarchie des catégories.|
| Inclure les attributs de produit dans les résultats de la recherche | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, les attributs seront renvoyés pour les produits dans les résultats de la recherche. Bien que ces attributs puissent être affichés sur un site Commerce, une extension est requise.|
| Afficher les prix d’affiliation | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, les prix d’affiliation pour les produits seront affichés dans les résultats de recherche quand un utilisateur connecté navigue sur la page. |
| Mettre à jour le volet d’affinement | **Vrai** ou **Faux** | Si cette propriété est définie sur **True**, le volet d’affinement sera mis à jour quand des affinements sont sélectionnés. Dans ce mode, certains affinements à sélection multiple se comporteront comme des affinements à sélection unique quand le volet d’affinement est mis à jour. |

> [!IMPORTANT]
> Dans Commerce version 10.0.16 et les versions ultérieures, la configuration **Afficher les prix d’affiliation** peut être utilisée pour afficher les prix d’affiliation sur la page.
>
> Dans Commerce version 10.0.20 et les versions ultérieures, la configuration **Mettre à jour le volet d’affinement** peut être utilisée pour mettre à jour le volet d’affinement au moment de la sélection d’affinements.

## <a name="supported-modules"></a>Modules pris en charge

Le module de résultats de recherche prend en charge le [module de visualisation rapide](quick-view-module.md), qui permet aux utilisateurs d’afficher des informations sur le produit et d’ajouter des articles au panier à partir d’une page de résultats de la recherche.

## <a name="add-a-search-results-module-to-a-category-page"></a>Ajouter un module de résultats de recherche à une page de catégorie

Pour ajouter un module de résultats de recherche à une page de catégorie dans le générateur de site, procédez comme suit.

1. Accédez à **Modèles**, puis cliquez sur **Nouveau** pour créer un nouveau modèle.
1. Dans la boîte de dialogue **Nouveau modèle**, entrez le nom **Résultats de la recherche**, et cliquez sur **OK**.
1. Dans l’emplacement **Corps**, sélectionnez le bouton représentant des points de suspension (…), puis **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Page par défaut**, puis cliquez sur **OK**.
1. Dans l’emplacement **Principal** du module **Page par défaut**, sélectionnez le bouton représentant des points de suspension (...), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Conteneur**, puis sélectionnez **OK**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (...), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Barre de navigation**, puis cliquez sur **OK**.
1. Dans le volet des propriétés **Fil d’Ariane**, entrez la valeur de **1** pour **Nombre minimal d’exécutions**.
1. Dans l’emplacement **Conteneur**, sélectionnez le bouton représentant des points de suspension (...), puis sélectionnez **Ajouter un module**.
1. Dans la boîte de dialogue **Sélectionner des modules**, sélectionnez le module **Résultats de la recherche**, puis cliquez sur **OK**.
1. Dans le volet des propriétés **Résultats de recherche**, entrez la valeur de **1** pour **Nombre minimal d’exécutions**, puis définissez toutes les autres propriétés requises pour le module de résultats de recherche. En définissant ces propriétés dans le modèle, vous vous assurez que toute personnalisation d’une page de catégorie spécifique inclura automatiquement ces paramètres.
1. Sélectionnez **Terminer la modification**, puis **Publier** pour publier le modèle.
1. Accédez à **Pages**, puis sélectionnez **Nouveau** pour créer une page.
1. Dans la boîte de dialogue **Créer une page**, sous **Nom de la page**, entrez **Page de catégorie**, puis cliquez sur **Suivant**.
1. Sous **Choisir un modèle**, sélectionnez le modèle **Résultats de la recherche** que vous avez créé, puis sélectionnez **Suivant**.
1. Sous **Choisir une mise en page**, sélectionnez une mise en page (par exemple, **Disposition flexible**), puis sélectionnez **Suivant**.
1. Sous **Revoir et terminer**, vérifiez la configuration de la page. Si vous devez modifier les informations de la page, sélectionnez **Précédent**. Si les informations de la page sont correctes, sélectionnez **Créer une page**.
1. Sélectionnez **Terminer la modification** pour archiver la page, puis **Publier** pour la publier.

## <a name="inventory-aware-search-results-module"></a>Module de résultats de recherche tenant compte des stocks

Le module de résultats de recherche peut être configurer pour intégrer les données de stock et de fournir les expériences suivantes :

- Affichez les étiquettes de niveau d’inventaire à côté des produits.
- Masquer les produits en rupture de stock de la liste des produits.
- Affichez les produits en rupture de stock à la fin de la liste des produits.
- Prenez en charge le filtrage des produits basé sur les stocks.

Pour activer ces expériences, vous devez d’abord activer la fonctionnalité **Découverte améliorée des produits d’e-commerce pour tenir compte des stocks**, puis configurer certains paramètres prérequis dans Commerce headquarters. Pour plus d’informations, voir [Liste des produits tenant compte du stock](inventory-aware-product-listing.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la page d’arrivée de catégories et de la page des résultats de la recherche par défaut](category-search-page-overview.md)

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module de visualisation rapide](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
