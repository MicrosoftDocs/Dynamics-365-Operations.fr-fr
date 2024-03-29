---
title: Personnaliser la navigation dans le site
description: Cet article décrit la procédure de création d’une hiérarchie de navigation en ligne personnalisée pour organiser vos produits à parcourir sur votre site Microsoft Dynamics 365 Commerce.
author: bicyclingfool
ms.date: 09/15/2020
ms.topic: article
ms.prod: ''
ms.technology: ''
audience: Application user
ms.reviewer: v-chgriffin
ms.search.region: Global
ms.author: StuHarg
ms.search.validFrom: 2019-10-31
ms.dyn365.ops.version: Release 10.0.5
ms.custom: ''
ms.assetid: ''
ms.openlocfilehash: 319bc4af5da19a7a8604f1d30088dbb4aefa6b63
ms.sourcegitcommit: 87e727005399c82cbb6509f5ce9fb33d18928d30
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/12/2022
ms.locfileid: "9275648"
---
# <a name="customize-site-navigation"></a>Personnaliser la navigation dans le site

[!include [banner](includes/banner.md)]

Cet article décrit la procédure de création d’une hiérarchie de navigation en ligne personnalisée pour organiser vos produits à parcourir sur votre site Microsoft Dynamics 365 Commerce.

Les vitrines en ligne permettent généralement aux clients de découvrir et parcourir des produits en navigant dans les catégories de produits. Cette fonctionnalité est généralement fournie par des onglets en haut de la page ou une barre de navigation à gauche. Dans Dynamics 365 Commerce, vous pouvez créer et gérer la structure hiérarchique de votre navigation par catégorie et les produits inclus dans les différentes catégories.

## <a name="create-a-channel-navigation-hierarchy"></a>Créer une hiérarchie de navigation du canal

Pour créer une hiérarchie de navigation du canal, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Produits et catégories \> Gestion des catégories et des produits**.
1. Sélectionnez **Hiérarchies des catégories**, puis sélectionnez **Nouveau**.
1. Nommez la hiérarchie.

    > [!NOTE]
    > La catégorie principale que vous créez est le nœud de catégorie racine. Elle n’est pas affichée sur votre site. Pour créer une hiérarchie de catégories dans laquelle un seul nœud principal s’affiche sur votre site, créez et nommez la catégorie en tant qu’enfant de la catégorie racine.

1. Sélectionnez **Nouveau nœud de catégorie**, puis nommez la catégorie.
1. Continuez à créer des catégories jumelles et parents comme vous le souhaitez.

Vous pouvez ensuite affecter les produits à chaque catégorie que vous avez créée sous la catégorie principale.

## <a name="customize-the-order-of-categories"></a>Personnalisation de l’ordre de catégories

Par défaut, les catégories que vous définissez s’affichent dans l’ordre alphabétique sur votre site. Toutefois, vous pouvez également personnaliser l’ordre d’affichage de catégories.

## <a name="assign-a-category-hierarchy-type"></a>Affectation d’un type de hiérarchie de catégories

1. Accédez à **Commerce et vente au détail \> Produits et catégories \> Gestion des catégories et des produits**.
1. Sélectionnez **Hiérarchie de catégories**.
1. Sur le volet Actions, sous l’onglet **Hiérarchie de catégories**, dans le groupe **Paramétrer**, cliquez sur **Associer le type de hiérarchie**.
1. Sélectionnez **Nouveau**.
1. Dans le champ **Type de hiérarchie de catégories**, sélectionnez **Hiérarchie de navigation du canal**.
1. Dans le champ **Hiérarchie de catégories**, sélectionnez la hiérarchie de navigation de canal que vous avez créée précédemment.

## <a name="publish-new-or-updated-navigation-hierarchies"></a>Publier des hiérarchies de navigation nouvelles ou mises à jour

Pour rendre la hiérarchie de navigation disponible sur votre vitrine en ligne, procédez comme suit.

1. Accédez à **Commerce et vente au détail \> Paramétrage du canal \> Catégories de canal et attributs de produit**.
1. Dans l’arborescence à gauche, sélectionnez votre magasin en ligne.
1. Sélectionnez **Publier les mises à jour du canal**.
1. Accédez à **Commerce et vente au détail \> Informatique Commerce et vente au détail \> Programme de distribution**.
1. Dans la liste, recherchez et sélectionnez **Tâche 1040**.
1. Sélectionnez **Exécuter maintenant**.
1. Répétez les étapes 5 et 6 pour les tâches 1070 et 1150.

## <a name="show-categories-on-your-site"></a>Afficher les catégories sur votre site

Pour afficher la hiérarchie de catégories de votre vitrine en ligne, vous devez ajouter le module du menu de navigation à l’emplacement approprié dans un modèle ou un fragment. Le module du menu de navigation affiche alors la hiérarchie de navigation, si tant est que vous avez publié votre hiérarchie de navigation sur le canal auquel votre site est associé.

> [!NOTE]
> Le module du menu de navigation qui est inclus dans la bibliothèque de modules permet aux utilisateurs d’accéder uniquement aux catégories qui n’ont pas de sous-catégories. Si vos clients peuvent accéder aux catégories qui ont des sous-catégories, vous devez personnaliser le module du menu de navigation.

## <a name="add-custom-navigation-options"></a>Ajouter des options de navigation personnalisée

Dans le menu de navigation, vous pouvez ajouter des options de navigation qui ne font pas partie de votre hiérarchie de catégories de produits. Par exemple, à la fin de la liste de catégories de produit, vous pouvez ajouter un élément **Nous contacter** qui désigne une page de contact que vous avez paramétrée pour votre site.

Pour ajouter des options de navigation personnalisées à votre menu de navigation, procédez comme suit.

1. Dans le modèle ou le fragment que vous souhaitez personnaliser, sélectionnez le module du menu de navigation.
1. Dans le volet de propriété, sous l’onglet **Données**, sélectionnez **Ajouter un article** pour créer un article de navigation du système de gestion de contenu (CMS).
1. Entrez le texte du lien et une URL.
1. Répétez les étapes 2 et 3 pour ajouter des options de navigation plus personnalisées.
1. Lorsque vous avez terminé, sélectionnez **Enregistrer** pour enregistrer le modèle ou le fragment, puis cliquez sur **Terminer la modification** pour l’archiver.

## <a name="additional-resources"></a>Ressources supplémentaires

[Vue d’ensemble des modèles et dispositions](templates-layouts-overview.md)

[Utiliser des modèles](work-with-templates.md)

[Utilisation des mises en page prédéfinies](work-with-layouts.md)

[Utiliser des fragments](work-with-fragments.md)

[Utiliser des modules](work-with-modules.md)

[Créer une URL de page](create-page-url.md)

[Utilisation de groupes de publication](publish-groups.md)


[!INCLUDE[footer-include](../includes/footer-banner.md)]
