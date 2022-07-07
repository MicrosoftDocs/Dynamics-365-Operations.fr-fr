---
title: Module de résultats de recherche
description: Cet article couvre les modules des résultats de recherche et décrit comment les ajouter aux pages du site dans Microsoft Dynamics 365 Commerce.
author: anupamar-ms
ms.date: 05/18/2022
ms.topic: article
ms.prod: ''
ms.technology: ''
ms.search.form: ''
audience: Application User
ms.reviewer: v-chgri
ms.search.region: Global
ms.search.industry: ''
ms.author: anupamar
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.8
ms.openlocfilehash: a087c213d4a7094f75da8c20e4ccc14fc52444ce
ms.sourcegitcommit: 6616b969afd6beb11a79d8e740560bf00016ea7f
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/17/2022
ms.locfileid: "9027089"
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

## <a name="enable-inventory-awareness-for-the-search-results-module"></a>Activer la connaissance du stock pour le module des résultats de recherche

Les clients s’attendent généralement à ce que le site web d’e-commerce tienne compte du stock tout au long de l’expérience de navigation, afin qu’ils puissent décider quoi faire s’il n’y a pas de stock pour un produit. Le module de résultats de recherche peut être configurer pour intégrer les données de stock et de fournir les expériences suivantes :

- Afficher une étiquette de disponibilité de stock avec le produit.
- Masquer les produits en rupture de stock de la liste des produits.
- Afficher les produits en rupture de stock à la fin de la liste des produits.
- Filtrer les produits dans les résultats de recherche par niveau de stock.

Pour activer ces expériences, vous devez d’abord activer la fonctionnalité **Découverte améliorée des produits d’e-commerce pour tenir compte des stocks** dans l’espace de travail **Gestion des fonctionnalités**.

> [!NOTE]
> La fonctionnalité **Découverte améliorée des produits de commerce électronique pour tenir compte des stocks** est disponible dans Commerce version 10.0.20 et versions ultérieures.

La recherche de produits prenant en compte le stock utilise des attributs de produit pour obtenir des informations sur la disponibilité de stock. Comme condition préalable à la fonctionnalité, des attributs de produit dédiés doivent être créés, des données de stock doivent être saisies pour eux et ils doivent être ajoutés au canal en ligne. 

Pour créer des attributs de produit dédiés afin de prendre en charge le module de résultats de recherche tenant compte du stock, procédez comme suit.

1. Dans Headquarters, accédez à **Retail et Commerce \> IT Retail et Commerce \> Produits et stock**.
1. Sélectionnez et ouvrez **Remplir les attributs de produit avec le niveau de stock**.
1. Dans la boîte de dialogue, entrez les informations suivantes :

    1. Dans le champ **Attribut de produit et nom du type**, spécifiez un nom pour l’attribut de produit dédié qui sera créé pour capturer les données de stock.
    1. Dans le champ **Disponibilité des stocks en fonction de**, sélectionnez le type de quantité sur laquelle le calcul du niveau de stock doit être basé (par exemple, **Physique disponible**). 

1. Exécutez la tâche en arrière-plan. Étant donné que le stock change constamment dans un environnement omnicanal, nous vous recommandons fortement de planifier cette tâche en tant que traitement par lots.

> [!NOTE]
> Pour un calcul cohérent du niveau de stock sur les pages et modules sur votre site web d’e-commerce, assurez-vous de sélectionner le même type de quantité pour **Disponibilité des stocks en fonction de** dans Commerce Headquarters et le paramètre **Niveau de stock basé sur** dans le générateur de site Commerce. Pour plus d’informations sur les paramètres du stock dans le générateur de site, voir [Appliquer les paramètres de stock](inventory-settings.md).

Pour configurer les attributs de produit pour un canal en ligne, procédez comme suit. 

1. Dans Headquarters, accédez à **Retail et Commerce \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Sélectionnez le canal en ligne pour activer le module de des résultats de recherche basé sur le stock.
1. Sélectionnez et ouvrez un groupe d’attributs associé, puis ajoutez-y l’attribut de produit nouvellement créé.
1. Pour les versions 10.0.27 de Commerce, sélectionnez **Définir les métadonnées d’attribut**, sélectionnez l’attribut de produit nouvellement ajouté, puis activez les options **Afficher l’attribut sur le canal**, **Récupérable**, **Peut être affiné** et **Peut être interrogé**.
1. Accédez à **Retail et Commerce \> Informatique Retail et Commerce \> Programme de distribution**, et exécutez la tâche **1150 (Catalogue)**. Si vous programmez la tâche **Remplir les attributs de produit avec le niveau de stock** en tant que traitement par lots, nous vous recommandons de planifier également la tâche 1150 en tant que traitement par lots qui s’exécute à la même fréquence.

> [!NOTE]
> Pour les produits qui sont affichés dans le module de résultats de recherche, le niveau de stock est affiché au niveau du produit principal au lieu du niveau de la variante individuelle. Il n’a que deux valeurs possibles : "disponible" et "en rupture de stock". L’étiquette réelle de la valeur est extrait de la définition [Profil de niveau de stock](inventory-buffers-levels.md). Un produit principal est considéré comme en rupture de stock uniquement quand toutes ses variantes sont en rupture de stock.

Une fois toutes les étapes de configuration précédentes terminées, les affineurs sur les pages de résultats de recherche affichent un filtre basé sur le stock et le module de résultats de recherche récupère les données de stock en arrière-plan. Vous pouvez ensuite configurer le paramètre **Paramètres de stock pour les pages de liste de produits** dans le générateur de site Commerce pour contrôler la façon dont le module de résultats de recherche affiche les produits en rupture de stock. Pour plus d’informations, voir [Appliquer les paramètres de stock](inventory-settings.md).

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble de la page d’arrivée de la catégorie par défaut et de la page des résultats de la recherche](category-search-page-overview.md)

[Vue d’ensemble de la bibliothèque de modules](starter-kit-overview.md)

[Module de visualisation rapide](quick-view-module.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
